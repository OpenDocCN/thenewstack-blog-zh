# StarRocks 为其分析引擎推出云服务测试版

> 原文：<https://thenewstack.io/starrocks-launches-beta-of-cloud-service-for-its-analytics-engine/>

StarRocks 是一个同名专业分析数据库的制造商，周四宣布了 StarRocks Cloud 的测试版，这是一个围绕数据库建立的完全托管服务。 [StarRocks Cloud](https://starrocks.com/products/starrocks-cloud) 最初将在[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)上提供；对微软 Azure 和谷歌云的支持将随之而来。StarRocks 云将于 2022 年第三季度正式上市。

## 重要统计数据

《新堆栈》采访了 StarRocks 战略副总裁李康，他解释了 StarRocks 的意义。Kang 解释说，StarRocks 是一个专注于实时分析/在线分析处理(OLAP)查询的数据库。就查询语言和客户端协议而言，它是一个完全兼容 MySQL 的关系数据库。此外，它还可以作为数据湖查询引擎，以及流数据和变更数据捕获(CDC)源。Kang 还表示，StarRocks 可以处理成千上万的并发用户，尽管他没有提到任何具体的文档或基准来证实这一指标。

StarRocks 于 2020 年由阿帕奇多丽丝团队的几名成员成立，他们脱离出来成立了这家公司。虽然 StarRocks 产品最初是基于 Doris 的，但 Kang 说现在 80%的代码都是新的。该公司表示，其最近一轮融资是 4000 万美元的 B 轮融资，迄今为止总融资额为 6000 万美元。

## 去规范化还是不去规范化？

StarRocks 是一个为 OLAP/分析查询而构建的数据库。它具有基于成本的优化器、完全矢量化的查询引擎、管道执行和该公司所谓的智能物化视图。StarRocks 与 [Rockset](https://rockset.com/) 、 [Apache Pinot](https://pinot.apache.org/) 、 [Apache Druid](https://druid.apache.org/) 和 [Clickhouse](https://clickhouse.com/) 等竞争。与这些产品一样，它是一个关系数据库，具有特定的设计点，以降低星型模式所需的多表连接的成本和复杂性，星型模式是为聚合和下钻查询而构建的数据库的通用结构。然而，StarRocks 在降低这些成本和复杂性的方式上与众不同。

它的几个竞争对手——例如 Druid 通过构建一个巨大的非规范化表来规避星型模式连接的开销。这有助于提高查询性能，但妨碍了用新数据更新数据库或处理结构变化的灵活性。另一方面，StarRocks 可以查询根表以避免处理延迟，还可以维护和查询非规范化的表，但只在必要时使用。

StarRocks 称其数据库已被 500 多家公司使用。康告诉 New Stack，Airbnb 用 StarRocks 取代了 Druid、 [Presto、](https://prestodb.io/) [Apache Hive](https://hive.apache.org/) 和 [Apache Spark](https://spark.apache.org/) 的组合，以实现其内部 [Minerva](https://medium.com/airbnb-engineering/how-airbnb-achieved-metric-consistency-at-scale-f23cc53dea70) metrics 商店的后端数据层。他还解释说，一家主要的社交媒体应用公司的实时广告数据平台在 StarRocks 上实现标准化之前，经历了使用[亚马逊红移](https://aws.amazon.com/redshift/)、Hive/Presto，然后是 Clickhouse 的过程。

## OLAP 的新旧

作为一个自 90 年代末以来一直从事商业智能技术工作的人，很难不将 Druid、Clickhouse 和 StarRocks 的非规范化/规范化二分法与 MOLAP(多维 OLAP)和 ROLAP(关系 OLAP)之间的老式分裂相提并论。在 MOLAP 的情况下，您有一个为快速查询而优化的结构，但是在添加新数据时有很大的处理负担，并且在结构变化方面不够灵活。在 ROLAP 案例中，处理是最少的，模型仅仅是为了语义的目的而构建的，而不是物理实现的。一些平台甚至可以混合 MOLAP 和 ROLAP 模型，这种方法似乎类似于 StarRocks 的非规范化和规范化表的混合。

无论是老 OLAP 还是新平台，一切最终都归结为“现在付钱还是以后付钱”的架构选择哪种方法是最好的将取决于用例。对于可操作化的分析，即在历史数据上重复和例行地执行相同的查询，MOLAP/非规范化表模型通常工作得最好，尽管它们的前期成本很高。对于探索性的情况，以及处理实时数据的情况，ROLAP/规范化的表结构通常是最好的。当分析“已知的未知”时，提前做好工作是一项不错的投资。当考虑“未知的未知”时，最好不要做太多的高级优化。

因此，StarRocks 的平衡方法似乎是理想的，即使其新的云服务将加入一个非常拥挤的领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>