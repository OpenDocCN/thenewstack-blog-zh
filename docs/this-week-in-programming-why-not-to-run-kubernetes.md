# 本周编程:为什么不运行 Kubernetes

> 原文：<https://thenewstack.io/this-week-in-programming-why-not-to-run-kubernetes/>

在 New Stack，您阅读了一篇又一篇赞美容器化、Kubernetes 和无数工具的优点的文章，这些工具构成了围绕开源容器编排工具的蓬勃发展的生态系统，但是今天，我们认为我们可能会带给您一个相反的观点。本周，数字货币交易网站比特币基地撰写了一篇博客文章，解释为什么 Kubernetes 不是其堆栈的一部分，除了提供过去十年容器化和编排的快速，向下和肮脏的历史，这篇文章还提供了一些见解，为什么 Kubernetes 可能对一些人有用，但可能不是所有人。在你彻底否定这一点之前，即使是 Kubernetes 的倡导者 Kelsey Hightower [也称这篇文章](https://twitter.com/kelseyhightower/status/1270363229009489921)为“值得研究的分析”，指出“让人们管理自己的 Kubernetes 集群就像让人们管理自己的虚拟机管理程序，而他们只是想要虚拟机。”

现在，请注意(Hightower 也指出了)，比特币基地并不反对容器化或对编排工具的需求。事实上，该公司建立了自己的“非常简单(有目的)”的编排平台，名为 [Odin](https://github.com/coinbase/odin) ，与亚马逊网络服务的自动扩展组(ASG)一起运行。

文章承认“容器编排平台是复杂而神奇的技术，帮助一些企业和团队解决了一整套问题”，但认为“然而，通常被忽视的是，容器技术也产生了大量的挑战，必须克服这些挑战才能[防止失败](https://github.com/hjacobs/kubernetes-failure-stories)。”比特币基地的论点的核心后来被重申，认为“运行 Kubernetes 并不能解决任何客户(工程)问题。运营 Kubernetes 实际上会产生一系列全新的问题。”

他们进一步分析了不使用 Kubernetes 的理由，指出需要一个大型的全职计算团队来处理操作繁重的集群升级和管理，受管 Kubernetes 产品还处于相对初级阶段，以及“保护 Kubernetes 不是一项简单、容易或容易理解的工作”今天，他们写道，“我们没有这个负担。”

不过，实际上，似乎从现在开始，焦点都集中在一件事上——“作为一家存储超过 80 亿美元加密资产的企业，保护和运营 Kubernetes 的复杂性。”虽然运行 Kubernetes 的复杂性是一个众所周知的痛点，但比特币基地认为，复杂性，以及保护这种复杂性的额外负担，是转向其他地方进行容器编排的真正原因——甚至是构建自己的工具来完成这项工作。

最后，比特币基地写道，Kubernetes“尽管面临挑战，但仍是一个伟大的工具”，“推动我们的行业朝着越来越积极的方向前进”尽管如此，他们也写道，“目前我们没有计划建造/拥有/运营 Kubernetes。”

## 本周的节目中

*   **Visual Studio Code 的 Go 扩展和 5 月发布:**每个月，Visual Studio Code 团队都会发布一个附带博客文章的版本，本月也不例外，[Visual Studio Code 2020 年 5 月](https://code.visualstudio.com/updates/v1_46)会关注许多新功能，包括[可访问性改进](https://code.visualstudio.com/updates/v1_46#_accessibility)、添加 GitHub remotes 、 [GitHub 问题笔记本](https://code.visualstudio.com/updates/v1_46#_notebooks)和 [Windows ARM64 支持](https://code.visualstudio.com/updates/v1_46#_windows-arm64-insiders)等等。在另一篇博客文章中，该团队还指出 [Visual Studio 代码 Go 扩展已经加入了 Go 项目](https://code.visualstudio.com/blogs/2020/06/09/go-extension)，Go 团队[写道](https://blog.golang.org/vscode-go)带来了“两个关键的变化”。首先， [Go 扩展](https://marketplace.visualstudio.com/items?itemName=golang.go)发布者将从“微软”转变为“谷歌的 Go 团队”，其次，该项目的存储库[将加入 Go 项目的其余部分](https://github.com/golang/vscode-go)。此外，微软在其博客文章中写道，“Go 团队已经正式成为 Go 扩展的新维护者”，“成为 Go 项目的一部分也将确保社区参与其中的每一步。”对于那些有兴趣参与的人，在[地鼠松弛](https://invite.slack.golangbridge.org/)上有一个#vscode 频道。
*   **Android 11 测试版推迟发布:**谷歌花了一些时间阅读房间，[决定](https://twitter.com/AndroidDev/status/1266589514937466880?s=20)推迟 Android 11 的测试版发布，完全放弃直播活动，而是“共享[几个视频和在线资源](https://developer.android.com/android11)，在合适的时候按照自己的节奏消费。”在开发者博客上的[博客文章](http://android-developers.googleblog.com/2020/06/unwrapping-android-11-beta-plus-more.html)中，谷歌写道，该版本包括许多针对 Android 开发者的优惠，包括“从 Kotlin 协同程序，到 Jetpack Compose 工具包的进展，到 Android Studio 中更快的构建，甚至是 Play 控制台的刷新体验”，重点是开发者友好性。虽然新增内容的范围太长，无法在此列出，但在开发者博客上有详细的概述，并且在 Android 开发者 YouTube 频道[上发布了十几个演讲。](https://goo.gle/android11)

[https://www.youtube.com/embed/bAdRKQNbLmQ?feature=oembed](https://www.youtube.com/embed/bAdRKQNbLmQ?feature=oembed)

视频

*   **Rust 的 2020 年活动阵容:**到目前为止，你已经非常熟悉疫情科技大会的颠覆，本周 Rust 团队向我们更新了 [2020 年活动阵容](https://blog.rust-lang.org/2020/06/10/event-lineup-update.html)，其中包括 RustConf 等主要活动。正如你所料，这些事件也不例外，其中大多数都演变成了虚拟事件，只是 Rust LATAM 完全取消了。关于聚会等其他活动的详细信息，请查看 Rust 简讯中的[社区日历](https://calendar.google.com/calendar/embed?src=apd9vmbc22egenmtu5l6c5jbfc@group.calendar.google.com)和[本周，以及](https://this-week-in-rust.org/)[Rust streams](https://github.com/jamesmunns/awesome-rust-streaming)的策划列表。
*   **PHP 加入 Java 25 周年俱乐部:**几周前，我们[庆祝了](https://thenewstack.io/this-week-in-programming-microsoft-build-keeps-pace-amidst-pandemic/)Java 25 周年纪念日，本周轮到 PHP，[用 JetBrains](https://www.jetbrains.com/lp/php-25/) 的一个漂亮的 PHP 时间表来纪念这一时刻。时间线本身在 GitHub 上是公开的[，但除此之外，点击也很有趣，链接范围从](https://github.com/JetBrains/php-timeline)[拉斯马斯·勒德尔夫介绍个人主页(PHP)工具的原始消息](https://groups.google.com/forum/#!msg/comp.infosystems.www.authoring.cgi/PyJ25gZ6z7A/M9FkTUVDfcwJ)到[即将到来和等待的 PHP 8](https://stitcher.io/blog/new-in-php-8) 。
*   **亚马逊用 AWS CodeArtifact 引入包管理:**包管理器并不缺乏，对于企业来说，这可能会在“应用程序的软件依赖性的两个版本和访问”方面提出挑战，亚马逊在他们的 AWS CodeArtifact 简介中写道。相反，中央存储库提供对访问和版本更改的控制，而 [AWS CodeArtifact](https://aws.amazon.com/codeartifact) 就是这样:一个完全托管的工件存储库服务，有助于安全地存储和共享软件包，这些软件包可以用于“流行的构建工具和软件包管理器，如 Maven 和 Gradle(用于 Java)、npm 和 yarn(用于 Javascript)以及 pip 和 twine(用于 Python)，还有更多。”他们还指出“CodeArtifact 是一个多语言的工件库，这意味着它可以存储任何支持类型的工件包。”要了解更多信息，请在 6 月 12 日中午(太平洋标准时间)收听[Twitch.tv/aws](https://www.twitch.tv/aws)或 [LinkedIn Live](https://www.linkedin.com/company/amazon-web-services/) ，团队将在那里展示如何开始。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>