# 苗条的核心团队琢磨 Rust 编译器，以进一步加快网络应用

> 原文：<https://thenewstack.io/svelte-core-team-mulls-a-rust-compiler-to-further-speed-web-apps/>

越来越受欢迎的网络应用框架 [Svelte](https://svelte.dev/) 的下一个主要版本，据其创造者 [Rich Harris](https://twitter.com/Rich_Harris) 称，可能会从 [Rust 编程语言](https://www.rust-lang.org/)中得到提升。

哈里斯在 web 开发工具提供商 Vercel 制作的视频采访中说，Svelte 4.0 最终版本可能的变化之一是用 Rust 编写的新编译器，哈里斯目前受雇于该公司。

“目前许多 JavaScript 工具都是用 Rust 编写的，如果用 Rust 编写苗条的编译器，也许会有意义，”Harris 说。他没有完全承诺在下一个版本中切换到 Rust，尽管他表示这是核心开发团队正在探索的一种有前途的方法。

目前，Svelte 通过[将 web 应用](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Svelte_getting_started)代码(由 HTML、CSS 和 JavaScript 构建)编译成高度优化的 JavaScript 来工作。它不同于 React 等流行的 JavaScript 框架。运行时在浏览器中呈现复杂网页的 JS 和 Vue。它通过提前编译应用程序，将大量渲染工作从浏览器中移出，从而消除了这一繁琐的步骤。

![](img/a755ff513ff2822c4c099313c3f2d75e.png)

尽管 Svelte 有潜在的性能改进，Harris 还是听到了对大型 web 应用程序产生的巨大代码量的抱怨。例如，第三方发现，Svelte 为大型网络应用程序编译的代码往往比 React 中呈现的类似应用程序的组件代码更庞大。

Harris 说，基于 Rust 的代码编译方法可能“不仅会消除这个问题，它实际上意味着编译后的代码比输入代码更小，我认为这是相当独特的”。最终的代码仍然是 JavaScript。

尽管有些难学，Rust 语言正被系统设计者迅速采用，不仅因为它的快速性能，还因为它的安全控制。为此，哈里斯指出，转移到 Rust“可能会打开错误边界的大门。”

## 赶上 React

核心团队还在研究许多其他潜在的增强功能，包括“[部分水合方法](https://twitter.com/rich_harris/status/1376578504704331778)”的整合

哈里斯还想继续探索 Svelte 对渲染动作的支持。“这是斯维尔特一直优先考虑的事情，”哈里斯吹嘘道。Svelte 具有声明性转换，可以轻松地在浏览器的文档对象模型(DOM)中添加或删除元素。“我们不会立即将该元素从 DOM 中取出。我们可以在上面播放一个过渡，这样你就可以获得优雅的滑入、滑出、飞入、飞出的行为，”他说。

尽管有这些先进的功能，Harris 一直在嫉妒 React 的 [Framer Motion](https://www.framer.com/motion/) 库用于制作动画布局。“我认为，如果一个框架把这些东西作为它的领域，那么你可以用最少的努力做一些非常好的 UI 设计，”他说。

当前版本的 Svelte (v3)于 2019 年 4 月发布，每隔一年半左右就会有新版本发布。Svelte 4.0 的发布日期尚未公开。

点击此处观看整个采访:

[https://www.youtube.com/embed/uQntFkK8Z54?start=1272&feature=oembed](https://www.youtube.com/embed/uQntFkK8Z54?start=1272&feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>