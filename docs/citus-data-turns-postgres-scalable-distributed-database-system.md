# Citus Data 将 Postgres 变成一个可扩展的分布式数据库系统

> 原文：<https://thenewstack.io/citus-data-turns-postgres-scalable-distributed-database-system/>

许多新数据库已经接受了分布式 SQL 的挑战，包括[谷歌云扳手](https://thenewstack.io/google-cloud-spanner-view-field/)、[cocroach db](https://thenewstack.io/cockroachdb-unkillable-distributed-sql-database/)、 [TiDB](https://thenewstack.io/tidb-brings-distributed-scalability-sql/) 、 [CrateDB](https://thenewstack.io/crate-addresses-database-speed-scaling-standard-sql/) 和 [FaunaDB。其他的，比如拼接机](https://thenewstack.io/faunadb-harnesses-serverless-cloud/)[和 Yugabyte](https://thenewstack.io/splice-machine-hybrid-sql-system-fuses-transactions-analytics/) 已经采取了一种混合的方法来解决 SQL 和 NoSQL 的争论。

总部位于旧金山的 Citus Data 并没有像其他人一样从零开始，而是专注于制作可靠的、20 年前的 Postgres 量表。

“我们希望解决为客户扩展数据库的难题，”Citus Data 的云计算主管 Craig Kerstiens 说。

“扩展数据库的老方法是不断扩展，直到无法再扩展为止。“你只能做到这一步，”克斯廷斯说。“我们只是让你继续扩展数据库。”

该公司希望客户能够专注于构建功能，而不是减轻他们的数据库痛苦。

Citus Data 提供了一个[扩展](https://www.citusdata.com/blog/2017/10/25/what-it-means-to-be-a-postgresql-extension/),它依赖于 Postgres 的 API 而不是 fork，这需要在每次新版本的 Postgres 出来时进行返工。这意味着它可以更快地保持最新状态。

它提供跨商用节点集群的自动分片和复制。如果集群中的任何节点变得不可用，Citus 只需将任何写操作或查询重定向到其他节点中的一个，该节点维护受影响碎片的副本。

Kerstiens 说，其最大的客户在一个 40 节点的集群上运行着大约 500 的数据。

他列举了 Citus 数据的两个主要用例:

*   面向客户的快速增长的 B-to-B 应用，如谷歌推荐的 CRM[prosper works](https://www.prosperworks.com/)。它增长如此之快，以至于公司认为它可能不得不停止吸收新用户。它发现答案是迁移到单个节点之外。
*   面向客户的分析仪表板，面向全球顶级内容交付网络(cdn)之一 Cloudflare 等客户。这些客户有成千上万的用户实时点击这些控制面板，并且需要数百 TB 数据的亚秒级响应时间。

**水平可扩展性**

斯坦福大学的校友[奥兹冈·埃尔多安](https://github.com/ozgune)、[苏迈德·帕塔克](https://www.linkedin.com/in/sumedh-pathak/)和[乌穆尔·库布库](https://twitter.com/umurc?lang=en)于 2010 年创立了这家公司，并于 2011 年夏天通过 Y Combinator。该公司于 2016 年 3 月开源了其技术。它已经筹集了超过 1300 万美元。

Citus Data 提供了 NoSQL 数据库的水平可伸缩性以及关系数据库的事务一致性和功能。

在高层次上，Citus 将数据分布在一个商用服务器集群中。然后，传入的 SQL 查询会在这些服务器上并行处理。

它使用类似 Hadoop 的架构:一个主节点使用关于碎片的元数据，并将传入查询的碎片打包到实际上并行运行查询片段的工作节点。

将查询分布到整个集群利用了所有相关节点和每个节点上所有单个核心的处理能力。

对于应用程序来说，协调器节点看起来像一个单节点 Postgres。它汇总来自工作节点的结果，并交付最终结果。它还希望最小化通过网络传输的数据量。

它提供:

*   SQL 分析的大规模并行处理。
*   分布式数据库表上的实时插入/更新。
*   商用硬件上的动态可扩展性，能够轻松添加或删除节点。
*   JSON 和结构化数据放在一个数据库中。
*   Postgres 的表现力和熟悉度。
*   面向超过 100，000 名租户的多租户。它支持租户隔离，为大型租户提供性能保证，并具有引用表的概念，以减少跨租户的数据重复。

IronNet 网络安全公司的首席软件架构师 Jarred Nicholls[说:“Citus 让我们有可能做一些在 NoSQL 世界里会是噩梦的事情。“迁移到 Citus 提高了我们数据库的可靠性和性能，事实上，它不是一个黑匣子，所有 Citus 元数据都是开放和可破解的，这给了我们很大的灵活性。”](https://github.com/jnicholls)

Kerstiens 说，该公司主要与手工分片的企业竞争，这可能需要工程师 6 个月到 2 年的时间。这是一笔很大的投资，而且相当耗时。

“如果你关心性能，不希望在解决性能问题时不得不停止功能开发六个月，这就是我们从客户那里看到我们大多数采用的地方，”Kerstiens 说。

## 专注于云服务

Citus Data 提供开源和企业版本，但最近专注于 AWS 上的托管服务。

它最近在其 [Citus Cloud](https://www.citusdata.com/product/cloud) 产品中增加了新的[功能](https://www.citusdata.com/blog/2017/11/16/citus-cloud-2-postgres-and-scale-without-compromise/)，包括:

*   **Warp** ，它允许您在准备迁移时，通过将所有更新流式传输到 Citus 云集群，继续写入现有的单节点 Postgres 数据库。
*   **零停机碎片再平衡器**支持客户在添加节点时不停机地弹性扩展内存、计算和存储。
*   **时间点恢复，**允许用户将数据库回滚到
*   过去 10 天。
*   **Followers，**数据库的最新只读副本，使开发人员和分析师能够运行实时、复杂的查询，而不会给生产数据库带来任何查询负载。
*   **支持分布式事务。**

Kerstiens 说，展望未来，该公司将继续专注于使数据库成为开发人员不必担心的东西，并使采用和迁移更容易。

谷歌云是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>