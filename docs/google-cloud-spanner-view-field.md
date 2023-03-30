# Google Cloud Spanner:弹性分布式 SQL 数据库服务

> 原文：<https://thenewstack.io/google-cloud-spanner-view-field/>

总部位于旧金山的初创公司 Quizlet 提供在线抽认卡和其他教育工具，它发现谷歌的新[云扳手](https://cloud.google.com/spanner/)是解决其扩展和管理高通量数据库问题的最佳解决方案。

在准备应对流量高峰时，其增长率和业务的季节性带来了令人头疼的问题，以前它通过垂直分片和添加副本来管理流量高峰。

谷歌[本月早些时候推出了云扳手](https://www.wired.com/2017/02/spanner-google-database-harnessed-time-now-open-everyone/)，称其为“第一个在全球范围内分发数据并支持外部一致的分布式交易的系统。”它描述它提供了“ACID 事务和 SQL 语义，而没有放弃水平伸缩和高可用性。”

据 NoSQL 数据库 [ScyllaDB](http://www.scylladb.com/) 的首席执行官兼创始人多尔·劳尔称，它已经将上限定理的边界延伸到了极限。该定理指出，分布式系统只能同时提供这三件事情中的两件:一致性、可用性和/或分区容差。

在一篇[博客文章](https://cloudplatform.googleblog.com/2017/02/inside-Cloud-Spanner-and-the-CAP-Theorem.html)中，Google 的 [Eric Brewer](https://research.google.com/pubs/EricBrewer.html) 说，根据他的 CAP 定理(该定理指出一个分布式系统只能有以下两个特征:一致性[C]、可用性[A]、分区[P])，用户将 Spanner 体验为一个 CA 系统，从技术上来说，它是一个 CP 系统，但可以实现多区域使用的五个九可用性的目标。

Quizlet 平台负责人 [Peter Bakkum](https://github.com/bakks) ，他指出了与谷歌 2012 年发表的原始[论文](https://research.google.com/archive/spanner.html)的显著差异，在一篇博客文章中概述了该公司对 Spanner 的测试，总结道:

*Cloud Spanner 是我们见过的用于扩展高吞吐量关系型工作负载的最引人注目的云服务，在我们的案例中是 MySQL。作为一个生产系统，它有些粗糙，但是它的延迟和可伸缩性是独一无二的。我们还没有见过另一个数据库，无论是关系数据库还是其他数据库，能够像 Cloud Spanner 那样平稳快速地扩展。而且它被托管的事实消除了整个维护类别。*

当然，新的云服务有利有弊。

他指出，它是专门开发来利用谷歌的大规模云，并使用 GPS 和原子钟来协调其分布式节点。它的全球[时间一致性](https://www.wired.com/2017/02/spanner-google-database-harnessed-time-now-open-everyone/)一直是它最受关注的特性之一。

扳手的计时技术 [TrueTime](https://research.google.com/pubs/pub45855.html) 目前在市场上是独一无二的，就像建立在谷歌先前工作基础上的项目的其余部分一样，[蟑螂实验室](https://github.com/spencerkimball)的首席执行官斯潘塞·金博尔指出。他和另外两名前谷歌员工着手开发 Spanner 的开源版本，名为[cocroach db](https://thenewstack.io/cockroachdb-unkillable-distributed-sql-database/)，他说这与 Spanner 的大部分功能相匹配，但不是全部，也不是 TrueTime。

“最大的区别是，你不能像谷歌创建 Spanner 那样在开源中构建软件，”他说。

谷歌自己也没有将该软件作为开源软件发布。

“谷歌不能开源的原因是，它是在现有系统的基础上构建新技术的。Spanner 是建立在巨型分布式文件系统[之上的。Colossus 构建在“D”之上，它将磁盘导出到网络，以便其他服务可以使用它们。所有这些东西都使用](https://www.wired.com/2012/07/google-colossus/) [Chubby](https://blog.acolyer.org/2015/02/13/the-chubby-lock-service-for-loosely-coupled-distributed-systems/) ，它相当于谷歌的 [ZooKeeper](https://zookeeper.apache.org/) 【关键价值故事】……该架构依赖于所有这些持续发展的复杂系统。这种模式对谷歌有很多好处，但如果你想为开源用户带来一些东西，显然(构建所有这些部分)是不现实的。”

Spanner 和蟑螂都宣称，即使某些系统出现故障，它们也能保持在线，并自动平衡服务器之间的资源。但是他们有一个不同的故障转移故事，根据 Kimball 的说法，他讲述了他在支付供应商 Square 的一个场景。

传统上，当刷卡时，进行授权，该人签名，可能添加小费，然后它作为“捕获”进入数据中心。如果数据中心出现问题，它会发送一条错误消息，告诉商家重新刷信用卡。金博尔说，这将启动第二次授权，授权将转到另一个数据中心，如果它们之间没有足够的沟通，就会导致客户卡上的两笔交易必须进行对账——这需要大量的移动部件。

在这种情况下，Spanner 和蟑螂将使用三个数据中心。如果交易开始时一个不可用，另外两个中至少有一个会自动处理，无需重新刷卡。

“没有明确的故障转移步骤；没有向商家发送错误消息。底层数据库保证至少有一个其他数据中心知道它。软件开发人员不必在软件中构建特殊的功能来知道这些事情可能会出错。这是 Spanner 和 CochroachDB 的基本生存特性之一，”他说。

他说，这两者还“允许 SQL 数据库变得任意大”，解决了 Oracle、MySQL、Postgres 等传统 SQL 关系数据库的可伸缩性问题。

[Monte Zweben](https://www.linkedin.com/in/mzweben/),[Splice Machine](https://www.splicemachine.com/)的联合创始人兼首席执行官称 Spanner Cloud 证实了市场对新型数据库的需求，并使 SQL 战胜了 NoSQL 的批评者。

“第一批横向扩展的数据库实际上只专注于分析。很少有人远程处理事务性工作负载，”他说。“我们认为这证明了(事务型)数据库正在向外扩展。”

他说，它的优势是跨数据中心“以一种非常好的方式”工作的高可用性，但这是市场上其他人很快就会赶上的功能。

对于 Spanner 的缺点，Zweben 指出，Spanner 的高可用性的代价是在某些应用程序中无法接受的延迟水平。

他说，如果你正在执行银行交易，比如机票预订，你可以承受一分钟的延迟，同时确保它们在多个数据中心提交，Spanner 可能是一个很好的数据库。

有趣的是，Quizlet 发现，与运行 MySQL 的虚拟机相比，Spanner 查询在低吞吐量下具有更高的延迟，但在横向扩展的某个点上，延迟水平保持不变，而随着 MySQL 的增长而增长。

然而，Zweben 说，如果你有一个客户服务应用程序，要求你对数百万笔交易做出非凡的响应，同时分析客户的盈利能力，并可能训练一个机器学习模型，这些同时进行的交易和分析需求更适合像 [Splice Machine](https://www.splicemachine.com/product/how-it-works/) 这样的数据库，它建立在 [Spark engine](http://spark.apache.org/) 之上。

他坚持认为 Spanner 并没有针对被称为[混合事务/分析处理(HTAP)](http://www.enterpriseappstoday.com/data-management/how-htap-database-technology-can-help-you.html) 的同步事务和分析处理进行优化。Kimball 认为 Spanner 和蟑螂都有 HTAP 功能，尽管他承认它们还没有达到类似 Hadoop 的水平，尽管它们可以很容易地被添加进来，他说。

“SQL 实际上非常适合分析，”他说。“您可以使用 Spanner 处理分布式 SQL 查询执行中的大量工作负载。蟑螂没有扳手走得远，但我们在过去的一年里取得了长足的进步，”他说。

与此同时，Laor 说他不认为 Spanner 会像 Scylla 一样排挤 NoSQL 的数据库。

Apache Cassandra 的 C++实现, [Scylla](http://www.scylladb.com/) 背后的人声称，它是世界上最快的 NoSQL 数据库，还提供高可用性、水平可伸缩性和低延迟。

他说，它允许开箱即用的多数据中心读取器/写入器，并且分区容忍度从未妥协。

“许多大数据工作负载不需要事务，因此不需要繁重的代价——事务、连接、MVCC(多版本并发控制)，因此 Scylla 可以轻松胜过 Spanner，”他说。

然而，根据金博尔的说法，虽然许多公司确实没有谷歌的全球规模需求，但即使是很小的初创公司也认为自己成长到了那个地步，这引起了人们对 Spanner 的主要担忧。

“有了 Spanner，你就承诺在 [Google Compute Engine](https://cloud.google.com/compute/) (GCE)中运行服务，并且很可能在服务的生命周期中一直在那里运行。如果你选择经营自己的栈，你就不会有下坡路，”他说。

他指出，Dropbox 是一家以亚马逊的 S3 存储服务起家的公司，后来决定开发自己的技术，这是一项重大任务。他说，GCE 上的 Snapchat 将很快面临类似的决定。

“如果你只是在谈论使用 AWS、GCE 或 Azure 的计算资源，那是一项相当低摩擦的投资。您可以相对简单地重新定位您的服务，因为它们都使用相同类型的底层硬件——大多数这些事情现在都是通过基于容器的技术和 Kubernetes 来完成的。它非常便于携带，”他解释道。

“但一旦你将数据存储到一个专有系统中，出站口充其量是模糊的，而且可能是不可能的，除非你是像 Dropbox 这样的公司，愿意投入资源和精力来提供自己的解决方案。”

他说,“蟑螂”不提供云服务，尽管将来某个时候会提供。它是可以在私有或公共云中运行的软件。它的灵活性允许您在它们之间迁移服务，只需更改配置，而不会让您的用户停机。

它还在进行地理分区，这是 Spanner 所没有的。它通过改善全球客户之间的沟通，提供了一种简单的方法来重新定位区域数据。

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>