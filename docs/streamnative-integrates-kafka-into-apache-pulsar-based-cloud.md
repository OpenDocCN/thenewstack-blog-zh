# StreamNative 将 Kafka 集成到基于 Apache Pulsar 的云中

> 原文：<https://thenewstack.io/streamnative-integrates-kafka-into-apache-pulsar-based-cloud/>

由 [Apache Pulsar](https://pulsar.apache.org/) 和 [Apache 簿记员](https://bookkeeper.apache.org/)提供支持的云原生事件流媒体平台的制造商 stream native】最近宣布其[stream native Cloud for Kafka](https://www.streamnative.com/cloudforkafka/)产品的 [beta](https://share.hsforms.com/1qi5-W7C0ReaiGz8aLLE_kQ3x5r4) 发布，该产品在云产品中集成了 [Apache Kafka](https://kafka.apache.org) 和 Pulsar。StreamNative 简要介绍了新的堆栈，解释了这两个看似竞争的流媒体平台如何融合在一起。

StreamNative 于 2019 年由前雅虎同事[思杰郭](https://www.linkedin.com/in/samuelguo)和[马泰奥梅里](https://www.linkedin.com/in/matteomerli)创立，他们是 Apache Pulsar 的最初开发者。大约 10 年前，这两个人从一开始就一直在研究这项技术。当时的目标是建立一个消息平台，将所有雅虎服务集中在一个系统中，并允许工作负载的可伸缩排队。当时可用的消息传递系统不符合雅虎的要求，包括处理跨工作负载的过多消息传递主题，以及提供多租户架构以简化基础设施管理。这些需求成为了 Apache Pulsar 的定义特征。

## 里面是什么

Pulsar 是一个开源的分布式消息传递系统，可以在广泛的用例中使用，通过将存储底层消息数据的资源与处理消息分发的计算资源分离，可以轻松地移动大量数据。

Pulsar 包括一个管理组件，支持内置的多租户和地理复制，用于在消息传递基础上复制数据。这种多层方法使得 Pulsar 特别适合云和容器化环境，这两种环境都将计算和存储的分离作为一个关键原则。

## 脉冲星 vs 阿帕奇卡夫卡:我们必须选择吗？

面向 Kafka 的 StreamNative Cloud 为在 Apache Kafka(几乎无处不在的分布式事件存储和流处理平台)上进行大量投资的组织带来了这些功能以及对大量主题的支持。面向 Kafka 的 StreamNative Cloud 允许用户保留和使用 Kafka 的 API、有线协议甚至其连接器，同时能够在后端充分利用 Apache Pulsar 及其自身的功能。

大约两年前，StreamNative 通过 Pulsar 上的[Kafka](https://github.com/streamnative/kop/blob/master/README.md)(KoP)为 Kafka 播下了 StreamNative 云的种子，这是开源 Pulsar 的先驱功能。现在，面向 Kafka 的 StreamNative Cloud 也将这一功能集成到了 StreamNative 的云平台中。

## 卡夫卡式的挑战

StreamNative 与许多投资 Apache Kafka 的组织合作，并表示这些组织已经看到了它的挑战。例如，StreamNative 表示，由于不同的组织或团队可能会使用完全不同的 Kafka 集群，因此很难在 Kafka 中以本机方式实施多租户，这反过来会产生大量管理开销。

[stream native 的首席架构师 Addison Higham](https://www.linkedin.com/in/addisonj) 评论道:“在微服务领域，你有许多不同的应用程序，[客户]将有各种各样的用例；例如，出于合规性和其他原因，他们需要对大量主题提供支持。海厄姆规定，对于卡夫卡，“如果你添加更多的主题，它会导致性能下降”，而且“…脉冲星…可以支持数百万个主题。”StreamNative 还解释说，Pulsar 提供了一个工作队列，用户可以根据需要连接任意多的消费者，而 Kafka 需要连接分区或主题，这通常会使复杂的计算变得困难，特别是在机器学习场景中施加了重大限制。

StreamNative 认为，有许多原因可以说明其新的 Kafka/Pulsar 产品可能会吸引已经投资 Kafka 的组织。Higham 说:“对于一些组织来说，这更多的是关于功能，而另一些组织则更多的是关于管理方面，而对于另一些组织来说，这是他们转向更具云原生特性的战略的一部分。在所有情况下，我们都看到 Pulsar 是一种解决他们问题的技术，现在我们支持 Kafka 的能力有助于简化迁移过程。”

## 简化流程

StreamNative 将面向 Kafka 的云产品视为将开源技术引入其完全托管的云服务并提供更完整解决方案的下一步。它认为该产品可以缩短 Pulsar 的价值实现时间，因为它使客户能够使用他们现有的应用程序，避免 Kafka 生态系统中的投资损失。

虽然启发 Apache Pulsar 创建的最初需求没有十年前那么紧迫，但 Pulsar 的许多核心价值主张仍然相关，对于一些组织来说，甚至可能比以前更相关。不足为奇的是，StreamNative 认为流媒体数据市场将会看到 Pulsar 应用的加速趋势。

虽然 Pulsar 的份额可能会增加，也可能不会增加，但有一点是明确的:即使 Kafka 不被用作原生消息后端，其 API、协议和连接器生态系统一起构成了事实上的行业标准。越来越多看似竞争激烈的技术和公司可能会支持这一标准。主要的云提供商已经这么做了，现在 StreamNative 也这么做了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>