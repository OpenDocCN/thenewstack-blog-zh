# 公司如何在生产中使用 InfluxDB 和 Kafka

> 原文：<https://thenewstack.io/how-companies-are-using-influxdb-and-kafka-in-production/>

查尔斯·马勒

查尔斯是 InfluxData 网站的技术营销作家。Charles 的背景包括从事数字营销和全栈软件开发。

[娱乐流媒体平台 Hulu](https://www.influxdata.com/customer/hulu/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04-25_spnsr-ctn_influxdb-kafka-in-production_tns) 需要一个解决方案来扩展其内部[应用和基础设施监控](https://www.influxdata.com/solutions/application-performance-monitoring-apm/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04-25_spnsr-ctn_influxdb-kafka-in-production_tns)平台，因为它的增长速度超过了每秒 100 万指标。

它创建的[解决方案](https://medium.com/hulu-tech-blog/how-hulu-uses-influxdb-and-kafka-to-scale-to-over-1-million-metrics-a-second-1721476aaff5)结合了两个开源工具——时序数据库 [InfluxDB](https://www.influxdata.com/?utm_content=inline-mention) 和事件流平台 Kafka。

不仅仅是像 Hulu 这样的全球企业能够获得世界级的工具和基础设施来实现他们的商业目标。即使是初创公司也可以“从货架上”获得合适的工具，而不是在内部创建它们，浪费开发人员的时间和资源。

对于许多公司来说，成功在于知道如何充分利用这些工具来解决团队最棘手的问题。在 [Kafka Summit 2022](https://www.kafka-summit.org/) 的筹备阶段，探索两个特定的开源工具如何协同工作是值得的:Kafka 和 InfluxDB。

在下面的文章中，您将对这两个项目有所了解，然后获得一些真实世界的例子，看看大公司是如何在生产中使用这些工具来解决问题的。

## 什么是 InfluxDB？

如前所述，InfluxDB 是一个开源的[时间序列数据库](https://www.influxdata.com/time-series-database/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04-25_spnsr-ctn_influxdb-kafka-in-production_tns)，设计用于处理[时间序列数据](https://www.influxdata.com/what-is-time-series-data/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04-25_spnsr-ctn_influxdb-kafka-in-production_tns)(也称为“时间戳数据”)。它针对处理正在写入的大量数据进行了优化，并提供了实时查询该数据的能力，而通用数据库由于设计上的权衡，如如何压缩数据和为涉及分析所需的特定时间范围内的数据的查询编制索引，可能难以达到类似的规模。

除了性能优势之外，InfluxDB 还提供了许多开发人员体验优势，使常见的时序工作负载更容易实现。这意味着内置的功能，如缩减数据采样、创建自定义警报以及专为处理时间序列数据而设计的 Flux 查询语言。

## 卡夫卡是什么？

[Kafka](https://kafka.apache.org/) ，活动流媒体平台，允许用户用他们的应用程序发布和订阅活动。Kafka 与提供类似功能的工具的区别在于内置的可伸缩性、容错和其他可用性功能，这些功能抽象出复杂性，使开发人员更容易操作。

Kafka 最初是由 LinkedIn 开发的，用于跨 LinkedIn 实时跟踪用户活动事件。在开源之后，Kafka 开始被广泛用于日志聚合、流处理、度量监控等用例，并作为分布式系统的消息代理。

## 公司如何一起使用 InfluxDB 和 Kafka

InfluxDB 和 Kafka 已经成为一种流行的组合，因为需要一种可以与 Kafka 一起扩展的数据存储。它们可以被视为补充工具，Kafka 可以处理组织的许多实时处理需求，而 InfluxDB 可以用于长期分析查询，或者将实时数据与历史数据相结合，以在需要时提供更多上下文。

因此，人们创造了许多工具来使 InfluxDB 和 Kafka 的集成变得更加容易。Confluent 创建了一个[连接器](https://docs.confluent.io/kafka-connect-influxdb/current/index.html)，它允许 InfluxDB 被用作数据存储，以及可以被推送到 Kafka 的事件源。

Telegraf metrics collector 代理还有一个专用的 [Kafka 插件](https://www.influxdata.com/integration/kafka-telegraf-integration/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04-25_spnsr-ctn_influxdb-kafka-in-production_tns)，它可以用于从指定的 Kafka 主题中提取消息，并将它们存储在 InfluxDB 中。您还可以使用 Telegraf 的其他处理器插件在存储之前转换或过滤数据。

以下是一些公司如何结合使用 Kafka 和 InfluxDB 的例子:

### 葫芦

[解决方案](https://medium.com/hulu-tech-blog/how-hulu-uses-influxdb-and-kafka-to-scale-to-over-1-million-metrics-a-second-1721476aaff5) Hulu 的团队为帮助其扩展内部监控解决方案而创建的解决方案使用 InfluxDB 作为存储层，在每个数据中心本地使用 Kafka 来保存指标，以防本地宕机。一旦问题得到解决，Kafka 持久化的数据可以被写入任何与其他数据中心中的集群不同步的 InfluxDB 集群。

### 欧洲原子核研究组织

[CERN](https://www.influxdata.com/customer/cern/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04-25_spnsr-ctn_influxdb-kafka-in-production_tns) 是一家研究机构，运营着世界上最大的粒子物理实验室——包括世界上最大、能量最高的粒子对撞机——大型强子对撞机。为了存储来自 ALICE 实验的数据，该组织使用 InfluxDB。在该实验中，CERN 的科学家正在寻找夸克和胶子在类似大爆炸的条件下如何相互作用。

爱丽丝实验包括监测原子在极端能量密度下如何相互作用。ALICE 以每秒 3.4TBs 的速度产生原始数据。该数据被压缩；然后用 InfluxDB 聚集和存储指标。 [Kafka](https://www.confluent.io/kafka-summit-london18/taming-billions-of-metrics-and-logs-at-scale-two-years-with-kafka-as-a-central-data-hub-for-monitoring-at-cern/) 被用作流处理管道的一部分，以聚合这些指标并发送原始数据进行归档。

### 罗宾汉

在线金融服务公司 Robinhood 使用 Kafka 和 InfluxDB 来支持其[异常检测平台](https://www.influxdata.com/customer/robinhood/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04-25_spnsr-ctn_influxdb-kafka-in-production_tns)。Kafka 用于通过 Telegraf 将数据发送到 InfluxDB，在那里数据被聚集和查询以创建预测并将这些预测与实际观察值进行比较。这些预测的结果被发送回 Kafka，在那里其他服务可以监听消息并根据这些预测采取行动。

## 包扎

InfluxDB 和 Kafka 都是非常通用的工具，在任何应用程序架构中都可以很好地相互补充。由于是开源的，这两个项目都有一个强大的工具和库生态系统，这些工具和库提升了它们的价值，超出了核心项目所提供的价值。

要了解更多关于 Kafka 和 InfluxDB 的信息，请查看我们的[资源页面](https://www.influxdata.com/kafka-event/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04-25_spnsr-ctn_influxdb-kafka-in-production_tns)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>