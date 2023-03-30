# ScyllaDB 的增量变化:只是冰山一角

> 原文：<https://thenewstack.io/scylladbs-incremental-changes-just-the-tip-of-the-iceberg/>

渐进式改变是一件坏事吗？和生活中的大多数事情一样，答案是“视情况而定”特别是在技术领域，创新和可靠的概念和解决方案之间的平衡似乎倾向于前者。或者至少，这是头条新闻给人的印象。好消息是生活中除了头条新闻还有更多。

创新不是一蹴而就的，也不是一蹴而就的。在大多数创造性的努力中，团队长期不懈地工作，直到他们准备好与世界分享他们的成就。然后他们回到车库，继续工作，直到下一个里程碑完成。如果我们间歇地窥视车库，我们可能会把我们大部分时间看到的称为“增量变化”

ScyllaDB 团队在车库大门打开的情况下工作，并不一定是在成为头条新闻之后。他们认为，如果渐进式变革能够带来稳定的进步，那就没什么好回避的。与 ScyllaDB Summit 2022 发布 ScyllaDB 5.0 相比，“增量变化”可能是 2 月份 ScyllaDB Summit 2023 的主题。但这只是冰山一角，因为这里有比看上去更多的东西。

我采访了 ScyllaDB 首席执行官兼联合创始人多尔·拉奥尔(Dor Laor)来讨论这个问题。

