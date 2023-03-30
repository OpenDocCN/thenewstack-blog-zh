# TimescaleDB 侧重于查询能力和规模

> 原文：<https://thenewstack.io/timescaledb-focuses-query-power-scale/>

随着公司越来越不能接受在规模和查询能力之间做出选择，而是坚持两者兼顾，SQL 与 NoSQL 之争愈演愈烈。

时间序列数据库 [TimescaleDB](https://www.timescaledb.com/) 是最近加入这场竞争的一家公司，它诞生于一个名为 iobeam 的物联网平台。它由 [Ajay Kulkarni](https://www.linkedin.com/in/ajaykulkarni/) 和[普林斯顿大学计算机科学教授 Michael Freedman](https://twitter.com/michaelfreedman?lang=en) 共同创建，由纽约市和斯德哥尔摩的一群博士建造。

事实证明，物联网客户对他们为 iobeam 构建的数据库更感兴趣，因此该公司重新调整了重点，并更改了名称。他们在 3 月份开源了 [TimescaleDB](https://github.com/timescale/timescaledb) ，Freedman 在 [Strata+Hadoop World](https://conferences.oreilly.com/strata/strata-ca/public/schedule/speaker/225207) 上重点介绍了它。

## Postgres-Plus

IOT 平台 [iobeam](https://github.com/iobeam) 是 Spark 流应用的缓存。在与客户公司的合作中，创始人在一个系统上有 10 万个或更多的设备，需要一个地方来放置所有这些传感器数据。

Kulkarni 说:“我们想要的东西可以快速地提出问题，提供交互式监控图表，进行探索，但也是可扩展的。”

他们对当前的数据库产品感到失望——他们使用了一些 Postgres、Mongo 和 Cassandra——但被迫在 NoSQL 的规模和关系数据库的查询能力之间做出选择。

正如 Kulkarni 所说，“要么你可以得到连接、二级索引、非基于时间的聚集和谓词，要么你可以得到规模”。

最终，他们决定在有 20 年历史的 Postgres 基础上进行建设，因为它的可靠性和丰富的生态系统。用户不必学习新系统，Postgres 工具仍然有效。它与卡夫卡、Tableau、Pentaho 等融合在一起。还有一个查询地理空间数据的扩展。

它是一系列新数据库中的一员，包括基于分布式 SQL 的谷歌扳手、TiDB 和 FaunaDB。

“有一个钟摆摆向 NoSQL；现在，NoSQL 数据库增加了一个 SQL 层，所以现在“不仅仅是 SQL”然后是 NewSQL 世界，比如说[蟑螂](https://thenewstack.io/cockroachdb-1-0/)，某种程度上是扳手。我认为钟摆摆回来的部分原因是人们说，“你知道，可靠性真的很重要。”“Postgres 即使不是最可靠的数据库，也是最可靠的数据库之一，”库尔卡尼解释道

“我们不想重新发明轮子，或者更好的类比是，我们不想从头开始制造一款全新的汽车。我们有一辆相当可靠的车，我们想安装一个更好的引擎和一些其他部件，让它跑得更快。显然，这就是规模。”

## 成长中的市场

“时间序列过去是一种利基事物，你只能在少数行业看到——华尔街、devo PS——但现在它正在物联网、区块链和其他行业扩展，”库尔卡尼说。

时间序列需要高写入速率，但在物联网或类似应用中，它主要关注最新数据，而不太关注事务系统的更新能力。

“在时间序列数据(监控、开发运维、物联网传感器数据)中，工作负载主要是到达您系统的新数据。我不是给你发送一年前的数据，我是给你发送现在正在发生的数据，”弗里德曼解释说。

时间尺度在很大程度上依赖于时间和空间的自然划分。写入通常针对最新的时间间隔，并跨越与主数据索引相关的“分区键”，例如传感器数据、位置、客户或用户的设备标识符。

时标创建一个超表，将数据视为一个表，无论其大小如何，都可以像使用标准 SQL 一样进行查询，并将数据划分为跨越两个维度的小块。一篇关于这项技术的论文解释说，跨两个维度查询的能力开启了大量新的机会。

块由运行时动态创建，并在作为集群运行时放置在不同的服务器上。它们也可以自动分布在单台机器的磁盘上。

通过保持区块较小，内存中可以容纳更多数据，并且系统经过优化，可以访问尽可能少的区块，以限制延迟并提高吞吐量。它采用高度结构化的索引来实现快速高效的查询。

Freedman 说:“我们有能力横向扩展，而且即使在单个节点上运行，也能为运行数据和查询数据提供更好的性能。该公司在论文中概述的测试显示，它仅在一个节点上就超过了“普通”Postgres。

他是这样解释的:

“数据发生在两个维度上，时间和空间。因此，我们将网格划分为这些块，这些块分布在服务器上。如果您查看新写入的去向，那只是在最近的时间段内。所以这些是一直保存在内存中的。这一切对用户和管理员来说都是透明的。

“我们进行了许多优化，以确保它们‘大小合适’——它们适合内存，并具有良好的性能和查询性能。因为我们保留了足够的元数据，你可以像一张巨大的桌子一样与之互动。在封面下，我们绑定了一个查询规划器和执行引擎，因此如果有类似这样的查询，“告诉我我所有设备上的平均 CPU 负载，按每小时、每个位置分组，并按最高顺序排序”，这样我就可以交给 DevOps，这样我就可以找出一些节点是否行为不当或有什么不正常的地方。

“我们进行了优化，因此需要最少的块来(回答这个问题)。我们这样做是为了保持较小的延迟并获得良好的性能。那种查询，单节点传统数据库无法支持，句号。”

超表的优点是您不必担心写入正确的分区或正确的节点，当您查询数据时，它只是一个表。

Kulkarni 说，它保留了关系数据库的所有优点，尤其是吹捧连接的效用。通过连接，在查询时，您可以将时间序列和业务数据结合起来，两者可以共存。

“与 NoSQL 相比，有很多问题你不能支持，而在我们这里你可以，”弗里德曼说。

专题图片:[肖恩·马森提](https://www.flickr.com/photos/smemon/)的[时间](https://www.flickr.com/photos/smemon/4961717384/in/photolist-8ys6Hs-93GPYw-nkc4GF-nN3cfZ-7ndGEZ-5r97iL-7UTmVK-dZrrr-mLTYN7-54R5E1-5qhemo-gXvhUX-7CBSbv-5ZvVMf-fKm5e6-4xVdmq-dtgLMo-dNSmDa-88G64K-oeXqzE-5eqYC3-FkRMPS-9grNy-2qCXZf-8B9xrH-9SWqmg-7ASABK-5dLnHV-bqNgjC-RYEBSv-e4pR7-qEC1wW-6JMRS8-6DruhW-dMpjq-8jqbkg-3eKq11-bfxmie-bbihYr-bbihHz-9vJDWb-7vyF57-g12GCs-8fb3eg-erDaj-9UQbk-3Vm7JN-jRcDHD-5Xx3no-5MLX4y)，以**的 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>