# Concord 利用 Mesos 实现高性能流处理

> 原文：<https://thenewstack.io/concord-leverages-mesos-high-performance-stream-processing/>

大规模流处理数据的挑战正在催生一大批新技术，包括 [Flink](https://thenewstack.io/apache-flink-addresses-continuous-stream-processing/) 、 [Apex](https://thenewstack.io/apache-gets-another-real-time-stream-processing-framework-apex/) 和 [Samza](https://thenewstack.io/apache-samza-linkedins-framework-for-stream-processing/) 。

创造了 [Storm](http://storm.apache.org/) 的 Twitter 最近开源了其实时流处理引擎 [Heron](http://venturebeat.com/2016/05/25/twitter-open-sources-heron-its-real-time-stream-processing-engine/) 。初创公司 [Confluent](http://siliconangle.com/blog/2016/05/24/kafka-gets-a-stream-processing-engine-to-compete-with-spark-and-samza/) 刚刚为 [Kafka](http://kafka.apache.org/) 发布了一个实时分析模块，旨在减少实现流处理集群所需的时间，并使管理更容易。

Concord 是一个基于事件的分布式流处理框架，构建在 Apache Mesos 之上，它也加入进来，宣布了一个公开测试版。它标榜自己的优势是动态拓扑、多语言支持和高性能。

> “Storm 不是为处理我们想要运行的工作的灵活性而设计的，”— Shinji Kim

联合创始人兼首席执行官 [Shinji Kim](https://twitter.com/shinjikim) 表示:“就流应用而言，我们越来越多地看到，流处理作业变得越来越像微服务或需要一定灵活性、集群管理、监控和调试这些服务的能力的应用，这与在后台作为报告运行的 MapReduce 或 ETL 作业截然不同。

总部设在纽约市的三人团队——金、[亚历山大·加莱戈](https://twitter.com/gallegoxx)和[罗伯特·布拉福德](https://twitter.com/rblafford)——大约一年半前成立了这家公司。它从彭博贝塔公司和几个天使投资者那里筹集了数目不详的种子资金，其中包括 Mesosphere 的联合创始人和高管。

Apache Storm 和 Spark Streaming 等开源流处理系统专注于实时运行 Hadoop MapReduce 函数，而 Concord 将实时应用程序作为异步服务运行。

“我们成立了这家公司，因为我们在扩展 Apache Storm 时遇到了很多问题，我们在以前的公司为一个广告交换网络运行大规模流处理，”Kim 解释道。“我们将 Storm 从每天运行数亿个数据点扩展到每天数百亿个数据点。我们的基础设施每天都需要大量的工作。”

该公司将 Storm 用于多种用途，包括投放广告、欺诈检测等等。

“Storm 不是为处理我们想要运行的工作的灵活性而设计的，”Kim 说。

“我们研究了类似的解决方案，如 Samza、Spark 和其他解决方案，但我们无法让它在操作上非常稳定，同时又能灵活地进行更改。我们与处于类似阶段的许多其他公司交谈过，他们在游戏和其他广告网络中处理大量数据，但他们在消息队列的基础上建立自己的系统，他们自己的调度程序。对于他们来说，在为非常具体的目的构建之后，很难对其进行扩展。所以我们认为应该有更好的流处理器。”

她说这个团队从谷歌转轮中获得了很多灵感。

Kim 说，Concord 的核心是用 C++构建的，这提供了可预测的性能和可伸缩性，而其他流处理器是基于 JVM 的。Concord 的软件支持 Python、Scala、Ruby、Java C++并在 Mesos 之上进行原生移植。

它还支持动态拓扑，允许用户更改或扩展部分拓扑，而无需硬重启。

“在 Concord，因为我们将每个运营商视为其自己的 [Mesos](http://mesos.apache.org/) 任务或集装箱化环境，拓扑管理可以是动态的，这意味着在运行时，你可以改变你的拓扑，你可以改变代码，你可以根据需要扩展部分工作，而不必担心整个系统的停机时间，”她说。“这允许不同的团队进行更改，而不用担心出现集群范围的故障或影响其他工作。这使得利用流的实时应用程序的迭代时间更快。”

该系统也是高性能的。它声称吞吐量比 Storm 或 Spark 流快 10 倍，延迟只有几毫秒。Kim 说，该公司计划在未来几周内发布一篇博客文章，详细说明它是如何对这些数字进行基准测试的。

## **工作原理**

用户可以在一个高级逻辑层中创建一个操作符，让 Concord 负责在物理层中分配工作。这种逻辑可以在 Kafka 之上编写，经过处理，然后输出到 HDFS、MySQL 或其他网站。

在物理层，Concord 集群使用 Apache Zookeeper 存储发生故障时所需的元数据；Mesos Master，它提供并跟踪每个代理的状态，并与 Concord Scheduler 一起工作来扩展和缩减作业；每个操作符都部署在一个由 Mesos 代理操作的 Linux 容器中。

Mesos 代理中的 Concord Executor 包含操作符、跟踪引擎和路由器，它们决定将结果发送到哪里。

当 Matt Asay 在 TechRepublic 上撰文，向 Kim 询问 Concord 何时是其他选项的次优选项时，她说，“目前，Concord 最多进行一次处理，如果有一个节点或操作符出现故障，它将失去其本地状态/缓存。”然而，她补充说，它正在努力与卡夫卡集成，以支持“至少一次”

她告诉 Asay [Concord 最适合用于](https://www.techrepublic.com/article/could-concord-topple-apache-spark-from-its-big-data-throne/)“当你更喜欢性能而不是完美的结果时”，比如在程序化广告交易中运行实时竞价模型。

[中间层](https://d2iq.com/)是新堆栈的赞助商。

特征图片:[喷](https://www.flickr.com/photos/bradhigham/13487271684/in/photolist-mxPMYY-87wNFQ-gVzX4-knNnxy-9oMohj-5ZRXLy-5ZRYvQ-9sSVeg-t9Tb6-6sfoqw-9NE3XZ-4XN6sm-CkN9o-56Xh9-5s5gXt-5iqmSF-abdyPn-i3HuH-4U3oWb-e6ZcCE-a7HHvB-ipzUz-4XHQgZ-fkExw6-MQChQ-3dbg7P-aFQdwB-4hVwEr-6GLyHM-CpBKn-6sTPxr-nBJper-qxdmJ-nzXJQh-nisPag-nBJokc-nzXHSA-5Y32iu-92CKg4-pp7n4G-5soF6t-CqrhD-6dLUFr-nxUF1J-6k6xfu-aMZNUe-aMZNUa-rvU5TM-7d6xes-5hKqSc)由[布拉德海汉姆](https://www.flickr.com/photos/bradhigham/)授权 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>