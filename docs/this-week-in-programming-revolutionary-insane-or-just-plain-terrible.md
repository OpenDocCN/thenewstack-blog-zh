# 本周编程:革命性的，疯狂的，还是简单的可怕？

> 原文：<https://thenewstack.io/this-week-in-programming-revolutionary-insane-or-just-plain-terrible/>

让我们以[本周开始一场关于 at /r/programming](https://www.reddit.com/r/programming/comments/901p0j/former_software_engineer_at_spotify_on_their/) 的讨论，这场讨论是由 Quora 的一个回答引发的，这个回答描述了 Spotify 的“[革命性(有点疯狂)的解决方案，即使用独立的 iframes 来增加团队自治](https://www.quora.com/How-is-JavaScript-used-within-the-Spotify-desktop-application-Is-it-packaged-up-and-run-locally-only-retrieving-the-assets-as-and-when-needed-What-JavaScript-VM-is-used)这个问题问的是 JavaScript 在 Spotify 桌面应用程序中是如何使用的，它如何处理检索各种资产，以及在需要时使用什么 VM。

据 Spotify 前软件工程师[马蒂亚斯·约翰松](https://twitter.com/mpjme)称，Spotify 并没有决定整个公司的统一框架，而是使用 iframes 来隔离主 Spotify 网络应用程序中的大量微型网络应用程序。该架构旨在使各个团队能够快速独立地工作。请继续阅读:

*“这种组织结构，结合浏览器中 JavaScript 的全球化特性，使我们能够从许多小型、独立的 web 应用程序(称为 Spotlets)中构建桌面客户端 UI。他们都运行在 Chromium 嵌入式框架中，每个应用程序都存在于自己的小 iframe 中，这使团队能够使用他们需要的任何框架，而不需要与其他团队协调工具和依赖关系，”Johansson 写道。“虽然这种方法的缺点是我们有许多不同版本库的重复实例，增加了应用程序的大小，但它提供了巨大的优势，即引入一个库是几个人之间的讨论，而不是涉及大约 100 个人及其各种需求的决策。这样的大讨论不仅非常费时费力，还会迫使我们使用最小公分母的方法来挑选库，而不是挑选专门针对每个小组的问题领域的库。”*

除了给予团队，呃，“小队”自主权之外，该方法还允许这些“小程序”独立于完整的应用程序升级而发布，而是实时部署到“用户的运行客户端”

现在，我认为这整个想法是一个新颖的，虽然有些臃肿，但能让许多有不同目标的团队更容易进行 web 开发的方法。为什么要花时间强迫每个团队使用相同的东西，而每个团队都可以发挥自己的优势呢？毕竟，Johansson 解释说,“虽然团队是自治的，但我们都希望分享一些功能，因为我们明确希望它在所有应用程序中以完全相同的方式工作。例如，我们有一个叫做 GLUE 的 CSS 框架。”所以，这并不是完全免费的，对吗？

然后我进入了 Reddit 的评论，从 [OP 的断言](https://www.reddit.com/r/programming/comments/901p0j/former_software_engineer_at_spotify_on_their/e2n2vn8/)这是一个“看起来疯狂/疯狂的聪明的解决方案】到[另一个](https://www.reddit.com/r/programming/comments/901p0j/former_software_engineer_at_spotify_on_their/e2ng1lj/)称这种方法是“一个粗暴和严重的解决方案”另一个人仍然声称这既不疯狂，也不聪明，也不是什么特别奇怪和新颖的东西，而是一种被称为[自包含系统(SCS)](https://scs-architecture.org/) 的方法，这是“一种专注于将功能分离成许多独立系统的架构，使完整的逻辑系统成为许多较小软件系统的协作。”SCS 网站列出了八个基本规则来管理这些应用程序应该如何设计，以确保一切正常工作，并帮助避免“不断增长并最终变得不可维护的大型整体问题”

最后，我发现自己在想——到底是哪个？这种方法是革命性的，疯狂的，还是非常可怕的？不管是什么，依我拙见，这也非常有趣。

## 本周的节目中

*   **微软的 Visual Studio IntelliCode 学习 C#惯例:**微软本周为我们带来了一些人工智能辅助编码方面的新闻，宣布 [Visual Studio IntelliCode 现在可以推断一致代码的编码惯例](https://blogs.msdn.microsoft.com/visualstudio/2018/07/17/visual-studio-intellicode-inferring-coding-conventions-for-consistent-code/)。如果你还记得的话，IntelliCode 最初是在几个月前的 Build 2018 上[宣布的](https://go.microsoft.com/fwlink/?linkid=872708)，现在 [IntelliCode 扩展](https://go.microsoft.com/fwlink/?linkid=872707)已经更新为 C#启用编码约定推断。简而言之，该扩展现在所做的是扫描您现有的代码，以了解您的约定，然后在您编写违反这些约定的代码时提醒您。在其声明中，微软提到了自己的一项研究来支持这一特性的实用性，声明“18%的拉式请求评审评论与编码约定、风格和命名问题有关。”要试用它，继续并[下载扩展](https://go.microsoft.com/fwlink/?linkid=872707)。
*   Google 让使用 Kubernetes 变得更加容易:对于那些记得使用 Cpanel 和安装 phpBBS 的 WordPress 之类的东西的人来说，Google 本周的声明可能听起来很熟悉——尽管有更多功能齐全的铃声和可扩展的哨声。该公司已经[在 GCP 市场](https://cloudplatform.googleblog.com/2018/07/introducing-commercial-kubernetes-applications-in-gcp-marketplace.html)推出了商业 Kubernetes 应用程序，这意味着你现在可以“在[谷歌云平台市场](https://console.cloud.google.com/marketplace/)(以前的 Cloud Launcher)找到你需要的解决方案，并快速部署在运行于[谷歌云平台](https://cloud.google.com/) (GCP)、Kubernetes 引擎、本地甚至其他公共云上的 Kubernetes 集群上。”这些应用程序包括 Gitlab、CloudBees、DataDog 等开发工具，“支持基于使用情况的许多参数计费(API 调用、主机数量、每月存储)，简化许可证使用，并为您提供更多消费选择。”(Gitlab 刚刚对此做了自己的公告，重点介绍了一键安装“[”的能力。)哦，如果你正在考虑加入，谷歌提供精选合作伙伴的免费试用，可以与他们的 300 美元注册积分结合使用。](https://about.gitlab.com/2018/07/18/install-gitlab-one-click-gcp-marketplace/)
*   **Amazon Translate 将其语言翻倍:**这里需要注意的是 [Amazon Translate](https://aws.amazon.com/translate/) 增加了对日语、俄语、意大利语、繁体中文、土耳其语和捷克语的支持[，使其支持的语言数量翻倍。亚马逊翻译是 2017 年首次发布的翻译 API，该公司计划在未来几个月内增加对丹麦语、荷兰语、芬兰语、希伯来语、波兰语和瑞典语的支持。目前，该功能在美国东部(北弗吉尼亚)、美国东部(俄亥俄州)、美国西部(俄勒冈州)、欧盟(爱尔兰)和](https://aws.amazon.com/blogs/aws/amazon-translate-adds-support-for-new-languages/) [AWS GovCloud(美国)](https://aws.amazon.com/govcloud-us/)提供。
*   **谷歌将搜索分析 API 请求增加了 5 倍:**另一个快速说明是，谷歌[更新了其搜索控制台搜索分析 API](https://www.programmableweb.com/news/google-updates-its-search-console-search-analytics-api/brief/2018/07/16) ，以“支持每个请求检索 25，000 行数据，高于之前每个请求 5，000 行的限制”，以及“增加每个请求可以返回的行数”，将 16 个月的数据添加到 API 中。如果你对此感兴趣的话，谷歌[有一个指南](https://developers.google.com/webmaster-tools/search-console-api-original/v3/searchanalytics)告诉你如何在不超过限额的情况下使用 API。
*   **Go 在 Go 1.11 中增加模块:**广受欢迎的谷歌支持的开源语言 Go 的下一个版本将在 Go 1.11 中获得模块。据 JaxEnter 上的报道，该版本预计将在下个月发布，并将为“模块”添加实验性支持。引用 Go Google Group 上的一个线程，以及 Heptio 的员工工程师 Dave Cheney 运行的一个[试验，这个故事解释说，模块将由主 repo 支持，并将使“在您喜欢的任何地方处理您的模块成为可能，而无需设置环境变量或遵循预定义的位置。”根据 Cheney 的说法，“有了 Go 1.11 和模块，你可以在任何你喜欢的地方编写你的 Go 模块，并且你不再被迫在你的$GOPATH 的特定子目录中签出一个项目的副本。”](https://dave.cheney.net/2018/07/14/taking-go-modules-for-a-spin)
*   **Python 的空王座:**正如我们上周[注意到的](https://thenewstack.io/this-week-in-programming-does-c-suck/)，Python 的“仁慈的终身独裁者”(BDFL)吉多·范·罗苏姆[宣布](https://mail.python.org/pipermail/python-committers/2018-July/005664.html)他将在一场关于采用 PEP (Python 增强提案)的特别有争议的辩论后，进行一次“永久休假”。在声明中，van Rossum 说他不会任命一个继任者，本周 JaxEnter 回顾了核心 Python 开发者之间的讨论，询问是否会有一个新的 BDFL(T16)或者民主是否是向前发展的最佳选择。目前在讨论桌上的选项包括走向“多数赢得投票”，独裁者 per PEP，执政长老三人组，或另一个独裁者，将做出所有唯一的选择。

谷歌和微软是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>