# 合并 SQL 命令以加速 Postgres 的采用

> 原文：<https://thenewstack.io/merge-sql-command-to-accelerate-postgres-adoption/>

PostgreSQL 15 中最新推出的功能可能会加速 Postgres 在企业市场上超越传统系统。

Postgres 已经扰乱了市场。根据最近的 Stack Overflow 开发者调查，它仍然是世界上最受欢迎、使用最多和最受欢迎的数据库之一。唯一的问题是 Postgres 多快能在企业中占据多数份额。答案可能会比预期来得更快。有了这些最新功能，传统系统统治企业的日子可能屈指可数了。

[PostgreSQL 15](https://www.enterprisedb.com/blog/postgres-15-coming) 中的特性包括改进的数据库安全性、增强的备份和恢复选项以及高级逻辑复制功能。新特性中还引入了`MERGE SQL`命令，这使得开发者从他们的遗留数据库应用[迁移到开源 Postgres 变得更加容易。私营和公共部门组织都将从这些进步中受益匪浅，尤其是当它们加速其](https://thenewstack.io/postgresql-15-merge-ahead/)[数字化转型战略](https://www.gartner.com/en/publications/transitioning-digital-government-2022)时。

`MERGE`是一个流行的 SQL 标准命令，可以在一条语句中处理`INSERT`、`UPDATE`和`DELETEs`，完全不需要重写`MERGE`语句。`MERGE`避免了多个 PL/SQL 语句，简化了数据库开发人员和管理员的 SQL 脚本。Postgres 实现符合 SQL 标准，有助于 Microsoft SQL Server 和 Oracle 数据库的开发人员过渡到 Postgres。这意味着开发人员必须编写更少的代码，并且产品代码可以更容易维护。

## 合并的历史:为消除障碍而建立

过去，由于缺少 MERGE 语句，开发人员不得不创建自定义的变通办法，而且这些变通办法并不总是在同一级别上执行。在应用程序经常使用`MERGE`命令的情况下，从时间和资源的角度来看，迁移的成本都非常高。在一些开发者和企业主看来，Postgres 采用的这些障碍往往会超过好处。

例如，我们在 EDB 的开发人员会花将近两天的时间为给定应用程序中的给定 MERGE 语句迁移代码。我们经常在一个应用程序中看到 14 条 MERGE 语句；然而，有许多应用程序有数百条 MERGE 语句。将两天的代码迁移乘以数百条语句…你就明白了。

像许多伟大的创新一样，这项备受期待的功能历经数年才得以实现。3 月 29 日，PostgreSQL 的长期主要开发者和 EnterpriseDB (EDB) [的战略专家Á·阿尔瓦罗·埃雷拉](https://postgresql.life/post/alvaro_herrera/)提交了一个名为“[添加对合并 SQL 命令](https://git.postgresql.org/gitweb/?p=postgresql.git;a=commitdiff;h=7103ebb7aae8ab8076b7e85f335ceb8fe799097c)的支持的 PostgreSQL 15 补丁补丁上的其他作者包括 Postgres 的长期主要贡献者 Pavan Deolasee、Amit Langote 和 Simon Riggs。当该补丁作为 Postgres 11 开发周期的一部分于 2017 年首次提出时，该小组与社区成员合作，在几年的时间内测试了功能和实施。

## 合并让开发人员更聪明地工作，而不是更辛苦

幸运的是，经过多年的合作，MERGE 语句现在在 v15 中可用，这使得从 Oracle 和 SQL Server 迁移应用程序变得非常容易。通过消除这一进入壁垒，我们希望看到更多的企业离开遗留系统，将 Postgres 作为他们的数据库标准。

除了移植的好处之外，`MERGE`允许开发人员编写更少的代码，并拥有更多可读的代码。一些资深开发人员可能很熟悉这个类比，它就像在 Java 1.5 中引入了注释，或者在 C++中引入了模板。开发人员可以更快地编写应用程序，他们生成的代码也更容易被遵循他们的人理解和维护。

类似的好处也体现在其他新特性中，包括 Postgres 存储过程和 PostgreSQL 的表分区，这使得应用程序可以更轻松地迁移并保留它们的语义。

## 开发人员可以欣赏的 PostgreSQL 15 附加特性

除了`MERGE` SQL 命令之外，v15 中还有很多开发人员喜欢的特性。下面是我们最喜欢的几个。

*   **改进的数据库安全特性:** Postgres 15 允许授予以前需要超级用户权限的`SET`和`ALTER SYSTEM`命令基于角色的权限。此外，非超级用户首次可以成为逻辑复制所有者，并且有增强的保护措施来确保订阅所有者遵守行级安全策略。这些新功能支持企业采用零信任安全态势。
*   **增强的备份和恢复选项:** Postgres 15 增加了新的服务器端备份压缩，为快速高效地进行备份提供了新的选项。无论是加快从备份服务器到远程存储的网络传输，减少压缩备份所花费的时间，还是优化 Postgres 备份的存储空间，Postgres 15 都有更多选项来帮助企业客户。
*   **高级逻辑复制功能:** EDB 延续了与社区合作的传统，将许多在 EDB Postgres 中首次引入的高级逻辑复制功能引入到 Postgres 代码中。EDB 通过列和行过滤对选择性复制做出了重大贡献，允许高级逻辑复制用例并减少发布和订阅者节点之间的网络流量，并允许使用`ALTER SUBSCRIPTION…SKIP`跳过订阅者上的事务。

Postgres v15 将于本月晚些时候通过 EDB 大动物在云上提供。我们预测，在未来五年内，这些特性将推动 Postgres 成为企业中占主导地位的数据库。在 Gartner 认为约 800 亿美元的市场中，已经是增长最快的数据库管理系统，我们可以预计 Postgres 技术将继续以比竞争技术更大的可扩展性和更低的成本颠覆市场。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>