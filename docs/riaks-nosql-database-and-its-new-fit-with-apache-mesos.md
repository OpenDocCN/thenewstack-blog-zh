# Riak 的 NoSQL 数据库及其与 Apache Mesos 的新配合

> 原文：<https://thenewstack.io/riaks-nosql-database-and-its-new-fit-with-apache-mesos/>

[Basho Technologies](http://basho.com/) 与思科合作，使 Riak KV NoSQL 数据库能够在 Apache Mesos 资源管理器上运行，从而自动化客户的底层数据中心基础设施。

据该公司称，Riak KV 管理数据层，Mesos 管理底层基础设施，随着 Mesos 为 Riak 节点聚合资源，集成还允许“按钮”扩展和缩小。

Mesos 是 Twitter 和 Airbnb 用来管理其庞大基础设施的资源管理器。对于这些互联网规模的公司来说，这是一个不同的现实。

> 但越来越多的企业发现，管理单一的应用程序并不重要。扩展很重要，而创新需要的不仅仅是用虚拟机优化服务器。

现在有了这个容器和复杂资源管理器的新世界，世界各地的公司都在玩这个游戏，以了解他们到底想做什么。

在某种程度上，这就是为什么像 Basho 这样的公司看到了 Mesos 生态系统的重要性。无论如何，他们也不是唯一一个将像 Mesos 这样的平台作为接触不断变化的企业客户群的方式的公司。

例如，Cassandra 是一个可扩展的 NoSQL 数据库，是 Riak 的竞争对手，根据 Mesosphere 博客，由于其点对点架构，Riak 非常适合在 Mesos 上运行。它具有横向可伸缩性，没有单点故障和简单的查询语言(CQL)。Mesosphere 是支持 Mesos 的主要公司。

还有像 [Crate](https://crate.io) 这样的公司，它是一个进行同步、分片、缩放和复制的分布式数据存储。它旨在自我修复和自动重新平衡群集。

板条箱与 Mesos 的集成允许跨板条箱实例进行管理，而无需明确了解数量及其规格。板条箱网站上提供了[集成](https://crate.io/overview/)的概述。

据首席执行官 Adam Wray 称，Riak 集成源于 Basho 最近发布的数据平台。该平台针对的是希望使用不同的开源数据库、分析工具或搜索产品构建应用程序的开发人员。为此，它提供了与 [Apache Spark](https://spark.apache.org/) 以及 [Redis](http://redis.io/) 和 [Apache Solr](http://lucene.apache.org/solr/) 等开源搜索技术的集成。

“我们希望能够处理许多数据模型，保持它们的索引、同步、群集、高可用性和高度准确的数据。目标是简化企业大型分布式数据集的管理。我们与思科公司所做的就是将它推进到下一层，”雷说。

> “我们希望为企业提供更加简化的解决方案和数据集，并使数据中心部分在本质上几乎自动扩展，资源调度器形式的 Mesos 是我们整个产品的一部分。”

Basho 正在开发与 Mesos 的开源集成，但也将提供受支持的企业版。Wray 表示，将与思科及其 Intercloud federated public cloud 开展更多合作，以进一步提供该领域的产品。

Wray 说，思科是 Basho 的客户之一。

“思科渴望解决大型分布式数据集的难题。通过与我们合作，他们觉得我们有最好的平台 core RIAK 来实现这一承诺，但他们也需要增加资源组件。他们需要它为自己的服务长途；我们知道这对所有向自己用户提供服务的大型企业客户都有价值，”他说。

Basho 一直试图决定是否建立自己的资源调度程序，但包括思科在内的大规模企业客户都在使用 Mesos。

“一致的主题是:这是一个为分布式环境设计的、经过深思熟虑的、经过良好验证的、资源有效的调度程序。…我们开始直接与 Mesos 合作，并意识到集成开源版本的 Mesos 比出去重新创建轮子更容易。”

Basho 将在 Basho 展台和思科展台展示在 Mesos 上运行的 Riak KV 测试框架，该框架在 MesosCon 的 Intercloud 上运行。Wray 说，Mesosphere 已经认证了与它的 Mesosphere 数据中心操作系统的集成。

Basho 正借助 NoSQL 数据库在企业市场上的受欢迎程度——Wray 表示，该公司的季度增长率为 226%——但面临 Aerospike 和 MemSQL 等公司的新竞争。

然而，Wray 说他认为 Basho 的主要数据库竞争对手是 [MongoDB](https://thenewstack.io/mongodb-grabs-wiredtiger-and-its-talent/) 、 [Cassandra](https://thenewstack.io/armed-with-additional-106-million-datastax-to-keep-pushing-cassandra-to-enterprises/) 和 [Couchbase](http://www.couchbase.com) 。

“我们的客户包括 Telefonic、China Payment、Cisco、Comcast 等，他们收集了更多的数据，并将其作为应用程序的一个战略使能器，这种僵硬的结构、关系数据库的概念是行不通的。在过去的 12 个月里，我看到——我认为这真的在升级——公司已经不再玩 NoSQL 了，当他们玩它的时候，开发者的易用性是唯一重要的事情。但当你从玩它过渡到能够使用大量数据以很大的延迟分发，期望它总是可用，但总是准确，期望水平大幅上升，”他说。

“在 Basho，我们觉得我们的观点胜过了整个行业，因为我们一直致力于可用性、数据准确性、运营规模和简单性。通过思科使用 Mesos，这是我们试图简化的另一件事，这样人们就可以在他们的应用程序中使用数据。”

除了与思科的合作，Wray 表示将在今年年底宣布其他大型合作，并在 30 至 60 天内宣布其他产品组件。

加州大学伯克利分校计算机科学主席兼算法、机器和人类实验室(AMPLab)主任迈克尔·富兰克林表示，Basho 的 Mesos 集成有几个有趣的地方:

> “首先，物联网应用天生具有广泛的分布性和高度的动态性，因此用于物联网数据管理的可扩展、地理分布的解决方案非常有意义。云计算和存储加上动态数据和资源管理软件的结合似乎是部署和发展数据密集型物联网应用的正确方法，”他说。

“其次，大数据领域的创新主要发生在与开源软件社区有密切联系的公司和实验室。思科一直是加州大学伯克利分校 AMPLab 和 RADLab 项目的长期赞助商，Apache Mesos 最初就是在这里开发的。思科对 Apache Mesos 和 Riak 的采用进一步证明了企业软件在快速发展的开源大数据社区的推动下持续快速发展。”

Basho 和思科是新堆栈的赞助商。

特征图片: [Alfonso Sintjago](https://www.flickr.com/photos/asintjago/) 的:[美洲资源中心-2010](https://www.flickr.com/photos/asintjago/4852757000/in/photolist-8oPDA9-7RwyKf-8TmJYp-7KEzh8-8XSpHF-8QRtQt-p9NzcF-dGMwyT-8XVwWp-egw4Wc-5eGk1T-82EV9M-7SxDjQ-96mdrG-7WBRdu-iZZoRL-hgZ5p4-9qpSdv-8XDX96-q8pCt7-6psiby-89Awqa-oTGWde-hVCbL6-qaCmQm-q16dgv-qgUN1J-8NPekA-8ZLyXJ-dEuFC9-9r9Ftc-n7JSwY-qF3qGy-88jGAZ-7AE2vH-7PUFWy-hgZtr6-ftqtuG-9RqMfn-vL94yg-7KKAC7-cTz5RS-qvLFvb-qvQHh2-7Ed1VQ-puvK5X-jGW1K9-qT65FJ-h6MMNE-iZWHQw)获得 [CC 下 2.0](https://creativecommons.org/licenses/by/2.0/) 的授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>