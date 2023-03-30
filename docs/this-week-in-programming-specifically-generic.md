# 本周编程:特别是泛型

> 原文：<https://thenewstack.io/this-week-in-programming-specifically-generic/>

上周，我们看了一些来自 Gophercon 2018 的[公告——Go 的最新版本，Go 2.0 的预览，以及现在从 vgo 诞生的实验模块系统。自从那次会议以来，一场新的辩论已经占据了 Go 社区，再次集中在“泛型”的主题上。](https://thenewstack.io/this-week-in-programming-gophers-dig-into-generics-go-2-0-and-gophercon-2018/)

在上周我看到的关于这个主题的各种博客文章中，我最喜欢的一篇文章尝试具体阐述泛型。这篇文章由谷歌工程师(不是 GoLang 团队成员)Emily Maier 撰写，深入探讨了这场争论的历史，并就围棋需要何去何从提出了一些想法。

“我们首先需要看到这样一个事实，术语‘泛型’本身就是泛型，呃，重载的([的两个难题](https://martinfowler.com/bliki/TwoHardThings.html)再次来袭)。Go 团队提出的(我认为应该由 Go 和任何实现“泛型”的未来语言实现的)是[有界参数多态性](https://en.wikipedia.org/wiki/Bounded_quantification)。可悲的是，它有两个错误的朋友，代码模板化和隐式装箱，它们也被称为“泛型”，分别在 C++和 Java 中实现。Maier 写道:“当人们谈论泛型可能在 Go 中实现时，他们通常会将这两种语言视为灵感或嘲笑(主要是嘲笑)的来源，”然后深入讨论细节。

对于那些对这个话题模糊不清的人，这篇推文用半外行的术语快速描述了泛型的使用(以及围绕它们的争议):

在比较了各种细节之后，Maier 得出结论,“与那些导致编译性能或可用性问题的东西或者根本不提供任何泛型相比，提供太有限或根本没有边界支持的 Go 2 要好得多。人们越早停止编写自己的代码模板系统或转向功能更全面的语言，就越好。”

与此同时，DataDog 的开发者 Jason Moiron 提出了他自己对这个提议的看法。Moiron 写道，尽管他反对增加泛型，但“现有 Go 程序的某些方面会随着泛型的出现而得到改善，这是无可争议的”，并且“Go2 不太可能在没有泛型的情况下发布。”与迈尔相似，莫伊伦反对将合同作为达到目的的手段，他写道“合同的语言感觉太微妙了。”

如果你对这个主题的阅读仍然不满意，不要担心，你还可以深入研究 Go 贡献者和团队成员戴夫·切尼对这个主题的思考，或者罗杰·佩佩对 T2 修改设计的建议。

## 本周的节目中

*   **Python 的持久受欢迎程度达到顶峰:**用不那么押韵的措辞来说，Python 已经[首次进入 TIOBE 指数前三名](https://www.tiobe.com/tiobe-index/)。如果你不熟悉，TIOBE index 每月发布一次编程语言受欢迎程度的排名。所以，它有一定的寿命，几十年后，这是 Python 第一次达到如此受欢迎的程度。正如他们所写的，“这真的花了很长时间。在 20 世纪 90 年代初，它进入了图表。然后又过了 10 年才首次登上 TIOBE 指数 top 10。”因此，他们认为该语言易于学习、安装和部署，是其缓慢但稳定地上升到前三名的原因。与此同时，Julia，我们几周前曾将其视为 Python 或 R 的潜在替代者，在索引中从第 50 位跃升至第 39 位。
*   **Visual Studio Code 的 Python 扩展和更多:**继续 Python 培训，Visual Studio Code 于 2018 年 8 月发布了其对[新功能的总结，据称包括“大量重大更新”在这些重大更新中，有一个](https://code.visualstudio.com/updates/v1_27)[设置编辑器](https://code.visualstudio.com/updates/v1_27#_settings-editor)、[自定义菜单栏](https://code.visualstudio.com/updates/v1_27#_custom-title-bar-and-menus-on-windows-and-linux)、[面包屑改进](https://code.visualstudio.com/updates/v1_27#_breadcrumbs-improvements)，一个[新终端菜单](https://code.visualstudio.com/updates/v1_27#_new-terminal-menu)、[特定于平台的键盘快捷键](https://code.visualstudio.com/updates/v1_27#_platform-specific-keybindings)、[CSS @导入路径完成](https://code.visualstudio.com/updates/v1_27#_path-completion-for-css-imports)、 [JSON 条件评估](https://code.visualstudio.com/updates/v1_27#_json)，以及[内置加载脚本视图](https://code.visualstudio.com/updates/v1_27#_loaded-scripts-view-now-reusable)。然而，除此之外，微软还宣布了 Visual Studio 代码的 [Python 扩展的发布。根据 SDTimes 的说法，该版本“以微软的 Python 调试器 ptvsd 的 4.1.1 版本为特色”，微软声称这是“对调试器 3.0 版本的重大改进”，它“现在建立在开源项目 pydevd 的基础上，使用户能够利用其性能和对第三方库的支持。”这个版本的扩展引入了一些新功能，包括对 Logpoints 的支持，“允许开发人员在不停止代码执行的情况下添加打印语句”，以及“对 Microsoft Python 语言服务器预览版的一些改进，这是一个托管在 VS 代码上的 Python 分析引擎。”请务必查看微软的博客文章](https://sdtimes.com/msft/python-extension-for-visual-studio-code-now-available/)，了解改进的完整列表。
*   **Kotlin/Native 的主要和突破性变化:**在我们本周的 dot 发布中， [Kotlin/Native v0.9 在这里](https://blog.jetbrains.com/kotlin/2018/09/kotlinnative-v0-9-is-here/)并承诺对其编译器工具链、Gradle 插件和 IDE 插件进行一些“主要(和突破性)”的变化，尽管编号不同。根据公告，宣布的最重要的变化包括迁移到 Kotlin 1.3-M2，支持 Kotlin stdlib 和 C/Objective-C/Swift interop 层中的无符号类型，支持 kotlin.coroutines 的稳定版本，返工的并发原语和 kotlin.native 包。详情请查看[的博客文章](https://blog.jetbrains.com/kotlin/2018/09/kotlinnative-v0-9-is-here/)或 [GitHub 发布页面](https://github.com/JetBrains/kotlin-native/releases/tag/v0.9)。

https://twitter.com/mnot/status/1036784792547680256

*   **与 Linux 基金会一起学习区块链:**对于那些仍然看好整个区块链的人来说，[Linux 基金会推出了一门新的区块链课程](https://sdtimes.com/softwaredev/sd-times-news-digest-hasura-graphql-engine-pushers-beams-api-and-the-linux-foundations-blockchain-course/)—lfd 271—Hyperledger Fabric Fundamentals—现已开放注册。本课程将涵盖核心区块链概念和分布式分类帐技术，以及构成 Hyperledger Fabric 应用程序的架构和组件。该基金会指出，“区块链技术的采用正在快速增长——据 TechCrunch 报道，区块链的就业机会是当今劳动力市场上增长第二快的”，而且“超过 100，000 名学生”参加了基金会免费的 Hyperledger 入门课程，这使其在下一门课程和即将到来的认证中有所深入。
*   **谷歌宣布数据集搜索:**作为一名开发者，你可能之前就被告知，你的程序只和它的数据一样好。或者不是。不管是哪种情况，有大量的博客文章都是这么说的。本周，[谷歌宣布](https://www.blog.google/products/search/making-it-easier-discover-datasets/)其“[数据集搜索](https://g.co/datasetsearch)，这样科学家、数据记者、数据极客或其他任何人都可以[找到他们的工作和故事所需的数据](https://www.youtube.com/embed/uJ3bCRM-SMI)，或者只是为了满足他们的求知欲 TechCrunch 在声明中写道:“传统上，数据集广泛分布在各个研究网站、NASA 和美国国家海洋和大气管理局等机构，甚至 ProPublica 等数据驱动的出版物中。通过数据集搜索，谷歌旨在调整其谷歌学术搜索方案，以帮助数据极客和研究人员在单个搜索栏中筛选这些数据。”
*   **TomTom 宣布免费地图和移动 SDK:** 我们最近谈论了一下谷歌地图的定价，现在看起来一些地图竞争对手正在利用人们的不满采取行动。TomTom 本周宣布其移动 SDK 上的免费地图和交通地图，安卓和 iOS 都可以使用。该出版物还对时机进行了评论，称“虽然 TomTom 没有在舞台上或新闻稿中提到谷歌的举动，但很难想象谷歌的新定价方案与 TomTom 的决定无关。”与此同时，TechCrunch 称这一宣布是“该公司从消费设备制造商向软件公司全面转型的一部分。”
*   **代码库的成本:**最后，本周，我们自己的网页上有一个关于[甚至开放源代码者如何为代码库付费的故事](https://thenewstack.io/add-it-up-even-open-sourcers-pay-for-code-repositories/)。引用[由 New Stack 和 Linux 基金会进行的一项调查](https://thenewstack.io/survey-open-source-programs-are-a-best-practice-among-large-companies/)，这篇报道关注“一半的人说他们使用免费的、供应商提供的解决方案，比如 GitHub，但是 53%的人也为代码库软件或服务付费。”当然，当最近讨论这个话题时，总是会想起微软对 GitHub 的收购以及由此产生的对垄断的恐惧，作者写道，各种调查表明，“在不久的将来，微软几乎不可能主宰代码库市场。”

谷歌和微软是新堆栈的赞助商

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>