# Kafka 替代 Pulsar 统一了流和队列

> 原文：<https://thenewstack.io/kafka-alternative-pulsar-unifies-streaming-and-queuing/>

阿帕奇软件基金会最新获得[顶级](https://globenewswire.com/news-release/2018/09/25/1575494/0/en/The-Apache-Software-Foundation-Announces-Apache-Pulsar-as-a-Top-Level-Project.html)地位的项目 Pulsar ，被拿来与 ASF 的另一个项目[卡夫卡](https://kafka.apache.org/)做比较。

Pulsar 是一个在商用硬件上运行的高可伸缩、低延迟的消息平台。它提供了简单的主题发布-订阅和队列语义、轻量级计算框架、订阅者的自动光标管理以及跨数据中心复制。

与此同时， [2018 Apache Kafka 报告](https://www.confluent.io/apache-kafka-report/)调查了 600 多名用户，发现数据管道和消息传递[对该技术的两大使用](https://thenewstack.io/this-week-in-numbers-apache-kafkas-metamorphosis/)。随着微服务架构的兴起，它得到了越来越多的应用。

“这两个系统的用例有很大的重叠，但最初的设计非常不同，”它的创始人之一 [Matteo Merli 说，他后来成立了一家提供快速数据平台的初创公司 Streamlio。](https://github.com/merlimat)

雅虎创建 Pulsar 作为一个单一的多租户系统，以解决其与多个消息系统和多个团队部署它们有关的问题。

它于 2016 年将其作为开源发布，并于 2017 年 6 月进入 ASF 孵化器。大约四年来，它一直被用于雅虎的应用程序邮件、金融、体育、双子广告和雅虎的分布式键值服务 Sherpa。

在一篇博客文章中，联合创始人郭思杰这样总结脉冲星和卡夫卡:

“Apache Pulsar 将高性能流(Apache Kafka 所追求的)和灵活的传统排队(RabbitMQ 所追求的)结合到一个统一的消息模型和 API 中。Pulsar 为您提供了一个用于流和队列的系统，具有相同的高性能，使用统一的 API。”

梅里说:“分流和排队是有区别的；在很多用例中，你需要其中的一个，但大多数人在不同的用例中都需要这两个。”

## 双层架构

Merli 说，双层设计是 Pulsar 的关键。有一个接收和发送消息的无状态代理层，以及一个有状态的持久层，其中有一组称为 bookies 的存储节点，提供低延迟的持久存储。

Merli 说，Pulsar 是建立在拥有强大数据保证的理念上的。它是为共享消费而设计的，而卡夫卡不是。Pulsar 使用户能够为消息配置一个保留期，即使在所有订阅都使用它们之后。

其分层体系结构和以段为中心的存储提供了关键优势:

*   您可以独立扩展代理或存储层。
*   由于代理是无状态的，主题可以很快转移到其他代理。这为平衡经纪人之间的流量开辟了一条有效的途径。
*   在同一个分区上可以有多个消费者，并且您可以根据需要添加任意多的消费者。

由于没有数据存储在本地，因此在扩展容量时无需复制分区数据，也不需要重新平衡。创建分区主题时，Pulsar 会以不可知的方式自动将数据划分给消费者和生产者。

代理将消息数据发送到多个簿记员节点，簿记员节点将数据写入预写日志，并在内存中保留一份副本。在节点发出确认之前，日志被强制写入稳定存储，这样即使断电也能确保保留。主题分区可以扩展到整个 BookKeeper 集群的总容量，并且您可以通过简单地添加节点来扩展集群。

Merli 说，自从进入孵化器以来，一个关键的焦点就是让 Pulsar 更容易上手。

Pulsar 的 2.0 版本于 6 月发布，包括一个名为 Pulsar Functions 的“流原生”处理功能，允许用户在数据通过管道时用 Java 或 Python 编写处理函数。版本 2.2 将很快发布，它将以交互式 SQL 查询为特色。

Pulsar 提供多种语言和协议绑定，包括 Java、C++、Python 和 WebSockets，以及 Kafka 兼容的 API。

在之前的一篇帖子中，[贾纳基拉姆·MSV](https://thenewstack.io/author/janakiram/)看了一下 ASF 的各种流媒体项目，包括卡夫卡、[、【风暴】T3、](http://storm.apache.org/)[火花](http://spark.apache.org/)、[萨姆扎](http://samza.apache.org/)、[光束](https://beam.apache.org/)等。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>