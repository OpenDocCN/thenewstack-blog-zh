# PostgreSQL 15:向前合并

> 原文：<https://thenewstack.io/postgresql-15-merge-ahead/>

随着上周第 15 版的发布，Postgres 关系数据库系统使得 Oracle 和 Microsoft SQL Server 的企业用户更容易迁移到这种开源替代方案，这要归功于它采用了 MERGE SQL 关键字。这个版本还改进了排序、压缩和逻辑复制。

我们与[的 Umair Shahid](https://www.linkedin.com/in/shahidumair/?originalSubdomain=pk) 坐在一起，他是 [Percona](https://www.percona.com/) 的 PostgreSQL 负责人，听听该公司认为这个最新版本的开源数据库系统的最佳新特性。

Percona 对 Postgres 非常感兴趣，并在此基础上构建了自己的企业支持发行版(完全开源的 btw ),以适应高性能工作负载。

Postgres 是最后一个通用的、开源的基于 SQL 的数据库系统，与 MySQL 并列，因此正被广泛地用于各种用途。它在金融技术社区中特别受欢迎，用于事务处理，以及为用户寻找 Oracle 的替代产品。DB-Rankings [将](https://db-engines.com/en/ranking)列为第四大最广泛使用的数据库系统，它的受欢迎程度在过去一年中惊人地增长了 35%。

沙希德说，v15 的许多改进对普通用户来说很大程度上是不可见的。例如，排序功能已经得到了相当多的关注。压缩现在由 [LZ4](https://github.com/lz4/lz4) 处理，这是一种快速获得青睐的无损压缩技术。以前数据库软件用的是 Gzip。Lz4 具有更高的压缩比——导致文件更小——并且压缩和解压缩文件的速度比 GZip 快 25%到 400%。

Shahid 说:“当我们谈论兆兆字节大小的数据文件时，你可以获得的每一个性能提升都是一个巨大的胜利。”例如，数据库备份应该尽可能快地完成。审计日志也需要压缩。

## **支持迁移的合并**

龙的一个[标准 SQL](https://blog.ansi.org/2018/10/sql-standard-iso-iec-9075-2016-ansi-x3-135/#gref) 命令，[合并](https://www.postgresql.org/docs/15/sql-merge.html)终于在 Postgres 中有了归宿。一旦理解了，合并可以为开发人员节省大量时间。它可以有条件地插入、更新和删除行。否则，开发人员的工作就是写出 if…then 循环的 CASE 语句。它在运行时也需要更少的处理。

该补丁的大部分工作是由 [EnterpriseDB](https://www.enterprisedb.com/?utm_content=inline-mention) (EDB)开发者[Á·阿尔瓦罗·埃雷拉](https://postgresql.life/post/alvaro_herrera/)贡献的，这是一个名为“[添加对合并 SQL 命令](https://git.postgresql.org/gitweb/?p=postgresql.git;a=commitdiff;h=7103ebb7aae8ab8076b7e85f335ceb8fe799097c)的支持的 PostgreSQL15 补丁 Pavan Deolasee，Amit Langote 和 Simon Riggs 也为该补丁做出了贡献，该补丁于 2017 年作为 Postgres 11 开发周期的一部分首次提出。

事实证明，这是许多潜在用户期待已久的功能。Oracle 和 Microsoft SQL Server 早就支持合并，所以那些希望从它们迁移到 Postgres 的数据库系统的用户现在有了完全的支持。

## 无限的逻辑复制

Shahid 指出,[逻辑复制](https://www.postgresql.org/docs/current/logical-replication.html)的许多改进为一些非常有趣的用例指明了方向。

逻辑复制在发布-订阅模型中复制数据对象。这里的新功能包括行和列过滤。

“当你从一个数据库移动到另一个数据库时，逻辑从一个数据库复制到其他行，你可以过滤表的列，并有选择地移动数据，”Shahid 说。

过滤提供了许多可能性。它可以用于安全目的，其中选择性数据可以对查看者保密。它可以用于多租户，即多个客户端可以使用一个数据库。

该特性可以实现多主控 Postgres 部署，这在以前是不可能的。地理上分离的集群可以处理冲突解决。

多主冲突解决 Postgres 目前可以完成，通常通过领域专业知识和许多工具。它仍然有局限性。真正的多主控冲突解决 Postgres 本质上意味着数据库软件可以伸缩。

在这个新版本中，Postgres 现在可以登录 JSON，从而更容易被可观察性工具使用。沙希德说，这些服务器统计数据现在保存在内存中，便于工具访问，如 [Percona 监控和管理](https://www.percona.com/blog/2019/08/30/pmm-for-postgresql-quick-start-guide/) (PMM)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>