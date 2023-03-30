# 谷歌将 Rust 带入 Chromium 项目

> 原文：<https://thenewstack.io/google-brings-rust-into-chromium-project/>

Google 现在在 Chromium 项目中支持来自 C++的第三方 Rust 库。

Dana Jansens，[在谷歌安全博客](https://security.googleblog.com/2023/01/supporting-use-of-rust-in-chromium.html)上写道，作为开始，该团队正在向其构建系统添加一个[生产 Rust 工具链](https://bugs.chromium.org/p/chromium/issues/detail?id=1292038)。Rust 代码将在下一年出现在 Chrome 二进制文件中。

谷歌在 Chromium 中加入 Rust 库是件大事。此前，微软和亚马逊网络服务对 Rust 编程进行了深度投资。詹森明确指出:谷歌不一定支持 Rust 本身，而是支持第三方 Rust 库。

詹森帖子的基调是谨慎行事。他们开始的很“慢”，并且会选择他们会考虑的第三方库。

Mozilla 最初开发了 Rust，一种类型安全的语言。微软和亚马逊网络服务已经投资了 Rust。从某些方面来说，这说明了 Mozilla 非常简单。Rust 是成功的。但除此之外，Firefox 还存在一定程度的不确定性，其市场份额正在萎缩。

谷歌采用 Rust 库有两个重要原因。接受 Rust 库的举动有望帮助加速 Chromium 的开发并提高安全性。就增长而言，Jansens 引用了更少的代码编写、更少的设计文档和更少的安全审查。为了保护:更具体地说，这是增加没有内存安全错误的代码行数，同时降低代码错误密度的机会。

一些人仍然对这种转变持怀疑态度，例如，由于引入了新的缺陷。 [Lolinder](https://news.ycombinator.com/item?id=34361985) 在黑客新闻上写道:

*“在 Rust 中重写不一定是任何给定项目的好主意，而且几乎可以肯定，谷歌不会像 Mozilla 一样主动在 Rust 中重写大量 Chrome。*

*原因是 bug 主要存在于新代码中，而不是长时间无人问津的代码。虽然您可以通过在 Rust 中重写来解决一些潜在的内存问题，但您可能会引入新的回归，这可能会更糟糕。专注于用安全的语言编写你独特的代码更有意义，并且只在需要大量重写的时候才逐步迁移。”*

但其他黑客新闻评论员对 Chromium 团队给予了肯定。正如一位谷歌资深人士所说:“这真的是一件好事，在谷歌的其他项目中经历过这种情况，我真诚地祝贺那些展现出坚韧不拔精神继续前进的人们，尽管我确信他们提出了很多真正的难题，也有很多 fud。从长远来看，这个结果对用户来说是好的。”

Jansen 写道，从 C++到 Rust,“目前”只支持一个方向的互操作。有趣的是，谷歌正在投资 [Crubit](https://github.com/google/crubit) ，这是一个“极其”实验性的 C++/Rust 双向工具。贡献最大的是谷歌工程师。

Rust 和 C++利用了影响互操作性的不同概念。如何弥补这些差异在某些方面将取决于如何对互操作进行建模，因此这两种语言至少可以理解它们的相似之处或站不住脚的差异。

值得注意的是，Rust 和 C++之间的大多数互操作都是由狭义定义的 API 导致的，这再次表明谷歌在互操作性方面面临着多么严峻的挑战。由于语言的差异，这种狭窄是必要的。

詹森写道:“例如，Rust 通过依赖于两个输入的静态分析来保证临时内存安全:[寿命](https://doc.rust-lang.org/book/ch10-03-lifetime-syntax.html) ( [推断](https://doc.rust-lang.org/reference/lifetime-elision.html)或显式写入)和[互斥可变性](https://doc.rust-lang.org/rust-by-example/scope/borrow/alias.html)。后者与 Chromium 的大多数 C++的编写方式不兼容。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>