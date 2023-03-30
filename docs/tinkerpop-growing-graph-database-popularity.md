# Tinkerpop 随着图形数据库的流行而发展

> 原文：<https://thenewstack.io/tinkerpop-growing-graph-database-popularity/>

在最近的纽约 [PyData](http://pydata.org/) 会议上，Pokitdok 背后的 PokitDok 数据科学团队描述了它如何在其医疗保健 API 平台中使用 TinkerPop 堆栈，以及 [Titan graph 数据库](http://titan.thinkaurelius.com/)和 Python 及容器。该堆栈允许该小组显示医生的模拟数据集以及与可能与他们预约的消费者的联系。

扩展可用的语言将是 [Tinkerpop](http://tinkerpop.apache.org/) 的主要关注点，这是一个图形计算框架，用于将关系数据库和图形数据库捆绑在一个统一的模型中，它刚刚成为 Apache 软件基金会的顶级项目。

“谈到技术，Tinkerpop 总是很棒，但它只是少数人在做某件事。Apache TinkerPop 的副总裁兼 DataStax 的软件工程师 Stephen Mallette 说。

[![apache-tinkerpop-logo](img/29677a7085765d48b452455748a26ada.png)](http://tinkerpop.apache.org/docs/current/reference/)

随着公司寻求理解他们数据中的关系，图表数据库已经远远超出了社交网站的范畴。Mallette 说，DataStax 的 [DSE Graph](https://thenewstack.io/datastax-unveils-enterprise-graph-database-built-cassandra-titandb/) 和 [IBM Graph](https://thenewstack.io/ibm-bulks-bluemix-apache-spark-based-analytics/) 是 Tinkerpop 最近的两个商业应用，另一个重点将是进一步扩大生态系统。

“我们的重点是我们的框架和接口，以及一些可用于生产的参考实现。它将成长为其他数据库。 [Apache Flink](https://thenewstack.io/apache-flink-addresses-continuous-stream-processing/) 可能是一个【可能的集成】；他说:“在基于 Hbase 的[阿帕奇]孵化器中，还有另一个项目叫做[S2 图 T22。”](http://incubator.apache.org/projects/s2graph.html)

图形计算框架依赖于 [Gremlin](https://github.com/tinkerpop/gremlin/wiki) ，这是一种图形遍历机器和语言，它使用户能够编写称为遍历的复杂查询，可以作为实时事务(OLTP)查询、批量分析图形(OLAP)查询或两者的混合来执行。

许多不同数据系统的参考实现，包括 [Neo4j](https://neo4j.com/) 、 [Apache Giraph](http://giraph.apache.org/) 、Spark 和 Hadoop。这些实现包括商业和开源图形数据库和处理器、Gremlin 语言变体、用于图形分析的可视化应用以及其他工具和库。

“我们采用了用 Java 编写的 Gremlin，并用不同的语言编写它，如 Scala 或 Closure 或 Python。我们正在开发这些东西，这样 JVM 内外的人都能学到一些东西。直到 Tinkerpop 3 正式发布之前，对于在 JVM 之外使用 Python 和其他语言的人来说，真的没有什么选择，”Mallette 说。

据 ASF 称，亚马逊使用 TinkerPop 和 Gremlin 来处理其订单履行图，该图包含大约 1 万亿条边(关系)。它还将 DynamoDB 产品与 Tinkerpop 项目之一的 Titan 进行了整合。

[![tinkerpop3-splash](img/8c7ed444ffe5317272098dc4e1fa39ed.png)](http://tinkerpop.apache.org/docs/current/reference/)

Mallette 说:“Tinkerpop 的优势在于对任何大小或复杂程度的图形都有统一的处理方法。“学习 Gremlin 和 Tinkerpop，并能够在单台机器上对一个小图使用它，或者使用完全相同的代码，并将其分布到一个大型机器集群，这真是一件非常棒的事情。这是一件非常强大的事情。

“避免供应商锁定作为这样做的副作用也非常酷。上午我可以使用 Neo4j，下午我可以使用 Titan，在这之间我可以在 Spark 中执行图形分析工作，所有这些都只是 Gremlin 遍历语言的知识。我不一定需要深入学习所有这些底层技术；仅仅学习 Tinkerpop 就足以让你前进。”

TinkerPop 于 2009 年起源于洛斯阿拉莫斯国家实验室，在 2015 年 1 月被捐赠给阿帕奇孵化器后发布了两次。

尽管人们的兴趣在增长，但图形数据库仍然只是数据库市场的一小部分。451 研究估计它代表了 2860 亿美元部门中的 2 亿美元；Forrester 预测，到 2017 年，行业占有率将达到 25%。

[巴拿马文件](https://panamapapers.icij.org/)，涉及巴拿马律师事务所 Mossack Fonseca 关于隐藏离岸账户的 2.6TB 数据泄露，提出了图形数据库更有趣的[用例之一。](http://www.computerweekly.com/news/450280758/Panama-Papers-revealed-by-graph-database-visualisation-software)

全球调查记者协会(global Institute of Investigative Journalists)花了四年时间仔细研究了超过 1150 万份文件，试图通过匹配电子邮件、法律文件和其他非结构化数据，将姓名与账户联系起来。在这个过程的后期，它使用了 Linkurious 数据可视化工具和 Neo4j 图形数据库来帮助揭示这些联系。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>