# Apache Hop 利用元数据创建可视化数据管道

> 原文：<https://thenewstack.io/apache-hop-harnesses-metadata-to-create-visual-data-pipelines/>

基于开源元数据的数据工程和数据编排平台 Apache Hop 最近被命名为 Apache Software Foundation 顶级项目。

Hop 中的所有内容都被视为元数据。这使得它能够灵活地处理数百个数据平台及其配置。

元数据描述了应该如何处理数据，或者应该如何协调工作流和管道。

该项目起源于二十多年前的提取-转换-加载(ETL)平台[水壶](https://www.openhub.net/p/kettle)，被 Pentaho(现[日立万塔拉](https://www.hitachivantara.com/en-us/products/data-management-analytics/pentaho.html))收购，并作为 Pentaho 数据集成(PDI)推向市场。

该软件经过了几年的重构，它的一个分支——代表 Hop 编排平台的名称——于 2020 年 9 月进入了 Apache 孵化器。

使用图形用户界面，可以直观地设置数据工作流和管道，并使用元数据进行描述。

借助其拖放式图形用户界面(GUI)，用户无需具备特定的编程知识即可设计、测试和运行工作流和管道。或者，程序员和开发人员可以从命令行工作。

它运行在 Java 环境中，可以独立于操作系统使用。它被设计为可以在任何地方工作:内部、云中、裸机操作系统上、容器中、物联网环境等等，以及 Windows、Linux 和 OSX 上。

[跳跃引擎](https://github.com/apache/hop)使用只包含核心功能的内核架构。所有其他功能都是通过插件添加的。标准安装提供了 250 多个插件，不过您可以轻松添加自己的或第三方插件。

Hop 1.0 于 10 月发布，其中包括针对当前内核加插件架构的大规模架构重新设计和代码重构。

“这种架构极大地改善了开发过程，并允许 Hop 适应它需要部署的架构，而不是相反，”Hop 项目管理委员会成员在一封电子邮件中说。

与 Apache Beam 的集成允许 Hop 管道和工作流不仅可以在本地和远程运行在 Hop 的本地引擎上，还可以在 Apache Spark、Apache Flink 和 Google Cloud Dataflow 上运行。这使得项目团队可以在不修改数据的情况下开展项目。

Hop 通过最佳实践、集成版本控制、单元测试、项目和部署环境支持等来支持项目生命周期管理。

它包括元数据注入管道的集成测试和模板库。注入在运行时完成，减少了手工开发的需要。

Hop 支持多个项目和环境。项目环境包含开发、测试、生产或项目生命周期的其他阶段的项目部署配置。

项目文件是通过 Hop GUI 的文件资源管理器中的 git 集成进行版本控制的，为用户提供了一些选项，比如可视化地比较工作流或管道的两个版本的能力。

使用 Hop GUI，开发人员和工程师可以管理整个项目生命周期:在项目、环境、运行时配置之间切换，管理 git 版本等。

“我们在 2021 年初开始在我们的数据集成项目中采用 Apache Hop，因为它具有灵活性、可扩展性和易用性，适用于从经典的 DWH ETL 流程到高度关键的实时流程的各种场景，”意大利商业分析公司 Serasoft S.r.l .的首席执行官兼首席架构师、Apache Hop 项目管理委员会成员 Sergio Ramazzina 表示。

“我们对社区在解决问题和帮助用户接近平台方面的响应速度印象深刻，这是增加用户采用率和信任度的重要一点。"

根据委员会的说法，Hop 社区在整个毕业过程中继续致力于 Hop 1.1.0 版本的开发

Hop 1.1.0 将包含 200 多张票的工作。其中包括大量的 UI 改进和错误修复、Apache Tika 支持和异步 web 服务。

除了扩展与 Apache Beam 的集成，[还在继续](https://hop.apache.org/docs/roadmap/)与其他 Apache 项目的集成，比如 Airflow、PLC4X 等。

“从长远来看，我们将建立一个可以轻松共享第三方插件的市场，一个用于改进管道监控、日志记录、调试和预览的新 GUI，以及社区已经在开发的许多其他令人兴奋的新功能，”该委员会表示。

“我们认为毕业是一个顶级项目，是 Hop 激动人心的新时代的开始。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>