# 本周编程:谷歌的 Golang 向云进军

> 原文：<https://thenewstack.io/this-week-in-programming-googles-golang-heads-for-the-cloud/>

曾几何时，一提到云，更专业的人就会发出一声呻吟。在很长一段时间里，“云”并没有发挥其潜力，而是简单地“T0”了互联网的“T1”这是一个可互换的术语，用于表示非本地的文件和服务，无论它们是否真正符合云计算的原则，如快速供应、可伸缩性、冗余、多租户等。如果某些东西不是在本地安装和运行的，那么它就是“在云中”，因此是未来的趋势。

虽然许多东西仍然被云清洗，就像公司[绿色清洗](https://www.truthinadvertising.org/six-companies-accused-greenwashing/)他们原本对环境有害的产品一样，我们真的开始看到云的承诺正在实现。本周，谷歌举行了年度云大会， [Google Cloud Next](https://cloud.withgoogle.com/next18/) ，并发布了许多公告，旨在让开发者比以往任何时候都更容易利用云——从[无服务器](https://cloudplatform.googleblog.com/2018/07/bringing-the-best-of-serverless-to-you.html)到[持续集成和持续交付](https://cloudplatform.googleblog.com/2018/07/accelerating-software-teams-with-cloud-build.html)到[机器学习和人工智能](http://ai.googleblog.com/2018/07/machine-learning-in-google-bigquery.html)。

所以，这就是我们本周关注的焦点——谷歌上周宣布的一些最有趣的新开发者好东西。对于那些非谷歌开发者来说，我们还会看到一些其他的新闻。事不宜迟…

## 本周的节目中

*   Golang 走向云端:首先，关于你最喜欢的谷歌支持的开源语言 Go。谷歌[本周](https://blog.golang.org/go-cloud)宣布，它将“发布一个新的开源项目， [Go Cloud](https://github.com/google/go-cloud) ，一个用于在[开放云](https://cloud.google.com/open-cloud/)上开发的库和工具，“旨在让 Go 成为开发人员构建可移植云应用程序的首选语言。”正如 [Techcrunch 所解释的那样](https://techcrunch.com/2018/07/24/google-wants-go-to-become-the-go-to-language-for-writing-cloud-apps/)，“今天，开发人员通常不得不编写自己的库来使用每个云的功能，但今天的组织希望能够轻松地在云之间迁移他们的工作负载。Go Cloud 为这些开发人员提供了一套开放的通用云 API，用于访问博客存储、MySQL 数据库和运行时配置，以及一个内置日志记录、跟踪和健康检查的 HTTP 服务器。”Go Cloud 将推出对谷歌云平台和亚马逊网络服务的支持，并计划在不久的将来增加对其他提供商的支持。根据 Go Cloud 的 [GitHub repository，“该项目的一个关键部分是还提供一个名为](https://github.com/google/go-cloud) [Wire](https://github.com/google/go-cloud/blob/master/wire/README.md) 的代码生成器，它“创建人类可读的代码，只为您使用的提供商导入云 SDK”，从而允许 Go Cloud“支持任意数量的云提供商，而不增加编译时间或二进制文件大小，并避免 init()函数的任何副作用。”确保查看[样本/教程](https://github.com/google/go-cloud/tree/master/samples/tutorial)页面开始学习。
*   **谷歌提供云构建 CI/CD:**继续把一切都带到云的主题，谷歌[本周还宣布](https://techcrunch.com/2018/07/24/google-announces-cloud-build-its-new-continuous-integration-continuous-delivery-platform/)发布云构建，它的“完全管理的持续集成/持续交付(CI/CD)平台，让你可以快速、大规模地构建、测试和部署软件。”根据 Techcrunch 的说法，该服务“可以在各种环境中工作，包括虚拟机、无服务器、Kubernetes 或 Firebase”以及“支持 Docker 容器，它为开发人员或运营人员提供了以日益自动化的方式构建、测试和部署的灵活性。”该公司还与 [GitHub](https://blog.github.com/2018-07-26-simplify-your-ci-process/) 发表了一份联合声明——重申了其合作伙伴关系，尽管 GitHub 最近被微软收购——为 GitHub 提供云构建，并为 GitHub 上的任何存储库提供“快速、无摩擦和方便的持续集成(CI)，直接集成到 GitHub 开发人员的工作流程中。”GitHub 表示，它将自动“检测存储库根目录下的 docker 文件，并自动建议您使用 CI 工具，如 GitHub Marketplace 的 Cloud Build(云构建),如果尚未安装的话。”
*   **走向无服务器化:**谷歌本周还宣布，它将[为你带来无服务器化的最佳体验](https://cloudplatform.googleblog.com/2018/07/bringing-the-best-of-serverless-to-you.html)。随着[云服务平台](https://cloud.google.com/solutions/cloud-services-platform)的发布，“这是一款全新的产品，让您能够提高速度和可靠性，改善安全性和治理，并且只需构建一次，即可在 GCP 的任何地方和内部环境中运行”，该公司宣布了其无服务器计算堆栈的几项开发。其中包括新的应用引擎运行时，一个 GKE 的无服务器插件，以及在[谷歌云功能](https://cloud.google.com/functions/)中提供 Node.js 8 和 Python 3.7 运行时。总体而言，这些公告导致 SDTimes 写道，该公司正在进入“人工智能和云民主化的下一步”
*   **完整的谷歌云下一个摘要:**在我们离开谷歌之前，这里是这家[公司的摘要博客文章](https://www.blog.google/products/google-cloud/next18-recap/)，它提供了每天的亮点。当然，我们已经错过了一些东西或遗漏了一些东西，但从过去的一周开始，还有更多要讨论的！比如…
*   **…最终的 Android P 预览:**没错，来自谷歌的最后一点——Android P 的[最终预览更新于本周发布，公布了最终的系统行为和官方的 Android P API(API 等级 28)。这意味着是时候在正式发布之前进行测试了。](http://android-developers.googleblog.com/2018/07/final-preview-update-official-android-p.html)
*   **微软提供量子卡塔:**微软[宣布](https://cloudblogs.microsoft.com/quantum/2018/07/23/learn-at-your-own-pace-with-microsoft-quantum-katas/)本周推出一系列[量子卡塔](https://github.com/Microsoft/QuantumKatas)“面向那些希望探索量子计算并按照自己的节奏学习 Q#编程语言的人。”编程练习提供了“关于某个量子计算主题的一系列任务，从简单到具有挑战性”,可在 [GitHub](https://github.com/Microsoft/QuantumKatas) 上获得。安装微软[量子开发工具包](https://www.microsoft.com/en-us/quantum/development-kit)开始使用。
*   **GitHub 学习实验室新增四门课程:**继续学习，GitHub 本周还在 GitHub 学习实验室上公布了四门[新课程。课程涵盖了如何](https://blog.github.com/2018-07-24-new-learning-lab-courses/)[上传](https://lab.github.com/courses/uploading-your-project-to-github)和[迁移](https://lab.github.com/courses/migrating-your-repository-to-github)到 GitHub，如何[成为 GitHub 社区](https://lab.github.com/courses/community-starter-kit)的一员，以及一个关于 HTML 的[基础介绍。这让我想起了另一个本周出现在我博客上的学习趣闻:](https://lab.github.com/courses/introduction-to-html)

[https://www.youtube.com/embed/IHaTbJPdB-s?feature=oembed](https://www.youtube.com/embed/IHaTbJPdB-s?feature=oembed)

视频

*   **Twitter 的新开发者要求:**接下来，这篇来自 ProgrammableWeb 的文章概述了 Twitter 的[新开发者要求](https://www.programmableweb.com/news/twitter-unveils-new-developer-requirements/2018/07/24)，它说“可能会激怒一些开发者，并使[公司重建开发者信任的努力变得复杂](https://www.programmableweb.com/news/twitters-jack-dorsey-to-developers-were-sorry.-lets-start-over./2015/10/21)这些要求会影响开发人员请求和获取 Twitter API 的方式。首先，开发者需要使用该公司去年首次宣布的方法申请访问权，这要求他们“提供关于他们打算如何使用 Twitter 的 API 的详细信息”以进行评估。文章称，这些新规定还将限制应用程序“每 3 小时 300 条合并推文和转发，每 24 小时 1000 个赞和关注，以及每 24 小时 15000 条直接消息。”
*   微软的 Visual Studio IntelliCode 添加 Python: 终于，微软的人工智能助手 [Visual Studio IntelliCode](https://blogs.msdn.microsoft.com/visualstudio/2018/07/24/visual-studio-intellicode-expands-ai-assisted-coding-to-python-in-visual-studio-code/) 添加了对 Python 的支持，该公司本周宣布。当然，到现在为止，您已经厌倦了阅读，所以我为您提供了一个可爱的视频来展示 Intellicode 必须提供的所有功能:

谷歌和微软是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>