# 阿帕奇拼花地板简介

> 原文：<https://thenewstack.io/an-introduction-to-apache-parquet/>

随着为分析而生成和存储的数据量以越来越快的速度增长，开发人员希望从各个角度优化性能并降低成本。在 Pb 级规模上，当涉及到存储和处理数据时，即使是边际收益和优化也可以为公司节省数百万美元的硬件成本。

这些优化技术的一个例子是 Apache Parquet。在本文中，您将了解什么是拼花地板，它是如何工作的，以及许多公司和项目将拼花地板作为其建筑中的重要组成部分。

## 什么是阿帕奇拼花地板？

[Parquet](https://www.influxdata.com/glossary/apache-parquet/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-10_spnsr-ctn_intro-apache-parquet_tns) 是一种开源的[面向列的存储](https://www.influxdata.com/glossary/column-database/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-10_spnsr-ctn_intro-apache-parquet_tns)格式，由 Twitter 和 Cloudera 开发，之后捐赠给 Apache 基金会。Parquet 旨在从各种性能指标方面改进 Hadoop 的现有存储格式，例如通过压缩减少磁盘上的数据大小，以及加快分析查询的读取速度。

随着时间的推移，越来越多的项目和公司采用了 Parquet，对于希望让用户更容易导入和导出数据的项目来说，它已经成为一种常见的交换格式。

采用 Parquet 可以让新用户更容易地迁移或采用新工具，对他们的工作流程影响最小，因此它对用户和希望为他们的产品获得新用户的公司都有好处。

## 阿帕奇拼花地板技术故障

拼花地板使用了许多创新的技术来提供出色的性能。在进入细节之前，我们可以看看与用于存储数据的另一种文件格式比较的结果:简单的 CSV(逗号分隔值文件)。

将 1tb 的 CSV 文件转换为 Parquet 文件时，来自 [Databricks](https://www.databricks.com/glossary/what-is-parquet) 的一些数字显示了以下结果:

*   文件大小减少到 130 千兆字节，减少了 87%
*   查询运行时间从 236 秒减少到 6.78 秒，快了 34 倍
*   为查询扫描的数据量从 1.15TB 降至 2.51GB，减少了 99%
*   成本从 5.75 美元降至 0.01 美元，降低了 99.7%

那么是什么秘方让 Parquet 的性能比 CSV 和其他文件格式好那么多呢？让我们看看拼花地板背后的一些关键概念和特征:

*   **游程长度和字典编码**—Parquet 能够简单地列出该值在一列中出现的次数，从而在值频繁重复的数据集上节省大量空间，而不是在磁盘上多次存储相同的值，从而有效地浪费空间。这方面的一个例子是 CPU 监控，其中每个值的百分比利用率都在 1-100 的范围内。
*   **记录粉碎和组装** — Apache Parquet 借用了谷歌 Dremel paper 的一项技术，允许 Parquet 将嵌套的数据结构映射到基于列的布局。这样做的好处是，开发人员仍然可以以更自然的嵌套方式处理数据，同时获得基于列的数据结构的性能优势。
*   **丰富的元数据** —在底层，Parquet 跟踪大量的元数据，这是实现上述策略所必需的。拼花数据分为行组、列块和页面。文件可以包含几个行组，这些行组中的每一个都恰好包含每一列的一个列块。每个列块包含一页或多页数据。所有这些复杂性都被抽象掉了，所以开发人员不必直接担心。

所有这些特点共同作用，使拼花地板的性能特点。简而言之，就是提供元数据来优化查询，以减少计算资源需求，同时减少重复数据点的数量，从而降低存储成本。这导致更快的查询和更少的存储需求。

在云计算时代，Parquet 尤其有利，因为许多云服务根据您正在处理和扫描的数据量收费。因为 Parquet 保留了关于您的[数据](https://www.influxdata.com/what-is-time-series-data/)的结构的额外元数据，它能够显著减少被扫描的不必要数据的数量，因此您不必花钱扫描、处理和[分析不需要的](https://www.influxdata.com/time-series-analysis-methods/)数据，您只需抓取您需要的数据。

## 使用 Apache 拼花地板的公司和项目

许多项目支持将 Parquet 作为导入和导出数据的文件格式，并在内部使用 Parquet 进行数据存储。以下是其中的一小部分，以及它们的用途:

*   [Hadoop](https://github.com/apache/hadoop) 是基于 Google 的 MapReduce 论文的大数据处理工具。Parquet 最初被设计为一种用于 Hadoop 的文件格式。
*   Apache [Iceberg](https://github.com/apache/iceberg) 通过允许 Spark、Trino 和 Flink 等[流处理](https://www.influxdata.com/solutions/stream-processing/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-10_spnsr-ctn_intro-apache-parquet_tns)工具对来自同一存储后端的所有数据进行查询和处理，试图将普通关系数据库表的简单性应用于大数据规模。
*   [Delta Lake](https://github.com/delta-io/delta) 是一个开源存储框架，用于构建数据湖风格的架构。Delta Lake 集成了 Spark、PrestoDB、Flink 和 Trino 等常用计算工具，使处理和存储数据变得简单。
*   Apache [Spark](https://github.com/apache/spark) 是一个用于处理大量数据的分析引擎。除了像 Pandas API 这样的高级工具之外，它还允许使用 SQL 进行数据处理。

## Apache 拼花地板和 InfluxDB

InfluxDB 时间序列数据库是另一个严重依赖于 Parquet 的项目，特别是 InfluxDB 新的列存储引擎，名为 [IOx](https://github.com/influxdata/influxdb_iox) 。InfluxDB 通过使用[对象存储](https://thenewstack.io/the-new-metrics-of-object-storage/)将 Parquet 用于数据的持久存储。这允许数据在热存储层和冷存储层之间高效地移动，从而允许 InfluxDB 为用户提供更好的性能，同时降低他们的存储成本。与之前的 InfluxDB 迭代相比，它还提供了更好的数据压缩率。

InfluxDB 通过以线路协议格式映射发送到 InfluxDB 的数据，然后将线路协议中定义的那些标签、字段和时间戳映射到 Parquet 中的列，来与 Parquet 协同工作。然后，可以根据该字段值的数据类型，使用最佳压缩算法来压缩这些列。然后，按时间范围分割拼花文件，这样您只需访问最少数量的拼花文件，就可以获得所需的时间序列数据。当从 Parquet 文件中提取数据时，使用 [Apache Arrow](https://www.influxdata.com/glossary/apache-arrow/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-10_spnsr-ctn_intro-apache-parquet_tns) 格式将数据加载到内存中，这也是基于列的，因此产生的性能开销最小。

## 包扎

当处理大规模数据时，每一点点的效率都会给你的公司和用户带来巨大的好处。拼花地板只是致力于提高效率的众多项目之一。虽然作为开发人员，您可能不会直接与 Parquet 进行交互，但是您经常使用的一些工具很有可能正在使用 Parquet。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>