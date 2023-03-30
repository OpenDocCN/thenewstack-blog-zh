# 本周编程:GitHub 的路线图上没有什么

> 原文：<https://thenewstack.io/this-week-in-programming-whats-not-on-githubs-roadmap/>

GitHub [在过去的一周发布了一份公开路线图](https://github.blog/2020-07-28-announcing-the-github-public-roadmap/)，该公司表示，这份路线图“旨在为你的团队提供更多关于未来几个季度你可以从 GitHub 获得哪些特性和功能的信息”

[GitHub 公共路线图](https://github.com/github/roadmap)作为一个公共存储库提供，其中[是一个项目板](https://github.com/github/roadmap/projects/1)显示即将发布的版本及其当前版本，以及产品 SKU 和部署模型。所有功能还将被标记为特定的“功能区域”，如协作或安全，这样您可以更容易地进行筛选和搜索。

由于先睹为快，他们最常用的产品之一将走向何方，许多人开始仔细研究路线图，看看有哪些令人兴奋的新功能已经计划好，但尚未推出。虽然目前有 [54 个未来特性或版本](https://github.com/github/roadmap/issues?q=label%3Ashipped+)在路线图上，比如 [GitHub 讨论](https://github.com/github/roadmap/issues/104)、GitHub 代码空间的[全面可用](https://github.com/github/roadmap/issues/55)或[拉请求的自动合并](https://github.com/github/roadmap/issues/107)，但对于一些人来说，路线图上没有的东西比路线图上有什么更有趣。

自从该公司第一次因与美国移民和海关执法局(ICE)签订 20 万美元的合同而面临用户的强烈反对以来，已经过去了近一年时间，简要浏览一下 Twitter 上对 GitHub 路线图的回应可以看出，许多人仍然关注这个问题。当然，这种事情不会包括在产品路线图中，它只是提供了一个借口，在许多人看来，这是一个明显的违反道德的行为。

与此同时，其他人指出，缺乏对 IPv6 的支持是当前路线图中缺失的一个关键技术特性。当然，需要说明的是，路线图仍处于早期阶段，GitHub 甚至承认“公开的路线图并不详尽”，该公司将继续通过“在重大活动中或偶尔在博客上发布前瞻性产品公告”来分享新功能的消息

在 IPv6 问题上，该公司没有立即做出回应。然而，路线图中缺少的另一个特性是任何开发者提供的总是被引用和期待已久的圣杯，黑暗模式。在这一点上，GitHub 首席执行官 Nat Friedman 花时间对[的缺席进行了评论，写道“黑暗模式即将到来。我们首先要做的基础工作是用更容易主题化的组件替换我们所有的定制 HTML 和 CSS。这还将帮助我们提高可访问性，并帮助我们用完全响应的用户界面取代我们的移动网站。”](https://news.ycombinator.com/item?id=23977950)

## 本周的节目中

*   **GitHub 转向令牌认证:**当我们在谈论 GitHub 的话题时，在继续之前还有几个花絮要提。首先，该公司将于 2020 年 11 月 13 日开始[要求对 API 和 Git 操作](https://github.blog/2020-07-30-token-authentication-requirements-for-api-and-git-operations/)进行基于令牌的认证，届时将对 REST API 和 GitHub.com 上所有经过认证的 API 操作进行认证。GitHub Enterprise Server 和 [GitHub Apps](https://docs.github.com/en/developers/apps/about-apps#about-github-apps) 不会受到这一变化的影响，但该公司还将要求“在未来的某一天”——可能是 2021 年年中的某个时候——对所有经过认证的 Git 操作使用个人访问令牌、OAuth 令牌或 SSH 密钥，他们写道。
*   **GitHub 的 OpenAPI 描述:**接下来，GitHub 已经[推出了其](https://github.blog/2020-07-27-introducing-githubs-openapi-description/) [GitHub REST API](https://developer.github.com/v3/) 的和 [OpenAPI 描述](https://github.com/github/rest-api-description)，它注意到该 API 在 12 年中“自首次发布以来，[仅在网站推出](https://github.blog/2008-03-12-the-api/)一个月后”就被修改了三次该描述本质上开放了对 API 的访问，而无需首先阅读文档或理解实现，该公司写道，该描述包含 600 多种操作，可以通过 [Postman 集合](https://www.postman.com/collection/)进行可视化探索，并且“可以用于为 [Octokit](https://github.com/octokit) 不支持的语言生成模拟服务器、测试套件和绑定。”买家请注意，该描述目前处于测试阶段。

*   **Git 迈出了超越“主”的一步:**最后，GitHub 提供了 Git 2.28 版本中的一些[亮点，它提供了一个新功能，向摆脱“从”和“主”的旧命名约定迈出了一步。现在，当您用 git init 初始化一个新的 Git 存储库时，您可以设置一个替代名称来替换“master”为了便于理解，软件自由保护协会上个月提供了一份关于该决定的声明，写道这一改变是“第一步”，该改变将成为目前正在讨论的默认设置。除了命名约定，Git2.28 还带来了更多的变化，这些变化在](https://github.blog/2020-07-27-highlights-from-git-2-28/)[公告邮件](https://lore.kernel.org/git/xmqq5za8hpir.fsf@gitster.c.googlers.com/)中有详细介绍。
*   **Python 将 Java 跃居第二:**一年两次的[red monk 编程语言排名](https://redmonk.com/sogrady/2020/07/27/language-rankings-6-20/)即将发布，尽管毫不奇怪，JavaScript 仍然占据第一的位置，但这一次的大新闻是 Python 已经超过 Java，占据第二的位置。实际上，他们写道 Python 根本没有移动，而是 Java 下降了一个位置，Python 成为“第一个单独进入这些排名前两位的非 Java 或 JavaScript 语言。”总的来说，他们说排名变化很小，但另一个值得注意的变化确实发生了，Rust 上升到前 20 名。

*   **跨平台 Windows 开发者获得一些帮助:**微软表示，它将发布一个新的开发者登陆页面[并发布报告](https://blogs.windows.com/windowsdeveloper/2020/07/28/new-developer-landing-page-and-issues-repo/)，首先关注那些“在 Linux 和 Android 等非微软操作系统上构建和部署应用和系统”的开发者[新的登录页面](https://docs.microsoft.com/en-us/windows/dev-environment/overview)旨在帮助这些特定的开发人员优化他们的环境设置和工作流程，提供有关如何设置和安装在 Windows 或 Windows Subsystem for Linux 上开发所需的语言和工具的指导和资源。至于[“WinDev”GitHub repo](https://github.com/microsoft/windev)，它旨在为 Windows 开发人员提供一个直接向 Windows 工程团队提交和讨论问题的地方，这些团队还没有自己的 repo，无论您发现的问题是与使用 Windows 本身有关，还是与在 Windows 上运行您的代码有关。
*   **Kotlin 1.4 候选版本带来了“重大的进化变化”:**[kot Lin 1 . 4 . 0 候选版本已经发布](https://blog.jetbrains.com/kotlin/2020/07/kotlin-1-4-rc-released/)，这一次描述了一个[特性版本](https://kotlinlang.org/docs/reference/evolution/kotlin-evolution.html#feature-releases-and-incremental-releases)，它具有“许多你已经从以前的博客帖子中了解到的新特性”和“现有 API 中的重大进化变化”值得注意的是，这意味着之前提供的几个带有实验性质警告的功能不会被转移到稳定版，不再要求用户选择加入。Kotlin 1.4 的一些突出特性包括[改进的*.gradle.kts IDE 支持](https://blog.jetbrains.com/kotlin/2020/07/kotlin-1-4-rc-released/#improved-gradle-kts-support)、[源集现在默认包含标准库依赖关系](https://blog.jetbrains.com/kotlin/2020/07/kotlin-1-4-rc-released/#stdlib-default)、[简化的 CocoaPods 依赖关系管理](https://blog.jetbrains.com/kotlin/2020/07/kotlin-1-4-rc-released/#kotlin-native)、[改进的 Kotlin/JS 集成](https://blog.jetbrains.com/kotlin/2020/07/kotlin-1-4-rc-released/#kotlin-js)、[node . JS API 绑定预览](https://blog.jetbrains.com/kotlin/2020/07/kotlin-1-4-rc-released/#kotlin-js-node)等等。

由[大卫·拉托雷·罗梅罗](https://unsplash.com/@latorware?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/wheels?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>