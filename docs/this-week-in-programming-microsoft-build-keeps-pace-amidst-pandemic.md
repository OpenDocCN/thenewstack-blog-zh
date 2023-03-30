# 本周编程:微软构建在疫情保持同步

> 原文：<https://thenewstack.io/this-week-in-programming-microsoft-build-keeps-pace-amidst-pandemic/>

又是一周，又是一场虚拟会议，这一次微软以跨越时区的连续 48 小时马拉松式重复会议的形式发布了 [Microsoft Build](https://mybuild.microsoft.com/) ，以安抚其全球观众。幸运的是，如果你错过了其中的任何一个，它都可以在网上供你悠闲地观看。

虽然其他人已经彻底取消了他们的开发者大会，或者保留了你可能在这样的活动中预期的一系列公告，但微软本周提供了一系列令人眼花缭乱的新开发者功能，从 Visual Studio 2019 对 Visual Studio 代码空间支持的[扩展](https://devblogs.microsoft.com/visualstudio/expanding-visual-studio-2019-support-for-visual-studio-codespaces/)到旨在重新统一基于 Windows 的应用开发体验的项目 Reunion 的推出[。](https://techcrunch.com/2020/05/19/microsoft-announces-project-reunion-to-make-windows-app-development-easier-again/)

老实说，尽管转向了在线格式，但新闻的数量还是有点多，因此，在浏览其他以开发者为中心的网络新闻之前，我们将快速浏览一下 Build 2020 的一些亮点。当然，可以从微软首席执行官[塞特亚·纳德拉](https://twitter.com/satyanadella)的主题演讲开始，该演讲概述了该公司的扩张努力和影响。

[https://www.youtube.com/embed/nt_Uy59cK3k?feature=oembed](https://www.youtube.com/embed/nt_Uy59cK3k?feature=oembed)

视频

如果你正在寻找本周开发者大会的新闻的一站式点，该公司确实在一篇博客文章中总结了许多以开发者为中心的东西，看看开发者如何能够从任何地方[编码、协作和发布他们的应用](https://azure.microsoft.com/blog/code-collaborate-and-ship-your-apps-from-anywhere/)。在代码方面，微软宣布了一系列事情——发布[。NET 5 预览版 4](https://dot.net/get-dotnet5) ，[ASP.NET Blazor web assembly](https://aka.ms/blazor)，以及 [C# 9.0](https://devblogs.microsoft.com/dotnet/welcome-to-c-9-0/) ，刚刚开始。虽然新功能和语言版本令人兴奋，但更令人兴奋的可能是微软宣布[开源 GW-BASIC](https://devblogs.microsoft.com/commandline/microsoft-open-sources-gw-basic/) 加入 [MS-DOS](https://devblogs.microsoft.com/commandline/re-open-sourcing-ms-dos-1-25-and-2-0/) 。当你可以花时间钻研 1983 年的汇编代码时，谁还需要新的语言呢，对吗？

本周的许多公告也围绕着微软 Azure，从 Azure Kubernetes 服务(AKS)对 Windows 服务器容器的支持的[全面上市，到对](https://aka.ms/k8sonaz/blog) [Azure 认知服务](https://azure.microsoft.com/services/cognitive-services/)的补充，到将 [GitHub Actions for Azure](https://aka.ms/GitHubActionsforAzureDocs) 集成到 Visual Studio 代码、Azure CLI 和 Azure 门户中。哦，更不用说该公司称仅用六个月就建成的基于 Azure 的[人工智能超级计算机。在他的主题演讲中，纳德拉解释说，他们“在每一层都进行创新，从边缘到混合到数据和人工智能”，公告的广度似乎肯定支持这一说法。当然，](https://blogs.microsoft.com/ai/openai-azure-supercomputer/) [Windows 终端 1.0](https://devblogs.microsoft.com/commandline/windows-terminal-1-0/) 的发布，将 Linux 体验带入 Windows，是我们进入一个大胆新世界的证据——也许，经过漫长的等待， [2020 年将最终成为 Windows 桌面上的 Linux 之年](https://www.zdnet.com/article/2020-will-be-the-year-of-linux-on-the-windows-desktop/)——等等，那不是 [2019](https://www.theregister.co.uk/2019/05/06/windows_subsystem_for_linux_terminal/) 吗？

[https://www.youtube.com/embed/y8OnoxKotPQ?feature=oembed](https://www.youtube.com/embed/y8OnoxKotPQ?feature=oembed)

视频

## 本周的节目中

*   启动您的(合同跟踪)引擎！上个月，我们写了一点关于[数字联系人追踪的困难](https://thenewstack.io/this-week-in-programming-the-ethical-quagmire-of-technological-contact-tracing/)的文章，并研究了一些潜在的解决方案，包括苹果和谷歌合作开发软件的提议，“额外的好处是可以同时嵌入 Android 和 iOS，这样两个主流移动操作系统不仅可以相互通信，还可以在后台运行这样的软件。”嗯，这种努力已经有了成果，就是新发布的暴露通知 API[，它希望这将成为当地卫生机构开发应用的基础。两家公司在一份联合声明中写道:“我们建立的不是一个应用程序，而是公共卫生机构将把 API 整合到他们自己的应用程序中，供人们安装。”“今天，这项技术掌握在世界各地的公共卫生机构手中，他们将发挥主导作用，我们将继续支持他们的努力。”现在，为了处理一直存在且令人讨厌的用户采用和选择加入部分…](https://www.blog.google/inside-google/company-announcements/apple-google-exposure-notification-api-launches/)
*   **Go 1.15 增加了工具方面的变化:**Go 编程语言[的第 16 个主要版本](https://golang.org/)已经进入“功能锁定”，预计将于 8 月 1 日发布，据说“比平时的变化更少”，根据对 Go 1.15 即将发布的内容的了解，大多数主要变化都将出现在“幕后或工具中”。这些变化包括一个新的链接器，它将加快构建时间，减少二进制文件的大小，以及“语言运行时的性能改进，支持的架构的变化，以及标准库的一些更新。”总的来说，这应该是一个坚实的语言升级。距离 Go 1.15 发布还有两个多月，有时间使用 [gotip](https://godoc.org/golang.org/dl/gotip) 工具测试自己的代码，或者等待 6 月 1 日的二进制 beta 版发布。

*   **Java 25 岁:**自从[Java 编程语言](https://www.infoworld.com/article/3544229/java-programming-language-celebrates-25-years.html)的出现到现在已经 25 年了，InfoWorld 提供了这种语言的过去和未来。他们写道，诞生于“Oak”项目之后，“面向对象的 Java 因其‘一次编写，随处运行’的可移植性而闻名[……]Java 继续在最突出的语言流行指数中名列前三。”即使在云原生世界，Java 也是一个坚定的选择，Quarkus 和 Spring framework 等东西让这种语言保持新鲜，并且这种语言的开发继续保持强劲。Java 14 于两个月前发布，JDK 15 计划于 2020 年 9 月发布。
*   **Deno 希望取代 Node.js:**TypeScript 和 JavaScript 运行时 [Deno 已经发布了 1.0 版本](https://deno.land/v1)，发布该版本背后的博客帖子提供了一些思考，说明为什么它是比 Node.js 更好的选择——特别是考虑到创建者 Ryan Dahl 也创建了 Node . js。他们解释说，Node“是在 2009 年设计的，当时 Javascript 是一种非常不同的语言”，并且“必须发明一些概念，这些概念后来被标准组织采纳，并以不同的方式添加到语言中。”因此，“构建节点项目可能会成为一项艰巨的任务，包括管理构建系统和其他繁重的工具，这剥夺了动态语言脚本的乐趣。”因此，Deno 在几年前诞生并公开，现在提供了一个基于 Rust 的运行时，用于在浏览器之外运行 JavaScript 和 TypeScript。

*   Knative 增加了新的 TOC 成员:对于那些在国内关注的人来说，我们从去年秋天开始就一直关注 Knative 及其治理的传奇，当时谷歌明确表示[不会将无服务器项目](https://thenewstack.io/this-week-in-programming-no-foundation-necessary-google-retains-knative-istio/)捐赠给一个中立的母组织，如 CNCF。本周，谷歌宣布 [Knative 已经选出了新的 TOC 成员](http://opensource.googleblog.com/2020/05/knative-elects-new-technical-oversight.html)，有效地产生了“Knative 的新技术管理，成员代表 RedHat、VMWare 和谷歌”，这将在未来两年指导该项目。至于 CNCF 的捐赠，这似乎仍然是一个坚实的没有。

红帽是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>