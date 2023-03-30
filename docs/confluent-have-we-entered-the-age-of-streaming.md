# 合流:我们已经进入流媒体时代了吗？

> 原文：<https://thenewstack.io/confluent-have-we-entered-the-age-of-streaming/>

三年前，当我们提出这个问题时，“[合流向何处去？](https://www.zdnet.com/article/where-is-confluent-going/)”，当时公司还处于独角兽阶段。但那时, [Apache Kafka](https://kafka.apache.org/) 正成为云时代默认的发布/订阅消息引擎。当时，我们与知名度更高的 [Spark](https://spark.apache.org) 进行了比较。从那时起，Confluent 已经进行了 IPO，而 Databricks 继续坐拥巨大的现金储备，因为它将自己定位为雪花在数据仓库方面的竞争对手。脉冲星最近成为一个竞争项目，但是游戏结束了吗？超大型企业正在提供类似亚马逊 Kinesis、Azure Event Hub 和谷歌云数据流这样的替代产品，但是你猜怎么着？ [AWS 共同市场融合云](https://www.confluent.io/blog/aws-and-confluent-announce-strategic-collaboration/)，与[微软 Azure](https://www.confluent.io/blog/confluent-microsoft-announce-strategic-alliance/) 的类似安排正在进行中。

更重要的是，今天的问题不是关于合流或卡夫卡，而是，流媒体将成为规范吗？

## 鸡和蛋

在上周大流行后的第一次会议上，首席执行官 Jay Kreps 用电作为比喻来宣传流媒体。克雷普斯认为流媒体是下一波先有鸡还是先有蛋的应用的关键。也就是说，当电被发明出来的时候，除了取代水或蒸汽动力，没有人想到其他的用途，但是后来，灯泡真的出现了。因此，除了对实时信息重要性的概括，Kreps 断言，流媒体的用例将很快变得显而易见，因为世界是实时运行的，即时可见性正在成为赌注。

换句话说，回想起来，传统观点会问为什么我们一开始没有想到实时。

这里有一定的讽刺意味:流媒体只是卡夫卡的一部分，因为这个系统的关键实际上是关于 PubSub 的。而阿帕奇卡夫卡的架构方式，你几乎可以即插即用任何流媒体服务；你不局限于卡夫卡流。至于 PubSub，这里真正的新内容是什么？第一个 PubSub 实现早于. com 时代。

早在 20 世纪 90 年代，Tibco 就开创了一个技术的商业市场，而资本市场公司以前都是自己发明的。[Tibco 的首席执行官兼创始人 Vivek Ranadive](https://www.linkedin.com/in/vivekranadive/) 写了一本关于此事的书，书名为[回到网络时代，现在的力量](https://www.amazon.com/Power-Now-Companies-Real-Time-Technology-ebook/dp/B000FA5L6S)。Tibco 后来将这一信息提炼为“2 秒钟的优势”前提是，即使你没有所有的信息，如果你比其他人提前两秒钟获得足够的信息，这应该会提供竞争优势，如果你在操作实时用例，如资本市场 tickers 任何形式的网络管理(想到电信和供应链)；现在是 90 年代，电子商务。

## 什么变了？

Kafka 为商用硬件上的大规模分布式规模重新发明了 PubSub 消息传递，并且与 Tibco 和 IBM MQ 时代不同，它是开源的。好吧，Kafka 不是第一个开源信息系统。但是它巨大的并行性让兔子 MQ 和 Java 消息服务望尘莫及。尽管 Kafka 最初不是为云而设计的，但它的横向扩展分布式架构预见到了这一点。[尽管如此，商业支持和相关开源项目的临界质量生态系统使 Kafka 成为云原生环境的 PubSub 技术的事实。至于在获得所有信息之前的两秒钟优势的旧观点，今天的大管道和云规模使这个问题变得学术化。](https://thenewstack.io/apache-pulsar-a-unified-queueing-and-streaming-platform/)

底线？根据阿帕奇软件基金会的数据，今天，大约 80%的财富 100 强公司使用 Kafka。

## 但是我们谈论的是流媒体

虽然 PubSub 是卡夫卡成功的关键，但上周在[召开的当前会议](https://thenewstack.io/confluent-brings-visual-design-to-kafka-based-data-streams/)的首要主题是预示流媒体时代的到来。Confluent 的观点是，流媒体将成为分析的新规范，因为世界是实时运行的，分析也应该如此。它从 Expedia 等参考客户那里获得了旅游定价的用例；美国邮政服务，用于处理来自其网站的免费 COVID 测试请求；和 Pinterest，用于实时内容推荐。

但是，是不是每个公司都像 Pinterest 这样的天生在线公司，或者像邮政服务这样的国家公用事业公司？这不禁让人联想到这样一个问题，是不是每个公司都是网络公司，还是每个公司都需要我们过去称之为“大数据”的东西这些隐喻 Confluent 可能不会反对，因为今天，任何 B2C 或 B2B 公司没有在线业务都是不可想象的，更不用说处理许多“大数据”的“Vs”现在已经成为 Redshift 或 Snowflake 等云分析服务的例行公事。

尽管如此，流媒体是否已经成为一种新的规范仍然是一个值得讨论的问题。我们非常赞赏 Confluent 在其活动中为不同观点腾出空间。一个障碍是观念问题。在他的会话中，[流仍然不是默认的](https://2022.currentevent.io/website/39543/agenda/)。Decodable 首席执行官 Eric Sammer 提出了为什么大多数分析系统仍在批量运行的问题。他搜寻了一些合理化建议，比如特定的用例不需要流。雪花工程师[丹·索托隆戈](https://www.linkedin.com/in/sortalongo/)和[泰勒·阿基多](https://www.linkedin.com/in/takidau/)在流媒体 101 的会议上强化了他的评论。

但是深究下去，还有对未知的恐惧。根据 Sammer 的说法，流媒体技术仍然比批处理技术更复杂。目前，您仍然需要编排多个组件，如消息代理、流处理格式和连接器；这是一个类似于动物园动物管理的问题，限制了 [Hadoop](https://thenewstack.io/will-kubernetes-sink-the-hadoop-ship/) 的采用。罪魁祸首不是核心的 Kafka 技术，而是工具分散且太低级的事实。架构师和开发人员必须处理底层参数，例如缓冲区大小(影响异常检测)，区分事件和处理时间(确保提要正确排序)；以及用外部一致性管理事务一致性。

## 卡夫卡会变得不那么卡夫卡式吗？

地平线上有好消息。Apache 项目正在用一个名为 [KRaft](https://developer.confluent.io/learn/kraft/) (基于 Raft 共识协议)的内部功能取代 [Zookeeper](https://zookeeper.apache.org/) ，这是 Hadoop 时代用于管理分布式配置的相同工具，现在已经进入早期使用阶段。Sammer 说他希望 Apache 项目通过构建自己的模式注册中心走得更远。我们不会争论。正如数据库隐藏了大量的原始资料一样，我们希望在卡夫卡身上看到更多。开源项目和工具生态系统都有负担。对于卡夫卡 SaaS 提供商，我们希望他们提供无服务器服务。

Confluent 的增长并不仅仅依赖于 Kafka——如果是这样，其云服务可能不会逐年增加一倍以上，因为每个超大规模公司都提供自己的托管 Kafka 服务。像 Databricks 一样，它专注于构建一个端到端的平台，统一原本复杂的工具链。他们构建了自己独特的 Apache Kafka 实现，对存储进行抽象和分层，使服务比通常的附加块存储更加灵活和经济。他们专注于简化一项技术的用户体验，因为这个问题是卡夫卡式的。

Confluent 使得 Apache Kafka(它是为 Java 编写的)可以被 Python 和其他语言的开发者访问；提供超过 100 个[开箱即用的连接器](https://www.confluent.io/product/connectors/)，并提供他们自己的流 SQL 引擎。大会上宣布了针对无代码/低代码人群的新的[流设计器](https://www.confluent.io/blog/building-streaming-data-pipelines-visually/)和新的增强版[流治理](https://www.confluent.io/blog/new-confluent-cloud-features-stream-designer-governance-and-more/)。它们包括使用全局可用模式注册中心进行流治理；现在包含业务元数据的目录；并将时间点回放能力添加到数据沿袭中。在操作简化的主题中，我们希望看到合流简化可观测性的设置；例如，客户不应该用[专门建立他们自己的时间序列数据库集群](https://docs.confluent.io/platform/current/tutorials/examples/ccloud-observability/docs/observability-overview.html#ccloud-promo-code)来跟踪性能；Confluent 表示，目前对大多数客户来说，这种能力是多余的。我们这样说是出于严厉的爱；Confluent 在使 Kafka 企业就绪方面取得了重要进展。

## 切入正题:流媒体准备好了吗？

汇合、雪花和超大规模有助于揭开我们过去称之为“大数据”的神秘面纱并降低其壁垒见鬼，甚至 Cloudera 也帮助我们忘记了动物园的动物。是的，仍然存在流特有的操作复杂性，但话又说回来，我们在分析大量和各种数据时也说过同样的话。这是一个学习的过程。

更大的问题是，流媒体是会跨越鸿沟，还是会跃入企业。我们视分析为一个光谱或需求，这取决于用例，答案不一定是一成不变的。例如，如果您的大部分业务都是在线的，这并不一定意味着它必须实时驱动。最大的例子可能是大型、高价值的资本货物，在这种情况下，订单不太可能像人们期待已久的新款必备移动设备那样激增。另一方面，即使您的组织交付的产品或服务可能不会随着每分钟的变化而变化，但您业务的某些方面可能会变化。例如，大型资本货物制造商可能会在其供应链中出现快速、短暂的异常值，从而影响长期规划。

我们对汇合者行动号召的回应？流媒体并不是一个闪亮的新事物，但它是大多数组织运营业务所需的新难题之一。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>