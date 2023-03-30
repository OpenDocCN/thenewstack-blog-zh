# 阿帕奇晶洞产生了“各种各样的内存中的东西”

> 原文：<https://thenewstack.io/apache-geode-spawns-sorts-memory-things/>

阿帕奇晶洞有点像六个盲人描述一头大象。今年早些时候， [Ampool](http://www.ampool.io/) 的产品经理 [Nitin Lamba](https://www.linkedin.com/in/nitinlamba) 告诉 [meetup group](https://www.youtube.com/watch?v=VzDRv1-R-8Q) 说。

[Geode](http://geode.apache.org/) 是一个分布式内存计算和数据管理平台，可灵活扩展，为大数据应用提供高吞吐量和低延迟。它在多个进程之间共享内存、CPU 和网络资源，还可以选择使用本地磁盘存储来管理应用程序对象和行为。

使用动态复制和数据分区技术，它提供了高可用性、改进的性能、可伸缩性和容错能力。

是分布式 [Redis](https://redis.io/) 吗？是的，兰巴说。是 [Memcached](https://memcached.org/) 吗？也是的。作为数据库，它可以运行对象查询，但不能运行 SQL 查询。

[Geode](https://cwiki.apache.org/confluence/display/GEODE/Index) 是“一个开发各种内存中事物的地方，根据你如何使用 Geode 生产的构建模块，你可以获得各种类型的产品，”Pivotal 开源总监兼开放数据平台倡议技术副总裁[Roman Shaposhnik](https://thenewstack.io/hadoop-standards-group-odpi-releases-runtime-specification/)在一次采访中说。

它可以用来构建数据库、数据网格等等。它正被用于事务处理；事件通知和处理；高可用性分布式缓存。例如:

*   流媒体项目 [Apache Apex](https://thenewstack.io/apache-gets-another-real-time-stream-processing-framework-apex/) 背后的公司 Data Torrent，正在将 Geode 与 [Apex](https://apex.apache.org/) 一起用于大数据项目的内存数据交换层。

*   加拿大帝国商业银行使用 Geode 作为数据和计算网格来评估多个交易系统的金融风险。

*   法国金融服务 IT 风险管理软件供应商 Murex 使用 Geode 和 [Storm](http://storm.apache.org/) 进行近实时聚合和通知。它将 Geode 用于不可变事件和事件日志记录，还用于连续查询，这是一组分布式、可扩展的内存侦听器，使用数据来识别事件通知并将其推送到客户端。

*   [西南航空](https://www.youtube.com/watch?list=PL62pIycqXx-RCEP2APj4Mq9Oeyvskj_0K&v=br1U6ok2p2w)正在使用它来改善其运营、货物和机组人员调度系统以及网站的实时决策。

## 对等系统

在其核心，Geode 是一个用于 [JVM](https://docs.oracle.com/javase/specs/jvms/se7/html/) ， [Swapnil Bawaskar](https://github.com/sbawaska) 的分布式散列表，Pivotal 的分布式系统软件工程师在接受[软件工程日报](https://softwareengineeringdaily.com/2016/11/21/apache-geode-with-swapnil-bawaskar/)播客采访时解释道。

它的抽象是缓存和区域。缓存是数据管理的一个单元，基本上是区域的集合。

根据 Lamba 的说法，一个地区是“类固醇的关键/价值储存库”。它们是分布式的和高度并发的。您可以将数据存储在内存中，也可以将其推送到磁盘。可以复制一个区域—集群中的每个成员都获得相同的数据—或者您可以选择将数据划分到多个节点上，这是一个更具可扩展性的解决方案。

因为它非常重视一致性，所以如果您制作了数据的两个副本，它可以确保主数据和两个冗余副本是一致的，然后再向用户返回一个确认，比如说 put 已经完成。

对于复制的区域，您可以选择向其他成员进行异步发送；这对于分区区域是不允许的。

成员是一个角色，一个客户端，一个服务器。这是一个可以存储数据的层。它可以嵌入到应用程序中。它可以被定义为客户端缓存。你可以有不同的配置或拓扑结构来配置它，Lamba 解释说。

对于经常查找的数据，您可以在应用程序中创建该数据的本地副本(客户端缓存),与主副本同步。

它还有一个名为定位器的发现服务，可帮助地理数据库服务器相互查找，并帮助地理数据库客户端查找服务器。

这是一个点对点的系统。如果定位器关闭，其他服务器仍然知道其他服务器在做什么，并且能够在它们之间解决问题。您可以添加服务器进行扩展，它们可以相互发现和了解。

Lamba 说，它的接口是 Java、REST 或 CLI，尽管与 [Redis](https://redis.io/) 、 [Lucene](https://lucene.apache.org/) 和 [Spark](http://spark.apache.org/) 的接口是实验性的。

根据 Bawaskar 的说法，Geode 可以在你难以扩展关系数据库以满足应用需求的任何时候使用。

“我们还看到它被用来实现 [CQRS](https://www.codeproject.com/articles/555855/introduction-to-cqrs) (命令查询责任分离)模式。这个想法是独立地扩展你的读写能力。通常会使用 Kafka 之类的系统来处理进入您系统的所有事件，然后因为 Geode 具有查询语义以及连续查询功能，所以您可以在 CQRS 模式上使用 Geode。

“此外，对于需要以主动-主动方式跨地理位置部署的应用程序，Geode 也可以做到这一点，”他说，例如，一家在伦敦、东京和纽约开展业务的贸易公司希望使用其本地集群，但也要将数据复制到其他站点以进行协调和业务处理。

他指出了 [CAP 定理](https://dzone.com/articles/better-explaining-cap-theorem)，该定理指出，在分区系统上，您必须在一致性或可用性之间做出选择，因为您不能放弃云中的分区容差。Geode 允许分区系统的用户在更注重一致性还是可用性之间进行选择。

## 寻求多样性

Geode 代码库最初由 Gemstone Systems 于 2002 年以 GemFire 的名义开发，后来被 VMware 收购。GemFire 技术在 2013 年被 Pivotal 剥离时被该公司收购。Pivotal [于 2015 年 4 月向 Apache 孵化器提交了 GemFire 技术](https://thenewstack.io/pivotal-makes-in-memory-database-gemfire-open-source/)，项目名称为 Geode。上个月成为顶级项目。

它最初引起人们的兴趣是因为华尔街交易平台中使用的交易数据引擎。现在，超过 600 家企业将该技术用于要求低延迟和 24×7 可用性的大规模业务应用。

Pivotal 在 2015 年宣布计划开源其整个大数据套件，包括 GemFire，分析大规模并行处理(MPP)数据仓库 [Greenplum Database](http://www.infoworld.com/article/2999396/big-data/greenplum-goes-open-source-and-a-new-cloud-analytics-star-is-born.html) 和 [HAWQ](https://thenewstack.io/hawq/) ，一个基于 SQL 的 Hadoop 分析引擎。

根据 Shaposhnik 的说法，Geode 和 Apache Ignite 从类似的目的出发，但他认为 [Ignite](https://ignite.apache.org/) 更倾向于 SAP HANA 的替代品。

根据 Shaposhnik 的说法，Pivotal 仍在开发其商业 GemFire 产品，专注于 [Spring](https://spring.io/) 集成，该集成涉及将应用逻辑与数据库逻辑解耦，从而更容易在微服务架构中切换数据库。

自项目开始以来，大部分工作都围绕着[重构 Geode 的核心](https://issues.apache.org/jira/browse/GEODE-77)，以便在最新版本的 jgroups 上运行；[广域网复制和连续查询](http://markmail.org/message/sulh26y7bazli3wk)功能；和[原生客户端](http://markmail.org/thread/aqxnyusltqf7shtd)功能。

“我希望看到这个项目变得更加多样化，只要有更多的公司参与，”Shaposhnik 说。“我们有不同的公司，但老实说，Pivotal 仍然由许多贡献者主导。”

他说，他相信治理模型将使项目达到 Spark 或 Hadoop 的多样性水平，其中 30%或更少的贡献者来自一家公司。

与 Spring、Spark 和 Redis-to-Geode 适配器的集成正在进行中。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>