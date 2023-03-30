# 本周编程:GitHub 从 Docker Hub 停止的地方开始

> 原文：<https://thenewstack.io/this-week-in-programming-github-steps-in-where-dockerhub-left-off/>

本周早些时候，GitHub [发布了 GitHub 容器注册表](https://github.blog/2020-09-01-introducing-github-container-registry/)的公开测试版——本质上是对去年发布的 GitHub 包功能[的补充](https://github.blog/2019-05-10-introducing-github-package-registry/)，这将使其用户能够“更好地执行访问策略，鼓励使用标准的基本映像，并通过更容易的跨组织共享来促进内包”然而，也许比这些特性更重要的是，GitHub 将提供对公共容器图像的匿名访问，它说这将是免费的。

这一消息紧随上个月 Docker Hub 服务条款的变化而来，该变化引起了[的一点骚动](https://www.reddit.com/r/docker/comments/i93bui/docker_terms_of_service_change/)，因为该公司引入了速率限制和自动删除非活动图像的时间表。对于一些人来说，这个时机似乎不太巧合，Docker 本身同时也在博客上写道“Docker 和 GitHub 将继续合作，让开发者的生活更轻松。”

并不是说你希望 GitHub 提到它，但阅读新闻时，你可能会忍不住认为这是 Docker Hub 的第一个替代品，而事实上 GitLab 自 2016 年以来就提供了这一功能。

GitLab 的高级开发人员布道者 Brendan O'Leary 通过电子邮件对这一消息发表了评论，准确地指出了这一事实，他说:“我们相信完整的 DevOps 平台对工程师和领导层都有巨大的好处。这就是为什么我们在 2016 年向 GitLab 添加了容器注册表，并继续专注于将完整的 DevOps 平台作为单个应用程序来交付。”

然而，GitLab 缺少了微软支持(并拥有)的 GitHub 所能提供的一大部分——它背后的云平台。

无论 GitLab 是否抢先一步，GitHub 正在加入这场游戏，恰恰是在 Docker Hub 似乎决定不为广泛(免费)使用买单的时候，它已经迈出了第一步，许多人认为它计划接下来采取这一步。

## 本周的节目中

*   **Postman 获得 API 工具的 Web 客户端:**到目前为止，Postman 依赖于旧的方法，实际上是强迫其用户下载并安装软件来使用其工具(过时了，对吗？)但现在，该公司[推出了新的网络客户端](https://www.businesswire.com/news/home/20200902005256/en/Postman-Launches-New-Web-Client-Simplify-API)，称其为用户提供了“简化的访问和卓越的协作”该公司将新的网络客户端称为“最受欢迎的功能之一”，并解释说，在网络上不仅可以让用户更容易登录，还可以进行深度链接和“从浏览器可扩展地发送 API 请求”《邮递员》的[网页版现已推出。](https://cts.businesswire.com/ct/CT?id=smartlink&url=https%3A%2F%2Fgo.postman.co%2Fbuild&esheet=52277736&newsitemid=20200902005256&lan=en-US&anchor=HERE&index=3&md5=76ba98f2556236f321ac61ce744c7579)
*   **谷歌总结了“Android 11 周”:**谷歌没有为 Android 11 的发布举行大型发布会，而是发布了过去 11 周的每周系列，本周是[的高潮](https://android-developers.googleblog.com/2020/08/11-weeks-of-android-thats-wrap.html?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+blogspot%2FhsDu+%28Android+Developers+Blog%29)。你猜对了，这个系列讨论了与 Android 11 相关的 11 个独立领域，包括许多特定于开发人员的主题，如编程语言、Android Jetpack、机器学习等等。本周的博客文章提供了一个很好的总结，为你指出每个主题的资源，并指出一个所有相关视频的播放列表。总之，对于有抱负和有经验的 Android 开发人员来说，这是一个很好的书签。

*   **在 Android 上共享 Kotlin 逻辑& iOS:** JetBrains 发布了 [Kotlin 多平台移动 SDK](https://blog.jetbrains.com/kotlin/2020/08/kotlin-multiplatform-mobile-goes-alpha/) 的 alpha 版本，允许用户在 iOS 和 Android 应用程序中使用相同的业务逻辑代码，以及 Android Studio 的[插件。当然，Kotlin 已经有了](https://plugins.jetbrains.com/plugin/14936-kotlin-multiplatform-mobile)[多平台能力](https://kotlinlang.org/docs/reference/multiplatform.html)，以及各种工具和特性，但是 KMM 允许你保留原生编程的好处，只写特定于平台的代码,“只有在必要的时候，实现原生 UI 或使用特定于平台的 API 时”核心业务逻辑代码用 Kotlin/JVM 编译成 JVM 字节码，用 Kotlin/Native 编译成本机二进制代码，这意味着 KMM 业务逻辑模块可以像任何其他常规移动库一样使用。要开始，请访问 [KMM 开发者门户](https://kotlinlang.org/lp/mobile/)，查看[文档](https://kotlinlang.org/docs/mobile/)或阅读[教程](https://kotlinlang.org/docs/mobile/getting-started.html)。
*   **站在开源大师的肩膀上:**我记得在大学里遇到其他有抱负的作家，他们不想阅读，因为害怕被无意中感染，也没有任何理由声称他们只是抄袭某某作者。这是一个我从未赞同过的观点，也是我在编程界更不赞同的观点。依我看，你应该读一读你的前辈，这样你也许能迈出下一步。这是几本研究开源应用架构的书背后的思路。“大多数软件开发人员只熟悉少数大型程序——通常是他们自己编写的程序——而从未研究过历史上的伟大程序，”这本书的介绍中写道。“因此，他们重复彼此的错误，而不是在彼此的成功基础上再接再厉。我们的目标是改变这种状况。”这些书包含了近 50 个开源项目结构背后的故事，由这些项目的作者自己编写，并提供了一瞥为什么这么多项目背后我们可能认为是理所当然的。

*   **亚马逊推出以容器为中心的 Linux 发行版 Bottlerocket:** 亚马逊已经[发布了](https://aws.amazon.com/blogs/opensource/announcing-the-general-availability-of-bottlerocket-an-open-source-linux-distribution-purpose-built-to-run-containers/)一款名为 [Bottlerocket](https://github.com/bottlerocket-os) 的开源 Linux 发行版，该发行版完全是为了运行容器而设计的，提高了安全性、操作性和可管理性。为了安全，Bottlerocket 使用安全性增强的 Linux (SELinux)来帮助隔离工作负载，并通过只包含绝对必要的内容来减少攻击面。他们还注意到大部分是用 Rust 编写的，Rust 以其内存安全性而闻名(与 C++以内存不安全而闻名相反)。在操作和可管理性方面，Bottlerocket 提供了一个 [API](https://github.com/bottlerocket-os/bottlerocket#api) ，专门用于运行容器，这意味着更新更少，出错更少，自动化更多。“对 Bottlerocket 的更新，”他们解释说，“可以以原子的方式应用和回滚，这使得它们易于自动化，减少了管理开销和运营成本。”AWS 提供的 Bottlerocket 构建可以与[亚马逊 EKS](https://aws.amazon.com/eks/) 和[亚马逊 ECS](https://aws.amazon.com/ecs/) 一起开箱即用，核心项目旨在与其他容器编排器一起工作。
*   **Rust 中的 Linux 内核开发一瞥:**让 Rust 社区的人兴奋的是，最近几个月[已经有一些](https://lwn.net/ml/linux-kernel/CAKwvOdmuYc8rW_H4aQG4DsJzho=F+djd68fp7mzmBp3-wY--Uw@mail.gmail.com/)[表示开放](https://www.theregister.com/2020/06/30/hard_to_find_linux_maintainers_says_torvalds/)在 Linux 内核开发中使用这种语言，作为 C 的替代语言。本周，LWN 的另一篇帖子着眼于在 Rust 中支持 Linux 内核开发的[，这一次提供了一些更具体的例子来说明这可能会是什么样子。这个话题最近在一个受欢迎的虚拟小组中被讨论，作为](https://lwn.net/SubscriberLink/829858/281103f9c6fd0dc2/) [2020 Linux 水管工会议](https://www.linuxplumbersconf.org/blog/2020/)的一部分，演讲者声明他们“并不是提议将 Linux 内核重写为 Rust 他们只关注于迈向一个新代码可以用 Rust 编写的世界，并指出“Rust 支持的三个潜在关注领域:利用内核中现有的 API，架构支持，以及 Rust 和 c 之间的 ABI 兼容性问题。”

GitLab 是新堆栈的赞助商。

由 [Zac Cain](https://unsplash.com/@zaccain?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/s/photos/barbeque?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>