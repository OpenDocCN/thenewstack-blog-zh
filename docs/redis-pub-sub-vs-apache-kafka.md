# Redis Pub/Sub vs. Apache Kafka

> 原文：<https://thenewstack.io/redis-pub-sub-vs-apache-kafka/>

Redis 是拥有许多数据类型的内存数据库的“瑞士军刀”[，](https://www.instaclustr.com/its-an-in-memory-key-value-store-its-a-database-its-redis/)[它经常被用于缓存](https://www.instaclustr.com/redis-java-clients-and-client-side-caching/)，但是它做的更多。它还可以作为一个松散耦合的分布式消息代理，因此在本文中，我们将研究最初的 Redis 消息传递方法 Redis Pub/Sub，探索一些用例，并将其与 Apache Kafka 进行比较。

## 1.Redis 发布/订阅

![](img/a149ca70ef5800d34bdcc18de5377506.png)

披头士风格的潜艇鸡尾酒。[图片](https://www.shutterstock.com/image-photo/fresh-lemon-yellow-submarine-blue-water-32171176)经 Shutterstock.com 授权使用。投稿人:[叶夫拉霍夫·瓦列里](https://www.shutterstock.com/g/valery_evlakhov)

“酒馆”这个主题在我的文章中频繁出现。在以前的一篇文章中，我写了一段在内地酒吧的对话，“阿帕奇动物园管理员遇到了用餐的哲学家，”在这篇文章中，我们正在调查 Redis Pub/Sub。这听起来像是某种受披头士启发的奇异的黄色潜水艇鸡尾酒，但 Pub/Sub 实际上是 publish/subscribe 的缩写，这是松耦合分布式消息传递系统的著名模式。

 [保罗·布雷布纳

Paul 是 Instaclustr 的技术布道者。他一直在学习新的可扩展大数据技术，解决实际问题和构建应用程序，并撰写关于 Apache Cassandra、Spark、Zeppelin 和 Kafka 的博客。Paul 在分布式系统、技术创新、软件架构和工程、软件性能和可扩展性、网格和云计算以及数据分析和机器学习方面拥有丰富的研发和行业经验。](https://au.linkedin.com/in/paul-brebner-0a547b4) 

[Redis 发布/订阅](https://redis.io/topics/pubsub)是 Redis 支持的最古老的消息传递模式，使用一种称为“通道”的数据类型，它支持典型的发布/订阅操作，比如发布和订阅。它被认为是松耦合的，因为发布者和订阅者彼此不了解。发布者将消息发布到一个或多个通道，订阅者订阅一个或多个通道。

一个通道可以有零个或多个订户，消息被传递给所有当前连接的订户。因此，Redis 发布/订阅非常灵活，支持多种拓扑，包括扇入(多个生产者，单个订户)、扇出(单个生产者，多个订户)和 1-1(一个生产者，一个消费者)。

到目前为止，这听起来像是一个相当典型的发布/订阅系统，但是，有一个特性非常重要，那就是“连接的”交付语义。

## 2.连接交付语义

连接交付功能，如收音机。无线电台不断地在不同的频率(频道)上广播，但是听众只能在他们的接收器被插入、打开并且他们被调到一个电台时才能听到广播。(“保持关注”可能是 Redis Pub/Sub 的座右铭)。

![](img/b4f723d74944e59f1137e3b3da75762e.png)

redis Pub/Sub——收听、插入、打开和收听。[图片](https://www.shutterstock.com/image-photo/tuning-92662957)经 Shutterstock.com 许可使用。投稿人:[埃弗雷特收藏](https://www.shutterstock.com/g/everett)

关联交付意味着:

1.  只有连接的订户才能接收消息。
2.  每个连接的用户都会收到每条消息。
3.  一旦消息被发送给所有当前订户，它就会从频道中删除(系统中没有“内存”)。

这意味着:

1.  如果用户取消订阅(断开连接)并在稍后再次订阅频道:
    1.  它将不会接收到它在断开连接时丢失的任何中间消息，并且
    2.  它不知道它是否错过了任何消息。
2.  如果当前没有订阅该通道的用户，消息将被丢弃，不会传递给任何订阅者。
3.  因此，传递语义是每个订户“最多一次”。
4.  因为消息在被删除之前必须发送给所有当前订户:
    1.  随着用户的增加，这将需要更长的时间。
    2.  这与无线电广播不同，后者目前以光速向范围内的每个接收器传送内容。

请注意，“断开”是有意设计的，但也可能是由于网络或客户端故障，因此可能是意外的，这也将导致潜在的消息丢失。

通过阅读 Redis 发布/订阅[文档、](https://redis.com/ebook/part-2-core-concepts/chapter-3-commands-in-redis/3-6-publishsubscribe/)和[其他文章](https://making.pusher.com/redis-pubsub-under-the-hood/)，似乎 Redis 使用推送通知来确保消息被传递给所有当前订户，这对于大量订户来说具有潜在的性能损失。

## 3.Redis 发布/订阅的用例

![](img/598a99e97e1847da2b3a9caf4912deea.png)

Redis 发布/订阅频道可以有多个订阅者，但是太多的订阅者可能会影响性能(不像真正的广播那样可以完美地工作于无限的接收者)。[图片](https://www.shutterstock.com/image-photo/vintage-radios-34992457)经 Shutterstock.com 许可使用。投稿人: [jimeone](https://www.shutterstock.com/g/robertochamorro)

Redis 发布/订阅“连接”交付语义的合适用例有哪些？

1.  实时、低延迟、紧急的消息:如果消息是短暂的并且迅速老化，那么，因此，只在短时间窗口内(基本上是“立即”)与订户相关。
2.  不可靠的传递/有损失的消息传递:如果由于不可靠的传递，一些消息被简单地丢弃(不重要的冗余消息，而不是唯一关键的“业务”消息)也没关系。网络和订户中的故障，或者从主服务器到副本服务器的[故障转移](https://support.huaweicloud.com/intl/en-us/ae-ad-1-usermanual-dcs/dcs-faq-0730011.html)，都可能导致消息被丢弃。
3.  要求每个用户最多发送一次(用户不能检测重复的消息，目标系统不是等幂的。)
4.  如果订户对频道有短暂的、不断发展的或动态的兴趣，并且只想在有限的时间段内接收来自特定频道的消息。例如，移动物联网设备可能只是间歇性连接，并且只对其所在位置的当前消息感兴趣和能够做出响应。
5.  如果订户——还有频道和出版商——本身也可能是短命的。
6.  每个频道有一个或多个用户，但是…
7.  每个频道只有少量的用户和模式。

## 4.Redis Pub/Sub 与 Apache Kafka 的比较

最后，我想知道阿帕奇卡夫卡能不能做类似 Redis Pub/Sub 的东西？卡夫卡能做:

### **1。向多个订阅者复制传递？**

是的。这对应了卡夫卡中的多个消费群体。发送到具有多个消费者组的 Kafka 主题的消息由每个组中的一个消费者接收。然而，为了确保每个用户群中只有一个用户收到每条消息，在 Kafka 中，每个用户群只有一个用户。

### **2。“无钥匙”信息传递？**

Redis 发布/订阅消息没有一个键，只有一个值，尽管在 Redis 中通道才是真正的键。

是的，因为钥匙在卡夫卡中是可选的。如果没有键，那么 Kafka 使用循环负载平衡算法在每个组中的可用消费者之间分发发送到一个主题的消息。如果只有一个消费者，那么这个消费者会得到所有的消息。

### **3。不可靠的消息传递？**

是的，Kafka 也可以做到这一点，因为 Kafka 的消费者可以选择什么偏移，或者时间，来读取，实现一些技巧，如重播相同的消息，从最后一次读取的消息可靠地断开连接，以及跳过消息等。Kafka 消费者对消息进行轮询，因此每次轮询时，他们可以选择从下一个(未读)偏移量开始阅读，或者，他们可以跳过未读消息，从结束偏移量开始阅读(使用 [seekToEnd()](https://kafka.apache.org/22/javadoc/org/apache/kafka/clients/consumer/KafkaConsumer.html#seekToEnd-java.util.Collection-) )，只阅读新消息。这当然不是 Kafka 的正常操作模式，但它在逻辑上是可能的，并且符合几种用例及操作要求，例如，如果消费者落后了，他们可以通过跳过消息来赶上，等等。

### **4。低延迟“即时”消息传递？**

Redis 发布/订阅是为速度(低延迟)而设计的，但只有少量的订阅者。订阅者不进行轮询，当订阅/连接时，能够非常快速地从 Redis 代理接收推送通知——在很短的毫秒内，[甚至不到 1 毫秒，如基准测试](https://gist.github.com/hmartiro/85b89858d2c12ae1a0f9)所确认的。

还要注意，一些文章报告 Redis 发布/订阅性能对消息大小很敏感；它适用于小消息，但不适用于大消息。

Kafka 的平均延迟通常只有几十毫秒。(在我们的[分区基准测试文章](https://www.instaclustr.com/the-power-of-kafka-partitions-how-to-get-the-most-out-of-your-kafka-cluster/)中报告的平均生产者延迟是 15 到 30 毫秒)。

Kafka[也不是为大消息](https://dzone.com/articles/processing-large-messages-with-apache-kafka)设计的，但它可以处理相当大的消息，甚至高达 1GB，特别是如果启用了压缩并且可能与 [Kafka 分层存储](https://cwiki.apache.org/confluence/display/KAFKA/KIP-405%3A+Kafka+Tiered+Storage)结合使用的话。

### **5。吞吐量？**

为了最大化 Redis 吞吐量，您需要管道化生产者发布操作，但是这将减少延迟，因此您无法通过 Redis 发布/订阅同时获得低延迟和高吞吐量。

Redis 大多是单线程的，因此提高代理并发性的唯一方法是增加集群中的节点数量。

另一方面，Kafka 消费者依赖于轮询，并可能批量处理消息，因此延迟可能会稍高，通常为几十毫秒。然而，由于 Kafka 消费者组和主题分区，可伸缩性更好，这支持由代理并发性支持的非常高的消费者并发性(多个节点和分区)。

### **6。耐用性和可靠性？**

只是提醒一下，Redis Pub/Sub 并不持久(通道仅在内存中)，但 Kafka 是高度持久的(它是基于磁盘的，并具有到多个不同节点的可配置复制)。

Kafka 还为成组的消费者提供自动故障转移——如果消费者失败，其他人会接管(但要小心[再平衡风暴](https://www.instaclustr.com/apache-kafka-kongo-6-3-production-kafka-application-scalng-on-instaclustr/))。并且 [Kafka Connect](https://www.instaclustr.com/apache-kafka-connect-architecture-overview/) 通过针对某些故障模式自动重启连接器任务[来实现更高的可靠性。鉴于 Redis Pub/Sub 没有用户组的概念，您在这里只能靠自己，并且需要以不同的方式处理这个问题，也许可以在](https://www.instaclustr.com/data-processing-pipeline-part-2/) [Kubernetes pods](https://www.instaclustr.com/anomalia-machina-7-application-deployment-kubernetes/) 中运行 Redis 订户客户端，并自动重启和缩放，等等。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>