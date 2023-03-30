# Visual Studio 2022 和。NET 6 终于来了

> 原文：<https://thenewstack.io/visual-studio-2022-and-net-6-finally-arrive/>

经过几个月的预览，Visual Studio 2022 和 T2 正式上市的时间终于到来了。NET 6 ，微软的两个主要发布版本已经(至少)酝酿了一年。虽然这两个版本带来了比我们在这里可能涵盖的更多的变化，但我们将回顾一些亮点，并通过大量的链接和视频让您探索所有其他内容。

首先，让我们从 Visual Studio 2022 的[发布开始，这是微软的 IDE 第一次](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-now-available/)[变成 64 位](https://devblogs.microsoft.com/visualstudio/tag/64-bit/)。显然，这意味着 Visual Studio 2022 可以更快地启动，利用增强的硬件，并承担那些通常会有点窒息的大型项目。微软此次发布的口号似乎是“Visual Studio 2022 将帮助您以前所未有的速度从想法到代码”，这显然是其中的一部分。

在同样的意义上，虽然 Visual Studio 2019 已经有了微软的“人工智能辅助代码伴侣” [IntelliCode](https://devblogs.microsoft.com/visualstudio/tag/intellicode/) ，但 Visual Studio 2022 对该工具进行了一些改进。例如，IntelliCode 现在可以完成整行代码，同时还可以注意到重复的编辑，并在发现类似模式的地方建议对代码进行相同的修复。

Visual Studio 2022 的最后一个主要特性是与。NET，这就是[热重装](https://devblogs.microsoft.com/dotnet/update-on-net-hot-reload-progress-and-visual-studio-2022-highlights/)的原因。NET 和 C++，它允许您看到代码更改立即生效，只需快速按 Ctrl-S 保存文件。如果你对这个特性感兴趣，我们认为是这样，你可能想回顾几周前的事情，看看为什么围绕它的戏剧性事件是关注微软开源管理的好理由。除此之外，微软的 Scott Hanselman(他是帮助拯救流行但一度濒临灭绝的热重装功能的人之一)提供了热重装奇迹的完整演示:

[https://www.youtube.com/embed/4S3vPzawnoQ?feature=oembed](https://www.youtube.com/embed/4S3vPzawnoQ?feature=oembed)

视频

正如微软在它的发布会上指出的，“在引擎盖下有数百种其他东西会帮助你”，比如对[调试器](https://devblogs.microsoft.com/visualstudio/tag/debug/)和[的改进。NET 语言服务](https://devblogs.microsoft.com/visualstudio/learn-whats-new-in-net-productivity/)、 [Web Live 预览](https://devblogs.microsoft.com/visualstudio/design-your-web-forms-apps-with-web-live-preview-in-visual-studio-2022/)和[Linux 上的跨平台测试](https://docs.microsoft.com/en-us/visualstudio/test/remote-testing)，所以一定要查看[发行说明](https://docs.microsoft.com/visualstudio/releases/2022/release-notes)和[文档](https://docs.microsoft.com/visualstudio/windows/?view=vs-2022)。对于 Visual Studio 用户来说，最后一件值得注意的事情是，Visual Studio 2022 for Mac 仍处于预览阶段，预览版 3 也将于本周发布，M1 处理器支持也即将推出。当然，如果你不准备阅读更多内容，有大量的[视频](https://www.youtube.com/visualstudio)带你了解新内容，包括这个概述发布会本身的视频:

[https://www.youtube.com/embed/f8jXO946eDw?feature=oembed](https://www.youtube.com/embed/f8jXO946eDw?feature=oembed)

视频

微软称之为“最快的”。网还没"发布。NET 6 是“经过一年多的努力。NET 团队和社区”，包括 C# 10、#F 6、所谓的“[性能大幅提升](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-6/)”，当然还有对苹果芯片的原生支持。微软指出。NET 6 将被支持三年，正如一个开发者在 Twitter 上指出的，这也意味着是时候更新了。尽快拿到 5 号网络。

现在，如果您认为没有足够的空间来包含 Visual Studio 2022 的所有新内容，那么这是的十倍。NET——即使是微软长达 20，000 字的博客文章也无法涵盖所有内容。正如他们所写的，“这个版本包括大约一万个 git 提交。即使这篇文章这么长，它也忽略了许多改进。尽管如此，一些最重要的亮点包括不断吹捧的性能提升，尽管“特别是对于文件 I/O”，以及它作为“跨浏览器、云、桌面、物联网和移动应用的统一平台的能力，所有应用都使用相同的功能。这是微软最初的目标。NET 5，但随后被疫情延迟。

正如微软在它的博客文章中提到的，除了它简短的(但仍然很长的)清单之外。NET 6，“你必须下载并尝试。NET 6 来看到所有新的东西，“称之为发布”另一个巨大的。NET 版本，在性能、功能、可用性和安全性方面都有近乎相同的改进。”

## 本周的节目中

*   **谷歌开放代码之夏:**首先，本周，谷歌广受欢迎的[代码之夏](https://summerofcode.withgoogle.com/archive/) (GSoC)项目[已经扩展到非大学生](http://opensource.googleblog.com/2021/11/expanding-google-summer-of-code-in-2022.html)——我们可以说是生活的学生(尤其是开源软件)，该公司在该项目中一直与大学生合作，在开源软件领域为他们提供指导。该计划现在已经进入第 18 个年头，已经“汇集了来自 112 个国家的 18，000 多名大学生和来自 746 个开源组织的 17，000 多名导师”，现在将对“所有 18 岁以上的开源新人”开放，而不仅仅是大学生或应届毕业生。如果你想知道，是的，这甚至包括中年人、转行者和自学成才的开发者，等等。没有年龄限制——只有学习开源的愿望。除了之前对大学招生的要求，GSoC 还扩大了所涉及项目的规模，包括“中型项目(~175 小时)和大型项目(~350 小时)，并允许项目时间安排的灵活性增加，允许项目运行长达 22 周，而不是仅仅 12 周。

*   **Go 庆祝 12 周年:**Go 团队正在庆祝[Go 12 周年](https://go.dev/blog/12years)，他们在博客中回顾了过去的一年和未来的一年。如果你还没有密切关注，那么，这是对过去一年围棋界发生的一切的完美总结——这里有太多的事情要列出来，但足以说，一些期待已久的变化已经完成，一些仍在进行中，如 [Go fuzzing beta](https://go.dev/blog/fuzz-beta) 和[generics](https://go.dev/blog/generics-proposal)的添加，这两个都预计在 2022 年初的 Go 1.18 中。说到泛型，Go 上周在 Google 开源 Live 上举办了第二届年度 [Go day，会议都是在线的，包括(和其他几个)Ian Lance Taylor 的《](https://opensourcelive.withgoogle.com/events/go-day-2021)[在 Go](https://www.youtube.com/watch?v=nr8EpUO9jhw) 中使用泛型》，介绍了泛型以及如何有效地使用它们。至于“未来一年”的事情，下个月将会看到 [GopherCon 2021](https://www.gophercon.com/) ，其中当然会包括来自整个围棋界的[演讲者](https://www.gophercon.com/agenda)。两个值得关注的会议是功能设计者和实现者 Robert Griesemer 和 Ian Lance Taylor 的“[为什么以及如何使用 Go 泛型](https://www.gophercon.com/agenda/session/593015)”，以及 Suzy Mueller 的“[使用调试适配器协议(DAP)调试 Go 代码](https://www.gophercon.com/agenda/session/593029)”，Suzy Mueller 将向您展示如何通过 Delve 使用 VS Code Go 的高级调试功能。除此之外，该团队还谈到了预期的语言功能，写道“泛型将是我们 2022 年的重点之一”，1.18 版本只是开始，供应链安全也是另一个重点。

[https://www.youtube.com/embed/nr8EpUO9jhw?feature=oembed](https://www.youtube.com/embed/nr8EpUO9jhw?feature=oembed)

视频

*   **Go Packages 获得新的搜索:**当我们在谈论 Go 的话题时，还有一个快速更新:该团队还根据[您的反馈](https://golang.org/issue/47321)于本周在 pkg.go.dev 上向[发布了新的搜索体验。简而言之，结果现在被分组在一起，以“减少当同一个模块中的几个包可能与一个搜索相关时的干扰”此外，相同模块的版本将被分组在一起，并且围绕导入、版本和许可的其他信息已被重新安排。](https://go.dev/blog/pkgsite-search-redesign)
*   **再见，Docker 桌面更新弹出窗口:** [Docker 桌面 4.2 于本周推出](https://www.docker.com/blog/docker-desktop-4-2-release-save-your-battery-with-pause-resume-and-say-goodbye-to-the-update-pop-up/)，在推出的众多功能中，有一个我们已经听到很多关于它的抱怨:那个烦人的弹出窗口询问你是否想要更新。嗯，这个版本取消了这一点，相反，在设置中增加了更新选项，你可能会说，这是应该的。除此之外，这个最新版本的 Docker Desktop 还允许您暂停，从本质上保存您的应用程序状态，并降低您的 CPU 使用率，这有助于降低笔记本电脑的电池消耗。接下来，Docker 表示将致力于改善 Mac 文件系统性能和实现 Docker Desktop for Linux，这是[公共路线图](https://github.com/docker/roadmap/projects/1)中最受欢迎的两个项目。

https://twitter.com/mhmd_azeez/status/1458113199040049157

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>