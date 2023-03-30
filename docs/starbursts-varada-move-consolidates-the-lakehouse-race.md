# 星爆的瓦拉达举动巩固了湖屋竞赛

> 原文：<https://thenewstack.io/starbursts-varada-move-consolidates-the-lakehouse-race/>

总部位于波士顿的关键数据湖/数据虚拟化公司 Starburst Data 上个月宣布收购总部位于特拉维夫的初创公司 [Varada](https://varada.io/) ，后者是一家专注于查询加速的提供商。两家公司都是专注于 [Trino](https://trino.io/) 的分析子组，Trino 是一个开源数据查询引擎，源自最初在脸书孵化的 [Presto](https://prestodb.io/) 项目。这两家公司的技术高度互补，产生了一个非常合理的整合，并对成功执行做出了良好的预测。

Starburst 实际上是专注于 Presto/Trino 技术的公司的创始成员。它雇佣了 Presto 最初的创造者，并诞生了 Trino 项目。Varada 也将其平台基于 Trino，但通过开发一个复杂的缓存、优化和索引层来改进原始技术。Trino 的大规模并行处理(MPP)查询引擎和 Varada 的查询优化层的结合意味着 Starburst 平台不仅可以分析大量数据和连接到各种支持系统，还可以提供高端查询性能，使其在数据湖领域更直接地与其他参与者竞争。

## 常识的合并

新的 Stack 与 Starburst 首席执行官兼联合创始人贾斯汀·博格曼(Justin Borgman)进行了交谈，他表示，他认为对 Varada 的收购“可以说是[它]可能进行的最明显的收购”，并对整合持乐观态度。关于 Varada，他告诉 New Stack“我们了解他们，我们知道他们的才华，我们是他们工作的忠实粉丝，他们基本上为我们的技术构建了…一个功能。因此，这可能是你见过的最快的并购后整合之一。”Borgman 补充说，“在 90 天内，这将在所有三种云上普遍可用，并准备推出。”

Borgman 表示，Varada 索引技术的加入将使查询速度提高 7 倍，而无需客户自己选择要索引的数据。Borgman 还表示，Varada 基于机器学习使用面向 SSD 的数据缓存，基于观察到的查询模式，减少了实际的查询工作，因此可以让客户在比其他情况下更小的 Trino 集群上运行。这反过来可以降低云计算的费用；事实上，Starburst 声称节省高达 40%。

性能提升和成本削减的结合使得 Starburst 将其即将推出的 Varada 平台定位为特别适合市场经济敏感时期的平台。

## 一丘之貉

Starburst 和 Trino 已经拥有 MPP，这是大多数数据仓库平台上的标准特性，并且能够连接到标准格式的数据，如 [Apache Parquet](https://parquet.apache.org/) 。加上 Varada 技术将带来的查询优化，Starburst 将自己置于更有利的位置，以承担所谓的数据湖库工作负载。

想想看: [Databricks](https://databricks.com/) ，lakehouse 范式的先驱，最近发布了其优化的 [Photon](https://databricks.com/product/photon) 引擎，并开源了其 [Delta Lake](https://delta.io/) 文件格式，该格式在 Apache Parquet 的基础上构建了事务一致性和时间旅行功能。Dremio[使用其 Parquet 和基于](https://www.dremio.com/) [Apache Arrow](https://arrow.apache.org/) 的 [Reflections](https://docs.dremio.com/software/acceleration/reflections/#:~:text=Reflections%20Overview%20Dremio%20maintains%20physically%20optimized%20representations%20of,the%20raw%20data%20in%20the%20underlying%20data%20source.) 技术进行快速查询，也支持 Delta Lake，但它是 [Apache Iceberg](https://iceberg.apache.org/) 的早期采用者，后者是一种具有类似功能的竞争开放格式。

[Cloudera](https://www.cloudera.com/) ，其数据湖技术基于 [Apache Impala](https://impala.apache.org/) ，其本身长期以来专注于将数据仓库查询引擎技术与开放格式的数据配对，就在上周[宣布](https://blog.cloudera.com/supercharge-your-data-lakehouse-with-apache-iceberg-in-cloudera-data-platform/)支持 Iceberg。雪花的平台一直是基于关系数据仓库技术，然而，在三周前的峰会上，雪花宣布它打算支持 Iceberg 作为自己数据存储格式的替代方案。同时，Starburst 的 Trino 引擎已经支持了 Delta Lake 和 Iceberg 格式。最初的 Presto 引擎也是如此，它也将 Ahana 带入了竞争的战场。

**也读作:**

## 围过来

似乎今天的数据湖和数据仓库平台越是与众不同，它们就越接近一组通用的标准和用例。这是科技领域的一个正常趋势，该领域已经有了大量投资，目前正在大力追逐企业客户。它还降低了这些客户的风险，因为它创建了一套共同使用各种开源技术的约定，增强了对这些技术的投资效率。

更广泛的问题是，Starburst、Dremio 和 Ahana 等只专注于数据湖的公司现在是否也需要承担流媒体、机器学习和数据治理工作负载，以便与 Databricks 和 Cloudera 等公司(或者就此而言，云提供商)竞争。就目前而言，专注并擅长某个专业可能更好。但是，总有一天，拥有一个完整的、跨工作负载的数据平台会成为竞争的必需品，而不仅仅是一个“好东西”

Cloudera 是 Brust 战略和咨询公司 Blue Badge Insights 的客户。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>