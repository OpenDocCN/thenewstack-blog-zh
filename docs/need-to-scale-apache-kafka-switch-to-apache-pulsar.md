# 需要缩放阿帕奇卡夫卡？切换到阿帕奇脉冲星

> 原文：<https://thenewstack.io/need-to-scale-apache-kafka-switch-to-apache-pulsar/>

今天，即使是最基本的 web 和移动应用程序也会消耗大量数据。交换和处理这些数据的关键是由事件驱动架构支持的消息传递系统。

事件驱动的系统使消息传递解决方案和处理具有可伸缩性和异步性。异步系统可以处理更多的请求，因为每个请求都在后台处理。

当一个请求被发送到服务器时，它被添加到一个队列中，在那里处理器将读取它。这使组织能够通过在单独的集群中处理请求，构建每秒接受数十万甚至数百万请求的系统。

业界已经产生了几个消息代理系统和主题驱动的[发布-订阅](https://pulsar.apache.org/docs/concepts-messaging/)(发布-订阅)平台，它们遵循这种事件和消息驱动的格式。 [Apache Kafka](https://kafka.apache.org/) 和 [Apache Pulsar](https://pulsar.apache.org/) 是两个广泛使用的分布式消息传递和[流系统](https://thenewstack.io/redis-pub-sub-vs-apache-kafka/)的例子。

Kafka 和 Pulsar 都是基于发布-订阅模式构建的，您可以使用该模式将消息传递到数千个连接的客户端。两者都提供了持久存储模型来确保消息不会丢失，并且都使用分区来存储和处理消息。

虽然 Kafka 和 Pulsar 在许多方面都很相似，但它们在功能上有一些显著的差异——特别是在管理大量数据、创建实时应用程序和大规模开发方面。

Kafka 提供了许多好处，但 Pulsar 对可扩展性和增长的支持是无与伦比的。在成长的某个阶段，最佳选择是不再试图优化卡夫卡，而是与它分道扬镳。在这里，我们将比较 Kafka 和 Pulsar 之间的差异，演示在使用 Kafka 时，可伸缩性的合理下一步是如何切换到 Pulsar。

## Apache Kafka 应用面临的挑战

Kafka 是软件架构中分布式发布-订阅模式的事实。使用 Kafka 的组织能够处理成千上万的消息，并同时将这些消息传播给几个消费者。

卡夫卡[有几个好处](https://www.upsolver.com/blog/apache-kafka-architecture-what-you-need-to-know)，但是在尝试规模化的时候也有一定的局限性。让我们探讨一下当您试图扩展用 Apache Kafka 构建的应用程序时将会面临的一些挑战。

### 存储限制

Kafka 的架构为您在 Kafka 中扩展应用程序带来了第一个挑战:存储。

有状态代理是组织发现难以扩展的第一个原因。Kafka 中的数据存储在[领导节点](https://stackoverflow.com/a/60837212/1762944)中，而数据的分区存储在本地磁盘上。数据被绑定到节点，Kafka 中的代理是有状态的。这意味着一旦首节点达到最大存储容量，群集就无法接受更多消息，除非增加基础架构存储。这具有挑战性，因为在不断增长的环境中，集群需要多次升级。

克服这一挑战的一种方法是购买大型存储集群，这非常昂贵。

此外，基于这种架构，一旦平台达到最大存储或内存限制，它就不能接受新的传入消息。这可能会给业务关键型应用程序带来巨大损失。卡夫卡的建筑设计是为了接受和传播大量的信息。长期数据存储不是首要任务。因此，扩展 Kafka 应用程序非常具有挑战性，因为它无法提供您需要的存储—至少在没有高昂价格的情况下无法提供。

### 消息处理的问题

管理 Kafka 很有挑战性，因为它不包括活动监控、处理消息和数据持久性所必需的功能。

Kafka 因无头信息广播系统而大放异彩，在这种系统中，你不需要在发送前改变信息。然而，假设您需要在将消息转发给消费者之前对其进行处理；这需要依赖额外的平台，这使得用 Kafka 处理消息更具挑战性和复杂性。

此外，其他平台(如上面列出的平台)的参与会显著增加数据交付系统的复杂性，因为流式平台的每个组件都需要维护，并且具有适用于整个集群的限制。此外，Kafka 集群的数据和消息持久性有限，因为您的数据需求会随着时间的推移而增长。

### 复杂的客户端库

企业主要使用 Kafka 为其提供流媒体服务。流式 API 编写在发布-订阅消息交付之上，以支持[独特的业务案例](https://stackoverflow.com/a/44041420/1762944)。Kafka Streams API 是一个独立的产品，提供面向企业客户的高级功能。Kafka Streams 最显著的特性，[事务](https://medium.com/lydtech-consulting/kafka-streams-transactions-exactly-once-messaging-82194b50900a)，帮助企业确保信息流产生的输出的一致性。因此，Kafka 为每个用例提供了两个独立的 API。

例如，Kafka 流库使企业能够提供“恰好一次”的消息传递。Kafka 和 Pulsar 提供的[交付保证](https://www.adservio.fr/post/apache-kafkas-delivery-guarantees)是:

*   至少一次
*   最多一次
*   正好一次

“恰好一次”交付保证了每条消息都有一个相关联的输出，这保证了在消费者崩溃的情况下消息得到处理。然而，这对于[消费者 API](https://kafka.apache.org/documentation/#consumerapi) 来说是不可能的，它允许应用程序从 Kafka 集群中的主题读取数据流，要求你编写平台中的大部分功能。这使得很难使用单个客户端库来满足您业务所需的所有功能，当您大规模工作时，这是不可持续的。

## 输入 Pulsar

对于上面强调的每一个卡夫卡式的限制， [Pulsar](https://thenewstack.io/apache-pulsar-a-unified-queueing-and-streaming-platform/) 都有解决方案。以下部分概述了 Pulsar 的一些优势。

### 持久数据存储

Pulsar 提供 Kafka 提供的消息流和发布功能，但增加了更长时间保存数据的能力。

Pulsar 使用 Apache Bookkeeper 提供数据存储持久性。簿记员维护数据，并帮助将数据持久性卸载到集群之外。您可以使用 AWS S3 等其他数据存储介质来存储数据，并超越本地磁盘的限制，这意味着您可以轻松扩展您的应用程序，而无需担心存储问题。

此外，Pulsar 包括一个[分层存储](https://pulsar.apache.org/docs/concepts-tiered-storage/)功能，有助于在热存储和冷存储选项之间移动数据；然后，只要业务需要，数据就可以存储在冷存储中。对于存储选项，群集不需要不断改变基础架构的大小。

Pulsar 还通过使一部分数据不可变，自动将旧消息从簿记员转移到更便宜的冷存储选项。不可变段可以移动到更便宜的存储中，有效地使 Pulsar 能够接受无限量的数据。

### 开发者体验

从开发人员的角度来看，Pulsar 为所有主要语言(Java、Python、Go 和 C#)提供了一个集成的、简单的客户端库。这些库有助于开发人员快速入门，这是大规模开发和发布应用程序的关键。Pulsar 的[二进制协议](https://pulsar.apache.org/docs/developing-binary-protocol/)根据需要扩展客户端库的特性，使库适合增长。(以下是可用的和官方支持的 [Pulsar 客户端库列表。](https://pulsar.apache.org/docs/client-libraries/))

### 脉冲星函数

[Pulsar Functions](https://pulsar.apache.org/docs/functions-overview/) 是一项开箱即用的功能，它使开发人员能够编写自定义代码来处理消息流中的消息，而无需部署像 Apache Heron、Apache Flink 或 Apache Storm 这样的系统。

Pulsar 函数在无服务器连接器框架 Pulsar IO 中使用，使得从 Pulsar 和向 Pulsar 移动数据更加容易。这个开箱即用的系统使 Pulsar 能够连接到外部 SQL 和 NoSQL 数据库，如 Apache Cassandra。

此外，这种消息处理是流原生的，这意味着消息在交付给消费者之前在集群内部被处理和转换。由于 Pulsar 功能是 Pulsar 消息传递系统的计算基础设施，因此它们支持业务级目标，包括开发人员的工作效率、简单的故障排除和操作的简易性，这些都是在大规模工作时对应用程序和团队性能至关重要的品质。

### 可量测性

除了上述功能和服务及其对可扩展性的影响，Pulsar 还提供各种功能，使其成为满足您企业的消息流和发布需求的可扩展选项。

Pulsar 的地理复制功能使 Pulsar 具有高度可扩展性。该群集将数据复制到全球多个位置，以备灾难导致应用程序停机时使用。支持同步和异步复制。与同步复制相比，异步复制速度更快，但提供的数据一致性保证更少。

Pulsar 使用每个主题一个代理的概念，确保同一个代理处理一个主题的所有请求。 [Pulsar 架构](https://pulsar.apache.org/docs/concepts-architecture-overview)展示了与 Kafka 集群相比，基于代理的方法如何提高系统性能。

## 包扎

Kafka 和 Pulsar 有一些相似之处，但在选择使用哪个平台时，尤其是当您需要可伸缩性时，有一些基本差异值得考虑。

Kafka 的架构、存储能力和可用性提出了许多挑战，这些挑战会抑制组织的发展能力。试图将 Kafka 集群扩展到某个点之外会变得非常昂贵，并且通常会比它的价值更麻烦。从它存储数据的方式到它支持消息转换的方式，Pulsar 是 Kafka 的下一代统一挑战者，它是为可扩展性而构建的。

[*了解 DataStax Astra Streaming*](https://dtsx.io/3htRWJh)*，基于 Apache Pulsar 构建，作为完全托管的服务交付。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>