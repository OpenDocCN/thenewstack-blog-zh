# 一名 React 开发人员选择了 Rails，引发了 JavaScript 争论

> 原文：<https://thenewstack.io/a-react-developer-chooses-rails-igniting-javascript-debate/>

结束一周的工作，还有什么比争论使用哪种技术更好的方式呢？本周，这场争论以开发者 Vadim Demedes T1 的博客形式出现，他写了“[为什么我从 JavaScript SPAs T3 转向 Rails。”](https://reviewbunny.app/blog/dont-make-me-think-or-why-i-switched-to-rails-from-javascript-spas)

在这篇文章中，德梅德斯讲述了他最近选择 [Ruby on Rails](https://rubyonrails.org/) 而不是使用他通常使用的基于 React[单页面应用](https://en.wikipedia.org/wiki/Single-page_application)框架的经历。他惊讶地发现，他“没有拖延确定完美的设置或选择依赖项”，而是“在完成 MVP 后拖延”，并补充道“我宁愿选择后者！”

他写道，问题是当开始一个新的 JavaScript 应用程序时，他必须做出太多的决定，从哪个包管理器使用哪个框架，到哪个数据库，认证，数据获取，等等。

相比之下，德梅德斯写道，“一旦我运行 rails new，我就拥有了所有这些。”现在，似乎 Demedes 并没有说我们把婴儿和洗澡水一起倒掉了，而是说许多 JavaScript 框架在这个领域需要一些帮助。他建议“更多强有力的意见和约定，让我们免于做出不必要的选择”，以及“在开始做任何事情时，减少配置和体力劳动。”

“在我看来，这正是我们 JavaScript 开发者在创建应用时需要的。在我们有更多的指导和约定之前，我们将继续花一周的时间来建立一个完美的应用样板。他总结道:“我仍然非常热衷于 JavaScript 社区，但现在我会继续使用 Rails，享受构建 web 应用的乐趣。”。

现在，你不必走很远就能找到一点分歧，许多人认为这更多的是 React 的问题，而不是整个 JavaScript 生态系统的问题。

黑客新闻[上的评论](https://news.ycombinator.com/item?id=30206989)同样将问题从一个狭窄的单一框架扩展到整个 JavaScript。

例如，[的一位评论者认为](https://news.ycombinator.com/item?id=30206989#:~:text=gavinray-,2%20hours%20ago,-%7C%20prev%20%7C%20next%20%5B%E2%80%93%5D)“如果你把 Rails 比作 Nest.js，你不会错过太多。Nest 是我在任何语言中使用过的最好的应用程序框架之一，它提供了所有你说 JS 没有的东西。”

各种框架和工具——Angular、Blitz.js、Remix——也进入了对话，但另一位[评论者认为](https://news.ycombinator.com/item?id=30207311)所有这些都可以归结为一件事:快速简单地完成某件事，正如 Demede 的博客标题所暗示的那样。

“我认为作者在这里谈得太深入了，因为这群人都是能够将这篇文章撕成碎片的人。但这样做既错过了更重要的一点，也在这个过程中证明了这一点——Rails 给了他们一系列足够好的答案，因此他们不需要深入研究，只需专注于他们的应用，”他们写道。“Rails 并不是这样做的唯一选择。拥有更广泛技能的人可以组合他们自己的解决方案，无论如何也可能不想要。但这位作者只是想选择一个平台，然后继续前进，没错，Rails 就是为此而生的。”

## 本周的节目中

*   **关于 WebAssembly 的争论:** WebAssembly 可能只是你顺便听说过的东西，或者你甚至读过一点点，但是本周流传的一篇文章认为是时候[关注 WebAssembly](https://harshal.sheth.io/2022/01/31/webassembly.html) 了，它非常值得一读。在我自己的采访中，WebAssembly 这个话题越来越多地出现，就在最近，Vercel 首席执行官 [Guillermo Rauch](https://twitter.com/rauchg?lang=en) 告诉我，JavaScript 开发人员应该密切关注“非常棒但还处于萌芽状态的[WebAssembly]生态系统”，他认为 JavaScript 在这个生态系统中具有优势。至于这篇文章，它认为“WebAssembly 正处于一个转折点”，并且在未来几年内，“从容器化到插件系统到无服务器计算平台，整个技术领域将会越来越多地采用 WebAssembly”。这里有太多的内容需要重述，但是总结一下 WebAssembly 的优势在哪里，它已经在哪里得到了最好的使用，以及它接下来可能的发展方向是很好的。WebAssembly 已经为亚马逊的 Video Prime、迪士尼+和 BBC 等许多公司提供了支持。虽然作者承认它仍然不够成熟，但他们写道，“这些问题中的许多正在积极研究，可能会在未来一两年内达到可接受的状态。因此，我们似乎正处于网络组装活动、生态系统和社区爆炸的边缘。”

*   **Go 最受欢迎的测试版得到了续集:**继第一个测试版之后，Go 1.18 的[第二个测试版于本周发布，该团队写道，这是“有史以来下载量最大的 Go 测试版，下载量是之前任何版本的两倍。”随之而来的是对 gopls 和 VS Code Go 扩展中泛型的支持。除了期待已久的](https://go.dev/blog/go1.18beta2) [generics](https://go.dev/blog/why-generics) 特性，Go 1.18 还引入了 [fuzzing](https://go.dev/blog/fuzz-beta) 和新的 [Go 工作区模式](https://go.dev/design/45713-workspace)。在测试了第一个测试版之后，该团队还写道，它“也被证明非常可靠；事实上，我们已经在谷歌的生产中运行它了。”尽管如此，Beta 2 是为了确保一切都好，因为 Beta 1 发现了一些“泛型新支持中的模糊错误”。候选版本预计将于本月晚些时候发布，最终的 Go 1.18 版本将于 3 月发布。当我们谈论 Go 1.18 时， [Go AWK](https://github.com/benhoyt/goawk) 解释器创建者 [Ben Hoyt](https://benhoyt.com/) 决定看看 [Go 从 1.2 到 1.18](https://benhoyt.com/writings/go-version-performance/) 版本的性能，使用他自己的工具“当使用 Go 从 1.2(我能下载的最早版本)到 1.18(现在处于测试阶段)的每个发布版本进行编译时”正如你可能期望的(或者希望的)，Go 在最近的版本中加快了速度。“总的来说，countwords 现在的速度是 Go 1.2 的 5 倍，sumloop 快了 14 倍！(虽然我第一次发布 GoAWK 时，Go 已经是 1.11 版本了，所以它并没有带来巨大的早期收益。)，”霍伊特写道。“对于一个像 Go 这样积极开发的编译器来说，仅仅通过等待并让其他人做所有艰苦的工作就能够获得性能提升是很酷的。:-)"

*   **GitHub 获得赞助商专用回购:**本周，随着 GitHub[新的赞助商专用仓库](https://github.blog/2022-02-02-new-sponsors-only-repositories-custom-amounts-and-more/)的发布，寻求开源努力中一点财务支持的开发者有了一个新工具。该功能允许开发人员将私有存储库附加到他们的每个赞助层，就像 Kickstarter 上捐赠层的礼物一样。GitHub 提供了一些潜在的用例，比如“赞助商软件”，或者只对你的赞助商开放的存储库，或者在回购开源之前让赞助商提前访问回购。除了赞助商专用回购协议，GitHub 还增加了对定制赞助金额的支持，包括销售税的能力，根据层级定制赞助消息，以及帮助确定什么会带来新赞助商的元数据。至于接下来会发生什么，GitHub 表示，它正在努力“改善 GitHub 上的发现体验，使社区更容易探索依赖关系和决定支持谁，并帮助使用赞助商的维护者增加他们的受众、社区和整体资金。”
*   **关于异步 Rust 的更新:**对于那些关注 Rust 中异步 I/O 发展的人来说，异步工作组已经提供了一点关于 2022 年[异步 Rust 的更新](https://blog.rust-lang.org/inside-rust/2022/02/03/async-in-2022.html)。之前已经写了一份[共享异步愿景文档](https://rust-lang.github.io/wg-async/vision.html)，该团队现在说他们“正在朝着实现那个愿景前进。”他们提供了一个 Rust 开发人员的假设轶事，在 2024 年，他愉快地拿出他们的 Rust 指南并开始编码，这与目前的情况形成了对比，在当前的情况下，“在定义和实现让我们编写我们谈论的代码的功能方面还有很多工作要做。”要了解他们在这个过程中所处的位置，请直接阅读这篇博文，或者查看[路线图页面](https://rust-lang.github.io/wg-async/vision/roadmap.html)。见鬼，如果你真的很投入，你也可以伸出援助之手。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>