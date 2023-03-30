# Fiberplane:一切都着火时的协作

> 原文：<https://thenewstack.io/fiberplane-collaboration-when-everythings-on-fire/>

自从把他以前的公司 [Wercker](https://thenewstack.io/wercker-automates-workflow-building-containers/) 卖给[Oracle](https://developer.oracle.com/?utm_content=inline-mention),[Micha Hernandez van Leuffen](https://www.linkedin.com/in/mhernandezvanleuffen/?originalSubdomain=de)后，他把注意力转向了大规模分布式系统中以及分布式团队中事件响应的困难。

这家总部位于阿姆斯特丹的新公司名为 [Fiberplane](https://fiberplane.dev/) ，为现场可靠性工程师提供实时协作工具，他们可以从 observability 和其他工具中获取数据，以找到问题的核心。

![](img/4d7c409160d5d765037f31b8dcbd3a96.png)

**“**当我们做 Wercker 时，它是一个容器原生的 CI/CD 平台，一个相当复杂的分布式系统……我们在 Kubernetes 上创建了许多实例和容器，并对它们进行编排。但是很难调试。因此，当我们需要弄清楚一些事情并进行一些调试时，它总是在指标、日志、跟踪和不同的仪表板之间来回切换，我总是称之为这种寻宝——弄清楚到底发生了什么，”他说。

“我们正在做这些微服务，它们分布在多个抽象层上，很难弄清楚在这些层下面发生了什么。此外，仪表板作为一种用于调试的形式并不适合。因为当你知道测量什么时，仪表板是很棒的，已知的已知，对吗？你预先设置了它们，假设你知道什么会出错。

“但是在微服务和分布式系统的世界里，当然还有 Kubernetes，这些未知因素更加普遍。这让我想到我们需要一种不同的外形，一种本质上更具探索性的外形。并与您使用的所有这些不同的系统集成在一起，”他解释道。

## 专为团队打造

Van Leuffen 坚持认为 DevOps 和站点可靠性工程师缺乏其他类型团队可用的专门构建的协作工具。

“围绕一个事件进行合作总是很难，因为你需要在同一个时区，或者至少在同一时间醒来，然后一起经历这场寻宝活动，”范·勒芬在去年 9 月的一集《新堆栈制造商》中说道。

“当谈到谷歌文档或生产力领域的概念时，显然是设计领域的 Figma，但 DevOps 并没有真正从这种向协作软件的转变中受益，”他在采访中说。

他说，围绕可观察性和监控的工具仍然是为个人用户而不是团队设计的孤立环境。

“在采访了 35 多家公司后，很明显，事件管理的现状是屏幕截图、日志粘贴和 Slack #宕机频道中的大量噪音以及偶尔出现的 Google doc 的混合。不同的工具导致认知负荷增加，伴随着警觉疲劳。我们可以做得更好，”一个公司博客[帖子](https://fiberplane.dev/blog/meet-fiberplane/)说。

## 锈和 Wasm

Fiberplane 从数据科学世界获得灵感，推出了一款 Jupyter 笔记本式互动[平台](https://fiberplane.dev/blog/creating-a-rich-text-editor-using-rust-and-react/)，该平台与现有的观察工具相集成。

该技术内置于[锈](https://thenewstack.io/rust-by-the-numbers-the-rust-programming-language-in-2021/)和[腹板装配](https://thenewstack.io/what-is-webassembly/) (Wasm)。为了解决多人同时在 Fiberplane 笔记本上打字和添加数据(包括图表)时的冲突，它使用了与 Google Docs 相同的算法[运算转换](https://en.wikipedia.org/wiki/Operational_transformation) 、。

“由于多个人可能在一个笔记本内协作，笔记本的状态可能会有所不同。在操作中处理这些冲突的逻辑同时存在于服务器和客户端。因此，使用相同的代码库实现一次操作转换是有意义的，而不是在客户端和服务器上重复它，可能使用不同的编程语言，”van Leuffen 说。

“因此，我们选择 Wasm——用 Rust 编写，因为我们的 API 也是 Rust——作为实现这一功能的方式，节省了相当多的开发时间，并降低了不一致的风险。它非常适合 Wasm。”

它集成了来自 Elastic、Loki、Prometheus 的数据，以及基于笔记本的 cli(如 kubectl (Kubernetes)和 awscli ( [亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention))的终端输出。本地运行命令的输出通过管道传输到笔记本中，在那里可以过滤和操作数据。

“这些是实时的真实图表、真实日志。…这样你就可以开始得出结论，并将事件关联起来，比如‘嘿，我在这个图表中看到了这个峰值。让我放大它。伴随特定服务的日志是什么？让我看看那个。"

这是来自您的可观察性堆栈的数据—监控、跟踪、记录。

"该数据可能来自服务器，但也可能从用户的浏览器到达。为了解决这个问题，我们实现了我们的插件模型 Fiberplane Providers，它既可以存在于浏览器中，也可以存在于用户的网络中。

“这使得插件可以在任何以 Wasm 为目标的语言中实现，从而提高了整体性能，而且 Wasm 沙盒模型提高了安全性。”

为了在多种环境中运行 Wasm 代码，它创建了 [fp-bindgen](https://fiberplane.dev/blog/announcing-fp-bindgen/) ，这是一个绑定生成器，可用于在 Rust 中编写插件，可以在浏览器和 Rust 环境中运行，增加了 Rust 和 Typescript 之间的互操作性。它有[开源的 fp-bindgen](https://github.com/fiberplane/fp-bindgen) 。

此外，它还提供了用所有图表和日志编写模板的能力，以便为某些场景、要执行的查询和可操作的情报做好准备，以推断正在发生的事情。

这项技术还处于私人测试阶段，尽管该公司正朝着 9 月份正式发布的方向努力。

在 TNS 制造商的谈话中， [base case capital](https://basecase.vc/) 的创始人兼管理合伙人 Alana Anderson 说，Fiberplane 拥有“笔记本的外观和感觉”,工程师们使用起来很舒服。

“你走进去，突然之间你就知道了所有正在发生的事情的历史，你可以看到房间里的其他人……而且，马上，你就能了解正在发生的事情，你也能对你的团队更有价值。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>