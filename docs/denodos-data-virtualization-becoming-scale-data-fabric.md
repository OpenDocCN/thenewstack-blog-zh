# Denodo 的数据虚拟化正在成为大规模数据结构

> 原文：<https://thenewstack.io/denodos-data-virtualization-becoming-scale-data-fabric/>

如果你要一杯水，是把整桶水拿来给你一杯，还是直接去拿一杯水更有效率？

这是 Denodo 首席营销官[拉威·香卡](https://www.linkedin.com/in/ravishankardevaraj/)用来解释数据虚拟化的类比。

与寻求创建一个中央数据池的数据集成技术不同，数据虚拟化连接到所有数据源—数据中心、云、第三方、机器—以实时提供业务问题的答案。关键是它不移动数据，这在传统的 ETL 过程中是昂贵的，并且会产生显著的滞后时间。相反，它只获取相关的数据。

如果您想知道过去五年的销售业绩，并且该信息的一部分在 Teradata 中，一部分在 Hadoop 中，您可能会谈论数百万行，数据虚拟化只返回那些与查询相关的行。然后，它将数据拼接在一起，提供答案。

数据虚拟化提供了一个抽象层:隐藏了数据来源和格式的复杂性；不复制数据，这使得传递更快；并为迁移到云的公司提供灵活性，因为他们可以在不影响用户的情况下切换数据源。

## 最快的查询路线

总部位于加州帕洛阿尔托的 [Denodo](https://www.denodo.com/en) 提供了一个单一平台，该平台具有不同的风格，如敏捷 BI、数据治理、逻辑数据湖和逻辑数据仓库，并且是为政府、医疗保健和石油天然气等垂直行业定制的。

它的客户包括[罗技](https://www.denodo.com/en/document/case-study/logitech-case-study-successful-cloud-modernization-denodo-cloud)，该公司已经将其数据中心迁移至云端。看看这项技术如何被用于预测山体滑坡。

Shankar 描述了三代数据虚拟化:

*   第一代:简单的数据联邦。它汇总各种来源的数据，并将其返回给消费者。性能差。他引用了 IBM、Oracle、SAP 和 Informatica 的解决方案作为例子。
*   第二代:包括性能优化，但您必须在设计时对其进行编程。然后就像一个不考虑交通的 GPS，它会带你到那里，但不是很快。
*   第三代:Denodo 使用的动态查询优化。GPS 会计算出交通模式，并重新路由查询，以尽可能缩短交付时间。

[Gartner](https://www.Gartner.com) 指出动态查询优化是 Denodo 的关键优势。

为此，Denodo 专门针对高数据量和复杂性使用了[基于统计成本的优化](http://searchoracle.techtarget.com/answer/Rule-based-vs-cost-based-optimization)。在运行时，它会计算每个查询需要多长时间。然后，它将跨源优化查询。如有必要，它将重写查询以尽可能快地获取数据。它将在下个季度发布的新版本中增加内存处理功能，以使处理速度更快。

首席技术官 [Alberto Pan](https://twitter.com/albertoapan) 称之为提高逻辑架构性能所需的两个[步骤](http://www.dbta.com/BigDataQuarterly/Articles/In-Memory-Parallel-Processing--and-Data-Virtualization-Redefine-Analytics-Architectures-118223.aspx)之一:

*   使用自动优化来最小化网络流量，将尽可能多的处理下推到数据源
*   在数据虚拟化层使用并行内存计算进行无法下推到数据源的后处理。

## 对大数据“至关重要”

Forrester 认为数据虚拟化对于解决企业面临的大数据挑战至关重要。在其 2017 年的调查中，56%的全球技术决策者表示，他们已经实施了数据虚拟化，正在实施或正在扩大实施范围，高于 2016 年的 45%。

根据 Forrester 的[报告](https://www.forrester.com/report/The+Forrester+Wave+Enterprise+Data+Virtualization+Q4+2017/-/E-RES133042)，供应商继续增加功能，包括社交媒体分析、物联网(IoT)、欺诈检测和集成洞察。它调用元数据目录，该目录跟踪所有数据的位置、可用性和状态，是这些服务不可或缺的一部分。

在最近关于新堆栈的专栏中，Denodo 的 Lakshmi Randall 解释了元数据和机器学习如何成为自动化集成的关键。

Denodo 通常被视为一家初创公司，实际上它只有 17 岁。Denodo 于 1999 年由西班牙 A Coruñ大学的教授 Angel Viñ创立。Denodo 于 2005 年将总部迁至硅谷。

## 熟悉的工具

使用 SQL 构建，用户会发现 Denodo 接口类似于关系数据库。

数据源构成底层，包括 Redshift、HP Vertica、Impala、Apache Spark、Teradata、Hive 等。它支持 Kafka、Storm 和 Spark 流媒体等流媒体技术，并集成了 Docker 技术。数据虚拟化位于中间，业务用户位于顶层，他们可以利用与 Tableau 和 Cognos 等报告工具以及定制应用程序的集成。

中间的“基本视图”表示上层可用的规范化模式。基本视图包含从数据源检索数据的所有逻辑，使用相关的 SQL 方言或在演示中使用 HTTP 调用。无论底层数据源技术如何，基本视图都是元数据的表示，看起来就像一个关系表。

[Denodo 平台](https://www.denodo.com/en/video/demo/connect-combine-publish-easily-data-virtualization)使用专门的数据源连接器在设计时检索它们的模式，在运行时检索源数据，以便进行后续处理。每个连接器都使用为每个数据源创建的语法和性能优化来最大限度地提高性能。这些连接器可以通过可视化编辑器进行配置。

Denodo 拥有与各种关系数据库和 NoSQL 数据库、打包应用程序(如 SAP 和 Salesforce)、web 服务(SOAP 和 REST)、Excel 电子表格、XML、JSON、日志文件、Web 应用程序等的连接器。它还提供了一个用于创建自定义本机连接器的 SDK。

该平台使用扩展的关系代数，使用户能够使用他们已经知道的 SQL 和关系工具执行复杂的数据转换、元数据建模以及数据质量和语义匹配操作。

不管访问方法如何，视图共享元数据和访问权限。

您可以通过 SOAP、REST 或 oData 将任何视图发布为 web 服务。ActiveMQ、Sonic 和 IBM Websphere MQ 等消息队列的 JMS 侦听器意味着 Denodo 可以用作服务总线。

它为业务用户提供自助搜索和数据探索功能。并且一个视图可以通过所有不同的接口同时展示。例如，一个用户可以通过 JDBC 访问它，而其他用户使用 REST Web 服务。

“Denodo 的主要优势在于统一和集中的数据服务结构，该结构可跨多个传统和大数据源提供端到端的安全性、沿袭、转换和协调。客户喜欢它易用、简单但复杂的数据建模能力；搜索能力；以及对各种大数据源的支持，”Forrester 在其分析中表示。

除了内存，该公司正在拥抱云。它现在可以在 AWS 和 Azure 上使用，并在未来加入谷歌和其他公司。该公司坚持认为，云中的延迟与内部实施相当。

它正在从数据集成扩展到数据管理。

“我们正在成为数据结构。Shankar 说:“这不仅仅是一个聚集数据的地方，而是一个你可以搜索数据、发现数据、理解关系、理解血统、理解所有数据治理方面的地方。数据目录也将是新版本的一部分。

客户正在走向成熟，因此 it 部门正在提升其支持大规模使用 it 作为数据层的大型企业的能力。

通过 Pixabay 的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>