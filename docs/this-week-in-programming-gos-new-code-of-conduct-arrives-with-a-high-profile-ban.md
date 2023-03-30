# 在本周的《编程:围棋》节目中，围棋新的行为准则带来了一个高调的禁令

> 原文：<https://thenewstack.io/this-week-in-programming-gos-new-code-of-conduct-arrives-with-a-high-profile-ban/>

Go 编程语言社区本周对其行为准则 (CoC)进行了[更新，这似乎与来自所有 Golang 社区空间的](https://go.dev/blog/conduct-2021)[永久禁止](https://twitter.com/peterbourgon/status/1438597459383623684)[著名且多产的 Go 贡献者和社区成员 Peter Bourgon](https://peter.bourgon.org/) 的相吻合。

Go first [在 2015 年](https://github.com/golang/proposal/blob/master/design/13073-code-of-conduct.md)通过了一项行为准则，即使在当时[也远远不是一项普遍接受的事情](https://groups.google.com/g/golang-nuts/c/sy-YcVPADjg/m/bcO6LAr29EIJ)，后来[在 2018 年](https://go.dev/blog/conduct-2018)更新了该行为准则，以包括明确与 Go 相关的空间之外的行为，但似乎两者都不够。Go 团队写道，本周的更新有助于两方面的更新:CoC 的执行，以及“地鼠价值观本身”。

关于执行的第一点，该团队指出，他们“希望每个人在这里都感到受欢迎”，而且“我们不能欢迎的一群人是那些让其他人感到不受欢迎的人”，有特定的渠道或 Go 空间有权执行禁令，而不必等待行为报告。他们接着列出了一些情况，当社区范围内的禁令，如显然传给布尔贡的禁令，可能会被执行，他们说这是罕见的。

关于第二点，对“地鼠价值观”的更新，Go 团队在 CoCs 的标准内容(“友好、欢迎”和“尊重”)中增加了“负责任”的概念，他们进一步描述为“你说什么和做什么很重要”。对你的言行负责，包括它们的后果，不管是有意还是无意。

“我们在小问题报告中看到的一个反复出现的主题是，人们不接受自己的言行会影响他人。在极端情况下，人们会说‘但这是互联网’之类的话。我们渴望比整个互联网更受欢迎，”他们写道。

更新中没有提到涉及波尔贡的情况，尽管这种说法“但这是互联网”似乎是直接暗指网飞·SRE[蒂姆·赫克曼](https://twitter.com/theckman/)提交的[行为报告](https://docs.google.com/document/d/1exmMfbgVCz3dRXOOlfUCYeiXCuyNaMUnDogDv88HV4g/edit)，关于最近与波尔贡在[Go Slack 频道](https://app.slack.com/client/T029RQSE6/C029RQSEE)的互动。

对于那些不是 Go Slack 频道成员的人来说，整个互动也被保存在 Imgur 上供你阅读，正如你所看到的，当被要求停止时，Bourgon 回答说:“这是互联网。”现在，在/r/Golang 上的一些[评论帖子中，以及在 Bourgon 的 Twitter 帖子中，有很多人认为 Bourgon 只做了一些轻微的微调，当然没有什么值得永久禁止的。Bourgon 本人辩称他没有做错任何事情，这似乎再次直接提到了现在添加到 Go CoC 中的“负责任”的想法。](https://www.reddit.com/r/golang/comments/ppluux/peter_bourgon_banned_from_all_go_community_spaces/)

本周的更新似乎再次谈到了这种情况，但没有直接解决这一问题，Go 团队写道，“可能值得全社区驱逐的不当行为的例子包括”骚扰和违规行为，“这些行为在孤立时可能看起来微不足道，但随着时间的推移，它们会形成一种与我们的 Gopher 价值观不匹配的行为模式，累积起来会造成实质性的伤害。”赫克曼在他的行为报告中抱怨的正是这种反复的冒犯，至少对于一个外部观察者来说，这可能导致了眼下的局面。

在 Reddit 上的一个特别不自觉或讽刺的评论中，[一位评论者写道【Bourgon 的评论“感觉像是在 Perl IRC 上完全可以接受的谈话”，而另一位评论者回答说“如果我必须提出最简单的 CoC '不要像 15 年前 IRC 上的一些人那样行事'将是一个不错的竞争者。”](https://www.reddit.com/r/golang/comments/ppluux/peter_bourgon_banned_from_all_go_community_spaces/hd5n48b/)

事实上，Perl 自己最近与 CoCs 之类的[的斗争](https://www.theregister.com/2021/08/13/perl_resignations/)似乎只是在线社区及其对毒性的容忍度道路上的又一个领头羊。

## 本周的节目中

*   **Visual Studio Preview 4:** 本周首先， [Visual Studio 2022 Preview 4 现已发布](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-preview-4-is-now-available/)，它聚焦于“个人和团队生产力、现代发展和持续创新的主题”其中，该团队表示，Preview 4 为搜索大型解决方案和 C++智能感知带来了性能改进，所有这些都将很快获得自己的博客帖子。这个最新的预览版还展示了改进的调试功能，这些功能使使用窗口选择器选择进程、为项目外部的库加载符号等事情变得更加容易，还展示了新功能，如依赖断点，用于在第一次命中另一个断点后配置其他断点。预览版 4 还修复了预览版 3 中报告的一些关于 Blazor 和 Razor 编辑器的问题，同时在 ASP.NET 核心中添加了新的热重新加载功能，包括文件保存时的热重新加载和实时应用对 CSS 文件的更改。Preview 4 还增加了一些个性化的新功能，如颜色编码的标签，该团队表示，它将“与社区主题作者合作，将一些 Visual Studio 代码主题转换为在 Visual Studio 中工作，在 Visual Studio 系列产品中增加更多灵活性”，如“Winter is Coming”主题[现已在市场上提供](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.WinterIsComing)。要了解全部细节，请查看下面的[博客文章](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-preview-4-is-now-available/)、[发布说明](https://docs.microsoft.com/en-us/visualstudio/releases/2022/release-notes-preview)和[视频](https://www.youtube.com/watch?v=qme1vmJEQJc)。

[https://www.youtube.com/embed/qme1vmJEQJc?feature=oembed](https://www.youtube.com/embed/qme1vmJEQJc?feature=oembed)

视频

*   **。NET 6 得到了第一个候选版本:**也于本周在微软的世界中发布，[。NET 6 候选发布版本 1 已经发布](https://devblogs.microsoft.com/dotnet/announcing-net-6-rc1/)，作为“两个支持生产的‘上线’候选发布版本中的第一个”，并将带来“质量改进，解决新功能中的功能或性能问题或现有功能的退化。”至于“生产中”部分。NET 团队说他们正处于“周期中最有趣部分”,他们“真诚地”鼓励用户在生产中使用这个候选版本，而且他们已经准备好帮助“二三十个早期采用者”完成这个过程。这个最新发布的候选版本得到了 [Visual Studio 2022 预览版 4](https://visualstudio.microsoft.com/vs/preview/vs2022/) 的支持，并附带了许多新工具，支持。NET 6 RC1 即将在 Mac Preview 1 的 Visual Studio 2022 中推出。
*   **甲骨文在“免费 Java 许可”下发布 JDK 17:**甲骨文本周在[“甲骨文免费条款和条件”(NFTC)许可](https://www.oracle.com/downloads/licenses/no-fee-license.html)下发布了 [Java 开发工具包(JDK) 17](https://openjdk.java.net/projects/jdk/17/) ，它表示允许所有用户免费使用，即使是商业和生产使用，只要它是免费的，就允许再分发。他们在一篇介绍新许可证的博客文章中写道:“开发者和组织现在可以轻松地[下载、使用、共享和再分发 Oracle JDK](https://www.oracle.com/java/technologies/jdk-script-friendly-urls/) ，而不需要点击。抛开许可不谈，Oracle 的最新 JDK 是作为长期支持(LTS)版本发布的，下一个 LTS 计划于 2023 年 9 月的 Java 21 发布，将 LTS 版本的发布周期从三年改为两年。新版本包括 14 项新功能，详见[发布页面](https://openjdk.java.net/projects/jdk/17/)。

*   招聘流程集成开发环境？我确信，当你读到这些文字时，你的第一个想法可能是“这是什么新鲜玩意儿？”好像开发人员面试过程已经不是[臭名昭著的](https://new.pythonforengineers.com/blog/the-programming-interview-from-hell/)了，SD Times 本周有一篇关于 [CodeSignal 为招聘过程开发的新 IDE](https://sdtimes.com/softwaredev/codesignal-announces-new-ide-for-the-hiring-process/)的文章，据说它旨在通过真实世界的评估来测试候选人的技术技能。“根据 CodeSignal 的说法，新的 IDE 可以作为编码环境的飞行模拟。他们写道:“这让雇主能够全面评估候选人的技能，同时也给候选人提供了展示自己能力的机会，证明他们为什么是这份工作的合适人选。”所以，这是你在找下一份工作时可以期待的事情。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>