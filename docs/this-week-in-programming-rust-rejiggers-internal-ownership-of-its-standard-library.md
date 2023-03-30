# 本周编程:Rust 重新调整了其标准库的内部所有权

> 原文：<https://thenewstack.io/this-week-in-programming-rust-rejiggers-internal-ownership-of-its-standard-library/>

像许多编程语言一样， [Rust](https://www.rust-lang.org/) 由核心规范、标准库、编译器和文档组成。正如您所料，构建这些东西所需的技能和关注点各不相同，因此通常会有不同的团队致力于每项任务。本周，Rust 团队仔细研究了这一点——标准库和编译器在标准库实现的[所有权](https://blog.rust-lang.org/inside-rust/2020/07/02/Ownership-Std-Implementation.html)中的区别——以及这些团队是如何根据他们的职责和所有权来定义的。

他们写道，展望未来，标准库团队(Libs)将拥有“公共 API”，而编译器团队将拥有其实现。“这很像 Lang 和编译器团队之间现有的关系，Lang 团队拥有 Rust 语言设计，编译器团队拥有实现它的代码，”他们写道。他们说，这里的想法是，作为一个代码库，“标准库是矛盾地专门化的。它拥有访问编译器内部的特权，深入的领域知识融入到算法中(例如，您是否想过如何有效地将一个浮点数格式化为文本？)、特定于平台的集成以及大量棘手的不安全代码。”

那么，为什么要重组呢？

他们说，Libs 团队“传统上选择喜欢设计 API 的成员”，并且他们当前的活动范围“为标准库本身的开发留下了很少的空间，这需要大量一致和专注的关注。”与此同时，“编译器团队习惯于对大项目给予一致和专注的关注。标准库正是编译器团队已经拥有多年工作经验的那种代码库。”

目前，整个事情只是一个尝试性的重组，他们计划在今年晚些时候进行重新评估，但我们期待着有见地的博客帖子，再次关注创造年复一年成为[最受欢迎的编程语言之一](https://thenewstack.io/this-week-in-programming-rust-remains-the-most-beloved-language/)的背后的方法和原因……尽管它有[的难度和陡峭的学习曲线](https://thenewstack.io/this-week-in-programming-whats-holding-back-rust-and-go/)。

## 本周的节目中

*   **亚马逊 CodeGuru 发现昂贵的代码，现在 GA:** 亚马逊[在预览版中推出](https://aws.amazon.com/about-aws/whats-new/2019/12/aws-announces-amazon-codeguru-for-automated-code-reviews-and-application-performance-recommendations/)其 [CodeGuru](https://aws.amazon.com/codeguru/) 工具已经一年了，现在该公司表示该工具已经[准备好投入生产，并普遍可用](https://aws.amazon.com/blogs/aws/find-your-most-expensive-lines-of-code-amazon-codeguru-is-now-generally-available/)。亚马逊写道，在此期间，该工具经历了[许多改进](https://aws.amazon.com/new/?whats-new-content-all.sort-by=item.additionalFields.postDateTime&whats-new-content-all.sort-order=desc&whats-new-content-all.q=CodeGuru&whats-new-content-all.q_operator=AND#feed)，包括[更具成本效益的定价模型](https://aws.amazon.com/about-aws/whats-new/2020/05/amazon-codeguru-reviewer-launches-new-pricing-model/)、[对 Bitbucket 存储库的支持](https://aws.amazon.com/about-aws/whats-new/2020/05/amazon-codeguru-reviewer-announces-support-for-bitbucket-repositories-and-enhancements/)，以及[使用命令行开关](https://aws.amazon.com/about-aws/whats-new/2020/05/amazon-codeguru-announces-javaagent-switch-to-start-profiler/)启动分析代理的能力。该工具由机器学习提供支持，旨在通过基于运行时数据的自动化代码审查和性能建议来改进应用程序，并且在此版本中被分为两个独立的部分:CodeGuru Reviewer 和 CodeGuru Profiler。评审者在开发过程中使用机器学习来检测潜在的缺陷并提出修复建议，而分析器再次使用机器学习，但这一次是通过帮助开发人员了解他们的应用程序的运行时行为，来确定在 CPU 使用或引入的延迟方面最昂贵的代码行。目前，这些工具支持用 Java 虚拟机(JVM)语言编写的应用程序，如 [Java、Scala、Kotlin、Groovy、Jython、JRuby 和 Clojure](https://docs.aws.amazon.com/codeguru/latest/profiler-ug/enabling-the-agent-with-code.html) 。这个版本还引入了对 [Github Enterprise](https://github.com/enterprise) 的支持、异常检测、Lambda 函数支持、代码着色、CloudWatch 指标和警报等等。

[https://www.youtube.com/embed/ZFoGBUGRqUY?feature=oembed](https://www.youtube.com/embed/ZFoGBUGRqUY?feature=oembed)

视频

*   **GitHub 整合了它的文档:** GitHub 说它正在[推出 docs.github.com](https://github.blog/2020-07-01-launching-docs-github-com/)，一个 GitHub 所有产品文档的单一主页，以取代之前为用户和集成商提供产品文档的两个网站。他们写道，新网站将 help.github.com 和 developer.github.com 上的产品内容结合成一个统一的体验，使你可以在一个地方搜索 GitHub 的所有文档。展望未来，他们计划为所有产品文档提供语言支持，包括面向集成商的内容，目前的语言包括日语、简体中文、巴西葡萄牙语和西班牙语。
*   出现了 TypeScript 4.0 测试版！TypeScript 3.9 发布已经一个月了，微软已经宣布了 TypeScript 4.0 测试版，这是该语言的“下一个重要里程碑”。根据发布的消息，新的主要版本引入了“不会比通常情况下大得多的突破性更改”，遵循的理念是提供“一种最大限度地减少破坏性突破性更改的升级路径，同时仍给我们一些灵活性，以便在适当的时候将可疑代码标记为错误。”在新特性方面，TypeScript 4.0 Beta 包括可变元组类型、带标签的元组元素、来自构造函数的类属性推断、短路赋值运算符、自定义 JSX 工厂等等。第一个候选版本定于 8 月 4 日发布，最终版本定于 8 月 18 日发布。
*   **Pylance 为 Visual Studio 代码提供了功能丰富的语言支持:**不要与微软为 Visual Studio 代码创作的其他 Python 扩展混淆， [Pylance](https://github.com/microsoft/pylance-release) 于[本周](https://devblogs.microsoft.com/python/announcing-pylance-fast-feature-rich-language-support-for-python-in-visual-studio-code/)发布，实际上构建在[核心 Python 扩展](https://marketplace.visualstudio.com/items?itemName=ms-python.python)之上。更具体地说，Pylance 是一个新的 Python 语言服务器，它使用语言服务器协议与 VS 代码进行通信。更一般地说，Pylance“用丰富的类型信息增强您的 Python 智能感知体验，帮助您更快地编写更好的代码。”该团队表示，它提供了更好的性能和许多新功能，如“流行模块的类型存根集合，以提供快速准确的自动完成和类型检查。”旁注，团队注意到这个名字是“向巨蟒剧团的兰斯洛特致敬，他是圣杯中第一个回答守桥人问题的骑士。”哦，当我们谈到 Visual Studio 代码的话题时， [WhiteSource 本周也发布了一个微软 Visual Studio 集成](https://www.prnewswire.com/news-releases/whitesource-launches-microsoft-visual-studio-ide-integration-301085749.html)，在开发过程中为开发人员提供有问题的开源组件的可见性和安全警告。

*   **微软推出移植助手。NET Core:** 向前看，微软已经[说](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/)它只会更新。NET 4.8 的错误，可靠性和安全性的更新，因为重点已经转移到。网芯。本周，该公司宣布了移植助手。NET ，一个帮助分析和移植的工具。NET 框架应用程序。NET 核心，涵盖了应用程序源代码和完整的公共 API 和 NuGet 包依赖关系树。出于好奇，引擎背后的数据模型，微软称是对数百万个包版本的数十万个独特包进行分析的结果，可在 [GitHub](https://github.com/aws/porting-assistant-dotnet-datastore) 上获得，更多细节可在[用户指南](https://docs.aws.amazon.com/portingassistant/latest/userguide/)中获得。
*   **微软的 Dapr 获得 Azure 功能扩展:**微软[去年首次发布](https://thenewstack.io/microsofts-open-source-dapr-could-help-developers-build-agnostic-microservice-applications/)其分布式应用运行时(Dapr)，现在[推出了 Dapr](https://cloudblogs.microsoft.com/opensource/2020/07/01/announcing-azure-functions-extension-for-dapr/) 的 Azure 功能扩展，Azure 功能提供事件驱动的编程模型，而 Dapr 提供一组云原生构建块。该扩展将这两者结合在一起，使无服务器和事件驱动的应用程序能够使用 Dapr 提供的越来越多的功能。该扩展是开源的，可以在 GitHub 上获得[。](https://github.com/dapr/azure-functions-extension)
*   **Apollo 为 GraphQL 添加了 Apollo Explorer:**上周，Apollo 推出了 Apollo Explorer，这是一款用于导航图表和构建 GraphQL 查询的新工具。Apollo Explorer 不是专注于服务器开发人员，而是为“图形消费者——整天与生产数据图打交道的产品工程团队”而构建的。该工具是一个查询构建器和运行器，它的操作编辑器构建在 [Monaco](https://microsoft.github.io/monaco-editor/) 上，这可能会让它看起来很熟悉。要了解这一点，要么前往 [demo.apollo.dev](https://demo.apollo.dev/) 网站，要么成为 Apollo Studio 的用户。

亚马逊网络服务是新堆栈的赞助商。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>