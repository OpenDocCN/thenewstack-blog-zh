# MapR 将 Apache Spark 和 Apache Drill 带到了 Kubernetes

> 原文：<https://thenewstack.io/mapr-brings-apache-spark-and-apache-drill-to-kubernetes/>

与大多数抽象一样，Kubernetes 的分布式应用程序架构解决了一些问题，但也带来了其他问题。例如，Kubernetes 使跨多个位置托管应用成为可能，无论是在本地、公共云或私有云，还是两者的混合。它还支持通过持续交付实现真正的云原生应用开发方法。同时，开发人员已经习惯的持久化有状态应用程序在默认情况下不再可用。相反，容器化的应用程序本质上是无状态的，因为容器旨在短暂地存在，允许它们被快速地创建和销毁，而无需考虑，从而实现真正的连续交付。

去年，数据平台 [MapR](https://mapr.com/) 通过[为 Kubernetes](https://thenewstack.io/developers-like-maprs-persistent-storage-kubernetes/) 提供持久存储层解决了这个问题，现在该公司正在扩展这一功能，为 [Apache Spark](https://spark.apache.org/) 和 [Apache Drill](https://drill.apache.org/) 提供新的集成。通过这些新功能，MapR 现在允许用户将 Spark 和 Drill 部署为由 Kubernetes 编排的计算容器，从而允许“包括数据工程师在内的最终用户在 Kubernetes 集群中运行计算工作负载，该集群独立于数据的存储或管理位置，”根据该公司的声明。

该声明称，新功能是去年版本的扩展，将“使更好地管理高弹性工作负载变得更容易，同时还促进了及时部署以及分别扩展计算和存储的能力。”

“我们正在扩展我们已经知道并在我们的 MapR 数据平台上经过时间测试的功能，并且我们正在将它们与 Kubernetes 集成。我们正在通过 Kubernetes 提供的 API 进行集成，并为最终用户提供一种运行预打包图像的 Spark 容器和 Drill 容器的方式。“Kubernetes 有一个横向自动缩放的概念。容器，就其固有的性质而言，保存着应用程序信息。也就是说，如果你有一个编辑 JPG 图像的应用程序，那么这个容器只能完成这个任务。它不包含任何关于操作系统或系统库的信息。他们几乎住在不同的地方。正因为如此，容器是轻量级的、弹性的和可移植的，因为它们只包含关于应用程序和运行时的信息。”

Visvanathan 继续解释说，新功能允许组织扩展 Spark 和 Drill 的使用，就像他们扩展容器化应用程序的其他方面一样。例如，如果一个团队需要运行一份需要数千个 Spark 作业的季度报告，而不是为团队提供一个专用的集群，您可以使用 MapR 的新集成按需旋转计算作业，无论是在本地还是在云中。

“MapR 为企业组织轻松完成两件关键事情铺平了道路:开始分离计算和存储，并在运行分析性 AI/ML 应用程序时快速采用 Kubernetes，”MapR 高级工程副总裁 Suresh Ollala 在一份公司声明中进一步解释了这一集成。“与 Kubernetes 核心组件的深度集成，如操作符和名称空间，允许我们定义多个具有资源隔离和限制的租户，所有租户都运行在同一个 MapR 平台上。这不仅对于需要灵活性和弹性的应用程序，而且对于需要在云之间来回移动的应用程序，都是一个重要的推动因素。”

该公司表示，这种集成将提供几个具体的好处，包括隔离资源以防止应用程序相互缺乏资源的情况，允许多租户环境，在同一平台上运行不同 Spark 和 Drill 版本的能力，处理计算突发的能力，以及根据负载和需求动态扩展钻头的能力。新集成的核心还将允许用户“跨多云环境(包括私有云、混合云和公共云)部署 Spark 和 Drill 容器应用程序以及 MapR 卷。”

目前，这些功能正在进行私下测试，将于 2019 年年中的某个时候正式推出。

来自 Pixabay 的 DarkWorkX 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>