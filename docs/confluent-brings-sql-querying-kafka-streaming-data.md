# 合流为 Kafka 流数据带来 SQL 查询

> 原文：<https://thenewstack.io/confluent-brings-sql-querying-kafka-streaming-data/>

随着数据量的不断增长，处理这些数据的需求也在不断增加。Confluent 通过其阿帕奇卡夫卡的商业包装帮助企业处理永无止境的数据流。现在，在本周于三藩市举行的 [Kafka 峰会](https://kafka-summit.org)上， [Confluent](https://www.confluent.io/) 推出了一个新的开源项目，名为 KSQL，据说它将允许用户对流媒体数据应用 SQL 查询。

在这一举措中，Confluent 是越来越多的公司之一，如 SQLSteam，试图将 SQL 的严格性应用到实时数据分析领域。

Confluent 的首席技术官和联合创始人 Neha Narkhede 表示，KSQL 为企业提供了许多潜在的用例，从处理进入组织的数据到处理数据仓库和系统间数据传输的提取、转换和加载(ETL)等工作。

Narkhede 说，“KSQL 是 Apache Kafka 的完全交互式分布式 SQL 引擎。它可以让你对流经卡夫卡的无限流进行各种连续的流处理和转换。”

Narkhede 说，传统上，通过 Kafka 处理流数据需要开发人员编写 Java 或 Python 代码。KSQL 将数据开发人员和 SQL 专家带入了流处理领域。Narkhede 说，KSQL 将成为一个独立的产品，并且已经在 GitHub 上可用。该项目目前处于开发者预览阶段，应该在几个月后正式发布。

Narkhede 说 KSQL 与 ANSI SQL 相似，但不完全兼容。它是 SQL 的修改版本，专门为查询数据流而定制。在数据库中，SQL 用于查询过去的事务。

“从某种意义上说，这是把数据库翻了个底朝天，你开始查询未来，而不是查询过去，”Narkhede 说。“目前语法相当不错，但我们计划增加更多功能，比如在卡夫卡的主题中插入语句。”

虽然 KSQL 第一次将 SQL 引入 Confluent 的产品线，但它并不是第一个这样的基于流的 SQL 系统。例如， [Striim](http://www.striim.com/) 、 [Kinetica](https://www.kinetica.com/product/) 和 [SQLStream](http://sqlstream.com/) 等公司已经提供类似的功能将近十年了。事实上，SQLStream 已经在 Kafka 上提供了 SQL。

那么是什么让 KSQL 与众不同呢？Narkhede 说这是分布式处理模型。“KSQL 建立在 Kafka 分区模型之上。您可以轻松地在集群上分发查询，这样您就可以使用正常大小的盒子，像 Kafka 一样将它们耦合在一起。它与 Kafka 的基本构建模块紧密集成，能够并行运行多个查询。Kafka 负责一台机器停机时的负载平衡，以及查询如何随着时间推移而变化。”

例如，[下面是 ETL 工作的 KSQL 查询](https://www.confluent.io/product/ksql/):

|  | 

创建 流VIP _ actionsAS

SELECTuserid，  页面，action

FROM点击流 c userid=u。user _ id

其中。 级别=‘白金’；

 |

SQLStream 的首席执行官兼创始人达米安·布莱克(Damian Black)说，纳尔克赫德和她的团队一年前来参观过，显然当时正在做笔记。目前，他的公司最大的用户来源是[亚马逊 Kinesis](https://aws.amazon.com/kinesis/) ，它是使用亚马逊的 Kafka-like 流媒体系统和 SQLStream 的 SQL 处理系统构建的。他说 SQLStream 受亚马逊欢迎的原因是它的速度。

“事实是，我们的速度快得多，您需要的只是服务器数量的一小部分。我们的一个客户有一项工作需要 180 台服务器[运行[MapR](https://mapr.com/)]三个小时。我们需要 12 台服务器以 40%的速度运行来实时处理数据，”Black 说。

Black 说，在 Kafka 内部构建 SQL 处理的最大问题之一是 Kafka 是用 Java 编写的。SQLStream 实际上在 JVM 内部运行，但它是用 C++构建的，并且经过高度优化，不会在 JVM 中产生垃圾。这意味着 SQLStream 以真正的实时速度运行它的查询。

Black 说现在评论 KSQL 的能力还为时过早，但他提到另一个流 SQL 处理引擎，Apache Spark 的引擎是基于批处理的，不能实时处理查询。

SQLStream 也在 Kafka 上运行，所以 Black 说他的团队熟悉 Confluent 在那里的工作。“合流是一个伟大的信息系统。这就是我们使用它的原因。它是免费的，考虑到它是用 Java 编写的，它的性能很好。我们还与亚马逊 Kinesis 和 AMQP 合作。我们提供更丰富的体验。它不像 SQL，而是真正基于标准的 SQL。它是用 C++写的，是无锁的。32 位整数就是 32 位整数，”布莱克说。

自从八年前推出以来，SQLStream 一直在提供类似的功能。Black 说，他感觉自己像是市场的先驱，许多企业仍然刚刚意识到使用 SQL 进行流处理的潜力。

然而，对于大多数企业来说，决策过程的一个方面是这种系统将基于的云。然而，这可能意味着许多数据处理系统的巨大变化。Narkhede 说，她认为目前的增长很大一部分来自谷歌的云。这是由 [BigQuery](https://cloud.google.com/bigquery/) 的采用推动的，她说，这也是该团队正在努力将 Kafka 与 BigQuery 集成的原因。

这可能意味着数据处理方式的巨大变化，因为团队放弃了现场 IT 管理的方法，而倾向于简单地使用谷歌自己的按需服务。从这个意义上来说，KSQL 和 SQLStream 可能只是谷歌赢得市场之前的首选解决方案。这听起来可能对 Confluent 不利，但 Narkhede 说，她看到谷歌内部正在大力推动将 Kafka 引入系统，以便与 BigQuery 合作。

“BigQuery 让人们转向谷歌，”Narkhede 说。“[谷歌]希望卡夫卡与 BigQuery 合作。有很多人向他们要卡夫卡的作品，而 BigQuery 是吸引他们的地方。这是世界上最令人惊叹的数据系统之一。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>