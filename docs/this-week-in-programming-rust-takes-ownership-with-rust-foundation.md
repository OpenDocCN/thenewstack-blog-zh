# 本周编程:Rust 与 Rust Foundation“取得所有权”

> 原文：<https://thenewstack.io/this-week-in-programming-rust-takes-ownership-with-rust-foundation/>

虽然在某种程度上，科技公司可能不会受到柯维德·疫情的影响，或者至少保持现状，但本月早些时候，Mozilla 表示，“全球疫情导致的经济状况已经严重影响了我们的收入”，并将重组 Mozilla 公司，包括解雇 250 名员工。

这些员工中有一些是 [Rust 项目](https://www.rust-lang.org/)的活跃成员，该项目最初是在 2010 年作为 [Mozilla Research](https://research.mozilla.org/) 项目创建的，因此本周 Rust [宣布](https://blog.rust-lang.org/2020/08/18/laying-the-foundation-for-rusts-future.html)将[启动一个基金会](https://twitter.com/pbwinston/status/1295833299793911809)——核心开发人员实际上从今年早些时候开始就在[积极考虑](http://smallcultfollowing.com/babysteps/blog/2020/01/09/towards-a-rust-foundation/)这件事，并且随着 Mozilla 的重组，这件事被放在了一个更直接的时间表中。

虽然自 2015 年推出 1.0 以来，Rust 已经成为一个独立的组织，但 Mozilla 仍然是“一个突出和一贯的财务和法律赞助商”，但现在，Rust 团队写道，“我们已经到了一个没有合法名称、地址和银行账户就很难运营的地步。Rust 项目如何签订合同？已经成为一个我们不能再拖延的问题。"

该基金会的当务之急将是获得“与 Rust、Cargo 和 crates.io 相关的各种商标和域名”的所有权，目标是在今年年底前上线运行。至于基金会的影响，Rust 核心团队成员 [Steve Klabnik](https://steveklabnik.com/) 在[黑客新闻主题](https://news.ycombinator.com/item?id=24199424)中评论说，目前的重点主要是商标。

“我们已经讨论了这么久，但仍未采取行动的部分原因是，基金会可以做很多事情，比如招聘开发人员。但是我们不确定我们想让它做什么。雇用开发人员有一些很大的优势，但也有很多缺点。目前，我们纯粹专注于商标所有权部分，作为一种 MVP，”克拉布尼克写道。

虽然对这一举动的大部分反应表面上看起来是积极的，但 Apache 联合创始人 Jim Jagielski [在推特上表示](https://twitter.com/jimjag/status/1296046862613598208)他担心运营一个基金会的行为会压垮 Rust 团队，这在黑客新闻的评论中得到了回应。

在这一点上，Klabnik 普遍认为这将是一个额外的压力，尽管其他人并没有面临这种压力，他写道:“花在管理基金会业务上的时间会占用管理项目本身的时间，至少在开始时是这样，因为有很多重叠。基本上，自举永远是个难题。”

## 本周的节目中

*   **Kotlin 1.4 旨在提高质量&性能:**JetBrains[发布了 Kotlin 1.4.0](https://blog.jetbrains.com/kotlin/2020/08/kotlin-1-4-released-with-a-focus-on-quality-and-performance/) ，写道这一次他们“投入了大量的精力和精力来提高 Kotlin 及其工具的性能和质量”，包括“期待已久的[kot Lin 接口的 SAM 转换](https://kotlinlang.org/docs/reference/whatsnew14.html#sam-conversions-for-kotlin-interfaces)如果博客帖子和[发行说明](https://kotlinlang.org/docs/reference/whatsnew14.html?_ga=2.55671587.987037362.1597950776-1270391434.1591892810)对你来说还不够，那么 [Kotlin 1.4 在线活动](https://kotlinlang.org/lp/event-14)，跨越 10 月 12 日至 16 日，应该可以满足你的需求，有四天的虚拟 Kotlin 会谈，Q &与 Kotlin 团队一样，还有更多——你可以[在这里注册](https://kotlinlang.org/lp/event-14#registration)。如果你有想得到答案的问题，你可以在 Twitter 上使用 [#kotlin14ask](https://twitter.com/search?q=%23kotlin14ask&src=typed_query) 标签提问，或者使用[这个表单](https://surveys.jetbrains.com/s3/Q-A-Your-question-for-the-Kotlin-team)提前提交。至于语言本身，最新版本解决了超过 60 个性能问题，包括许多导致 IDE 冻结或内存泄漏的问题。其他改进包括速度提高了四倍的代码突出显示，新的[协程调试器](https://kotlinlang.org/docs/reference/whatsnew14.html#coroutine-debugger)和 [Kotlin 项目向导](https://kotlinlang.org/docs/reference/whatsnew14.html#new-flexible-project-wizard)，以及超过 [40 种新的快速修复](https://youtrack.jetbrains.com/issues?q=%23Feature%20Subsystems:%20%7BIDE.%20Inspections%20and%20Intentions%7D%20%23Fixed%20resolved%20date:%202019-10%20..%20Today%20and%20Target%20versions:%20-1.4.20)。他们写道，他们还在开发一种新的编译器——一种将“统一 Kotlin 支持的所有平台，并为编译器扩展提供 API”的编译器——并且该团队已经开始“与新的实验性 kot Lin[编译器前端 T25 集成，这将使 ide 快得多。”](https://blog.jetbrains.com/kotlin/2020/08/kotlin-1-4-released-with-a-focus-on-quality-and-performance/#new-compiler)
*   **TypeScript 4.0 到来时“没有重大的突破性变化”:**距离测试版发布仅一个多月， [TypeScript 4.0 已经发布](https://devblogs.microsoft.com/typescript/announcing-typescript-4-0/)，带来了许多变化，尽管没有“重大的”突破性变化，以及自 3.0 发布以来静态类型 JavaScript 子集的简要历史。关于没有大的变化这一点，该团队写道，“事实上，如果你是这门语言的新手，现在是开始使用它的最佳时机。这个社区已经在这里了，而且还在成长。”确实发生了一些变化，包括改进的用户体验、增强的性能和可伸缩性，以及入门级体验的扩展等。
*   **学习编写 Visual Studio 代码扩展:**扩展是 Visual Studio 代码流行的一大部分，但是编写一个扩展可能很困难。当然，微软在让你为其流行的 IDE 创建更多扩展方面有既得利益，所以它正在与 [Mads Kristensen](https://devblogs.microsoft.com/visualstudio/author/madsk/) 一起在 [YouTube](https://youtube.com/user/visualstudio) 和 [Twitch](https://www.twitch.tv/visualstudio) 上开始一系列如何直播的视频，他在过去十年中编写了 130 个扩展。该展览将在每周五下午举行，将着眼于修复错误，探索新的 API，为扩展器构建工具，等等。如果你有一个你想涉及的话题，在 Twitter 上提出来。
*   **谷歌的第二个“文档季”开始了:**作为一个开源维护者，你已经有足够多的时间去修复错误、添加功能和编写代码，你可能最不想做的事情就是编写文档，对吗？今年你来得太晚了，但也许明年你会成为被选中的项目之一，与一名技术作家配对，获得作为谷歌[文档季](https://developers.google.com/season-of-docs)的一部分而撰写的文档。本周，谷歌[向](https://opensource.googleblog.com/2020/08/season-of-docs-announces-2020-technical.html)宣布了 [2020 年技术写作项目](https://developers.google.com/season-of-docs/docs/participants/)，这些项目是从 500 多名作家和 800 个项目中挑选出来的，从本周开始，他们将开始相互熟悉的过程，然后从 2020 年 9 月 14 日开始撰写文档。

*   **亚马逊 EKS Fargate 用户现在获得 EFS 支持:**尽管缩写 jambalaya (EKS、ECS、EFS、CSI——他们继续)组成了[这个公告](https://aws.amazon.com/blogs/aws/new-aws-fargate-for-amazon-eks-now-supports-amazon-efs/)，但消息很简单——如果你使用 AWS Fargate 通过亚马逊的托管 Kubernetes 服务(EKS)运行无服务器容器，那么你现在将能够使用其[弹性文件系统](https://aws.amazon.com/efs/) (EFS)进行数据持久性和有状态工作负载。新特性可用于新创建的 Kubernetes 版本 1.17 的 EKS 集群，并在未来几周内支持 EKS 上的其他 Kubernetes 版本。查看[最新文档](https://docs.aws.amazon.com/eks/latest/userguide/fargate.html)了解更多详情。
*   **GitHub 通过 ReadME 项目突出开源:**终于在本周，另一个旨在突出开源维护者和贡献者体验的项目启动了，这一次 GitHub [介绍了](https://github.blog/2020-08-20-readme-project/)ReadME 项目。该项目将是(并且已经是)一系列关于项目和维护者的简介，从 Henry Zhu、Samson Goddy、Sonia John、Ovilia Zhang 和 Dirk Lemstra 开始，他们正在接受[提名](https://github.com/readme/nominate)。

来自 Pixabay 的 Myriam Zilles 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>