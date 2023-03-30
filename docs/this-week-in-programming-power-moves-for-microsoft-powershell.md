# 本周编程:微软 PowerShell 的权力转移

> 原文：<https://thenewstack.io/this-week-in-programming-power-moves-for-microsoft-powershell/>

天哪，自从美国政府起诉微软违反联邦反垄断法以来，近 21 年来我们已经走了多远。尽管人们对微软当时的受欢迎程度有不同的估计，但许多迹象再次表明，这个软件巨头正在发生变化。

是什么给这家有时被冠以“微软(Micro$oft)”或其他不适合礼貌发表的贬义词的公司带来了这种善意？一个因素可能是它正在采用开源原则。

当微软去年收购 GitHub 时，并不缺乏警惕，然而与此同时,[有些希望,](https://thenewstack.io/this-week-in-programming-it-couldve-been-way-worse/)这是该公司真正采用开源思想的更大努力的一部分。

现在，头条新闻经常告诉我们微软开源旧代码库，例如去年秋天发布的 [MS-DOS 源代码](https://opensource.com/article/18/10/microsoft-open-source-old-versions-ms-dos)或超过 60，000 项专利的[开源](https://www.forbes.com/sites/jasonevangelho/2018/10/11/microsoft-just-open-sourced-60000-patents-proving-it-really-does-love-linux/#3f51bca63807)。就在本周，开发人员正为另一个奇怪代码的开源而欢欣鼓舞，那就是 Windows 计算器。

据[微软博客文章](https://blogs.windows.com/buildingapps/2019/03/06/announcing-the-open-sourcing-of-windows-calculator/)称，该代码[在麻省理工学院许可下可在 GitHub](https://github.com/Microsoft/calculator) 上获得，包括源代码、构建系统、单元测试和产品路线图，使开发人员能够“了解计算器应用程序的不同部分如何工作，轻松地将计算器逻辑或 UI 集成到您自己的应用程序中，或者直接为 Windows 中提供的东西做出贡献。”

除此之外，该公司表示，这也是“了解最新微软技术的一个很好的方式，比如通用 Windows 平台、XAML 和 Azure Pipelines”，以及“从微软的整个开发生命周期中学习”

同时,《应用开发趋势》杂志为我们带来了在微软的开放时代 PowerShell 的使用是如何增长的故事。微软的 PowerShell 是一个命令行外壳和相关的脚本语言，用于任务自动化和配置管理框架。

他们写道:“微软拥抱开放性和互操作性的一个副产品可能是 PowerShell 的受欢迎程度的提高，PowerShell 是该公司古老的脚本语言。”“这是 [TIOBE 指数](https://www.tiobe.com/tiobe-index/)的结论，除了 PowerShell 在 3 月份的新报告中重新进入前 50 名之外，该指数在每月的编程语言流行度指标中没有发现什么值得注意的重要信息。”

文章接着引用了 TIOBE 的报告，该报告认为微软不断转向开源是这背后最可能的原因。

“PowerShell 脚本语言已经有超过 12 年的历史了，而且它以前一直排在前 50 名，”该报告称。PowerShell 通常用于基本的脚本编写。直到最近，它只适用于 Windows，但微软使用其。NET 核心平台打造 [PowerShell 核心](https://redmondmag.com/articles/2018/09/14/microsoft-releases-powershell-core-6-1.aspx)。这个版本是开源的，可以在所有主流平台上运行。这可能是 PowerShell 再次变得更受欢迎的原因。”

你不可能一直取悦所有人，对吧？

## 本周的节目中

*   **可移植 API 到达 Go 云开发套件:**[Go 云开发套件](https://gocloud.dev/) (CDK)于去年 7 月首次[推出](https://blog.golang.org/go-cloud)，现在 Go 团队带来了关于[项目的更新](https://blog.golang.org/gcdk-whats-new-in-march-2019)，该项目以前被称为“Go Cloud”，提供“库和工具来改善使用 Go 开发云的体验”特色更新包括“一套通用云服务的可移植 API”，允许开发人员编写应用程序，部署在“任何提供商的组合上，包括 AWS、GCP、Azure、内部部署或测试用的单台开发人员机器上。”CDK 提供了一次编写、随处运行的体验，并推出了一组 API，包括用于 blob 数据持久性的 [blob](https://godoc.org/gocloud.dev/blob) 、用于发布/订阅主题消息的 [pubsub](https://godoc.org/gocloud.dev/pubsub) 、用于查看外部配置变量的 [runtimevar](https://godoc.org/gocloud.dev/runtimevar) 、用于加密/解密的 [secrets](https://godoc.org/gocloud.dev/secrets) 、用于连接到云 SQL 提供者的助手，以及即将推出的文档存储 API。更多详情，请查看 [godoc](https://godoc.org/gocloud.dev) 和[教程](https://github.com/google/go-cloud/tree/master/samples/tutorial)。

*   **一个狂野的 TensorFlow 2.0 Alpha 出现:**我们前阵子听说 TensorFlow 2.0 正在路上，现在 ProgrammableWeb 报道 [TensorFlow 2.0 现已在 Alpha 预览版中可用](https://www.programmableweb.com/news/tensorflow-20-now-available-alpha-preview/brief/2019/03/07)。本周在 [TensorFlow Dev Summit 2019](https://www.tensorflow.org/dev-summit) 上公布了预览版，TensorFlow 团队表示，“TensorFlow 2.0 专注于简单易用，具有渴望执行、直观的高级 API 和在任何平台上灵活构建模型等更新。”以免你怀疑该平台的受欢迎程度，ProgrammableWeb 报道说，“该团队透露，该平台自推出以来已被下载超过 4100 万次，在全球范围内有超过 1800 名贡献者。”根据 SDTimes 的说法，新版本将[将人工智能功能扩展到移动，物联网和 JavaScript](https://sdtimes.com/ai/tensorflow-to-expand-ai-capabilities-into-mobile-iot-javascript/) ，alpha 预览版专注于“更多地让库及其 API 更容易使用，无论你是创建机器学习模型的专家还是初学者。”他们写道，“TensorFlow 最大的变化是它的热切执行和@tf.function。其他功能包括 Python 控制流、遗留代码的优化和改进的错误消息传递。”

[https://www.youtube.com/embed/kPweUtct2yY?feature=oembed](https://www.youtube.com/embed/kPweUtct2yY?feature=oembed)

视频

*   **谷歌的本地人工智能平台 Coral:** 接下来，我们本周会听到一些来自谷歌的新闻，首先是他们对 Coral 的[介绍，Coral 是其“用于构建本地人工智能智能设备的平台”。根据该公司的公告，](http://developers.googleblog.com/2019/03/introducing-coral-our-platform-for.html) [Coral](https://coral.withgoogle.com/) 正在进入公开测试，以提供“本地人工智能工具包，使你的想法从原型到生产变得容易”，其中包括“硬件组件、软件工具和内容，帮助你在你的设备上本地创建、训练和运行神经网络(NNs)。”这些工具可以与[谷歌云物联网](https://cloud.google.com/solutions/iot/)一起使用，谷歌提供[产品文档、数据表和样本代码](https://g.co/coral) e。

*   **谷歌开源 GPipe:** 谷歌[也开源了](http://ai.googleblog.com/2019/03/introducing-gpipe-open-source-library.html)其 [GPipe](https://ai.googleblog.com/2019/03/introducing-gpipe-open-source-library.html) ，一个用于高效训练大型深度神经网络的库。根据 [VentureBeat 文章](https://venturebeat.com/2019/03/04/google-open-sources-gpipe-a-library-for-efficiently-training-deep-neural-networks/)的说法，该库提供了“在 Lingvo(一种用于序列建模的 [TensorFlow](https://venturebeat.com/2018/03/30/googles-tensorflow-ai-framework-adds-swift-and-javascript-support/) 框架)下”训练深度神经网络的能力，并且它“适用于任何由多个顺序层组成的网络。”

*   **Android Jetpack WorkManager 变得稳定:**最后一个谷歌开发者新闻本周，该公司[发布了](http://android-developers.googleblog.com/2019/03/android-jetpack-workmanager-stable.html)Android Jetpack work manager[1.0 稳定版，解决了 Android 开发者面临的最大问题之一——“以可靠且电池友好的方式进行后台处理。”谷歌表示，它对这些问题的答案来自于 WorkManager，它在谷歌 I/O 2018 上首次亮相，目标是让后台操作更容易处理。“WorkManager 考虑了电池优化、存储或网络可用性等限制，仅在满足适当条件时才运行其任务。它还知道何时重试或重新安排你的工作——即使你的设备或应用重启，”他们写道。像往常一样，查看完整的细节后。](https://developer.android.com/topic/libraries/architecture/workmanager)

[https://www.youtube.com/embed/pe_yqM16hPQ?feature=oembed](https://www.youtube.com/embed/pe_yqM16hPQ?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>