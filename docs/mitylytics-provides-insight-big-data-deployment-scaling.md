# MityLytics 提供对大数据部署、扩展

> 原文：<https://thenewstack.io/mitylytics-provides-insight-big-data-deployment-scaling/>

为什么在部署大数据应用程序时很难获得可预测的性能？

这是 MityLytics 在 2015 年成立时就着手解决的问题。它旨在帮助开发和运营人员了解他们的工作负载在各种硬件上的表现，并帮助 It 主管规划如何为未来提供最佳扩展。

首席技术官[马尼什·辛格](https://www.linkedin.com/in/manish-singh-2234881/)解释说:“我们观察一个应用程序在做什么，以及你的容量和预算到底是多少。”。然后，如果你想改变某些东西——例如，如果你想改变它划分数据的方式，或者使用不同的硬件——它的预测算法会让你知道将会产生的影响。

这是通过建模和模拟大数据工作负载的行为来实现的，例如 MapReduce 上的[Terasort](https://mapr.com/resources/terasort-benchmark-comparison-yarn/)。Singh 去年在 Data by the Bay 上谈到了如何识别 Spark、Hadoop 和 Hive 的瓶颈，最近在迈阿密举行的 ApacheCon 的一部分“大数据北美”上谈到了在 ARM 处理器上运行 Cassandra。

它与提供裸机云的 [Packet](https://www.packet.com/) 合作，在裸机上测试 Kafka、Spark 和 Cassandra 的[性能。](https://www.packet.net/media/images/r6uQ-stress.testinglow.pdf)

一旦客户在模拟硬件上部署了大数据应用程序，它将决定如何在纵向扩展的基础架构上扩展和处理更大数量的数据。其全自动性能测试采用深度学习软件来预测运行时间和资源利用率。想加 RAM 或者 CPU 怎么办？

“你实际上不必启动一个应用程序来查看它将如何运行，”辛格谈到它的模拟器时说，该模拟器提供了一个跨越应用程序整个生命周期的动态评估。

辛格说，它可以帮助你做计划，通过概述一笔特定的美元投资你将得到的表现。他说，这种类型的规划类似于土木工程和航空项目中使用的规划。

开发者可以在模拟环境中测试他们的应用。他们可以帮助确保他们的应用程序获得所需的资源，并且随着变化，应用程序将保持在成本和资源预算内。

它在开发和部署时提前通知性能和伸缩瓶颈，并提出代码更改建议，以提高整个工作负载的性能。

它甚至可以在自定义应用程序上运行，只需从给定基础架构中的所有端点运行 10 次数据。它只需要了解本土环境的特征，辛格说

## 看到变化的影响

联合创始人 [Rishi Divate](https://www.linkedin.com/in/rishidivate/?ppe=1) 将他在 [SumoLogic](https://www.sumologic.com/) 的经验运用到应用程序优化中。Singh 在 [Pica8](http://www.pica8.com/) 有软件定义网络的背景，在 GoGrid 有云服务编排和自动化的背景。第三位联合创始人[希瑟·麦克维](https://www.linkedin.com/in/heather-mckelvey-4b31441/)，也来自 GoGrid 和[巴绍科技](http://basho.com/)。他们位于加州阿拉米达的公司有 7 名员工。

它正在提供 MiCPM 的试驾，这是一个具有 Spark-HDFS 集群的“指向并部署”SaaS 平台。通过使用聚合的监控数据和算法，MiCPM 提供了工作负载模拟和自动化性能调优。

其技术旨在用于私有云和公共云大数据环境，如 [AWS Elastic MapReduce](https://aws.amazon.com/emr/) 和 [Azure HDInsight](https://azure.microsoft.com/en-us/pricing/details/hdinsight/) 以及部署在企业数据中心的集群。

该公司正在进行五项概念验证，包括电信和高性能计算公司。它正在寻找更多的参与者。

与之合作的财富 500 强公司通常拥有本地数据中心，但他们想知道如果迁移到云，他们的应用程序会受到什么影响。辛格说，MityLytics 帮助他们做到了这一点。

[数据包](https://www.packet.com/)是新堆栈的发起者。

Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>