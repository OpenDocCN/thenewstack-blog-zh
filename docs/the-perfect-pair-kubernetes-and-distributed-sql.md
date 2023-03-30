# 完美的组合:Kubernetes 和分布式 SQL

> 原文：<https://thenewstack.io/the-perfect-pair-kubernetes-and-distributed-sql/>

[KubeCon + CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 赞助了这篇文章，期待于 8 月 13 日至 16 日在阿姆斯特丹举办 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 。

 [卡尔蒂克·阮冈纳赞

Yugabyte 的联合创始人兼首席技术官 Karthik 是脸书最初的数据库工程师之一，负责构建分布式数据库，包括 Cassandra 和 HBase。在 Cassandra 被脸书开源之前，他是 Apache HBase 的提交者，也是 Cassandra 的早期贡献者。他目前是 YugabyteDB 公司的联合创始人兼首席技术官，YugabyteDB 是一个完全开源的分布式 SQL 数据库，用于构建云原生和地理分布式应用程序。](https://www.linkedin.com/in/kranganathan/) 

容器受欢迎的原因有很多。许多人将其增长归功于容器为运行(或寻求运行)基于微服务的现代云原生应用的开发人员、开发运维团队和企业提供的众多优势。容器化有助于组织变得更加灵活，行动更快，并在选择底层基础设施时获得自由。事实上，[预测](https://dzone.com/articles/benefits-of-kubernetes-for-microservices-architect)今年将有超过 50%的公司使用容器技术，高于 2017 年不到 20%的比例。

容器的强大之处在于它们的可移植性、灵活性和跨应用环境实现一致性的能力。如今，容器和容器编排技术使企业能够采用基础设施即代码(IaaC ),并加快应用从开发到测试再到生产的速度。但是回顾十年前，IaaC 运动需要…更多的编码。一个典型的企业拥有数据中心和 Amazon Web Services (AWS ),并且不得不编写大量代码来将他们的应用程序部署到这些位置，因为不同的基础设施提供商需要考虑独特的细微差别。DevOps 团队花费了大量的时间和精力编写代码，以将应用程序从底层基础架构中分离出来，然后才能在不同的环境中部署应用程序。

几年后，情况发生了变化 Kubernetes(紧随 Docker 之后)和更多的公共云，包括 Azure 和 Google Cloud。几乎在一夜之间，旧的 IaaC 时代(尽管它比之前的“一切都是手动的”时代要好)不再足够敏捷来开发应用程序，并从笔记本电脑和跨应用程序环境(托管在云中或多个云和内部)一致地测试和部署它们。

Kubernetes 是一种技术，它让旧的 IaaC 时代被一种新的、更快的部署和运营基础设施的方式所取代。多年来，已经有很多关于三大容器编排竞争者之间的战争的文章:Kubernetes、Docker Swarm 和 Apache Mesos。然而，不可否认的是，Kubernetes 由于其开源软件和多样化的开发人员社区，一直保持着作为部署最广泛的容器编排技术的领先地位。今天，使用 Kubernetes，开发人员和 DevOps 工程师真正能够构建一个并多次部署，因为，例如，在 AWS 上请求磁盘的方式类似于在 Google Cloud 上的方式。

IaaC DevOps 运动与我们在应用程序开发中看到的趋势同步发展。事务性和面向用户的应用程序越来越需要更高的可用性、即时可扩展性、随处运行的能力(包括多云和混合云环境)以及操作简单性，以便在应用程序的整个生命周期内更轻松地运行应用程序。

随着基础设施和应用程序本身的发展，数据层也在发展。几十年来，SQL 一直是关系数据库(即 RDBMS)的事实语言。但是，Oracle、PostgreSQL 和 MySQL 等原始 SQL 数据库是单节点 SQL 解决方案，无法跨多个实例自动分发数据和查询以提供高可用性和可扩展性。在通往可伸缩性和弹性的道路上，像 MongoDB 和 Apache Cassandra 这样的 NoSQL 数据库在 2000 年代中后期开始崭露头角。它们最初被定位为当时单一 SQL 数据库的替代品，它们的分布式特性对应用程序和应用程序开发人员很有吸引力。

各种 NoSQL 语言专注于单行(也称为键值)数据模型，放弃了 SQL 语言的关系/多行结构。然而，企业很快意识到 NoSQL 数据库必须与 SQL 数据库共存，而不是取代它们。持续需要 SQL 数据库的主要原因是需要支持单行一致性和多行 ACID 事务的关系数据建模。2010 年代初，出现了 NewSQL 数据库，也称为“可伸缩”SQL 数据库，以支持大规模 OLTP 工作负载，其中数据正确性和可伸缩性都很重要；然而，即使是 NewSQL 数据库[也会有妥协](https://blog.yugabyte.com/distributedsql-vs-newsql/)，尤其是在 Kubernetes 本地的多云部署中。

反过来，企业已经转向分布式 SQL 数据库，以获得传统单节点 SQL 系统的综合能力:强一致性、ACID 事务和对 SQL 语法的支持、NoSQL 的分布式特性和 NewSQL 的可伸缩性。

借助 Kubernetes 驱动的容器化应用流程编排，企业能够自动扩展服务、实现容错、在不停机的情况下部署升级等等。当应用程序是无状态的时，这一切都是有意义的——控制由 Kubernetes 完成，而 Kubernetes 完成整个生命周期。

当谈到有状态应用程序(存储数据的应用程序；数据库就是一个例子)，Kubernetes 可以提供伸缩性、容错和其他好处，但是有状态应用本身也需要为编排做好准备，并实现这些承诺。有状态应用程序必须具备可伸缩性和容错性，并且不会丢失数据。

SQL 数据库是一个有状态的应用程序，是在 Kubernetes 中运行的最复杂的工作负载之一。Kubernetes pods 的短暂性和将它们重新安排到新的 Kubernetes 主机上的持续需求要求底层数据库层也变得同样敏捷。否则，应用程序将会出现中断、速度变慢，更糟糕的是，数据丢失和结果不正确。大多数有状态 SQL 数据库无法获得 Kubernetes 的好处；开发人员必须告诉 Kubernetes 不要应用这些好处，因为数据库无法处理它。

然而，分布式 SQL 数据库可以解决这些挑战，并使企业能够利用 Kubernetes 提供的固有优势。例如，分布式 SQL YugabyteDB 数据库通过持续监控和重新平衡可用节点上的数据碎片，确保应用程序永远不会出现中断、速度变慢或数据丢失的情况，即使在 Kubernetes 集群这样的高度动态环境中也是如此。

随着企业从云托管环境迁移到云原生环境，DevOps 构建应用程序和存储全球分布数据的方式正在发生变化。使用 Kubernetes 作为行业标准的容器编排系统，开发人员可以高效地构建更复杂的应用程序和数据存储环境。通过将您的容器化环境与分布式 SQL 配对，这一过程变得更加容易，允许企业解决业务问题并实现真正的数字化转型。

*要了解更多关于集装箱化基础设施和云原生技术的信息，请考虑参加 8 月 13 日至 16 日在阿姆斯特丹举办的 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 。*

管理 KubeCon + CloudNativeCon 的 Cloud Native Computing Foundation 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>