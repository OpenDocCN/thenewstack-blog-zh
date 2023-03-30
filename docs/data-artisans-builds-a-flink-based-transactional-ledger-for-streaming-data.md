# Data Artisans 为数据流建立了一个基于 Flink 的交易分类账

> 原文：<https://thenewstack.io/data-artisans-builds-a-flink-based-transactional-ledger-for-streaming-data/>

[数据工匠](http://data-artisans.com/) ，开源项目 [Apache Flink](https://flink.apache.org/) 背后的公司，已经接手了一个令人头疼的流处理问题——一次只能处理一行事务。它引入了 [Streaming Ledger](https://data-artisans.com/streaming-ledger) ，这是一个位于 Flink 之上的库，在高性能系统中跨多个表、行和流提供可序列化的分布式 ACID 事务。

据 data Artisans 联合创始人 [Fabian Hueske](https://github.com/fhueske) 称，它源于金融服务客户的需求，而当前的流处理技术(包括 Flink)无法充分满足这些需求。然而，该公司预见了该技术的广泛使用案例。

“这些应用程序具有某种事务性行为，您必须访问和更新流式应用程序中的多行。到目前为止，流处理一直擅长为单行提供一致性，类似于键值存储。但我们的客户希望交易更类似于关系数据库系统——以一致的方式访问和更新多行，这对于键值存储也是不可能的，”他说。

他以将资金从一个帐户转移到另一个帐户为例，其中一个帐户可能在数据中心的一个节点上，而另一个帐户在另一个节点上。为了完成这个事务，你需要使用一个数据库或者[乐观并发控制](https://www.youtube.com/watch?v=yxct7c-UghU)，这对于流处理器来说是不可能的。

Streaming Ledger 为库存管理、定价、计费、供需匹配和物流等大规模应用提供了一致性和高吞吐量，而无需底层关系数据库。该公司预测，这项技术将为数据流架构带来一种全新的应用。

“欺诈检测、机器学习和实时交易定价等数据密集型实时应用现在可以毫不费力地升级到流媒体时代，”data Artisans 首席技术官 [Stephan Ewen](https://github.com/StephanEwen) 在一篇[博客文章](https://data-artisans.com/blog/serializable-acid-transactions-on-streaming-data)中写道。

## 并行，但在单线程上

众所周知，Flink 能够以低延迟处理非常大容量的流，并且只产生一次结果。包括阿里巴巴、网飞、优步、微软、荷兰国际集团在内的企业客户大规模使用它。分析师[贾纳基拉姆·MSV](https://thenewstack.io/author/janakiram/)之前概述了它如何对抗 Storm、Spark 和其他[阿帕奇流媒体项目](https://thenewstack.io/apache-streaming-projects-exploratory-guide/)。

Heuske 说，Streaming Ledger 保持高吞吐量和高性能，他指的是本白皮书中概述的一项测试，该测试使用全球分布式数据中心，基准测试为每秒 200 万次交易。

串流分类帐的核心构建块包括:

*   **表**在一个或多个键/值存储中维护状态。它们可以完全存储在内存中，也可以存储在 RocksDB 中。表的键和值可以是任何类型(结构化行、对象、blob 等)。)
*   **交易事件流** —分类账可以处理多个事件流。事件携带事务的“参数”——关于要修改什么数据以及如何修改的信息。
*   **交易功能**包含复杂的业务逻辑，用 Java/Scala 实现。它们被描述为“直接在管理数据的系统中执行的强大的存储过程，而不是取出数据并推回更新。”
*   可选的**结果流**可用于声明成功或失败，或者将更新发送到外部系统中的表镜像。

Heuske 说，流式分类帐要求用户预先声明交易功能，类似于在数据库系统中注册股票程序。

在他的例子中，“事件流将提供诸如从哪个账户取钱、将钱转移到哪个账户以及金额等数据。交易函数将接收这些事件，并读取应用程序中管理的一些状态，从源帐户中减去金额，将其添加到目标帐户中，并更新这两个帐户。因此，这个事务函数将执行两次读取，两次写入，并且所有的读取和写入将以一致的方式完成。许多交易将并行完成，但交易功能将确保它们以一致和可序列化的方式完成，”他解释说。

Streaming Ledger 不使用分布式锁或多版本并发控制，而是依靠状态访问的无冲突调度和轻量级逻辑时钟来实现高吞吐量。

Heuske 说:“它的行为就像是有一个单线程在处理所有这些事务，而实际上它们是并行进行的，以实现更好的性能。”Streaming Ledger 不是开源 Flink 项目的一部分，而是数据工匠企业 River 版的一个特性。然而，该公司已经在 GitHub 上发布了 Maven 模块，用于定义流媒体账本应用程序所需的 SDK 一个简单的串行运行程序，用于实验 SDK 和一些示例程序。白皮书还包括示例代码。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>