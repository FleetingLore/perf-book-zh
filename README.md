# perf-book-zh

The Rust Performance Book 中文翻译.

## 阅读本书

[英文原版](https://nnethercote.github.io/perf-book/)

[本书的中文翻译](https://fleetinglore.github.io/perf-book-zh/)

## 自行构建

此书采用 [`mdbook`](https://github.com/rust-lang/mdBook),
可以按以下方法构建这个工具:

```bash
cargo install mdbook
```

以此构建本书:

```bash
mdbook build
```

所生成的文件将位于 `book/` 路径下

## 对于开发

以此检查本地的版本:

```bash
mdbook serve
```

这将在本地的 `3000` 端口创建一个动态同步更新的服务器,
以预览构建后的版本

以此运行相关测试:

```bash
mdbook test
```

## 意见建议

本人出于学习目的翻译此书,
欢迎对译文中的**术语译法,
表达准确性,
知识性错误**提出意见

翻译除参考[原版](https://github.com/nnethercote/perf-book)外,
还参考了以下已有译本:

  * [Blues-star/perf-book-zh](https://github.com/Blues-star/perf-book-zh)
  * [mokurin000/perf-book-zh](https://github.com/mokurin000/perf-book-zh)
  * [JohnTitor/perf-book-ja](https://github.com/JohnTitor/perf-book-ja)

## 许可证

可以选择使用以下任一许可证:

  * [LICENSE-APACHE-2.0](LICENSE-APACHE)
  * [LICENSE-MIT](LICENSE-MIT)

## 贡献

除非你明确说明,
否则你按照 Apache-2.0 许可证提交的任何打算纳入作品的贡献,
都将按上述方式双重授权,
不附加任何额外条款或条件.
