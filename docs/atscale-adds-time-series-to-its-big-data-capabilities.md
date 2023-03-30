# AtScale 将时间序列添加到其大数据功能中

> 原文：<https://thenewstack.io/atscale-adds-time-series-to-its-big-data-capabilities/>

为了使数据更容易访问，甚至跨多个数据库和云，数据虚拟化供应商 AtScale 最近增加了时间序列分析功能。

这是行业趋势的一部分，即创建“符合目的”的大数据处理和分析，而不是一刀切的方法。

AtScale 的联合创始人兼首席技术官[马修·贝尔德](https://www.linkedin.com/in/mattbaird/)说:“过去，一切都与性能有关，但战场正在转移或已经转移到敏捷性。

在他所说的为工作应用最佳工具中，时间序列能力包括:

*   通过单一 web 界面，使用基于时间的计算、指标和关系对实时数据进行建模。
*   跨任意时间定义的标准化周期间比较。
*   智能联合到最合适的数据库，而不管其位置如何，以支持复杂的大规模基于时间的分析。

“我们在市场上看到，性能、安全性和灵活性都非常重要，过去如此，将来也是如此。但在云世界，也有成本因素，”他说。

虚拟化意味着你不关心数据在哪里，你不关心它是如何被访问的，你关心的是让你的问题得到回答，并让计算机以最佳方式得到答案，他说。

AtScale 提供跨各种数据平台的虚拟化，包括 Teradata、Oracle、Snowflake、Redshift、BigQuery、Greenplum 和 Postgres。

“我们的目标是允许人们快速合并来自几个不同来源的数据，推出数据服务，然后让他们的用户开始查询。当他们这样做时，他们会发送他们的意图，即什么数据对他们来说是重要的，AtScale 会通过做这些数据工程工作来提高系统的性能、安全性和灵活性，”他说。

### 连接数据

AtScale 最初是在 Hadoop 上创建的，但后来在 Spark 上构建了一个数据结构。它包括可扩展的维度计算引擎、机器学习性能优化器、通用数据抽象层和企业级安全、治理和元数据管理功能。

它将 Tableau、Excel 和 Power BI 等商业智能工具连接到实时数据源，而无需移动数据，消除了提取、转换和加载(ETL)以及其他手动流程。

在一个演示中，Baird 将五个数据库放在一起——两个在物理云中，三个在不同的云数据库中——使 20 个表看起来像一个大表。

Baird 将其技术描述为两个部分:用户体验应用程序，人们在其中设计数据服务；和接受查询的服务器。他说，它看起来像一个蜂巢数据库，但它更像一个自主的数据工程和更高层次的基于成本的优化器。

它使用熟悉的框架，如 BusinessObjects Universe 或 Cognos Frameworks Manager，将数据建模为虚拟 OLAP(在线分析处理)立方体。然后可以通过 ODBC、JDBC 和 MDX 发布该模型以供查询。

通用语义层允许用户将任何工具连接到 AtScale 并访问模型，而无需连接表、创建计算或业务规则。它随着对模型的了解而进行调整，并不断审查用户如何与数据进行交互，以自动化其工作背后所需的数据工程。

关键是只获取相关数据。用户只需询问他们需要的数据，AtScale 就会自动重写查询以优化获取数据的性能。

在它所谓的自适应缓存中，它根据了解哪些数据是重要的，如何使用以及如何最好地塑造这些数据，实时汇总查询。这些集合与原始数据一起存储在选定数据平台的磁盘上，加快了后续查询的响应速度。

[https://www.youtube.com/embed/F_XJPf1oXLE?feature=oembed](https://www.youtube.com/embed/F_XJPf1oXLE?feature=oembed)

视频

它的客户包括家得宝、维萨、联合医疗、丰田等。

## 增加安全性

据 [IDC](https://pages.alteryx.com/idc-infobrief-state-data-science-analytics.html) 称，数据工作者通常使用四到七种不同的工具来获取、查询、建模和分析数据，占用他们 40%的时间。

无数的公司都在努力使处理数据变得更容易管理，比如在 Kubernetes 上运行 Spark 的[Pepperdata](https://thenewstack.io/peppercorn-spark-kubernetes-ticket-off-big-data-island/)；自助服务平台 [Qubole](/qubole-harnesses-automation-provide-data-self-service/) 和[全景图](/panoply-shrinking-datas-time-to-business-value/)；最近[Amundsen](/lyfts-amundsen-data-discovery-with-built-in-trust/)Lyft 开源项目帮助用户快速找到数据，并对其可信度进行排名。

然而，Baird 认为 AtScale 最接近的竞争对手是纯粹的虚拟化玩家 [Denodo](/denodos-data-virtualization-becoming-scale-data-fabric/) 和同样将不同来源的数据整合在一起的 [Dremio](/dremio-wants-put-data-scientists-drivers-seat/) 。

AtScale 采用联邦来支持多维分析。贝尔德表示，它可以与更多工具对话，并更好地简化分析。它支持 Excel、Hyperion、Cognos 和 BusinessObjects 等工具。

“我们解决问题的方法非常不同。Denodo 和 Dremio 专注于大规模性能的联合和缓存。我们采用这种自主的数据工程方法:数据工程团队会做什么？”贝尔德说。

它还集中了安全性，如果您四处移动数据，安全性很快就会过时。

“我们拥有端到端委托和模拟的专利，我们称之为真正的委托。因此，执行查询的人，坐在 Windows 桌面上与 Power BI 或他们正在使用的任何工具交谈，是后端查询所使用的同一身份。无论我们如何构建加速结构并存储它们，底层数据仓库的安全性都适用于这些查询，”他说。

他还引用了一个友好的 UX 来构建用例，只需要几分钟或几小时，而不是几周的复杂性。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>