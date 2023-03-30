# 如何让卡夫卡云本土化

> 原文：<https://thenewstack.io/how-to-make-kafka-cloud-native/>

Raygun 赞助了这个播客。

[制作卡夫卡云原生](https://thenewstack.simplecast.com/episodes/making-kafka-cloud-native)

在这一集的 [The New Stake Makers](https://thenewstack.io/podcasts/makers) 播客中，我们加入了 [Neha Narkhede](https://www.linkedin.com/in/nehanarkhede/) ，他是首席技术官和 [Confluent](https://www.confluent.io) 的联合创始人，也是 Apache Kafka 的联合创始人之一。

随着超过 60%的财富 100 强依赖于阿帕奇卡夫卡，这项服务变得既受欢迎又根深蒂固。但是，随着云技术的发展，一些根本性的变化是必要的，以使 Apache Kafka 真正成为云本地的。

在堆栈中，Kafka 位于操作层之上，应用层之下。它与关系数据库和/或现代的非 SQL 数据库以及数据仓库一起存在于数据基础设施层。她说，它为数据提供了一个新的基础，可以将所有不同种类的服务数据集中到一个地方，这样你就可以大规模地消费这些数据。

“我们对企业的了解是，他们想买下整辆车，”Narkhede 说。因此，该公司的工程师花了一年左右的时间来建立一个云原生的、完全托管的服务，开发者可以在公共云中使用。她解释说，他们增加了 Kafka 工作负载的安全性，因此您可以在真实的企业中部署它来处理真实的工作负载。接下来，他们创建了一个完整的工具生态系统，从不同系统的连接器到流处理层，再到管理模式的方法。

Kafka 架构也需要进行根本性的改变，以利用规模经济来提供完全云原生所必需的弹性。

第一个重大变化是解决多租户问题，并在系统中增加了管理配额的功能。随着亚马逊网络服务等服务共享容器和服务，[融合云](https://www.confluent.io/confluent-cloud/)围绕多租户架构建立了安全性，并制定了弹性配额。她说，这是“所以你可以扩展，仍然保持几个 9 的正常运行时间。”

其次，弹性扩展消除了调整集群规模以适应服务高峰的需求。融合云可以弹性扩展到 100 毫克/秒(读取和写入)，而无需计划任何事情或与任何人交谈，本质上提供了“无集群”体验。

第三个根本性的变化与卡夫卡没有任何关系。

Narkhede 说，当你开始弹性扩展工作时，你会不断遇到云基础设施对云抽象的限制，例如，当时可以建立的连接数。因此，Confluent 围绕 Kafka 构建了一个控制平面来自动处理限制。

他们遇到的一个更困难的问题是建立一个真正的“按流付费”的体验。因此，您的所有后端系统都可以占用您的时间，并且您将为您真正使用的资源和集群付费。

“用户关心的是数据，”Narkhede 说。他们希望创建主题，并希望从主题中发送和接收消息。他们希望将这些主题与 S3 等外部系统联系起来，或者只是编写一些 SQL 查询来理解主题中的内容。"

请收听 Narkhede 关于脱离集群配置的演讲，您接下来应该学习的内容，以及融合客户正在做的一些有趣的事情。

### 在这个版本中:

[1:16:](https://thenewstack.simplecast.com/episodes/making-kafka-cloud-native?t=1:16) 对融合提供的服务和产品的高度概括。
[7:07:](https://thenewstack.simplecast.com/episodes/making-kafka-cloud-native?t=7:07) 如何改变 Kafka 以利用现在云中可用的服务。
[10:33:](https://thenewstack.simplecast.com/episodes/making-kafka-cloud-native?t=10:33) 使用容器和为实际使用而构建的财务收益/损失
[11:48:](https://thenewstack.simplecast.com/episodes/making-kafka-cloud-native?t=11:48) 如果您不是从集群的角度进行配置，那么您使用的是什么角度？
[14:47:](https://thenewstack.simplecast.com/episodes/making-kafka-cloud-native?t=14:47) 不再将数据视为每天需要处理一次的静态存储，而是持续查看信息流。
[18:15:](https://thenewstack.simplecast.com/episodes/making-kafka-cloud-native?t=18:15) 给工程师稳定职业生涯的建议

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>