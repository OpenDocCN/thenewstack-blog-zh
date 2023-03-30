# 在现代实时数据库上加速 SQL 查询

> 原文：<https://thenewstack.io/accelerating-sql-queries-on-a-modern-real-time-database/>

在广泛的垂直行业中部署大规模实时应用程序时，企业需要通过通知、即席查询、仪表板和报告对这些系统进行“实时”可见性，有时是接近实时的可见性。

SQL 被广泛用作分析的数据访问语言，Trino 为 SQL 访问多个数据源提供了强大的引擎。Trino 连接器允许 SQL 通过 Trino 访问实时数据，更广泛地说，允许数据架构师和开发人员扩展可从 Trino 访问的快速分析数据。

对于分析用例，您可以使用高级的 [XDR 协议](https://aerospike.com/resources/tech-videos/xdr/)将全球分布的集群中的事务和运营数据近乎实时地同步到记录系统(SOR)或分析存储。

## 支持大规模快速查询

卓越的数据库以巨大的并行性提供了对大量数据的快速访问。

### 大容量快速存储

现代数据库具有跨越多个节点的集群体系结构，以提高规模、性能和可靠性。高密度的快速存储通过固态硬盘(SSD)实现。混合内存架构(HMA)将索引和数据存储在动态随机存取存储器(DRAM)、SSD 和其他设备中，以提供经济高效的快速存储容量。

### 低延迟访问

磁盘(SSD)读写针对延迟和吞吐量进行了优化。

索引在实现快速数据访问中起着关键作用。这需要支持整数、字符串、地理空间、地图和列表列的辅助索引。

### 多级并行

集群节点上的线程架构经过优化，以利用现代硬件的多核处理器的并行性，并最大限度地减少冲突和提高吞吐量。数据均匀分布在所有节点上，以最大限度地提高并行性和吞吐量。客户端库直接连接到单个群集节点，通过将请求分发到并行处理请求的节点，并组合结果，在单个跃点中处理请求。

### 细粒度子查询

理想情况下，您希望将记录分布在统一的分区中，并允许对它们进行单独的子查询，以实现最大的并行性。换句话说，一个查询被分割成一个或多个分区上的独立并行子查询，以使所需的并行性与所需的吞吐量相匹配。此外，通过添加模数过滤器表达式`digest % N == i for 0 <= i < N`，每个数据分区可以被细分为 N 个子分区，其中 digest 是记录的散列关键字。

由于摘要与其他记录元数据一起保存在内存中，因此对子分区中记录的成员资格的筛选表达式评估不需要访问 SSD 上的数据。因此，子分区查询仅读取其子分区中的数据，从而最小化跨多个子分区的 SSD 读取。该子划分方案允许任意数目的并行流。

使用此方案，Trino 工作节点中的大量并行任务可使用分区查询结合模过滤器表达式经由相等数目的互斥且共同穷举的拆分或流来统一拆分数据以供处理。适当的数据规模、吞吐量和响应时间可以通过调整群集大小以及每个节点连接的 SSD 设备数量来实现。

### 流访问

通过重复请求特定数量的剩余记录，可以在更小的区块流中检索和处理查询结果。

## Trino Connector

Aerospike Trino Connector 支持通过 Trino 访问实时数据，用于分析使用情形，如即席 SQL 查询、报告和控制面板。多个集群中的数据可以使用 Trino 的数据联盟一起查询，这也使得将 Aerospike 数据与来自其他来源的数据合并成为可能。

有关 Trino Connector 的更多详细信息，请参见博客文章[“使用 Docker](https://developer.aerospike.com/blog/deploy-aerospike-and-trino-based-analytics-platform-using-docker) 部署基于 Aerospike 和 Trino 的分析平台”和[“Aerospike Trino Connector–第二章](https://developer.aerospike.com/blog/aerospike-trino-connector-chapter-two)。

Starburst 是基于 Trino 的基于 SQL 的 MPP(大规模并行处理)查询引擎，使您能够在单台计算机、一组计算机、内部部署或云中运行 Trino。[博客“使用 Aerospike 和 Starburst Anywhere](https://developer.aerospike.com/blog/analyze-data-with-aerospike-and-starburst-anywhere) 分析数据”介绍了如何使用 [Starburst Enterprise](https://www.starburst.io) 。最近发布的 [Aerospike SQL 由 Starburst 1.1.0](https://download.aerospike.com/enterprise/download/connectors/aerospike-sql/notes.html#1.1.0) 提供支持[star burst Enterprise Platform(SEP)](https://docs.starburst.io/starburst-enterprise/index.html)，这是“一个完全受支持的企业级 Trino 发行版，它增加了集成、提高了性能、提供了安全性，并使您可以轻松地部署、配置和管理集群。”

## 其他 SQL 选项

应用程序可以通过其他几种方式通过 SQL 访问数据。

### 火花

您可以使用 Spark SQL 在 Spark 平台上操作 Aerospike 数据。Aerospike Spark 连接器提供从 Spark 到 Aerospike 集群的并行访问。

Spark SQL 合并了两种抽象:复制分布式数据集(rdd)和关系表，并用于操纵和处理 rdd 中的数据。在这些教程的[中可以找到从 rdd 导入和存储 Aerospike 数据的例子。](https://developer.aerospike.com/tutorials/spark)

关于 Spark 连接器的更多细节可以在博客文章[“使用 Aerospike 连接 Spark](https://medium.com/aerospike-developer-blog/aerospike-is-a-highly-scalable-key-value-database-offering-best-in-class-performance-5922450aaa78) ”和[“使用 Aerospike 加速 Spark 查询和谓词下推](https://developer.aerospike.com/blog/accelerate-spark-queries-with-predicate-pushdown-using-aerospike)”中找到

### JDBC

应用程序开发人员可以使用简单的 SQL 通过社区贡献的 JDBC 连接器访问 Aerospike 数据。请阅读博文[“介绍气塞式 JDBC 驱动](https://developer.aerospike.com/blog/introducing-aerospike-jdbc-driver)”中的更多细节

### 气塞式 API

需要 [Aerospike API](https://developer.aerospike.com/blog/aerospike-through-sql) 全部功能的应用程序可以使用 API 中可用的[SQL 模式]轻松实现特定的 SQL CRUD 操作。

Aerospike Database 的快速高容量存储和并行处理与 Trino 的分布式 SQL 查询引擎相结合，可加速大型数据集的查询处理。Aerospike 的混合内存架构(HMA)利用固态硬盘和 DRAM 来大幅扩展其集群中的 fast 存储容量。此外，Aerospike 将数据和处理分布在大量分区上，提供了高度的并行性。对于对 Aerospike 中数据的 Trino 查询，结果是大规模加速性能。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>