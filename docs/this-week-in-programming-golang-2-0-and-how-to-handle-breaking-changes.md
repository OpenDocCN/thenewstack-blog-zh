# 本周编程:GoLang 2.0 和如何处理突发变化

> 原文：<https://thenewstack.io/this-week-in-programming-golang-2-0-and-how-to-handle-breaking-changes/>

本周，GoLang 首席工程师伊恩·兰斯·泰勒(Ian Lance Taylor)提出了他对[从 Go 1 走向 Go 2(T3)的思考，同时考察了其他一些主流语言的发展，以及它们如何处理(或不处理)突破性的变化等等。](https://github.com/golang/proposal/blob/master/design/28221-go2-transitions.md)

虽然 GoLang 爱好者可能对具体细节更感兴趣，但我觉得这种对语言发展的上下文分析特别有趣——我故意使用“发展”这个词，因为这似乎取决于文化，甚至是用于创建语言的特定程序，语言可以成为某些社区成员可能意想不到的东西。事实上，在过去的一年里，随着 vgo 版本化系统的实施，我们看到 Go 社区的成员[争论、不同意，并最终继续前进。类似地，Rust 社区也经历了 RFC 过程中的动荡和从想法到讨论再到实现的转变。在这两种情况下，我们看到每个社区的成员都试图分析并找到一条清晰、合理的前进道路。](https://thenewstack.io/this-week-in-programming-vgo-and-the-onus-of-a-technical-solution-to-all-possible-scenarios/)

今天，我们来看看另一个这样的尝试，在泰勒的[提议中，从 Go 1 转移到 Go 2](https://github.com/golang/proposal/blob/master/design/28221-go2-transitions.md) 。

在他的提案中，Taylor 简要分析了 C、C++、Java、Python 和 Perl 如何处理各种转换，试图创建一个“提案，说明如何在尽可能少中断的情况下从 Go 1 到 Go 2 进行不兼容的更改。”

作为背景，Go 语言和标准库包含在 [Go 1 兼容性保证](https://golang.org/doc/go1compat)中，它声明“编写到 Go 1 规范中的程序将在该规范的生命周期内继续正确编译和运行，没有变化。”Taylor 解释说，“Go 2 过程的目标之一是考虑打破这种保证的语言和标准库的变化”，并且“因为 Go 是在分布式开源环境中使用的，所以我们不能依赖于[标志日](http://www.catb.org/jargon/html/F/flag-day.html)。我们必须允许使用不同版本的 Go 编写的不同包之间的互操作。”

对于所考察的每种语言，Taylor 都提供了一些经验教训，作为推进 Go 2 的指导。例如， [C](https://github.com/golang/proposal/blob/master/design/28221-go2-transitions.md#c) 表明“向后兼容性很重要”，但是“以小的方式破坏兼容性是可以的，只要人们能够通过编译器选项或编译器错误发现破坏。”[与此同时，Java](https://github.com/golang/proposal/blob/master/design/28221-go2-transitions.md#java) 表明语言设计者应该“意识到兼容性问题会如何限制未来的变化。”而 [Python 的](https://github.com/golang/proposal/blob/master/design/28221-go2-transitions.md#python)从 Python 2 到 Python 3 的不协调的过渡例证了向后兼容性的重要性。

我们从 [Perl](https://github.com/golang/proposal/blob/master/design/28221-go2-transitions.md#perl) 中学到了什么？“不要成为 Perl 6，”Taylor 写道，还提到了设置和满足截止日期(Perl 6 只用了 15 年)以及不要“一次改变一切”的重要性。

泰勒的帖子是一个很好的例子，说明人们采纳了被永远错误引用的格言“那些不记得过去的人注定要重复过去。”通过对过去的审视，也许围棋会成功避免这种谴责。

再说一次，泰勒并没有解决细节问题，而是尝试中最有趣的大方向。泰勒总结道:“如果上述过程按计划进行，那么从某种重要意义上来说，永远不会有第二次尝试。”。“或者，换一种说法，我们将慢慢过渡到新的语言和库特性。我们可以在过渡期间的任何时候决定现在我们是 Go 2，这可能是很好的营销。或者我们可以跳过它(从来没有 C 2.0，为什么要有 Go 2.0？)."

那么，经过如此详细的语言发展历史分析，泰勒的结论是什么呢？

"也许不出所料，真正的 Go 2 是有害的."

## 本周的节目中

*   **Go 变小:**本周继续 GoLang 线程，我们不禁注意到提到了 [TinyGo](https://github.com/aykevl/tinygo) ，这是一款基于 LLVM 的 Go 编译器，用于微控制器和单处理器内核的小型系统。根据 GitHub 上的存储库描述，TinyGo 类似于 [emgo](https://github.com/ziutek/emgo) ，但是保留了“Go 内存模型(这意味着某种垃圾收集)。”它还“在内部使用 LLVM，而不是发出 C，这有望产生更小、更高效的代码，当然也会带来更大的灵活性。”你可能会问，为什么要为微控制器开发 Go 编译器？“如果 [Python](https://micropython.org/) 可以在微控制器上运行，那么 [Go](https://golang.org/) 当然也应该能够在更低级别的微控制器上运行，”该项目的创建者写道。
*   **GitLab 11.4 增加了合并请求评审&更多:**继续 GoLang，GitLab 本周宣布了 [GitLab 11.4，增加了合并请求评审和特性标志](https://about.gitlab.com/2018/10/22/gitlab-11-4-released/)，据说这将使代码评审更加高效，增加了[合并请求评审](https://about.gitlab.com/2018/10/22/gitlab-11-4-released/#merge-request-reviews)和[文件树，用于区分](https://about.gitlab.com/2018/10/22/gitlab-11-4-released/#file-tree-for-browsing-merge-request-diff)。[特性标志](https://about.gitlab.com/2018/10/22/gitlab-11-4-released/#create-and-toggle-feature-flags-for-your-applications-alpha)，一个特性切换系统正在 alpha 中引入，Auto DevOps 和 CI 正在获得 [PostgreSQL 迁移](https://about.gitlab.com/2018/10/22/gitlab-11-4-released/#support-postgresql-db-migration-and-initialization-for-auto-devops)和[定时增量展示](https://about.gitlab.com/2018/10/22/gitlab-11-4-released/#add-timed-incremental-rollouts-to-auto-devops)。[合并请求评审](https://about.gitlab.com/2018/10/22/gitlab-11-4-released/#merge-request-reviews)特性将让评审者“在代码或合并请求上输入多个评论，然后在一批中完成它们。”

*   **GitHub 获得 FedRAMP 授权:**不管公司本周发生的整个[事件](https://blog.github.com/2018-10-22-incident-update/)，GitHub 宣布 [GitHub 商业云现在获得 FedRAMP 授权](https://blog.github.com/2018-10-24-github-is-fedramp-authorized/)，通过“FedRAMP 定制的安全控制基准”这基本上意味着政府用户可以继续使用 GitHub，并知道他们的屁股是受保护的——他们遵循了指导方针，并使用了经认证符合“我们的美国联邦政府合作伙伴设定的安全标准基线”的服务。
*   **OpenJDK 可能会转向 GitHub:** InfoWorld 本周报道称 [Java SE 的 OpenJDK 可能会转向 GitHub](https://www.infoworld.com/article/3315618/java/java-ses-openjdk-could-be-headed-to-github.html) ，通过提供对大量自动化工具和“用于开发 JDK 本身的熟悉资源”的访问，“这一举动可能会帮助 Java 开发人员”文章称，此举是 Skara 项目的一部分，“这是一项正在进行的工作，旨在检查 OpenJDK 的新基础设施，[并]可能将回购转移到基于 Git 的回购，可能包括 GitHub 或其他主机。”就时间而言，这一举动可能发生在“JDK 12 号的时间框架内，该时间框架定于 2019 年 3 月，或者可能在此之后。”
*   **Node 11 到来:**根据 JAXEnter 的说法， [Node.js 11 完全是关于改进内部的](https://jaxenter.com/node-js-11-improving-internals-151021.html)，其中最值得注意的两个特性是放弃 FreeBSD 10 和重新安排间隔计时器“即使前一个间隔抛出了错误。” [Node v11.0.0 公告](https://nodejs.org/en/blog/release/v11.0.0/)还指出 Node.js 10.x 将成为最新的长期支持(LTS)版本，这“基本上意味着它将准备好用于生产和需要扩展的应用程序。”JAXEnter 还问“Node.js 的日子屈指可数了吗？注意到“需要解决房间里的大象”——node . js 的创建者 Ryan Dahl 最近宣布“在 V8 上运行一个安全的类型脚本，称为 [Deno](https://jaxenter.com/ryan-dahl-fixing-node-deno-146190.html) ”，据说它可以解决安全问题，Dahl 强调“这是他对[Node.js]的一个主要遗憾。"
*   GNU 友好交流指南:最后，在本周，SDTimes 讲述了[理查德·斯托尔曼如何发布 GNU 友好交流指南](https://sdtimes.com/os/richard-stallman-releases-gnu-kind-communication-guidelines/)“努力引导对话向更友好的方向发展”的故事，圆满结束了语言发展的话题以及这一过程中固有的(经常是激烈的)辩论斯托曼在[的帖子](https://www.gnu.org/philosophy/kind-communication.html)中提到“人们有时会因为某些交流模式而不愿意参与 GNU 的开发，这些模式给他们的印象是不友好、不欢迎、拒绝或者苛刻。这种沮丧情绪尤其影响到贫困人口，但不仅限于他们。因此，我们要求所有的贡献者在 GNU 项目讨论中有意识地努力，以避免这种结果的方式进行交流——避免可预见的和不必要的将一些贡献者拒之门外的做法。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>