# CockroachDB 无服务器发布，渴望成为开发者的数据库

> 原文：<https://thenewstack.io/cockroachdb-serverless-launches-aspires-to-be-developers-database/>

世界上有两种技术专家:一种将数据库视为终结的手段，另一种将数据库本身视为终结。在很长一段时间里，后一组人主导了数据库对话，这些对话深入关注性能调优、优化和架构策略，如分片、向量处理、列存储和数据一致性模型。

但是前一个群体——主要由只希望数据库能够实现其应用程序的愿景，然后退出的开发人员组成——实际上在数据库平台决策中具有巨大的影响力。蟑螂实验室推出了[cockoroach db](https://www.cockroachlabs.com/product/)无服务器，旨在为那些开发者提供低摩擦的数据库服务。

## 通往开发者内心的路

开发人员不想盲目崇拜数据库平台的特质，也不想去关心和喂养它。他们只是希望数据库易于建立，易于使用，运行成本低廉，并且快速可靠，甚至不需要考虑这些。实际上，开发人员希望数据库消失，只留下一个 API(应用程序编程接口)来存储、获取、查询和分析他们的数据。希望这个 API 和他们已经知道的非常相似。

这是蟑螂实验室正在用 CockroachDB Serverless 实现的叙事，该公司正在以测试版形式发布该产品。这项服务毫不掩饰地面向低摩擦的开发人员，提供一个与流行的 [PostgreSQL](https://www.postgresql.org/) 数据库平台兼容的 SQL 和有线协议数据层。

在蟑螂实验室的首席产品宣传员[吉姆·沃克](https://www.linkedin.com/in/jwwalker/)的简报会上，大部分内容都被解释给了新的堆栈。沃克总结道，CockroachDB Serverless 试图成为“每个开发人员的首选数据库”，并解释说，新产品是“一个完全弹性的关系型云数据库，由熟悉的 SQL API 支持，使开发人员能够立即开始构建，而无需规划容量、性能或可用性。”

## 不可见 b？

CockroachDB 无服务器自动扩展，不使用离散的集群或节点。因此，它不需要调整大小、分片或调整。相反，类似于云数据库平台，如[亚马逊 Aurora](https://aws.amazon.com/rds/aurora/) 和[谷歌 BigQuery](https://cloud.google.com/bigquery) ，CockroachDB Serverless 不需要供应或显式启动。相反，它提供了一个“你的愿望就是我的命令”风格的界面。

该服务每月免费提供高达 5GB 的存储空间和 2500 万个“请求单位”(RUs——由计算、网络和 IOPS 组成的使用抽象)，甚至不需要信用卡就可以启动和运行。显然，对于使用量超过这些入门级阈值的项目，将需要一种支付方法，但即使在这种情况下，计费也是以纯粹基于消费的模式为前提的。这也意味着开发人员在学习或试验该平台时将花费很少的费用。在生产中运行货币化应用程序的成本表面上将与收入成正比。

## 云给予；传统方法带走了

虽然大多数企业和个人用户现在依赖云作为他们全新开发的主要平台，但这一举措并没有解决数据库面临的许多基本运营挑战。例如，传统的数据库扩展方法不利于实现云的弹性优势。同样，相对于内部场景，在云中实施传统的主动/被动高可用性不会降低复杂性。同时，云增加了本地安装不会面临的事务延迟挑战。很明显，如果我们不能认识到云的优势，并且我们也遭受了它带来的新挑战，那么就需要重新启动。

本质上，CockroachDB Serverless 扩展了其前身[蟑螂企业](https://www.cockroachlabs.com/get-cockroachdb/enterprise/)和[蟑螂云](https://www.cockroachlabs.com/product/cockroachcloud/)带来的功能，提供了自动化弹性伸缩、自动化弹性、基于消费的计费、短暂集群、即时启动、多租户等特性。

如前所述，这个 CockroachDB 无服务器版本是一个测试版本。因此，它有一些限制，其中之一是它只能在单个地区使用。然而，该公司表示，它将在明年年初为多地区消费做好准备。Walker 告诉我们，其他特性，如自动地理分区和 REST 接口，也将很快推出。

## 比较者和竞争者

鉴于蟑螂首席执行官[斯潘塞·金博尔](https://www.linkedin.com/in/spencerwkimball/)在谷歌的任期以及他对分布式[谷歌文件系统](https://static.googleusercontent.com/media/research.google.com/en//archive/gfs-sosp2003.pdf)的“[巨人](https://cloud.google.com/blog/products/storage-data-transfer/a-peek-behind-colossus-googles-file-system)”迭代的贡献，CockroachDB 经常被比作[谷歌扳手](https://cloud.google.com/spanner)。但是，在 CockroachDB 无服务器的情况下，将其与横向扩展 PostgreSQL 云产品进行比较可能更有用，如前面提到的 Amazon Aurora 或[Azure Database for PostgreSQL–Hyperscale](https://docs.microsoft.com/azure/postgresql/hyperscale/)。然而，与那些云提供商的“自有品牌”产品不同，CockroachDB Serverless 运行在所有三个主要的云平台上，不需要在其中任何一个平台上拥有帐户。这种多功能性可能确实对开发人员很有吸引力。

不过，蟑螂需要这种吸引力，因为它正在与三大商业关系数据库平台([微软 SQL Server](https://www.microsoft.com/sql-server/sql-server-2019) 、[甲骨文数据库](https://www.oracle.com/database/)和 [IBM DB2](https://www.ibm.com/products/db2-database) )及其开源对手(PostgreSQL、 [MySQL](https://www.mysql.com/) 和 [MariaDB](https://mariadb.org/) )竞争。随着该公司获得企业客户的青睐，它也必须讨好基层开发人员。如果可以的话，那么对手的任期可能会变成不那么强大的资产，而他们的长期遗产可能会变成越来越大的负债。

*披露:帖子作者 Andrew Brust 和 Farheen Raparthi 就职于 [Blue Badge Insights](https://www.bluebadgeinsights.com/) ，*一家研究、战略和咨询公司，为数据和分析软件公司、解决方案提供商和客户提供服务。**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>