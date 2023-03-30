# 本周编程:何时选择 F#而非 Rust

> 原文：<https://thenewstack.io/this-week-in-programming-when-to-choose-f-over-rust/>

有什么比看民意调查更好的呢，无论我们谈论的是总统选举还是编程语言的流行？当然，争论我们为什么选择一种编程语言而不是另一种！

本周，这一讨论来自于 [Dark Lang](https://darklang.com/) 的创始人兼首席执行官 [Paul Biggar](https://paulbiggar.com/) ，这是一种编程语言(内置基础设施)，承诺[“无部署”部署](https://thenewstack.io/dark-a-new-programming-language-for-deployless-deployments/)，从代码到生产[的时间少于 50 毫秒](https://thenewstack.io/dark-deep-dive-from-editor-to-infrastructure-in-less-than-50-milliseconds/)。

最初，在迁移到 OCaml 之前，Dark 是用 Python 编写的，但是现在 Biggar 说他们因为许多原因而放弃了 OCaml，包括缺乏工具、库和困难的学习曲线。Biggar 说，在寻找替代者的过程中，他早就预料到重写会发生在 Rust 中，因为它确实有“优秀的工具、伟大的库、令人愉快的社区等”但是经过一个月的工作，很明显这不是命中注定的。当时，他提供了 OCaml 和 Rust 的直接比较，指出“所有编程语言都很糟糕，尤其是你最喜欢的那一种”，这些似乎是本文中任何此类讨论的明智之言。

也就是说，Biggar 决定 [Dark 的新后端将在 F#中，原因很简单:F#是“由世界上最大和最有经验的编程语言创造者支持的 OCaml”。在 OCaml 很棒的领域，F#也很棒！求和类型、静态类型、急切执行、管道、不可变值，所有这些真的很棒。”然而，除了 OCaml 和 F#之间的转换容易之外，还有一些 Rust 特有的原因导致了](https://blog.darklang.com/new-backend-fsharp/)[Dark 没有选择 Rust](https://blog.darklang.com/why-dark-didnt-choose-rust/) ，他还说一篇博客文章可以简单地命名为“你永远不会相信垃圾收集器为你做了多少！”

因此，在简要说明了 Clojure、Haskell 和 Scala 为什么也不行之后，Biggar 解释了为什么越来越流行的 Rust 没有像他曾经预期的那样最终成为首选语言。简而言之，“这归结为几件主要的事情:缺少 GCP 图书馆，以及语言的低级本质。”除此之外，他还指出模式匹配并不是特别好，有太多的方法可以做事情，语言不是不变的，而且“不得不做内存管理很糟糕。”

最后，他把这个决定归结为一个可能适用于许多考虑生锈的人的决定:“我认为我们大多数人不需要生锈。我认为 Rust 是一个很棒的社区、生态系统和工具，它包装了一种语言，很好地解决了我们很少有人遇到的问题。在你真正写代码之前，那里真的很好。[……]有了 GC，我们就不用做任何会导致 Rust 出现这些问题的事情了。也许这需要牺牲性能，但我更需要快速编写代码的能力，而不是额外的性能。”

## 本周的节目中

*   **Python 在 TIOBE 中超越 Java:**本月的 [TIOBE 指数](https://www.tiobe.com/tiobe-index/)，一个根据搜索引擎结果对编程语言的排名，出了一个吸引眼球的标题“Python 势不可挡，超越 Java”根据这篇文章，这是 Java 和 C 第一次不是两个顶级语言——尽管 C 在这个月占据了第一，Python 已经取代了 Java 成为第二名。至于原因，他们提出 Python 在榜单上的新人气“与一般需求有关”，而不仅仅是数据科学的繁荣。TIOBE 首席执行官保罗·詹森写道:“如今编程技能到处都需要，而优秀的软件开发人员却很缺乏。”。“因此，我们需要一些简单的、非软件工程师也能处理的东西，一些易于学习、编辑周期短、部署流畅的东西。Python 满足了所有这些需求。”

*   **重述 kot Lin 1.4:**kot Lin 的最新版本是 10 月份为期三天的在线活动的一部分，现在一切都在网上为那些错过的人准备。流行语言背后的公司 JetBrains 写了一份 [Kotlin 1.4 在线活动摘要](https://blog.jetbrains.com/kotlin/2020/11/kotlin-1-4-online-event-recap-materials-and-quizquest-winners/)，其中有一个活动视频播放列表，包括五个观看次数最多的视频，其中包括对[新语言功能](https://youtu.be/9ihevvUCoG0)的了解、[对未来的展望](https://youtu.be/0FF19HJDqMo)，对 Kotlin 在 Android 中的[状态的检查，以及对 coroutines](https://youtu.be/FRCASfAMXoQ) 的[更新，以及对](https://youtu.be/E5bje5HgKs0) [Kotlin 多平台移动设备](https://youtu.be/PW-jkOLucjM)的了解。除了视频，在 Reddit 上还有一个为 Kotlin 团队举办的 [AMA 会议，为活动期间提出的 700 多个问题提供了答案。](https://www.reddit.com/r/Kotlin/comments/ji9z19/kotlin_team_ama_2_ask_us_anything/ga59r4x/?utm_source=reddit&utm_medium=web2x&context=3)
*   **TypeScript 4.1 候选版本增加了模板文字类型:**继 8 月份的 [TypeScript 4.0](https://devblogs.microsoft.com/typescript/announcing-typescript-4-0/) 发布之后，微软[宣布了 TypeScript 4.1 RC](https://devblogs.microsoft.com/typescript/announcing-typescript-4-1-rc/) ，它表示该版本具有“一些令人兴奋的新特性、新的检查标志、编辑器生产力更新和速度改进。”与此同时，InfoWorld 写道， [TypeScript 4.1 带来了模板文字类型](https://www.infoworld.com/article/3576004/typescript-41-brings-template-literal-types.html#tk.rss_applicationdevelopment)，并深入介绍了一些新特性，包括映射类型中的[键重映射](https://devblogs.microsoft.com/typescript/announcing-typescript-4-1-rc/#key-remapping-mapped-types)、[递归条件类型](https://devblogs.microsoft.com/typescript/announcing-typescript-4-1-rc/#recursive-conditional-types)、大量的[突破性更改](https://devblogs.microsoft.com/typescript/announcing-typescript-4-1-rc/#breaking-changes)等等。

*   **Travis CI 重组定价模式:**本周早些时候，我们看到了期待已久的对 Docker Hub 的更改开始生效，与此同时，Travis CI 表示，他们正在引入一个[新定价模式](http://blog.travis-ci.com/2020-11-02-travis-ci-new-billing)，该模式将提供更快的构建时间和更大的灵活性，同时还指出，这一更改“不会影响大多数使用 Linux 和 Windows OS 在公共和私有存储库上运行构建的 Travis CI 用户”谁将会和不会受到这些变化的影响的列表是详细的，所以请确保点击通过，但足以说这些变化的发生是因为“滥用者已经占用了我们的构建队列并导致每个人的性能下降。”因此，他们说他们“正在为我们的公共构建库实现一些改变”,这将使事情对他们的用户更加公平。
*   **亚马逊网络服务结束。NET SDK 支持:** AWS 已经[宣布结束对。NET 版本 1](https://aws.amazon.com/blogs/developer/announcing-the-end-of-support-for-the-aws-sdk-for-net-version-1/) ，将于 2021 年 4 月 1 日进行，届时结束更新和发布，包括关键 bug 或安全更新。虽然代码仍然可用，但他们建议迁移到最新的主要版本— [AWS SDK for。NET 版本 3 (v3)](https://www.nuget.org/packages/AWSSDK.Core/) ，如果你直接从 v1 迁移，它确实包括一些[突破性的变化](https://docs.aws.amazon.com/sdk-for-net/v3/developer-guide/migration-v3.html#net-dg-migrate-v3-breaking)。有关更多详细信息，请查看[迁移指南](https://docs.aws.amazon.com/sdk-for-net/v3/developer-guide/migration-v3.html)。

亚马逊网络服务是新堆栈的赞助商。

Steve Buissinne 通过 Pixabay 制作的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>