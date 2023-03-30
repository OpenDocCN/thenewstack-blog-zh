# 在后 Hadoop 时代优化计算

> 原文：<https://thenewstack.io/optimizing-compute-in-the-post-hadoop-era/>

在我最近的《CIO.com 邮报》中，“[Hadoop 之后还有生活吗？”](https://www.cio.com/article/3624628/is-there-life-after-hadoop-the-answer-is-a-resounding-yes.html)，我写了关于后 Hadoop 时代以及组织可以部署来帮助他们过渡的两个关键策略。这些策略是:1)建立一个更好的湖，2)优化计算。

我将在以后的文章中详细介绍如何构建一个更好的湖，但是今天我想把重点放在等式的计算部分。正如我在上一篇文章中所写的那样，Apache Spark 的灵活性、列式数据方法、对人工智能(AI)和机器学习的适用性，以及它在 Hadoop 上大幅提升的性能，都有助于近年来大幅提高它的采用率。对于大多数用户来说，它已经成为 Hadoop MapReduce 的逻辑继承者。本文介绍了如何从 Spark 中获得最大收益，并帮助点燃一场革命。

## **为什么会产生火花？**

 [兰迪·托马森

作为 HPE 埃兹迈拉软件公司的全球解决方案架构师，Randy 提供技术领导力、战略和架构指导，涵盖广泛的技术和学科，包括应用开发和现代化、大数据和高级分析、基础设施自动化、内存和 NoSQL 数据技术和 DevOps。](https://www.linkedin.com/in/randy-thomasson-2857273/) 

Spark 是用于大规模数据处理的统一分析引擎。它使用最先进的 DAG(有向无环图)调度程序、查询优化器和物理执行引擎，实现了批处理和流数据的高性能。它和 Hadoop 也有很强的亲和力，使用了很多 Hadoop 库。Spark 还支持一系列自己的库，包括 SQL 和 DataFrames、Spark Streaming、MLib 和 GraphX。Spark 应用程序在集群上作为独立的进程集运行，由 SparkContext 对象协调。

Spark 集群非常适合解决当今数据驱动型业务的需求，因为它对流和内存处理的支持可以比 Hadoop 等更加面向批处理的技术带来显著的性能提升。

Spark 基于集群的架构也使其非常适合处理各种数据集。此外，Spark 提供了多种部署选项，并直接支持四种不同的集群管理器:

*   [独立](https://spark.apache.org/docs/latest/spark-standalone.html)–Spark 附带的一个基本集群管理器，用于简单、易于运行的集群。
*   [Apache Mesos](https://spark.apache.org/docs/latest/running-on-mesos.html)——一个开源集群管理器，也可以运行 Hadoop MapReduce 和服务应用。
*   [Hadoop YARN](https://spark.apache.org/docs/latest/running-on-yarn.html)–Hadoop 2 中包含的开源资源管理器。
*   Kubernetes–一个用于自动化部署、扩展和管理容器化应用的开源系统。

好消息是底层集群管理器对 Spark 应用程序是透明的。因此，选择不同的集群管理器不需要修改 Spark 应用程序，只需要修改部署配置。

## **选择部署**

Spark 集群管理器的选择略有不同，但大多数组织传统上都使用 Hadoop YARN 运行生产 Spark 工作负载。然而，势头正在转向 Kubernetes 上的运行火花。这是事实，原因有几个:

*   **独立是有限的—**它最容易开始，但是最适合单节点开发/测试集群。它缺乏其他三个集群管理器的动态管理功能，并且在当今基于容器的虚拟化基础设施环境中，它落后于 Kubernetes 等更先进的技术。
*   **Mesos 死了—**就在几个月前，Apache Mesos 似乎正走向阁楼，那里是 Apache 项目死亡的地方，但在最后一刻，它获得了缓刑。也就是说，该社区的活动已经大幅放缓，2020 年只有一个版本，2021 年迄今没有一个版本。Mesos 的采用者包括苹果、Twitter、网飞和优步等大牌，但它从未达到临界质量，也没有像 Hadoop 或 Kubernetes 那样成为主流。
*   **YARN 是昨天的****–**YARN 由于各种原因一直是最受欢迎的 Spark 集群管理器。然而，与 Mesos 和 Kubernetes 不同，YARN 是相对较新的容器(最近在 Hadoop 3.1.1 中，它被认为是试验性的和不完整的)，并且作为 Hadoop 的一个组成部分，需要 Hadoop 集群运行或独立于 Hadoop 集群部署 YARN 的方法(例如，作为 [KubeDirector](https://github.com/bluek8s/kubedirector) 应用程序)。容器支持的状态和额外的 Hadoop 负担转化为更高的生命周期成本，并使其对新的 Spark 部署缺乏吸引力。

考虑到当今数据驱动的业务流程，其中共享的虚拟化基础架构在跨内部数据中心和公共云的复杂部署中运行，当今生产 Spark 工作负载的选择很明确:Kubernetes。

Kubernetes 为 Spark 部署提供了一些独特的优势。其中最主要的是它对容器的支持。容器彻底改变了应用程序打包和部署的方式，就像虚拟化彻底改变了服务器基础设施一样。容器提供了更好的隔离、改进的可移植性、更简单的依赖性管理，最重要的是，极大地减少了应用程序的周期时间。Kubernetes 还提供了更高效的资源管理，消除了对临时集群的需求——如 Databricks、EMR 等所推荐的。—避免非 Kubernetes Spark 环境中的资源冲突/影响。Kubernetes 提供的更短的应用程序迭代周期和明显更少的安装/拆卸延迟转化为更低的生命周期成本。因此，将 Spark 工作负载迁移到 Kubernetes 的组织可以降低 50%到 75%的成本。

## **大象退休**

Hadoop 已经运行了多年，但对于许多组织来说，是时候继续前进了，Spark 已经成为替代它的首选工具。Spark 改进的性能、与现有 Hadoop 资产的密切关系及其更先进的数据处理方法使其成为迁移 Hadoop 工作负载的热门选择。也就是说，Hadoop 将会伴随我们一段时间。这是因为多种原因:

*   迁移数 Pb 的 Hadoop 数据和相关应用需要时间。
*   一些 Hadoop 服务在 Spark 生态系统中还没有直接的替代品。
*   仍然有一些使用案例表明 Hadoop 是更好的选择。

鉴于这一现实，从 Hadoop 迁移的组织需要一种解决方案策略，在迁移期间和之后为其剩余的 Hadoop 资产提供一个经济高效的家，同时适应不断增长的 Spark 工作负载，最好使用基于容器的通用平台。理想情况下，该解决方案将支持现有 Hadoop 资产以及较新的 Spark 工作负载的计算和存储需求，同时最大限度地减少运行时平台和相关存储的数量。

## **用火花点燃革命**

近年来，人工智能和数据驱动的应用出现了爆炸式增长。这反过来推动了从 Hadoop 的迁移，并推动了 Spark 和机器学习技术的采用。

随着组织寻求迁移现有的 Hadoop 数据和应用，他们需要一种方法来有效管理不断缩减的 Hadoop 投资，同时增加对 Spark 和机器学习技术的投资。做到这一点的最佳方式是采用火花加数据的分析结构策略。

通过采用[HPE·埃兹迈拉](https://www.hpe.com/us/en/software.html)，组织可以轻松地从[过渡到后 Hadoop 时代](https://assets.ext.hpe.com/is/content/hpedam/documents/a50001000-1999/a50001473/a50001473enw.pdf)，利用 Spark 优化分析计算功能，同时在此过程中有效管理传统 Hadoop 资产。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>