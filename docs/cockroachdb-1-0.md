# CockroachDB 分布式 SQL 数据库报告用于生产任务

> 原文：<https://thenewstack.io/cockroachdb-1-0/>

每个人都知道细节中的魔鬼，但是谁能想到在构建一个高度一致、始终可用、可伸缩的 SQL 数据库时会有这么多的细节呢？

据首席执行官[斯潘塞·金博尔](https://www.linkedin.com/in/spencerwkimball/)称，这是蟑螂实验室从其 CockroachDB 项目的测试版中吸取的教训。他说，与此同时，该公司也被对该项目的兴趣“冲昏了头脑”。

经过三年的制作，该公司宣布该数据库现在已经可以生产了。

CockroachDB 是一个分布式 SQL 数据库，构建在事务性和强一致性的键值存储之上。它水平缩放；从磁盘、机器、机架甚至数据中心故障中幸存下来——因此它指的是昆虫的生存能力——延迟中断最少，无需人工干预。它还支持强一致性的 ACID 事务；并为结构化、操作和查询数据提供了熟悉的 SQL API。

蟑螂实验室的 Jessica Edwards 在之前的一篇关于新堆栈的文章中解释了[cocroach db 架构](https://thenewstack.io/cockroachdb-unkillable-distributed-sql-database/)。

金博尔在[的博客文章](https://www.cockroachlabs.com/blog/cockroachdb-1-0-release/)中解释说，过去一年的开发集中在三个领域:分布式 SQL 支持小型和大型用例的无缝扩展；多活动可用性，实现始终一致的高可用性；以及在几乎任何环境中的灵活部署。

自 2016 年 3 月测试版发布以来，它的下载量已超过 10 万次。客户包括[英雄实验室](https://heroiclabs.com/)，它为构建社交和实时游戏提供开源的可扩展服务器，以及中国互联网公司百度，它最近展示了一个用例，涉及每天处理 20 亿次插入，同时针对“混沌事件”进行测试，以检查弹性。

1.0 版提供了完全分布式的 ACID 事务、零停机模式更改以及对二级索引和外键的支持。它还引入了分布式查询执行引擎，使分布式连接能够支持分析查询，随着节点添加到集群中，分析查询的速度会线性加快。

[https://www.youtube.com/embed/tV-WXM2IJ3U?feature=oembed](https://www.youtube.com/embed/tV-WXM2IJ3U?feature=oembed)

视频

该数据库使用“多活动可用性”的概念，这一概念起源于蟑螂创始人的前雇主谷歌。它包括使用两种以上的资源，并从他们那里迅速获得一致性的共识，而不是达到最终的一致性。他说，亚马逊的 Aurora 也提供类似的跨站点复制。

他说，数据不仅存在于三个或更多的地方，而且处理也发生在这些不同的地方。任何节点、任何复制站点都可以为应用程序提供服务。

Kimball 说，编写最初的数据库实现花了大约一周时间，解决问题花了两年多时间，尤其是围绕 [Raft](https://raft.github.io/) consensus 算法。

CockroachDB 可以在笔记本电脑、公共云或私有云上本地运行。它仍然没有自己的云服务，尽管这可能会在未来 12 个月内实现。金博尔说，与 AWS 或谷歌云服务相比，它的优势在于它不会绑定到特定的云。

在之前讨论[谷歌扳手](https://thenewstack.io/google-cloud-spanner-view-field/)时，金博尔认为，由于它是专有的，如果你后来决定要将数据转移到其他地方，就没有真正的障碍。许多大公司运营着自己的数据中心，但正在寻求向公共云服务转移。他说，这对于蟑螂来说很简单——只是一个配置上的改变。

[蟑螂经常被比作](https://www.nextplatform.com/2017/02/22/google-spanner-inspires-cockroachdb-outrun/)和[谷歌扳手](https://thenewstack.io/google-cloud-spanner-view-field/)，后者占据了最近数据库的大部分头条。然而，许多其他项目也加入了为分布式 SQL 增加规模的探索，包括 [TiDB](https://thenewstack.io/tidb-brings-distributed-scalability-sql/) ，它也旨在构建 Spanner 的开源版本； [Crate](https://thenewstack.io/crate-addresses-database-speed-scaling-standard-sql/) ，重点支持 Docker 容器和微服务；和[时标](https://www.timescale.com/)，为时序数据构建。还有 [FaunaDB](https://thenewstack.io/faunadb-harnesses-serverless-cloud/) ，它将自己描述为关系型，但不是 SQL。

蟑螂实验室还宣布了 2700 万美元的 B 轮融资，由 Redpoint Ventures 的 Satish Dharmaraj 领投，Benchmark、FirstMark Capital、GV(原谷歌风投)、Index Ventures 和 Work-Bench 也参与了融资。

金博尔说，新的资金将进一步使该公司能够努力填补公司需求和数据库提供之间的差距。

该公司一直在宣传地理分区，称其竞争对手不具备这一功能。蟑螂计划在今年年底实现地理分区测试版。

他说，就公司需要什么来运行全球服务而言，这只是冰山一角，特别是随着更多涵盖数据主权的法规的出现。

Kimball 之前解释过地理分区是将数据移动到不同区域的有效方法，因为毕竟客户确实会移动:

“地理分区允许公司拥有单一的逻辑数据库。但是每个区域都是透明和独立的。澳大利亚客户的数据位于澳大利亚。欧盟数据仅限于欧盟。在德国，这可能比欧盟还要严格。但是如果需要的话，系统中没有任何东西可以阻止你在这些系统之间进行操作。因此，如果您跨区域添加一些功能，可以通过一次操作完成。这使它原子化，使它一致，”他说。

从开发人员的角度来看，它只是数据库模式中的一列。假设数据位于欧盟，如果您更改该字段，关于该客户的所有数据都会移到后台。这对于运营团队来说更简单，因为您拥有规模经济。你有一个全球服务，而不是一套不同的监控，不同的机器，不同的发布周期。

CockroachDB 起源于 [GitHub 项目](https://github.com/cockroachdb)。然而，该公司还宣布了付费企业层。一个企业级功能是分布式增量备份和恢复。免费版本包括非分布式备份和恢复。

金博尔说，该公司需要一个可行的商业模式，但它希望在免费版本中保留大多数真正有用的功能。他说，只有那些只适用于拥有庞大数据集的大公司的产品才会进入企业版。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>