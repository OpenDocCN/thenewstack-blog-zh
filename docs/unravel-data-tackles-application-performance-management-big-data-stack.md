# 解开数据难题大数据堆栈的应用程序性能管理

> 原文：<https://thenewstack.io/unravel-data-tackles-application-performance-management-big-data-stack/>

大数据是否需要自己的应用性能管理(APM)平台？[解开数据](http://unraveldata.com/)相信是这样的，引用了管理分布式计算和并行处理应用程序的复杂性。

它旨在简化大数据堆栈中的所有操作。

“这真的很复杂。有一大堆:Hadoop、Spark、Impala、Cloudera、Hbase、Kudu……市场上严重缺乏人才——没有人知道如何真正做好数据工程和数据科学，”Unravel 首席执行官 [Kunal Agarwal](https://www.linkedin.com/in/kunalkunal/) 说。

旧的 APM 工具收集所有日志、指标并创建图表和仪表板，然后说，“这是您的系统中发生的情况。你去找出问题出在哪里，”Agarwal 说。

underline 认为，给人们数百张图表和屏幕不会帮助他们弄清楚发生了什么。

“我们决定自己使用大数据技术来帮助客户发现问题，用简单的英语告诉他们:这就是问题所在。事情是这样的。以下是解决方法，”他说。

它从堆栈的每一层(从应用程序到基础架构)收集信息，然后应用机器学习在一个平台上做三件事:

*   优化:加速你的应用程序，减少资源占用，等等。
*   故障排除:找到问题的根本原因并解决它们。
*   分析:确定谁在用什么，用了多少。我可以更好地规划我的集群吗？我能否为我的多租户集群进行按存储容量使用计费和按存储容量使用显示来分配成本？

## 不同的问题

Agarwal 认为大数据需要自己的 APM 工具。

他说，举例来说，对于网络应用，你要考虑的是交易时间。

“在大数据中，问题的时机和种类完全不同。…假设你想做一份销售报告。你把这项工作分成 100 个相等的块，你拿一段代码，在 100 台并行机上运行，这样这项工作就能快速完成。这里的问题在于负载和平衡，并行性，一台机器上的一个任务是否比其他机器做更多的工作。所以问题很不一样。检测和诊断这些问题所需的数据种类是不同的。解决这些问题的方法是不同的。因此，你真的必须为大数据从头开始设计 APM，”他说。

通过强制实施有关哪些数据应放入内存和哪些数据应移至归档的策略，unlapper 承诺发现并纠正应用程序性能和可靠性问题，提高群集利用率并帮助优化存储。

他说，例如，一项推荐引擎工作需要在每天早上 8 点前完成，人们经常会看到性能从一天到第二天急剧下降。unlaunch 可以分析各种运行，并查明导致问题的变化。

“可能是我正在处理更多的数据。也可能是有人更改了应用程序的配置设置，或者更糟糕的是，可能同时有另一个作业在群集上运行，它窃取了所有资源。他说:“与其让你自己把所有的点都联系起来，还不如让解开程序筛选所有的历史，分析性能模式，然后用简单的英语告诉你:这是今天发生的 100 个可能的问题中的一个，这是你可以解决它的方法。”。

“人们只能使用这种开源技术，如果它不粗糙，如果它能及时向他们返回答案，以满足他们的 SLA。”

它还可以设置为向多租户环境中运行的作业动态分配资源，并提供数据的热、温、冷分析，以优化存储。

## 不断增长的投资组合

unprofile Data 声称是业内唯一一个为大数据提供全栈解决方案的 APM 平台，尽管它正在逐步增加其产品组合。

这家总部位于加州门洛帕克的公司成立于 2013 年，推出了对 Hadoop 和 Spark 的支持，最近又增加了对开源流处理平台 [Apache Kafka](https://kafka.apache.org/) 和 Cloudera 支持的大规模并行处理(MPP)引擎 [Impala](https://www.cloudera.com/products/open-source/apache-hadoop/impala.html) 的支持。它还支持[亚马逊 EMR](https://aws.amazon.com/emr/) 。

下一个:NoSQL 支持。由于 Cassandra 在 Spark 和 Hadoop 堆栈中的使用非常受欢迎，它已经与一些公司合作进行了四五个月的私人测试。

然而，总部位于加利福尼亚州阿拉米达的初创公司 MityLytics 也专注于大数据的 APM，为测试大数据工作负载的变化提供预测建模和模拟环境。

[AppDynamics](https://www.appdynamics.com/) ，在 Unravel Data 的董事会中有一个代表，从年初开始就一直在吹捧一个 [Kafka 扩展](https://www.appdynamics.com/community/exchange/kafka-monitoring-extension/)，用于绩效管理的[工程流程](https://kweo.com/application-performance-management-distributed-real-time-data-processing/)已经成为讨论的话题有一段时间了。

[并发](http://www.informationweek.com/big-data/software-platforms/big-data-grows-up-apm-tools-emerging-/d/d-id/1322825)2015 年推出 Hadoop 的 APM。它后来更名为 Driven，并被数据集成公司 [Xplenty](https://www.xplenty.com/) 收购[。OpsClarity 今年早些时候被](http://www.driven.io/) [Lightbend](http://www.lightbend.com/company/news/lightbend-closes-second-acquisition-in-9-months-buys-opsclarity-for-most-advanced-monitoring-in-modern-distributed-application-stack) 收购，也在 2016 年推出了针对大数据的异常检测和事件关联解决方案。

## “传感器”的使用

在内部安装中，unlauncher 被部署为自己的服务器，尽管一些客户也将其作为 SaaS 产品使用。

“在我们进行分析所需的全部数据中，75%已经以某种形式存在于您自己的集群中。Hadoop 本身正在收集大量此类信息，如来自集群管理和监控工具的 CPU、IO、指标等集群信息。我们吸收了所有数据，而相关性和分析是解开谜团的价值主张，”阿加瓦尔说。

它使用所谓的传感器来填充其余部分。

“这些传感器与代理有一点不同:我们不需要像代理那样以 root 用户身份部署传感器。这些传感器不需要 24 小时运行，给集群带来不必要的开销，”他说。

“例如，传感器可以动态地检测任何应用程序、任何用户、集群中的所有应用程序，但只会以您定义的频率吸收丢失的信息，然后将这些信息发送回去进行分析。”

这是专利技术。如果你有 100 台机器，而你的工作需要 20 台机器。这段代码像一个 [JAR 文件](https://docs.oracle.com/javase/tutorial/deployment/jar/basicsindex.html)一样工作，所以它只在那 20 台机器上运行，你可以将这段代码部署到你的 Spark 作业中，它只在你的作业运行时吸收数据，然后它将自己折叠回去，离开集群。他说，它只在你为你正在运行的工作级别指定的时间吸收数据。

这都是 API 驱动的，所以 unfraud 可以与您当前的监控系统对话。例如，如果您希望同时监控 Oracle 和 Hadoop，您可以将所有监控数据从 Oracle 引入 unfraud，或将 unfraud 数据提供给任何其他已有的消息传递、监控和警报系统。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>