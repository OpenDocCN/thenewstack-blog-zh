# VoltDB 增加了地理空间支持、跨站点复制

> 原文：<https://thenewstack.io/voltdb-adds-geospatial-support-cross-site-replication/>

VoltDB 是一个内存数据库系统，它正在扩大自己的影响范围。

最新发布的分析数据库版本 6 提供了地理空间支持和许多其他好东西，以帮助 VoltDB Inc .将其软件称为“快速数据”的方法。VoltDB 在单个横向扩展平台中将流分析与事务处理相结合。

新版本增加了

*   地理空间查询支持；
*   改进的数据接收和导出连接；
*   跨数据中心“主动/主动”复制；
*   VoltDB 管理中心，包括对集群管理、工作负载平衡和监控的增强。

地理空间支持提供了“你能做的事情的一个全新的维度。VoltDB 首席营销官 Peter Vescuso 说，你可以个性化体验”等等。

VoltDB v.6 现在支持两种新的数据类型——GEOGRAPHY 和 GEOGRAPHY _ POINT——来表示多边形和处理多边形的点，一组定义购物中心或体育场等区域的纬度/经度点，VoltDB 的 John Piekos 在一篇博客文章中解释道。

它还提供了通过添加地理空间列功能来查询它们之间的关系的能力，包括包含、距离和面积等。

例如，一个应用程序可以指引出租车司机找到活动地点，在那里他们可以找到大量的潜在客户。Piekos 提供了一个 SQL 查询示例，它给出了每个公共场所附近的与会者人数。

威斯库索说，HPE、OpenNet、诺基亚等客户拥有世界上最苛刻的环境，他们也对耐用性有很多要求。

“我们最近完成了一系列我们称之为跨数据中心复制的功能。这意味着你可以有独立的数据库实例，你可以使用基于东海岸和西海岸业务的移动应用程序进行本地交易和承诺。假设你是威瑞森，你有一个东海岸的客户去三藩市旅游，该客户需要看到真正快速和互动的性能，否则该客户会不高兴。实现这一点的一个方法是分布不同的数据库，这样你就可以在本地提供性能，”他说。

“跨数据中心复制使您能够分离数据库、维护它们、保持它们同步，并实现性能优势和/或您可以将这种能力用于灾难恢复，”Vescuso 说。

在解释“主动/主动”复制时，VoltDB 软件工程师 John Hugg 说，VoltDB 的电信客户最希望的事情之一是能够写入本地数据中心。

“如果他们让 Volt 在离他们很近的数据中心运行，让 Volt 在离其他客户很近的数据中心运行，我们现在的工作就是同步这些数据。我们与应用程序开发人员合作完成这项工作。转向“主动/主动”世界，我们需要同步复制，而不是异步复制。应用程序有可能在两个地方覆盖相同的数据。因此，我们给开发者工具，试图避免这种情况，并在发生时减轻这种情况，”他说。

“在 NoSQL 领域，有很多系统在尝试这样做。Volt 的优势之一是它在单个数据中心上是完全事务性的、完全可序列化的 ACID。我们将只复制提交的事务。因此，可以进行一些检查，并在您的跨数据中心逻辑中包含该业务逻辑。如果你继续这种商业逻辑，它只会被复制。在 Volt 上构建主动/主动应用程序当然需要更多的工作，但我们相信这比在大多数其他系统上构建主动/主动应用程序更容易。”

新版本还包括与大数据流软件 [Kafka](https://thenewstack.io/confluent-2-0-bringing-kafka-0-9-features-enterprise/) 的直接集成，因此开发人员可以直接导入数据，在其上进行交易，并通过与 Elasticsearch 的直接集成以相同的速度导出数据。

## **让应用程序更快、更智能**

VoltDB 实现了一种下一代应用，即可以利用直播数据并从中获利的应用。Vescuso 说，应用程序继承了平台的很多健壮性，容错性，否则开发者必须自己解决。

“每个人都在谈论大数据。他说，我们专注于快速数据——实时流媒体数据，前端”，并为快速数据提供应用开发平台。

“我们一直在增强 VoltDB 处理大容量、高速度数据的能力。快速接收、处理这些数据，这就是我们所说的针对这些数据的明智决策，并最终将其导出到下游的长期数据存储中。”

VoltDB 的客户，包括惠普、诺基亚、Aipush 和其他公司，使用 VoltDB 来确定何时向 MMPG(大型多人游戏)玩家提供游戏内优惠；何时向谁投放合适的广告；和定价方面做出毫秒级的决策。

Vescuso 表示，其客户 [Emagine International](http://www.emagineinternational.com/) 提供移动营销平台，VoltDB 的响应时间为毫秒，而眨眼时间为数百毫秒。

“我们让应用程序变得更快，我们让它们在实时做什么方面变得更智能，它们也更简单，因为它们利用了 VoltDB 下的平台，volt db 是一个一致的事务性操作数据库，是一整套分布式数据基础设施，开发人员可以依赖它们，而不必构建自己的基础设施，”Vescuso 说。

它承诺为开发人员简化基础设施，开发人员可能正在拼凑开源基础设施来支持他们的应用程序。

Hugg 说:“VoltDB 的大规模运行具有速度更慢、数据库更小的特点。

“如果你习惯了 Oracle 或 Postgres 的一致性，它们就不会达到你想要的水平。人们经常求助于流媒体系统、NoSQL 系统和分片系统。也许他们把《暴风雨》、《卡珊德拉》和《卡夫卡》结合起来了。可能是火花和雷迪斯。在许多情况下，这些应用程序可以构建在 VoltDB 上。它的设计非常易于管理。”

大量的新数据库正在涌现，如[cocroach db](https://thenewstack.io/cockroachdb-unkillable-distributed-sql-database/)、 [Riak KV](https://thenewstack.io/riaks-nosql-database-and-its-new-fit-with-apache-mesos/) 、 [Splice Machine](https://thenewstack.io/splice-machine-hybrid-sql-system-fuses-transactions-analytics/) 以及具有地理空间功能、图形支持等功能的 Aerospike。Orchestrate 的首席执行官兼联合创始人 Antony Falco 告诉新的堆栈，生产中可能有 35 到 40 个 10 年前不存在的数据库。它们被用来检测欺诈，瓦解有组织的犯罪，并且在几年前还是不可想象的。

分析师 Tim Crawford 说，虽然他还没有深入研究这些新数据库的细节，但似乎更多的是为特定目的设计的。

“这可以很好地服务于那些导致(特定)垂直的应用。这也可能标志着‘通用’数据库的减速——而不是消亡，”他说。

HPE 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>