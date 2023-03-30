# Fluentd 在当今云世界中作为数据收集者的角色

> 原文：<https://thenewstack.io/fluentds-role-as-a-data-collector-in-todays-cloud-native-world/>

[Fluentd 在当今云原生世界中作为数据采集者的角色](https://thenewstack.simplecast.com/episodes/fluentds-role-as-a-data-collector-in-todays-cloud-native-world)

开源软件 Fluentd 已经成为一个开源数据收集器，可以收集来自许多不同来源的大量日志数据——这种方式对于 Kubernetes 上的云原生部署特别有用。

作为开发人员之一， [Eduardo Silva](https://www.linkedin.com/in/edsiper/) 是 [Arm](https://www.arm.com/) 的首席工程师，也是 [Treasure Data](https://www.treasuredata.com/) 的 Fluentd 开发团队的一员，他描述了 Fluentd 的实用程序如何以及为什么变得更加重要，以满足当今云原生世界对扩展数据的需求。他在新堆栈的创始人兼主编亚历克斯·威廉姆斯主持的播客中讨论了数据收集器提供的这一点和其他好处，该播客是在上海举行的[kube con+CloudNativeCon 2018](https://www.cncf.io/kubecon-cloudnativecon-events/)上录制的。

Silva 说，Fluentd 的主要好处是任何生产环境都可以访问关于应用程序的全面数据分析，无论它们是在标准服务器上运行还是在 Kubernetes 的分布式系统上运行。这些数据可能包括错误信息、警告或关于应用程序如何运行的一般信息。这些信息是以消息的形式提供的，称为日志记录，说明它们是如何操作的。

“但当你大规模运行这个应用程序时，你需要有一种方法来执行这种数据分析，为此，你需要集中这个日志，你需要过滤这个日志，处理日志，然后将它们汇总到某种数据库中，”席尔瓦说。“作为一种过程方式，这是一种痛苦，但 Fluentd 是为解决特定问题而构建的解决方案。”

Silva 说，虽然大多数人认为日志记录由包含许多信息记录的日志文件组成，但今天的用例远不止这些。“如今，日志记录完全是关于数据流应用程序，该应用程序不断发送有关他们如何工作、如何操作的数据，不仅仅是应用程序，还有硬件，”Silva 说。

席尔瓦说，例如，防火墙通常会发送关于安全相关信息的日志信息，但流动的数据不仅仅是文件，而是数据流。“所以，我想说，现在的任何日志记录解决方案都需要大规模处理数据，数据来自流，文件变成流，”席尔瓦说。

席尔瓦说，通过这种方式，Fluentd 在统一和集中数据方面发挥了重要作用。例如，对于 Kubernetes 集群，会生成许多不同种类的日志信息和数据流。“你的目标是做数据分析，但你需要收集这些数据，”席尔瓦说。"所有这些数据都来自不同的格式和不同的途径."

席尔瓦说，解决数据收集问题并提供数据分析的日志记录解决方案需要能够关联并能够侦听来自不同格式的消息。“对于数据分析，解决方案必须聚合和集中所有信息，”席尔瓦说。

Silva 说，Fluentd 被设计为一个可插拔的架构，因为“这是创建一个能够在项目基础上创造更多价值并利用它的社区的唯一方式”。

席尔瓦说，Fluentd 目前有 800 多个插件可用，而 Treasure Data 维护的插件不超过 20 个。其余的由开源社区维护，包括微软，红帽和其他组织和贡献者，席尔瓦说。

存在许多有趣的用例。席尔瓦说，例如，一些组织可能会使用 [Kafka](https://kafka.apache.org/) 作为 Fluentd 收集的数据在数据库中的持久性。席尔瓦说，然后他们让 Fluentd 从日志文件、TCP 或环境中运行的所有服务中收集日志，然后他们将所有数据聚合回 Kafka。“卡夫卡具有持久性，当他们出于某种原因，出于商业原因，想要消费回那些日志时；他们只是连接到一个特定的卡夫卡主题，他们知道数据就在那里，”席尔瓦说。“因此，关于 Fluentd 的整个事情是，您[不必]只在一个地方注入数据，它可以在多个地方。”

https://www.youtube.com/watch?v = fgaJKykG _ ng " class = " MCE _ SELRES _ start " >

### 在这个版本中:

[1:49:](https://thenewstack.simplecast.com/episodes/fluentds-role-as-a-data-collector-in-todays-cloud-native-world?t=1:49) 什么是 Fluentd？
[4:13:](https://thenewstack.simplecast.com/episodes/fluentds-role-as-a-data-collector-in-todays-cloud-native-world?t=4:13) 您如何将该环境中的数据与应用程序架构分离开来？那些是如何相交的？
[8:50:](https://thenewstack.simplecast.com/episodes/fluentds-role-as-a-data-collector-in-todays-cloud-native-world?t=8:50) 插件架构管理如何适用于用户？
[12:01:](https://thenewstack.simplecast.com/episodes/fluentds-role-as-a-data-collector-in-todays-cloud-native-world?t=12:01)Kubernetes 在 Fluentd 的建筑中扮演什么角色？
[15:59:](https://thenewstack.simplecast.com/episodes/fluentds-role-as-a-data-collector-in-todays-cloud-native-world?t=15:59) 为什么用 C 编程语言写[流利位](https://fluentbit.io/)？
[20:26:](https://thenewstack.simplecast.com/episodes/fluentds-role-as-a-data-collector-in-todays-cloud-native-world?t=20:26) 项目将如何发展，其前进的方向是什么？

[Raygun](https://raygun.com) 赞助了这个播客，由新栈独立制作。KubeCon + CloudNativeCon 2018 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>