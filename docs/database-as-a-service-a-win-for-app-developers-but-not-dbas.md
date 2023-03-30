# 数据库即服务:应用程序开发人员的胜利，但不是数据库管理员

> 原文：<https://thenewstack.io/database-as-a-service-a-win-for-app-developers-but-not-dbas/>

在我的前一篇专栏文章中，我写了“无服务器”趋势如何为应用程序开发人员抽象出基础设施层。同样的事情也发生在数据库上，通过数据库即服务(DBaaS)解决方案，如 Amazon Aurora、MongoDB Atlas、Azure SQL 数据库和 Redis Cloud Essentials。

在去年关于 DBaaS 厂商的[报告](https://www.forrester.com/report/The+Forrester+Wave+DatabaseAsAService+Q2+2019/-/E-RES144407#figure2)中，分析公司 Forrester 指出，这种趋势正在加速新业务应用的部署。DBaaS 为应用程序开发人员提供了“一个数据库平台来快速构建从简单到复杂的应用程序，使他们能够专注于应用程序逻辑，而不是应对数据库管理挑战。”

Forrester 宣布亚马逊、甲骨文、MongoDB、微软和谷歌是蓬勃发展的 DBaaS 市场的领导者，Redis Labs 和其他一些公司被列为“表现强劲的公司”。

对 DBaaS 的需求正在快速增长。在 MongoDB 2020 年第四季度的收益电话会议上，该公司[宣布【Atlas 收入同比增长超过 80%，目前占其总收入的 41%。此外，我最近与 Redis 实验室进行了交谈，他们告诉我 DBaaS 占他们业务的 50%。](https://www.fool.com/earnings/call-transcripts/2020/03/17/mongodb-inc-mdb-q4-2020-earnings-call-transcript.aspx)

对 DBaaS 有如此需求的部分原因是在云上运行数据库的复杂性。首先，现在有很多不同类型的数据库可供选择。SQL 是唯一的数据库游戏的日子已经一去不复返了。NoSQL 数据库——由于其可伸缩性和分布式特性，目前是互联网公司的最爱——正在迅速超越传统的关系数据库。

根据去年的 ScaleGrid 调查，NoSQL 现在占了所有数据库使用量的 40%——这主要归功于流行的云原生选项，如 MongoDB、Redis 和 Cassandra。顺便说一下，所有这些项目都是在 Web 2.0 中期开始的——在亚马逊 2006 年推出第一批云产品后不久。

“NoSQL”一词在 2009 年左右开始流行。这是一个有点模糊的术语，涵盖了多种类型的数据库——键值、文档和宽列只是其中的几个。但是一般来说，NoSQL 数据库没有 SQL 那么结构化，因此比 SQL 更灵活。

DBaaS 市场中的大平台玩家——甲骨文、亚马逊、谷歌和微软——更喜欢覆盖他们的基础，并在云中支持 SQL 和 NoSQL 数据库。这再次提醒我们，SQL 还没有消亡——事实上远非如此。正如 NoSQL 公司 Couchbase [的 Andrew C. Oliver 本周早些时候在新的 Stack](https://thenewstack.io/sql-is-dead-right/) 中所写的，“没有专有的查询语言像 SQL 一样雄辩而简洁地表达应该包含、关联和排除哪些数据。”

据 Forrester 称，亚马逊拥有“最广泛的采用和最广泛的[DBaaS]选项。”它甚至提供了一种叫做亚马逊量子账本数据库的东西，尽管不幸的是它并不是如名字所示的量子计算数据库(它是区块链的产品)。

那么除了 Amazon 和 MongoDB 这样的供应商，谁会从 DBaaS 产品中受益呢？最大的受益者是(你猜对了)开发者，因为这意味着在构建应用程序时少了一个令人头疼的系统问题。

事实上，就被抽象掉的东西而言，开发人员从来没有过这么好的体验。使用无服务器解决方案，开发人员无需接触服务器。现在有了 DBaaS，他们也可以避开数据库。

在[去年 11 月发布的一篇关于新堆栈的帖子](https://thenewstack.io/why-database-as-a-services-dbaas-are-do-or-die-for-todays-cloud/)中， [MongoDB](https://www.mongodb.com/) 云产品副总裁 Andrew Davidson 写道，“新一代的开发人员除了将数据库层抽象成一个可以工作的弹性服务之外，无法理解还能做什么。”

但是，在 20 世纪 80 年代和 90 年代，IT 团队的主要成员数据库管理员(DBA)发生了什么变化呢？嗯，如果亚马逊最近的[大规模数据库迁移](https://aws.amazon.com/blogs/aws/migration-complete-amazons-consumer-business-just-turned-off-its-final-oracle-database/)——将 75pb 的数据从数千个 Oracle 数据库转移到亚马逊自己的 DBaaS 产品上——有任何迹象表明，DBA 的时间现在已经“解放”了亚马逊网络服务首席传道者杰夫·巴尔解释道:

*“…我们的数据库管理员曾经花费大量时间管理和扩展我们的传统 Oracle 数据库。迁移节省了时间，我们的数据库管理员现在可以利用这些时间更好地进行性能监控和查询优化，所有这些都是为了让他们提供更好的客户体验。”*

我不确定 Amazon 的 DBA 是否会将对性能监控和优化的关注视为职业生涯的一大进步。这些听起来像是自动化成熟的任务，特别是在 DevOps 时代，操作自动化是开发过程的关键组成部分。

然而，并不是所有人都认为 DBA 是濒危物种。根据最近在开源数据库服务公司 [Percona](https://www.percona.com/) 上的[博客文章](https://www.percona.com/blog/2020/03/24/the-changing-face-of-enterprise-dbas-in-cloud-driven-environments/)，DBA 现在是“设计和调优数据库以支持应用程序”的人在 Percona 看来，现代数据库管理员越来越关注设计和架构，这些东西不太容易自动化。

这可能是真的，但是 NoSQL 趋势对开发人员来说是一个福音，你不得不认为这是以数据库管理员为代价的。传统的关系数据库需要一套不同于开发人员所知道的技能，这就是为什么 DBA 在 SQL 数据库占主导地位的时候如此有价值。但是有了 NoSQL，开发者可以用更适合他们在 T4 工作的方式与数据互动。在去年 12 月发布的关于新堆栈的播客中，Redis 实验室的首席产品官 Alvin Richards 很好地解释了这一点:

*“事实上，开发人员看到的是他们熟悉的数据结构。所以他们得到列表，集合，排序集合，他们得到 JSON 文档。这是他们的心理模型。在关系世界中，您拥有 DBA 拥有的数据库模式，然后您拥有 Java 代码或 C#代码。而且这两个东西看起来完全不一样。所以你有这个映射层来做这个不断的转换。这对一个开发者来说是非常陌生的。”*

当然，开发人员现在还必须应对云世界日益增加的复杂性，包括分布在许多不同云和本地服务器上的数据。但最终，这将导致更强大的分布式应用。

回到 3 月份的 MongoDB 收益电话会议，首席执行官 [Dev Ittycheria](https://www.linkedin.com/in/dittycheria/) 指出，该公司未来战略的一个关键部分是“未来的应用程序将在功能和范围上大幅扩展。”

Ittycheria 表示，未来的应用程序将需要处理“大量的实时数据”，因此，“开发人员将需要一个统一的界面，旨在汇集大规模的数据，以更快更有效地构建这些新的应用程序。”

DBaaS 趋势有助于这一未来的到来，因为它将数据库直接交到了开发人员的手中。

亚马逊网络服务、MongoDB 和 Redis 实验室是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>