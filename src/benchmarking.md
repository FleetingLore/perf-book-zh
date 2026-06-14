# Benchmarking

对于同一个任务, **基准测试工作** 可比较不同实现方法的性能.
 有时这可能会关联到若干程序, 例如 Firefox 与 Safari 与 Chrome.
 有时则比较同一程序的两个不同 **版本**.
 后者通常更容易回答 "这个改动是否使软件更快地完成任务?" 这样的问题

基准测试工作很复杂, 完整介绍超出了本书的范围, 但这里会覆盖一些基础

首先, 你需要 **工作负载** 来做测量.
 理想情况下, 你会有各种工作负载, 反映被测试程序在使用时的情况.
 真实环境下的输入是最有效的, 但 **微基准测试** 和 **压力测试** 的适度使用也有帮助

其次, 你需要一种运行工作负载的方式, 这也制约了所使用的度量标准

- Rust 内置的 [benchmark tests] 是一个简单的起点, 但它们使用了不稳定的特性, 只能在 Nightly Rust 上运行
- [Criterion] 和 [Divan] 是更复杂的替代方案
- [Hyperfine] 是一个出色的基准测试工具, 面向广泛的使用情形
- [Bencher] 可以在 CI 上持续运行基准测试, 包括 GitHub CI
- [Gungraun] 与 `cargo bench` 对接, 提供高精度测量
- 也可以搭建自定义的基准测试框架, 例如 [rustc-perf] 对 Rustc 进行基准测试

[benchmark tests]: https://doc.rust-lang.org/nightly/unstable-book/library-features/test.html
[Criterion]: https://github.com/bheisler/criterion.rs
[Divan]: https://github.com/nvzqz/divan
[Hyperfine]: https://github.com/sharkdp/hyperfine
[Bencher]: https://github.com/bencherdev/bencher
[Gungraun]: https://github.com/gungraun/gungraun
[rustc-perf]: https://github.com/rust-lang/rustc-perf/

至于度量标准, 有多种选择, 这取决于被测程序的特性.
 例如, 适用于批处理程序的, 未必适用于交互式程序.
 **墙钟时间** 是许多情形下的自然选择, 因为它对应了用户的直观感受.
 然而, 它的波动可能较大.
 具体来说, 内存布局的微小变化可能引起显著但短暂的性能波动.
 因此, 其他波动较小的度量标准, 例如 **周期计数** 或 **指令计数**, 可能是合理的替代

Summarizing measurements from multiple workloads is also a challenge, and there
are a variety of ways to do it, with no single method being obviously best.

Good benchmarking is hard. Having said that, do not stress too much about
having a perfect benchmarking setup, particularly when you start optimizing a
program. Mediocre benchmarking is far better than no benchmarking. Keep an open
mind about what you are measuring, and over time you can make benchmarking
improvements as you learn about the performance characteristics of your
program.

---

[`benchmarking`](https://chat.deepseek.com/share/f3dccyot5ccyw188f5) 基准测试工作

[`version`](https://chat.deepseek.com/share/j3fw26ampi0x6uzniw) 版本

[`workloads`](https://chat.deepseek.com/share/233p8r8ikd4t5wk5bg) 工作负载

[`microbenchmarks`](https://chat.deepseek.com/share/jqu83xiuhxsnbpoi2q) 微基准测试

[`stress tests`](https://chat.deepseek.com/share/wura1hxt9m0crsv9wd) 压力测试

[`Wall-time`](https://chat.deepseek.com/share/dbmp7p88j1dys2nwyo) 墙钟时间

[`cycle counts`](https://chat.deepseek.com/share/i35shk93ubt6s6vigd) 周期计数

[`instruction counts`](https://chat.deepseek.com/share/95ybph1xvzw5f0p3wj) 指令计数
