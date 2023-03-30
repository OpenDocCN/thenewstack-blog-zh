# 本周编程:谷歌解决开源共享的悲剧

> 原文：<https://thenewstack.io/this-week-in-programming-google-tackles-the-tragedy-of-the-open-source-commons/>

作为其参与最近宣布的开源安全基金会[的一部分，谷歌已经写了一篇博客文章，概述了它作为该组织的一部分将采取的第一步，试图在](https://thenewstack.io/the-open-source-security-foundation-looks-to-unite-and-conquer/)[找到关键的开源项目](https://opensource.googleblog.com/2020/12/finding-critical-open-source-projects.html)。

他们写道:“开源软件(OSS)长期以来一直遭受‘公地悲剧’问题的困扰。”。“大多数组织，无论大小，每天都在利用开源软件来构建现代产品，但许多 OSS 项目都在为所需的时间、资源和关注而挣扎。”

因此，作为解决这个问题的一种方式，并帮助资助那些需要资金的项目，谷歌发布了[关键程度评分](https://github.com/ossf/criticality_score)项目。该项目给项目一个关键程度分数(0 到 1 之间的数字)，该分数是“从各种项目使用度量中得出的”，例如“项目的年龄、参与的个人贡献者和组织的数量、用户参与度(在新问题请求和更新方面)，以及使用提交提及对其依赖性的粗略估计。”如果您认为合适，您还可以从那里添加自己的指标。当然，就像任何要打分的事情一样，这是第一个有人认为适合吹毛求疵的地方。

关于这个主题的一个[黑客新闻线程](https://news.ycombinator.com/item?id=25381397)提供了一个易读的列表，列出了许多语言的十大项目，其他人也在那里找到了类似的错误。该项目的创建者之一 Abhishek Arya 指出，该项目仍处于初始阶段，欢迎对“任何我们可以使用的度量方法的想法”的反馈 Arya 还[指出](https://news.ycombinator.com/item?id=25386610)该项目目前仅限于对 GitHub 上托管的开源项目进行排名，但是“在不久的将来会扩展到我们的源代码控制系统。”

“虽然我们在这个问题上取得了一些进展，但我们还没有解决它，并渴望社区的帮助来完善这些指标，以确定关键的开源项目，”宣布该项目的博客帖子总结道。

哦，如果你碰巧，就像流行的 XKCD 漫画中提到的那样，是“内布拉斯加州的一个随机的人”,在过去的几十年里一直在吃力不讨好地维护这样一个关键项目，谷歌鼓励你[伸出手，直接请求一些帮助](https://github.com/ossf/wg-securing-critical-projects/blob/main/README.md#communications)。

## 本周的节目中

*   **GitHub 获得黑暗模式(和其他一些东西):**在本周的 GitHub Universe 上，GitHub 终于发布了公开测试版的黑暗模式，你可以[在你的设置](https://github.com/settings/appearance)中启用这一模式。除了黑暗模式，GitHub 本周发布了许多公告，所有这些都可以在这个[简明摘要](https://github.blog/2020-12-08-new-from-universe-2020-dark-mode-github-sponsors-for-companies-and-more/)中找到，更新并添加了许多功能。例如，GitHub 赞助商现在接受公司的付款，而不仅仅是个人，而且发布时有十几个公司赞助商注册。与此同时，GitHub Discussions 现在对所有公共存储库提供测试版，正如依赖性审查的测试版一样，pull request auto-merges 将于下周在公共存储库中作为公共测试版提供，在 Team 和 GitHub Enterprise Cloud plans 上作为私有存储库提供。然后，本月晚些时候，GitHub Actions 将获得许多新功能，包括受保护的环境和必需的审查者，这增加了一个步骤，即尝试部署到环境的作业会自动暂停，并通知审查者。这将在 GitHub Enterprise Cloud 上的私有存储库和所有公共存储库的测试版中提供。同样，工作流可视化、部署和部署日志将在 GitHub 上面向所有人进入公测。最后，GitHub 推出了[GitHub Enterprise Server 3.0](https://enterprise.github.com/releases)，将于 12 月 16 日推出，并“通过 GitHub 动作和包为平台带来内置的 CI/CD 和自动化功能”，同时增加了对 [GitHub for mobile](https://github.com/mobile) 的支持。
*   Mirantis 将接管 Dockershim 的支持: Mirantis 公司去年收购了 Docker 的大部分股份，该公司表示将[接管 Kubernetes dockershim 的支持](https://www.mirantis.com/blog/mirantis-to-take-over-support-of-kubernetes-dockershim-2/)，并写道“dockershim 的消亡的谣言被大大夸大了。”你可能还记得，我们[上周](https://thenewstack.io/this-week-in-programming-kubernetes-says-dont-panic-about-docker-deprecation/)报道了这个话题，从那以后几乎没有什么变化，除了“Mirantis 和 Docker 已经同意合作，在 Kubernetes 之外独立维护 shim 代码，作为 Docker 引擎 API 的一个兼容的 CRI 接口。”这意味着 Mirantis 容器运行时(MCR)将符合 CRI，并且[可以作为开源](https://github.com/Mirantis/cri-dockerd)使用。他们指出，正如在许多论坛上指出的那样，“对大多数人来说，dockershim 的贬值不是问题。”对于其他人来说，“只需要一个小的配置变化”，他们会提供。

*   **Docker Engine 增加 Cgroups V2 支持，Docker Desktop 3 到来:**[最新版本的 Docker Engine](https://www.docker.com/blog/introducing-docker-engine-20-10/) 增加了几个新功能，包括对 [cgroups V2](https://thenewstack.io/linux-cgroups-v2-brings-rootless-containers-superior-memory-management/) 的支持，对 API、客户端和构建体验的改进，以及将多个功能移出实验性的。Cgroups 和名称空间是容器的 Linux 核心，cgroups 的 V2 于 2016 年问世，改变了组的管理方式，并增加了对无根容器施加资源限制的支持。随着 runc 容器运行时对 V2 的支持，Docker 也增加了支持，该公司指出，“这一变化反过来允许 Docker 从实验性的无根功能升级为完全支持的功能。”要了解更多细节，请查看[博客文章](https://www.docker.com/blog/introducing-docker-engine-20-10/)，并前往[变更日志](https://docs.docker.com/engine/release-notes/)了解 Docker 引擎 20.20 带来的所有变更。当我们谈论 Docker 时， [Docker Desktop 3.0 已经到来](https://www.docker.com/blog/docker-desktop-3-0-0-smaller-faster-releases/)，这一次更新应该会花费你更少的时间，因为更新只是添加到以前的版本中，而不是作为一个完整的安装程序。与此同时，Docker 正在摆脱其稳定和边缘渠道，将一切纳入一个流。如果您仍然有兴趣提前获得这些预览功能，可以看看加入 Docker 开发者预览计划的[。](https://www.docker.com/blog/expanding-dockers-developer-preview-program/)
*   Rust 举办了一场“基金会对话”:在今年早些时候的[公告](https://blog.rust-lang.org/2020/08/18/laying-the-foundation-for-rusts-future.html)的基础上，在 Mozilla 重组并解雇了许多从事该语言工作的员工后，Rust 团队在过去的一周举办了被称为[的基金会对话](https://blog.rust-lang.org/2020/12/07/the-foundation-conversation.html)。对话是以一系列问答和直播的形式进行的，同时还互动创建了一个 Rust Foundation FAQ。顺便说一下，这是上述常见问题解答中的第一个答案之一——该基金会将被称为“Rust 基金会”，该团队表示，它的成立是因为他们“根本没有找到一个我们认为与我们的社区目标一致的组织。”至于为这样一个基金会提供资金，他们说下个月会有这方面的消息。如果你对创建 Rust 基金会有想法，团队也会要求你填写[一份主题为](https://docs.google.com/forms/d/e/1FAIpQLSeciTU1hLi-Y5842fvWC2lhYRHvkWOtPbk39p72amGcGmZIaA/viewform)的调查。当你读到这篇文章的时候，对大多数问答环节来说已经太晚了，但是有些会在 YouTube 频道上看到。

[https://www.youtube.com/embed/OmEcRWyT6Ak?feature=oembed](https://www.youtube.com/embed/OmEcRWyT6Ak?feature=oembed)

视频

*   Kotlin 修改其文档:Kotlin 背后的公司 JetBrains 说，它正在[修改 kot Lin 文档](https://blog.jetbrains.com/kotlin/2020/12/revamped-kotlin-documentation/)，它希望你能试一试。新的文档将是移动友好的，有更好的导航和结构，以及最重要的黑暗模式。和其他事情一样，他们希望你的[对新的](https://blog.jetbrains.com/kotlin/2020/12/revamped-kotlin-documentation/#share-your-feedback)[改进文档](https://blog.jetbrains.com/kotlin/2020/12/revamped-kotlin-documentation/#view-new-documentation)的反馈，你可以在这里打开。要查看旧格式，你需要在另一个浏览器或匿名窗口中进入[常用链接](https://kotlinlang.org/docs/reference/)，以避开将你的偏好设置为新版本的 cookie。如果你愿意，你也可以恢复到旧文档。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>