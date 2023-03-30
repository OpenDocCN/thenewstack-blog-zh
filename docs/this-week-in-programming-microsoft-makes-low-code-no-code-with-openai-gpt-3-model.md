# 本周编程:微软用 OpenAI GPT-3 模型制作低代码无代码

> 原文：<https://thenewstack.io/this-week-in-programming-microsoft-makes-low-code-no-code-with-openai-gpt-3-model/>

当心那些耸人听闻的标题，它们警告着我们所知道的编程工作的终结，因为它们远非事实。尽管如此，对于我们所有可能涉猎、可能认为自己是“[编程的家庭厨师](https://thenewstack.io/this-week-in-programming-what-kind-of-developer-are-you-anyway/)”的人来说，随着本周[微软 Build](https://mybuild.microsoft.com/) 开发者大会传出的消息，我们的生活将变得更加容易，该公司在会上宣布，[将利用 GPT-3 模型](https://blogs.microsoft.com/ai/from-conversation-to-code-microsoft-introduces-its-first-product-features-powered-by-gpt-3/)“帮助用户构建应用程序，而无需知道如何编写计算机代码或公式。”

这一消息建立在今年早些时候的另一项声明之上，当时[微软在微软 Ignite 上发布了其低代码 Power Fx 语言](https://thenewstack.io/this-week-in-programming-microsofts-power-fx-low-code-language/)。被微软称为“面向所有人的低代码编程语言”的 Power Fx ，本质上是一种开源的低代码公式语言，基于微软 Power 应用中使用的 Microsoft Excel。随着这个新特性的引入，低代码很快变成几乎没有代码。

现在，正如你在上面看到的，我们不是在谈论人工智能为你编写一个完整的应用程序，而是将自然语言查询翻译成数据库查询。微软提供的例子是将“查找名称以‘孩子’开头的产品”转换为“过滤(‘BC 订单’Left(‘产品名称’，4)=‘孩子’)”这些有希望成为开发人员的人现在可以用英语(这是启动时选择的语言)输入他们的查询，而不是依赖文档来找到正确的命令和语法，或者，让我们面对现实吧，Google 或 StackOverflow 来找到一段别人预先写好的代码到 CTRL-C 和 CTRL-V。

顺便说一下，微软选择的短语是“公民开发者”，他们解释说，所说的“公民开发者”仍然需要对使用新功能的逻辑有基本的理解。

“这些功能并不能取代人们理解他们正在实现的代码的需要，而是旨在帮助学习 Power Fx 编程语言的人们选择正确的公式来获得他们需要的结果。他们写道:“这可以极大地扩展更高级的应用程序构建，并更快速地培训人们使用低代码工具。

至于整个事情是如何工作的，GPT-3 是一个“完全运行在 Azure 上的巨大自然语言模型”，最初由 [OpenAI](https://openai.com/) 开发，[微软拥有独家许可](https://blogs.microsoft.com/blog/2020/09/22/microsoft-teams-up-with-openai-to-exclusively-license-gpt-3-language-model/)将其直接集成到其产品中。GPT-3 扫描了数十亿页公开可用的文本来训练它的模型，如果你没有看过，可以提供给[一些非常有说服力的文本](https://www.theguardian.com/commentisfree/2020/sep/08/robot-wrote-this-article-gpt-3)，其中一个人工智能试图让你相信，亲爱的读者，它不是要终结人类。然而，在所有的扫描之后，它可能没有最乐观的穆斯林照片。除此之外，使用所有适当的括号、逗号和分号将您的自然语言业务语言转换成数据库查询可能非常合适。

为了避免你担心机器人会抢走你的工作，微软引用微软低代码应用平台公司副总裁查尔斯·拉曼纳的话来结束它的声明:“在所有情况下，都有一个人在循环中，”拉曼纳说。“这根本不是要取代开发人员，而是要在世界上找到下一个 1 亿名开发人员。”

…目前来说…(哈哈哈哈哈)

## 本周的节目中

*   **接下来是 Build 2021 的其余部分:**当然，在本周的 Build 上还有一系列其他与微软相关的开发人员公告，我们不会花时间逐一详细介绍，而是将您引向正确的位置。例如，微软为微软 Build 2021 提供了一份 [Windows 开发人员指南，该指南概述了该公司最近所做的所有创新(其中许多我们已经在这里详细介绍过，例如用于图形处理单元(GPU)的 Linux 支持的](https://blogs.windows.com/windowsdeveloper/2021/05/25/the-windows-developers-guide-to-microsoft-build-2021/) [Windows 子系统](https://docs.microsoft.com/en-us/windows/win32/direct3d12/gpu-accelerated-training)和用于 WSL 中的 Linux GUI 应用的[等等)。还有](https://aka.ms/wslg)[对所有 Azure](https://azure.microsoft.com/blog/azure-at-microsoft-build-recap-build-amazing-things-on-your-terms-anywhere/) 的回顾，其中包括[新的人工智能功能](https://aka.ms/Build21-CloudNativeDataAIBlog)、一系列 Java 特性、微软 data verse[Azure Synapse Link 的引入](https://aka.ms/Build21-DataverseSynapseBlog)等等。事实上，如果你想了解本周推出或更新的所有内容，只需前往微软的 [Build 2021 Book of News](https://news.microsoft.com/build-2021-book-of-news/) 即可在一个方便的位置找到所有内容，包括摘要、链接等。

*   软件能有多环保？作为一名开发人员，这可能不是你的第一个想法，但也许是时候让它进入前十名了:你的软件有多可持续？最近最常见的例子是比特币及其[极度计算饥饿的过程](https://www.azocleantech.com/article.aspx?ArticleID=1231)，据说其影响堪比 YouTube 上数千小时的疯狂观看。嗯，[埃森哲](https://www.accenture.com/us-en/services/sustainability-index)， [GitHub](https://github.blog/2021-04-22-environmental-sustainability-github/#:~:text=Carbon%20neutral%20since%202019:%20GitHub,clean%20renewable%20energy%20by%202025.) ，[微软](https://www.microsoft.com/en-us/corporate-responsibility/sustainability?activetab=pivot_1%3aprimaryr3)和 [ThoughtWorks](http://www.thoughtworks.com/) 已经与 [Linux 基金会](https://www.linuxfoundation.org/)联合起来[发起绿色软件基金会](https://blogs.microsoft.com/blog/2021/05/25/accenture-github-microsoft-and-thoughtworks-launch-the-green-software-foundation-with-the-linux-foundation-to-put-sustainability-at-the-core-of-software-engineering/)，该基金会称其有三个目标:建立绿色软件行业标准，加速创新，推动意识和增加宣传。他们已经表示，数据中心占全球电力需求的 1%,预计在未来十年内将上升至 3-8%。
*   **未来一年的路线图:**展望未来一年，本周发布了两份我们认为值得关注的路线图。首先，Jetbrains 向[展示了科特林路线图](https://blog.jetbrains.com/kotlin/2021/05/nine-highlights-from-the-kotlin-roadmap/)中的九个亮点，该路线图着眼于 2021 年及以后的计划。 [Kotlin 公共路线图](https://kotl.in/h4nimn)有所有细节，但博客帖子将其浓缩为这九个，包括[新编译器](https://blog.jetbrains.com/kotlin/2021/05/nine-highlights-from-the-kotlin-roadmap/#new-compiler)、[押注 WebAssembly](https://blog.jetbrains.com/kotlin/2021/05/nine-highlights-from-the-kotlin-roadmap/#webassembly) 、[新的和实验性的 kot Lin/原生垃圾收集器](https://blog.jetbrains.com/kotlin/2021/05/nine-highlights-from-the-kotlin-roadmap/#kn-gc)、[对苹果芯片的支持](https://blog.jetbrains.com/kotlin/2021/05/nine-highlights-from-the-kotlin-roadmap/#apple-silicon)、[对 IDE 性能和稳定性的改进](https://blog.jetbrains.com/kotlin/2021/05/nine-highlights-from-the-kotlin-roadmap/#ide-performance)、[新的核心库特性](https://blog.jetbrains.com/kotlin/2021/05/nine-highlights-from-the-kotlin-roadmap/#lib-features)等等。接下来，是新发布的 [Visual Studio 2022 路线图](https://docs.microsoft.com/en-us/visualstudio/productinfo/vs-roadmap)，这是该公司上个月发布的预览版的后续，它宣布将采用 64 位，这让用户既高兴又不安。他们写道，Visual Studio 2022 将有三个关键主题:个人和团队生产力、现代发展和不断创新。欲知详情，请访问 [Visual Studio 2022 公告博客](https://devblogs.microsoft.com/visualstudio/visual-studio-2022/)。高层次的亮点包括迁移到 64 位、增强的可访问性、改进的诊断和调试等。

*   **亚马逊扩展 Lambdas，在任何地方提供 ECS:**最后，亚马逊本周发布了一些值得一提的消息。首先， [Amazon ECS Anywhere 现已正式推出](https://aws.amazon.com/blogs/aws/getting-started-with-amazon-ecs-anywhere-now-generally-available/)，将 Amazon 的弹性容器服务带到 AWS 区域之外的位置，例如内部。[亚马逊 ECS Anywhere](https://aws.amazon.com/ecs/anywhere) 让用户“在本地运行和管理基于容器的应用程序，包括虚拟机(VM)、裸机服务器和其他客户管理的基础设施”，拥有亚马逊 ECS 本身提供的所有功能。接下来， [AWS Lambda 扩展现在也普遍可用](https://feedproxy.google.com/~r/AmazonWebServicesBlog/~3/Ojzzq6mN-AU/)，它为无服务器架构带来了监控、可观察性、安全性和治理工具。这个消息伴随着许多新的合作伙伴——imper va、Instana、Sentry、Site24x7 和用于 OpenTelemetry 的 AWS 发行版——并支持异步响应，这“使扩展能够执行一些活动，如在函数的响应返回后将遥测发送到首选目的地。”虽然有许多合作伙伴提供了扩展，但是您也可以使用 [Lambda 扩展 API](https://docs.aws.amazon.com/lambda/latest/dg/runtimes-extensions-api.html) 构建自己的扩展。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>