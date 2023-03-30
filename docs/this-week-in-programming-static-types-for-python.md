# 本周编程:Python 的静态类型？

> 原文：<https://thenewstack.io/this-week-in-programming-static-types-for-python/>

对于那些既喜欢数字又喜欢 Python 编程语言的人来说——鉴于 Python 对数据处理等的偏好，维恩图相当接近于另一个圆中的一个圆——这是令人兴奋的一周，因为 2020 年 Python 开发者调查的[结果刚刚发布。](https://www.jetbrains.com/lp/python-developers-survey-2020/)

由 [JetBrains](https://www.jetbrains.com/) 和 [Python 软件基金会](https://www.python.org/psf/)在去年 10 月进行的调查收集了来自近 200 个国家和地区的 28，000 多名 Python 开发者的真实意见和习惯，现在你可以发现你的特定 Python 编程习惯到底有多不正常。

一些你可能一点都不惊讶的统计数据包括 Python 开发人员倾向于将该语言与 JavaScript 结合使用(根据结果，75%的 web 开发人员使用这两种语言)，数据分析、web 开发和机器学习是该语言最常见的三个用例。

根据 InfoWorld 上的一份[结果概要，调查的另一个明显收获是用户希望看到这种语言的下一步走向:“Python 开发人员最想要的特性是静态类型和严格类型提示，紧随其后的是性能改进，”他们写道，并指出结果显示了领先选择之间的密切联系。“静态类型和严格的类型提示被证明是最受欢迎的功能，有 21%的受访者表示，紧随其后的是性能改进，有 20%的受访者表示。更好的并发性和并行性排在第三位，15%的人表示这是他们最想要的功能。”](https://www.infoworld.com/article/3609589/python-developers-want-static-typing.html)

当然，没有什么是 100%的，也不是所有人都同意他们最喜欢的语言的下一步应该是什么。

同样值得注意的是，看起来人们终于明白了关于 Python 2 的信息(您肯定知道，Python 2 已经在一年多前寿终正寝了)，仍然使用现已死亡版本的用户比例已经从一年前的 10%下降到了 6%。现在是时候了！

不过这只是冰山一角，所以请点击所有漂亮的图表，看看 Python 世界有什么新的变化。

## 本周的节目中

*   **GitLab 13.9 增加了安全仪表板，维护模式:**git lab 的最新版本[已经](https://about.gitlab.com/?utm_content=inline-mention)发布，在 60 多项新功能中， [GitLab 13.9](https://about.gitlab.com/releases/2021/02/22/gitlab-13-9-released/) 打算“大规模加强开发人员”，用[安全警报仪表板](https://about.gitlab.com/releases/2021/02/22/gitlab-13-9-released/#security-alert-dashboard-for-container-network-policy-alerts)来筛选高优先级警报，[维护模式](https://about.gitlab.com/releases/2021/02/22/gitlab-13-9-released/#maintenance-mode)支持分布式团队，额外支持 [DORA 指标](https://gitlab.com/groups/gitlab-org/-/epics/4358)，以及高级自动化功能新版本的另一个功能是[关注其他 GitLab 用户](https://about.gitlab.com/releases/2021/02/22/gitlab-13-9-released/#follow-user-activity)的能力，这是该版本中包含的 [299 个合并的更广泛的社区贡献](https://gitlab.biterg.io/goto/937475d38035f496df3501c9b30af5ef)，所以请确保点击查看相当长的[发行说明](https://about.gitlab.com/releases/2021/02/22/gitlab-13-9-released/)。
*   **GitLab 的 Kubernetes 集成进入“新时代”:**当我们谈论 GitLab 时，该公司上周发布了另一则公告，这似乎特别适用于我们的读者，围绕[Kubernetes 集成的新时代](https://about.gitlab.com/blog/2021/02/22/gitlab-kubernetes-agent-on-gitlab-com/)。GitLab 之前在去年 9 月推出了 [GitLab Kubernetes 代理](https://docs.gitlab.com/ee/user/clusters/agent/)，现在可以在 GitLab.com 和 SaaS 的 GitLab 上使用，最近对代理进行了一些修改，以提供更好的安全模型。以前，GitLab 使用集群管理权限通过 Kube API 连接到 Kubernetes。现在，GitLab Kubernetes 代理使用 websockets 或 gRPC 提供了一个安全、永久的连接，让最终用户对访问进行更精细的控制。目前，该代理仅面向选定的客户，但是如果您想尝试一下，请联系负责该代理的产品经理 [Viktor Nagy](https://about.gitlab.com/company/team/#nagyv-gitlab) 请求访问。

[https://www.youtube.com/embed/17O_ARVaRGo?feature=oembed](https://www.youtube.com/embed/17O_ARVaRGo?feature=oembed)

视频

*   **Red Hat 向开源组织开放 RHEL:**继去年[弃用 CentOS 而支持流媒体版本](https://thenewstack.io/red-hat-deprecates-linux-centos-in-favor-of-a-streaming-edition/)之后， [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 本周表示将[向开源组织扩展免费的 Red Hat Enterprise Linux(RHEL)](https://www.redhat.com/en/blog/extending-no-cost-red-hat-enterprise-linux-open-source-organizations)。随着 RHEL 开源基础设施的引入，该公司表示，它正在为“项目、社区、标准机构和其他参与开源的非营利软件团体提供一个更简单、更清晰和有记录的过程，以获得 RHEL 订阅。”本质上，虽然该公司已经为某些开源组织提供了免费访问 RHEL 的机会，但他们说“这个过程并不像我们希望的那样正式、一致、可访问或透明”，这似乎可以解决这个问题。开源基础设施 RHEL 将向“合格的组织”提供免费订阅，供“在其基础设施范围内”使用，并且将是自我支持的。至于谁有资格，他们写道“一般来说，所有在 Fedora 批准的许可下分发的软件都被认为是用于本计划目的的开源软件”，并且它“不适合于希望在独立开源项目基础设施之外使用 RHEL 的个人开发者、当前的 Red Hat 客户/合作伙伴、政府组织、医疗保健组织、学术机构或非盈利组织。”
*   根据 Go 安全团队成员 [Katie Hockman](https://github.com/katiehockman) 提交的提案[和基于 Go 社区反馈的](https://golang.org/s/draft-fuzzing-design)设计草案，Go 编程语言[似乎即将在 Go 1.17](https://github.com/golang/go/issues/44551) 中加入模糊测试支持。“这项功能在 Go 1.17 中将被视为实验性的，该 API 还不会被 Go 1 兼容性承诺所涵盖，”Hockman 写道。此版本中加入的功能预计会有错误和缺失功能，但应作为概念验证，Go 开发人员可以对此进行试验并提供反馈说到反馈，该提案仍在开发和讨论中，所以如果您有想法，现在是时候加入进来了。

*   **Google 发布 Jetpack Compose Beta:** 对于 Android 开发人员来说，Google 本周发布了一些令人兴奋的消息，发布了 [Jetpack Compose Beta](https://developer.android.com/jetpack/compose) 的[版本](https://android-developers.googleblog.com/2021/02/announcing-jetpack-compose-beta.html)，这是一个 UI 工具包，旨在通过声明性 Kotlin APIs 在所有 Android 平台上构建本机应用程序，并与现有的 Android 应用程序和 Jetpack 库集成。该版本提供了一个 API 完整且稳定的 Compose 版本，这意味着您可以在今年晚些时候发布 1.0 版本之前开始使用 Compose 进行构建。测试版引入的新功能包括协程支持、对讲的可访问性支持和易于使用的动画，而 Compose 测试版由最新的 Android Studio 北极狐的金丝雀支持，它也有一些新工具。与此同时，JetBrains 还在本周宣布了[Jetpack Compose for Desktop:Milestone 3](https://blog.jetbrains.com/kotlin/2021/02/jetpack-compose-for-desktop-milestone-3-released/)，因此有很多新闻值得关注。
*   **TypeScript 4.2:** 随着 [TypeScript 4.2](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2/) 的发布，微软的静态类型 JavaScript 超集的最新版本已经在本周到来，增加了[更智能的类型别名保留](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2/#smarter-type-alias-preservation)、[tuple 类型中的前导/中间 rest 元素](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2/#non-trailing-rests)、[对“in”操作符](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2/#stricter-in-checks)更严格的检查，以及其他变化。SDTimes 提供了新功能的简要总结，并指出“TypeScript 团队也已经在开发 4.3 版本，预计将于 3 月 30 日发布第一个测试版，5 月 25 日发布最终版。”

由 [Nick Hillier](https://unsplash.com/@nhillier?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/s/photos/numbers?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>