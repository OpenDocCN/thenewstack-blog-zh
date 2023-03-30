# 微软为 Postgres Scale 获取 Citus 数据

> 原文：<https://thenewstack.io/microsoft-acquires-citus-data-for-postgres-scale/>

微软周四宣布，它已经收购了总部位于旧金山的初创公司 Citus Data。

作为一个[开源 PostgreSQL 扩展](https://github.com/citusdata/citus)，Citus 软件本质上将应用程序变成了一个分布式数据库。Citus Data 提供了 NoSQL 数据库的水平可伸缩性以及关系数据库的事务一致性和功能。

据 Citus Data [的一篇博客文章](https://www.citusdata.com/blog/2019/01/24/microsoft-acquires-citus-data/)称，该公司成立于八年前，当时科技界的大部分注意力都集中在 Hadoop 和 NoSQL 数据库上，这些数据库被认为比传统的关系型数据库提供了更多的数据管理选项。

然而，该公司选择建立在近 30 年历史的 Postgres 基础上，尽管它已有 30 年的历史，但基于其持续的受欢迎程度，DB-Engines 将 2018 年的 [DBMS 评为年度](https://db-engines.com/en/blog_post/79)。

从高层次来看， [Citus 将数据](https://thenewstack.io/citus-data-turns-postgres-scalable-distributed-database-system/)分布在一个商用服务器集群中。然后，传入的 SQL 查询会在这些服务器上并行处理。

它使用类似 Hadoop 的架构:一个主节点使用关于碎片的元数据，并将传入查询的碎片打包到实际上并行运行查询片段的工作节点。

它提供:

*   SQL 分析的大规模并行处理。
*   分布式数据库表上的实时插入/更新。
*   商用硬件上的动态可扩展性，能够轻松添加或删除节点。
*   JSON 和结构化数据放在一个数据库中。
*   Postgres 的表现力和熟悉度。

斯坦福校友[奥兹冈·埃尔多安](https://github.com/ozgune)、[苏梅德·帕塔克](https://www.linkedin.com/in/sumedh-pathak/)和[乌穆尔·库布库](https://twitter.com/umurc?lang=en)于 2010 年创立了这家公司，并于 2011 年夏天通过 Y Combinator。该公司于 2016 年 3 月开源了其技术。它已经筹集了超过 1300 万美元。

“微软和 Citus Data 将共同进一步释放数据的力量，使客户能够扩展复杂的多租户 SaaS 应用程序，并通过对数十亿行的实时分析加快洞察时间，所有这些都使用开发人员熟悉和喜爱的 PostgreSQL 工具，”【Azure Data 公司副总裁 Rohan Kumar 在宣布收购的博客文章[中写道。交易条款没有披露。](https://blogs.microsoft.com/blog/2019/01/24/microsoft-acquires-citus-data-re-affirming-its-commitment-to-open-source-and-accelerating-azure-postgresql-performance-and-scale/)

微软称此次收购是其继续支持开源数据库(包括 MySQL、PostgreSQL 和 MariaDB)的一部分，也是其投资 Linux 上的开源 SQL Server、带有 Azure Cosmos DB 的多模式 NoSQL 数据库以及开源分析项目 Hadoop 和 Spark 的一部分。

微软预计不会大幅改变 Citus Data 的业务，但库马尔补充说，此次收购将“加速从 Azure 到 PostgreSQL 的关键企业就绪功能的交付，并使关键的 PostgreSQL 工作负载能够放心地在 Azure 上运行。”

Citus 是一个完全托管的数据库服务、企业软件和免费开源下载。

Citus 的联合创始人补充道:“作为微软的一部分，我们将继续专注于在 PostgreSQL 的基础上构建一个令人惊叹的数据库，为我们的用户提供他们所需的改变游戏规则的规模、性能和弹性。我们将继续推动这一领域的创新。”

Citus 并不是唯一一家基于 Postgres 的创业公司。它是时间序列数据库[时标](https://thenewstack.io/timescaledb-focuses-query-power-scale/)的基础，而[易碎数据](/crunchy-data-brings-kubernetes-operator-postgres/)和 [PingCAP](https://www.pingcap.com/en/) 都是建立在基于 Postgres 的数据库的[操作符](/coreos-contributes-operators-containers-configure-kubernetes/)的概念之上。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>