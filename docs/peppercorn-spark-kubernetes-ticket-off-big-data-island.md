# 对于 Pepperdata 来说，Kubernetes 上的 Spark 是离开大数据岛的门票

> 原文：<https://thenewstack.io/peppercorn-spark-kubernetes-ticket-off-big-data-island/>

根据 [Pepperdata](https://www.pepperdata.com/) 的联合创始人兼首席技术官肖恩·苏克特的说法，就像吉利根和他的团队一样，大数据需要离开这个岛。

他之前在雅虎工作，是 Hadoop 的首批用户之一，他看到了整个大数据堆栈——HDFS、MapReduce、YARN——是为处理规模问题而开发的。

他解释说，“有意地，有计划地，它与它能做的一切都是分开的。”

这导致了这种脱节:你可以用主流 IT 做的所有事情——所有工具、日志管理、存储系统——对大数据世界来说完全不可访问。

“所以你得到了我所说的大陆和岛屿。主流 IT 的大陆和大数据的孤岛。它不共享技术，不共享硬件，不共享人员或专业知识，不共享工具。十多年来一直如此。你不能利用一个或另一个的进步，”他说。

他认为运行在 [Kubernetes](/category/kubernetes/) 上的 Spark 是实现这一目标的一种手段，Kubernetes 是由云原生计算基金会[管理的开源容器编排工具。](https://www.cncf.io/)

该公司坚持认为 Spark 比 MapReduce 快几个数量级，更容易编码，也更灵活。

随着帮助客户解决 Hadoop 和 Spark 大数据问题的 Pepperdata 开始调查在 Kubernetes 上本地运行 Spark 和 HDFS，它发现了一个公司社区——仅举几个例子， [Google](https://cloud.google.com/kubernetes-engine) 、 [Red Hat](https://www.openshift.com/) 、Palantir、彭博——正在处理相同的问题。Kubernetes 特殊利益集团上的[火花](https://groups.google.com/forum/#!forum/kubernetes-sig-big-data)形成了一个火花的分叉。Kubernetes 预计将在几个月后的下一个版本中成为 Spark 的核心。

这将为用户提供第四种运行 Spark 的方式，超越单机、YARN 和 Mesos。

他说，虽然 Kubernetes 1.8 增加了对 Spark 的本地支持，但要让 Spark 完全说 Kubernetes 还需要做更多的工作。

“Kubernetes 已经为您提供了所有这些灵活性，您可以在其中描述您的 pod，您有守护程序集、副本控制器和原语。我们得到了一个使用已经存在的原语的基本版本，”他说。

在 2017 年 spark 峰会上，谷歌软件工程师 [Anirudh Ramanathan](https://www.linkedin.com/in/anirudhrx/) 解释说，将两者一起运行可以减少运营商需要管理的基础设施，为开发人员提供单一界面来管理他们的所有工作负载，提高基础设施利用率，庞大的 Kubernetes 生态系统增加了大量可以立即提供给 Spark 用户的服务，例如最近推出的 [Istio](https://thenewstack.io/kubernetes-microservices-istio%E2%80%8A-%E2%80%8Aa-great-fit/) service mesh 项目。

[https://www.youtube.com/embed/0xRHONrWwvU?feature=oembed](https://www.youtube.com/embed/0xRHONrWwvU?feature=oembed)

视频

两大工作领域是安全性和时间安排。

Kubernetes 拥有安全原语，但它并没有真正扩展到企业内的所有任意用户，他说，所以有一些扩展使它像带有网络认证协议的大数据系统一样工作。

它支持基于 Kerberos 的身份验证，以保护对整个环境的访问，并保护用于访问应用程序的凭据。

此外，还需要对短暂微服务不断变化的工作负载进行调度。

[https://www.youtube.com/embed/DxCDxi08HWo?feature=oembed](https://www.youtube.com/embed/DxCDxi08HWo?feature=oembed)

视频

该项目包括一个数据位置功能，使得在 Kubernetes 上跨分布式 HDFS 实例访问数据变得更快。它将允许用户管理数据所在的所有孤岛，无论它们是部署在内部还是云中。

“将会有 [Helm](https://github.com/kubernetes/helm) 图表，因此用户可以在他们的 Kubernetes 系统上设置存储，并将其用作安全的大数据存储。安全和高性能。这是在裸机上使用集群结构的传统问题之一，即大数据系统非常需要资源。Kubernetes 的强大之处在于它抽象地设置了这些东西，可以获得与裸机相同的性能。对于大多数(大数据)系统来说，事实并非如此，”他说。

离开孤岛意味着公司可以在他们的 Kubernetes 集群上运行另一个项目，而不需要笨重的多系统架构。他预测，在两年内，一家公司可以在一个系统中运行分析——例如，一个反馈到面向用户的应用程序中的机器学习项目。

## **关注火花**

Pepperdata 加强了对 Spark 的关注。据其“生产 Spark”[网络研讨会](https://www.brighttalk.com/webcast/13073/246259)系列的专家称，易于集成、内置机器学习和支持流数据等功能正在推动 Spark [的采用](https://www.infoworld.com/article/3216144/spark/the-rise-and-predominance-of-apache-spark.html)。

该公司最近宣布了 Spark 的代码分析器，它使开发人员能够将性能问题与导致问题的代码块联系起来。

今年 3 月，它发布了 Application Profiler，这是 LinkedIn 的 [Dr. Elephant](https://engineering.linkedin.com/blog/2016/04/dr-elephant-open-source-self-serve-performance-tuning-hadoop-spark) 的软件即服务版本，是一种开源工具，可以帮助 Hadoop 和 Spark 的用户分析和改善他们的流的性能。

将大数据与其他 IT 基础设施统一的一个新选项来自 SAP Vora，这是一个用于 HANA 的内存计算引擎，运行在 Red Hat 基于 Kubernetes 的 OpenShift 容器平台上。它从 Spark、Hadoop 或直接从云环境中收集数据。

与此同时，Hadoop 似乎正在失宠。

今年早些时候，Gartner [宣布](https://www.datanami.com/this-just-in/gartner-reveals-2017-hype-cycle-data-management/) Hadoop 已经过时，理由是整个 Hadoop 堆栈的复杂性和可疑的实用性。它指出，许多组织正在考虑基于云的选项，包括按需定价和适用的数据处理。

Cloudera [将](https://www.datanami.com/2017/03/20/hadoop-strata-not-exactly-failure-complicated/) Hadoop 从之前命名的 Strata + Hadoop 世界大会中移除。

在 5 月份的 ApacheCon North America 上， [Cloudera](https://www.cloudera.com/) 的 [Daniel Templeton](https://www.linkedin.com/in/danieltempleton/) 以[安全和其他问题](https://thenewstack.io/docker-hadoop-theres-good-bad-ugly/)为由，建议等到 Hadoop 3.0 之后再部署 Docker 容器。

Hortonworks 去年同样将其 Hadoop 峰会系列会议更名为 DataWorks Summit，以反映数据流架构的更大作用。

云本地计算基金会、[、谷歌](https://cloud.google.com/kubernetes-engine)、[红帽](https://www.openshift.com/)是新堆栈的赞助商。

专题图片:[岛](https://www.flickr.com/photos/72334647@N03/36550546111/in/photolist-XFR6Xv-oBPsJR-9gmcZS-bE47jp-dMVs57-nndQvP-21ptJRg-pheaXw-oUkqT6-oBP2Ct-apEQs3-CE5srS-4bpSFy-oBPaMe-bE47Yg-orBNjr-oSi1gN-oBPZRR-5CiXuV-oU4xHg-4zaBeS-aF3wKs-oBQtTy-bE3QZa-9rsBgU-oBQ)由 [**司机摄影师**](https://www.flickr.com/photos/72334647@N03/) ，授权于 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>