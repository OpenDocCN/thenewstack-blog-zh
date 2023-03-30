# Hazelcast 通过内存计算提升流处理能力

> 原文：<https://thenewstack.io/hazelcast-boosts-stream-processing-with-in-memory-computing/>

总部位于加州圣马特奥的 [Hazelcast](https://hazelcast.com/) 推出了一个实时智能应用平台，通过将[流处理](https://thenewstack.io/vendors-compete-for-users-of-stream-processing-technologies/)与[内存计算](https://thenewstack.io/in-memory-computings-big-moment/)相结合，统一了交易、运营和分析工作负载。

Hazelcast Platform 5.0 将实时流处理引擎与内存计算结合在一起，提供了一个高性能、可扩展和可靠的简化架构，[hazel cast](https://www.linkedin.com/in/kelly-herrell/)首席执行官 Kelly Herrell 表示。

“我们在高端市场竞争，你必须提供卓越的延迟、性能、弹性和规模，”他说。“我们拥有全球客户群，尤其是在金融服务和电子商务领域，”Herrell 补充道，并指出这些环境对低延迟、高性能和规模的需求。

Herrell 说，预计到跨企业的实时数据的爆炸，Hazelcast 认为将其流处理引擎 Jet 与公司的内存数据网格结合起来是合适的。

在 2019 年第四季度的[Forrester Wave](https://www.forrester.com/report/The+Forrester+Wave+Translytical+Data+Platforms+Q4+2019/-/E-RES144975):Translytical Data Platforms 中，该研究公司实际上预测像 Hazelcast Platform 5.0 这样的系统即将出现。

“传统数据平台无法满足新的业务需求，这些需求要求实时数据、性能、规模、集成数据和安全性的完美结合，”Forrester 报告称。“不同的技术堆栈会影响向各种应用程序、运营系统和分析提供及时、集成的数据。最大的优势是能够在单个数据库中执行所有这些工作负载(事务性、操作性和分析性)，利用内存、多模式、分布式和云架构方面的创新。”

Hazelcast [Jet engine](https://hazelcast.com/products/stream-processing/) 是一个批处理和流处理系统，使 Hazelcast 成员能够以一致的低延迟对大量数据进行无状态和有状态计算。成员是 Hazelcast 中的计算和数据存储单元。

Hazelcast 的首席技术官[约翰·德斯贾丁斯](https://www.linkedin.com/in/johnmdesjardins/)说，虽然 Jet 现在是整个 Hazelcast 平台的一部分，但 Jet 的名称将在代码中继续存在，以指代流处理引擎，并作为一个 [API 调用](https://hazelcast.com/developer/jet/)。

Forrester Research 的分析师 [Mike Gualtieri](https://www.linkedin.com/in/mgualtieri/) 说，Hazelcast 平台 5.0 和 Jet 将 Hazelcast 带入了现代应用的新市场。

“通过 Jet，Hazelcast 将一个极低延迟的交易数据平台与流分析结合在一起，”他说。“这两种能力都是支持实时应用和人工智能应用所必需的。”

然而，Gualtieri 说，“流”和“流分析”之间有一个关键的区别。

“当开发者想到‘流媒体’时，他们通常会想到卡夫卡，”他说。“Kafka 是关于将数据从 A 点传输到 B 点、C 点、D 点。另一方面，流分析实际上是实时分析数据流，可用于欺诈检测、预测性维护、电子商务购物、驾驶和交付服务、实时交易和许多其他用例。”

Herrell 说，新平台使企业能够将事件流与数据库和数据湖等传统数据源统一起来。

他在一份声明中说:“虽然数据仍然是企业最有价值的资源，但只有当他们能够及时获得可操作的见解时，它才是有用的。”

Heller 说，Hazelcast 平台允许企业将历史数据、事件数据和基于文件的数据与微秒延迟的单个查询结合起来。流媒体引擎在接收数据时对数据进行预处理，而内存计算可以实时分析和处理洞察。该公司表示，统一的数据也可以由流媒体引擎输入机器学习代码，进行实时推理。

Hazelcast 平台现已推出测试版，并将于下个月正式推出。

DesJardins 说，对于开发者来说，新版本提供了简化的应用程序开发和维护。

“作为一名开发人员，你可以使用一个统一的查询引擎，它可以处理所有这些不同类型的数据，”他说。“所有这些都部署在单个运行时上，这意味着开发人员不必安装一堆不同的组件来启动和运行他们的开发。这确实简化并加速了开发人员的 API 端和运行时端。”

此外，DesJardins 表示，Hazelcast 致力于支持一系列不同的开发人员体验和语言——从数据工程师、分析专家到微服务开发人员的规则和语言。

此外，Hazelcast 提供了一个广泛的不同数据源连接器库，例如 MongoDB、Redis Labs 和 Snowflake，因此该平台可以作为应用程序调用的单个数据层和接入点。

新版本中的其他增强包括基于磁盘的持久性和增强的 SQL 支持。

基于磁盘的持久性为任何单个集群成员提供了更长的正常运行时间。它还有助于数据的恢复。

与此同时，该公司表示，Hazelcast 平台中的 SQL 引擎现在支持基本数据操作语言(DML)功能，可以在 Hazelcast 中插入、更新和删除数据。该平台还增加了排序、聚合和新的 SQL 表达式。

此外，它允许企业使用 SQL 以声明方式从 Kafka 等消息系统以及 Amazon S3 等文件和对象存储中获取数据，并通过 SQL 执行流式查询和计算。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>