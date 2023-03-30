# 在 Kubernetes 上获得完整数据堆栈的途径

> 原文：<https://thenewstack.io/the-path-to-getting-the-full-data-stack-on-kubernetes/>

如果您使用 Kubernetes 部署您的应用程序，您可能已经将数据库作为堆栈的一部分。在过去的几年里，Kubernetes 周围的开源社区在运行数据库方面投入了大量的精力，结果它变得越来越主流。

构建云原生应用的领导者也已经精通运行有状态工作负载— [调查数据](https://dok.community/dokc-2021-report/)支持这一点，这是一个显著的优势。Kubernetes 是一种我们可以灵活快速地创建虚拟数据中心的方式。

有鉴于此，我们应该考虑虚拟数据中心中的整个应用程序堆栈，以及如何最有效地利用构成运行应用程序的资本成本的计算、网络和存储。少了什么？

## 甲板上的溪流

 [帕特里克·麦克法丁

帕特里克是即将出版的《在 Kubernetes 上管理云原生数据》一书的合著者。他目前在 DataStax 的开发者关系部门工作，并且是 Apache Cassandra 项目的一名贡献者。Patrick 曾是 Apache Cassandra 的首席布道者和 DataStax 的顾问，在那里他度过了构建一些最大的生产部署的美好时光。](https://www.linkedin.com/in/patrick-mcfadin-53a8046) 

流工作负载是数据应用程序中的结缔组织，在 Kubernetes 中部署越来越受欢迎。但是解决方案的成熟度落后于容器化持久性的发展。这是一个项目和供应商很快解决的问题，以解决流媒体带来的一些独特问题。

数据库的生死取决于存储的质量，而[的 StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) 已经正面解决了这个问题；流媒体系统也可以利用这项工作。然而，因为流是一个面向网络的系统，所以在像 Kubernetes 这样的分布式动态环境中部署和维护需要更多的协调。

我直接参与了 [Apache Pulsar](https://pulsar.apache.org/) 项目，所以我可以谈谈那里正在解决的挑战。首先是流媒体可能增加的复杂性。Pulsar 是协调进程的集合，而不仅仅是一个可执行文件。 [Apache Zookeeper](https://zookeeper.apache.org/) (或者很快 [others](https://github.com/apache/pulsar/wiki/PIP-45%3A-Pluggable-metadata-interface) )用于元数据存储和协调。应用程序连接到 Pulsar 代理，Pulsar 代理是无状态的进程，向作为持久层的一组 [Apache Bookkeeper](https://bookkeeper.apache.org/) 节点传递读写操作。这就是简短的版本。

该系统在部署时必须协调一致，这对 Kubernetes 来说是一项完美的工作。Pulsar 项目越来越使 Kubernetes 成为首选的[平台](https://pulsar.apache.org/docs/en/helm-overview/)，因此，Kubernetes 正在基于云原生特性做出决策。

## 分析是下一个前沿领域

从 [Google MapReduce](https://research.google/pubs/pub62/) 最先进的时候开始，大规模分析就一直是一个分布式系统的话题。从 [Apache Hadoop](https://hadoop.apache.org/) 的开始到更现代的 [Apache Spark](https://spark.apache.org/) ，关键特性一直是协调许多计算节点并行处理较小的数据块。

因为这项工作已经进行了近 20 年，不同的编排系统来来去去都在帮助基础设施工程师遏制不可避免的蔓延。YARN 和 Mesos 多年来一直是最受欢迎的，但时代已经变了，现在需要围绕 Kubernetes 进行整合。这不仅仅是工程师迁移到下一个很酷的东西。使用 Kubernetes 有一些明显的优势，包括它管理容器和依赖项的能力。安全和网络管理紧随其后，而且，在一些组织使用 Spark 的规模上，即使是效率上的小进步也是一个巨大的胜利。

目前，大规模运行分析仍然是早期采用者的主张。Kubernetes 运营商使其更少一次性，但 Kubernetes 本身有一些确定的限制，在更大的负载下可能成为一个问题。

Kubernetes 最初是为无状态工作负载设计的，只有很少的核心组件来解决分析中的特定痛点。从本质上来说，分析工作负载可能是高度动态和突发的，Kubernetes 可以在一定限度内处理这些工作负载，但最终，您会发现上限。

例如，典型的全堆栈部署可能有数百个机架，一旦就位，就保持相对静态。一个 Spark 任务可能需要 10，000 个 pod，并且只需要 10 分钟。令人欣慰的是，这些问题正在得到解决。

诸如 [Apache YuniKorn](https://yunikorn.apache.org/) 和 [Volcano.sh](https://volcano.sh/en/) 之类的新调度程序直接解决了现有 Kubernetes 子系统的限制，使任何卷的分析都变得容易。基础设施工程师为 Kubernetes 感到兴奋，这就是我们要去的地方。

## 继续前进

关于 Kubernetes 的坏消息是，并不是所有事情都已经解决了。关于 Kubernetes 的好消息是，并不是所有事情都已经解决了。我们正在为我们需要的东西建立一个开源社区。在数据库的持久性方面已经做了大量的工作，随着我们转向数据领域的其他部分，新的标准正在出现。

流正在成为应用程序堆栈的关键部分，在 Kubernetes 中运行流的成熟度正在赶上数据库。分析为 Kubernetes 创造了一个挑战，即寻找新的限制并推动术语“大规模”的边界。我很有信心我们会找到出路，因为我们以前已经做过很多次了。接下来 10 年的基础设施建设令人兴奋，而且只会越来越好。

如果您想知道是否应该在 Kubernetes 上部署您的应用程序，请不要犹豫。我给了你一些优势来评估，但是大多数部署只会变得更容易运行。

如果你发现了一个极限，加入社区，为将来做更好的事情。关于 Kubernetes 社区的[数据](https://dok.community/)是人们和组织共同努力改善下一代基础设施的聚集地。如果你想讲述你的故事，Kubernetes Day 的数据正好在 KubeCon EU 之前，我们很想听听。

你可以在从事云原生数据库主题的项目中找到我；请过来参加讨论。届时，请告诉我您将如何使用 Kubernetes 在虚拟数据中心部署整个数据堆栈。我总是被创造未来的聪明工程师所激励，我喜欢了解你让它工作的新方法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>