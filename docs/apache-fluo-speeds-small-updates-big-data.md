# Apache Fluo 加快了大数据的小更新

> 原文：<https://thenewstack.io/apache-fluo-speeds-small-updates-big-data/>

当新文档不断到来时，Google 最初很难满足拥有最新的 web 索引的需求。更新其搜索索引过去需要花费三天时间完成一系列 MapReduce 工作，直到它为其 [Bigtable](https://cloud.google.com/bigtable/) 数据分析服务创建了 [Percolator](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/36726.pdf) 更新技术。

Percolator 的开源版本， [Apache Fluo](https://fluo.apache.org/) ，同样允许并发的小更新，而没有重新处理整个数据集的延迟。

Fluo 最近被命名为 Apache 软件基金会的顶级项目。

Fluo 与 [Apache Accumulo](https://accumulo.apache.org/) 协同工作，后者是一个基于 Bigtable 设计的分布式键/值存储，用于管理大量结构化数据。Accumulo 将数据存储在 [Apache Hadoop](https://hadoop.apache.org/) 的 HDFS 中，并使用 [Apache Zookeeper](https://zookeeper.apache.org/) 进行协商。

Apache Fluo 的副总裁 Keith Turner 解释说:“Percolator 和 Fluo 允许你做一些你可以用 MapReduce 做的事情，但是延迟更低，所以当数据更新时，你有更快的周转时间。

特纳表示，Percolator 为用户提供了两个主要组件。一个是跨节点事务，即更改驻留在集群中多台机器上的数据的能力。要么全部通过要么一个都不通过。

他说，在 Bigtable 中，你只能获得存储在单台机器上的数据的事务行为。

第二个东西叫做观察者，它允许你在事情发生变化时插入用户代码。

“你可以注册，‘哦，这一点数据发生了一些事情，我想让一些用户代码对数据库中的行-列运行一个事务’，这个事务可以读取可能在其他节点上的其他行-列，写入存储在其他节点上的其他行-列，它可以设置其他通知，稍后触发其他观察器，”他解释说。

“因此，增量工作流来自这两个基本前提……你把交易和观察者放在一起，你就有了这些渗透到系统中的变化。”

在 BigTable 中，在一个节点上处理数据。

“如果我是一家在 Bigtable 中按客户 ID 存储客户数据的公司，但我想向客户 ID 添加新信息，那么就需要一个连接来向现有信息添加新信息。他说:“你不能用一种理智的、事务性的方式去做的事情是，比如说，当一个客户发生变化时，我希望它转过身来，更新客户过去购买过的产品，更新他们过去购物过的商店。

“这些信息会存储在其他计算机上。我想以一种事务性的方式来做这件事，这样，要么全部通过，要么一个都不通过。你可以把一个客户的所有信息都存储在一起，把所有产品的信息都存储在一起，把所有商店的信息都存储在一起，但是当你想让一个商店的变化影响其他商店的变化时，你必须做一些比 Bigtable 提供的更多的事情。”

该项目在 6 月下旬发布了 1.1.0 版本，其中包括一个新的 Observer API，该 API 具有使用 lambdas 的能力。API 以前需要为每个被观察的列配置一个观察器类，这很麻烦，并且不可能使用 lambdas。有了新的 API，您只需配置一个提供所有观察者的类，就可以将这些观察者分配给一个列。它还改进了[与 Spark](http://www.i-programmer.info/news/136-open-source/10927-apache-fluo-improves-spark-integration.html) 的集成。

“Apache Fluo 是一个非常聪明的软件，很好地补充了 Apache Accumulo 存储和维护非常大的索引的能力，”Accumulo 和 Fluo 项目的负责人 [Christopher Tubbs](https://github.com/ctubbsii) 说。“其对事务的支持使 Accumulo 能够解决一系列全新的大数据问题，其 observer 框架使设计摄取工作流变得有趣。”

特纳说，Fluo 项目正在解决的最大问题是将其与纱线分离。

“它从盒子里拿出来的时候，有一个支架，可以用纱线把它推出来。我们正试图把它从核心项目中剥离出来，使它成为自己的子项目。但在我们这样做的同时，我们希望像 Kubernetes 和 Mesos 一样更容易推出。现在我们和纱线紧密相连。我们希望摆脱将纱线作为唯一选择来生产纱线的做法，以此来运营 Fluo，”他说。

由于他也参与了 Accumulo 项目，他说他希望通过使 Accumulo 支持异步读/写操作来增加吞吐量。

你可以在 10 月 16 日马里兰州哥伦比亚的 Accumulo 峰会上了解更多关于 Apache Fluo 项目的信息。

谷歌是新堆栈的赞助商。

通过 Pixabay 的特色图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>