ScyllaDB 团队在车库大门打开的情况下工作。看看 2022 年团队忙于什么[，以及高性能计算和存储的趋势和权衡。](https://thenewstack.io/scylladb-challenges-dynamodb-on-latency-and-pricing/)

*注:除了阅读文章，你还可以在本期播客中听到完整的对话:*

迷你播放器:

## 数据是实时传到云端的，ScyllaDB 也是

ScyllaDB 团队密切关注客户如何处理他们的数据。我在 2022 年注意到的是[的数据正在实时传到云端，ScyllaDB 5.0](https://www.zdnet.com/article/data-is-going-to-the-cloud-in-real-time-and-scylladb-5-0-is-going-with-the-data/) 也是如此。接着，我想知道这些趋势是否与它们以前表现出来的方式保持同步。

拉奥尔证实，答案很简单:绝对是。该公司的数据库即服务 ScyllaDB Cloud 在 2022 年的年增长率超过 100%。自 2019 年推出以来的短短三年时间里，ScyllaDB 云现已成为 ScyllaDB 的主要收入来源，超过 50%。

“每个人都需要拥有核心数据库，但服务是使用它最简单、最安全的方式。这个主题不仅在 ScyllaDB 中非常突出，在其他数据库中也是如此，有时甚至超出了具有其他类型基础设施的数据库。这很有意义，”Laor 指出。

类似地，ScyllaDB 通过其变更数据捕获(CDC)特性对实时更新的支持正在被大量采用。所有 CDC 事件都进入一个可以像普通表一样读取的表。Laor 指出，这使得 CDC 易于使用，也可以与 Kafka 连接器结合使用。此外，CDC 打开了另一种可能性的大门:不仅将 ScyllaDB 用作数据库，还可以作为 Kafka 的替代方案。

“并不是说 ScyllaDB 是卡夫卡的替代品。但是，如果你有一个数据库加上 Kafka 堆栈，有些情况下，你可以不在 Kafka 中排队，而是将它们推送到数据库中，你也可以在数据库本身内排队，”Laor 说。

这并不是因为卡夫卡本身不好。这里的动机是减少基础设施中活动部件的数量。[帕洛阿尔托网络公司做到了这一点](https://thenewstack.io/nosql-nomq-palo-alto-networks-new-event-streaming-paradigm/)，其他公司也纷纷效仿。Numberly 是另一个用 ScyllaDB 代替卡夫卡和 Redis 的例子。

## 高性能和无缝迁移

Numberly 是在 [ScyllaDB 峰会 2023](https://www.scylladb.com/scylladb-summit-2023/presentations/?siteplacement=thenewstack) 上展示的众多用例之一。其他的包括 Discord，Epic Games，Optimizely，ShareChat 和 Strava。浏览这些内容，会发现两个关键主题:高性能和迁移。

迁移是 ScyllaDB 作为 Laor 共享的典型采用途径。许多用户从其他数据库来到 ScyllaDB 寻求可伸缩性。由于 ScyllaDB 看到了许多迁移，它提供了对两个兼容 API 的支持，一个用于 Cassandra，一个用于 DynamoDB。还有几个迁移工具，比如 Spark Migrator，扫描源数据库，写入目标数据库。疾病预防控制中心也可能有所帮助。

虽然每次迁移都有其自身的复杂性，但当像 Discord 或 ShareChat 这样的组织迁移到 ScyllaDB 时，这一切都与规模有关。不和谐迁移了数万亿条信息。ShareChat 迁移了许多服务。事情会变得复杂，用户会做出自己的选择。一些用户在没有保持 API 兼容性的情况下重写他们的堆栈，甚至用另一种编程语言如 Go 或 Rust 重写他们的部分代码库。

Epic Games、Optimizely 和 Strava 都展示了高性能用例。史诗游戏是虚幻游戏引擎的创造者。它的发展反映了现代软件发展的方式。过去，使用虚幻游戏引擎就像下载一个二进制文件一样简单。如今，一切都是分布式的。Epic Games 通过提供参考架构和推荐栈与游戏厂商合作，厂商选择如何消费。ScyllaDB 在这个堆栈中用作分布式缓存，提供对存储在 AWS S3 中的对象的快速访问。

## 存储的海洋，筏和无服务器

ScyllaDB 越来越多地被用作缓存。首先，这是因为 ScyllaDB 不需要缓存，这使得 Redis 过时了。对于史诗游戏，需要在 S3 的基础上增加一个快速发球层。

Laor 指出，S3 工作得很好，具有弹性和经济性，但是如果你的应用程序有严格的延迟要求，那么你就需要一个缓存。这是业内许多人都知道的事情，包括 ScyllaDB engineering。正如 Laor 所分享的，ScyllaDB 中的 R&D 也在努力使用 S3 进行存储。正如他所说:

“S3 是廉价存储的海洋，但它也很慢。如果您能够将 S3 和快速存储这两者结合起来，那么您就能够打破计算和存储之间的关系。这为您带来了诸多好处，从极高的灵活性到更低的总拥有成本。”

这是 ScyllaDB 的 R&D 目前正在进行的一个关键项目，但不是唯一的项目。

在即将到来的开源版本 5.2 中，ScyllaDB 将拥有基于 Raft 的一致的事务模式操作。在下一版本 5.3 中，还将支持事务性拓扑更改。元数据强一致性对于以编程方式扩展集群和数据定义语言的经验丰富的用户来说至关重要。

这为 ScyllaDB 数据分片方式的改变铺平了道路，使其更具动态性，并带来更好的负载平衡。

在向无服务器发展的过程中，这些努力汇集在一起。在 ScyllaDB 峰会上提供了基于 serverless 的免费试用，并将在今年晚些时候全面推出。

## P99，生锈和超越

Laor 并不是生活在一个只有 ScyllaDB 的世界里。作为一个拥有 hypervisor 和 Linux Red Hat 背景的人，他欣赏 P99 的细微差别。P99 潜伏期是第 99 个百分位数。这意味着 99%的请求会比给定的延迟数快，或者只有 1%的请求会比 P99 延迟慢。

[P99 CONF](https://www.p99conf.io/) 也是 all things performance 上的一个活动名称，由 ScyllaDB 团队组织，但当然不限于他们。P99 CONF 是为痴迷于 P99 百分位和高性能、低延迟应用的开发人员准备的。在这里，开发人员可以深入了解情况，分享他们的知识，并实时关注性能。

Laor 说，鼓励参与者展示数据库，包括竞争对手，以及谈论操作系统开发、编程语言、特殊库等。

ScyllaDB 最初的前提是更快地实现 Cassandra API，用 C++而不是 Java 编写。

尽管 ScyllaDB 在 C++代码库上投入了大量资金，并随着时间的推移不断完善，但 Laor 也给予 Rust 很大的赞誉。事实上，他说，如果他们今天就开始实施，他们很可能会使用 Rust。与其说是性能原因，不如说是易用性。此外，许多 ScyllaDB 用户喜欢 Discord 和 Numberly 正在转向 Rust。

尽管任何明智的开发人员都不想抛弃经受住时间考验的代码库，但 ScyllaDB 也在拥抱 Rust。Rust 是 ScyllaDB 新一代驱动程序的首选语言。正如 Laor 解释的那样，未来 ScyllaDB 驱动程序的核心将会用 Rust 编写。由此，将衍生出其他特定语言的版本。ScyllaDB 还为其代码库的特定部分采用了 [Go](https://thenewstack.io/shaving-40-off-googles-b-tree-implementation-with-go-generics/) 和 [Wasm](https://thenewstack.io/scylladbs-take-on-webassembly-for-user-defined-functions/) 。

回到原点，有许多渐进的变化正在发生。也许如果车库门没有打开，我们只需要在精心编排的演示中看到成品，这些变化会积累更多的印象。显然，对 Laor 和 ScyllaDB 来说，这并不重要。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>