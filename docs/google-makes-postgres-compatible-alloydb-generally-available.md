# 谷歌使兼容 Postgres 的 AlloyDB 普遍可用

> 原文：<https://thenewstack.io/google-makes-postgres-compatible-alloydb-generally-available/>

谷歌今天宣布，alloy db T1——其兼容 T2 PostgreSQL T3 的数据库系统，早在 5 月份就推出了公共预览版——现已全面上市。集群云数据库平台将加入[云扳手](https://cloud.google.com/spanner)和[云 SQL](https://cloud.google.com/sql) 作为谷歌云上的第一方操作关系数据库服务。随着 GA 的发布，Google Cloud 重申了 AlloyDB 的两个配套服务的最新预览版，以及该平台的许多合作伙伴开发。

谷歌云表示，AlloyDB 提供了全面的 PostgreSQL 兼容性、横向扩展计算和存储、集成分析以及 AI/ML 驱动的管理。它还表示，AlloyDB 对于事务性工作负载的速度是标准 PostgreSQL 的四倍，对于这些工作负载的速度是“亚马逊可比的 PostgreSQL 兼容服务”的两倍后者表面上指的是兼容 PostgreSQL 模式的[亚马逊 Web 服务](https://aws.amazon.com/?utm_content=inline-mention)’[Aurora](https://aws.amazon.com/rds/aurora/)数据库服务。谷歌云正在为 AlloyDB 提供“四个九”(99.99%)的服务水平协议，并表示该服务“在 60 秒内检测到大多数数据库故障并从中恢复。”

## 其他公告

9 月份首次宣布的重申的配套服务预览包括 [PostgreSQL 到 AlloyDB 的迁移](https://cloud.google.com/blog/products/databases/database-migration-service-supports-migration-to-alloydb-for-postgresql)，通过利用谷歌云的无服务器[数据库迁移服务](https://cloud.google.com/database-migration)来适应基于 Postgres 的系统到 AlloyDB 的转换。这对 AlloyDB 来说至关重要，alloy db 显然旨在服务于提升并转移到云的 Postgres 工作负载(稍后将详细介绍)。

另一个预览服务， [AlloyDB 与数据流](https://cloud.google.com/blog/products/data-analytics/introducing-seamless-database-replication-to-bigquery)的集成，引入了变更数据捕获/复制服务，将 AlloyDB 中的数据与谷歌 [BigQuery](https://cloud.google.com/bigquery) 同步。谷歌还重申，自 5 月份 AlloyDB 预览版发布以来，它已经通过客户管理的加密密钥(CMEK)和 VPC 服务控制等关键安全功能增强了这项服务。谷歌表示，它还对 AlloyDB 的性能、可用性、复制延迟和监控进行了改进。

在合作伙伴方面，Google Cloud 宣布 [Confluent](https://www.confluent.io/partner/google-cloud/) 已经为其托管的 Kafka Connect 产品添加了一个用于 [AlloyDB](https://thenewstack.io/google-i-o-2022-urges-developers-to-focus-on-the-real-world/) 的专用流数据[接收连接器](https://docs.confluent.io/cloud/current/connectors/cc-alloydb-sink.html)，并且 [Collibra](https://www.collibra.com/us/en/partners/technology/google-cloud) 已经在其市场上发布了一个 [AlloyDB 驱动程序](https://marketplace.collibra.com/listings/jdbc-driver-for-alloydb/)。Google Cloud 的 Lighthouse 客户包括巴西美容科技初创公司 [B4A](https://b4a.com.br/) ，该公司表示，将 AlloyDB 与 GraphQL API 相结合，其产品目录查询时间减少了高达 90%，总部位于伦敦的[think Machine](https://www.thoughtmachine.net/)，该公司表示 AlloyDB 为其全球一级银行客户提供了最高水平的服务。[谷歌云](https://thenewstack.io/how-google-cloud-enabled-a-record-calculation-of-pi/)没有提供 B4A 以前的数据库架构和 think Machine 关于什么构成“最高级别”性能的标准的细节。

## 如此多的 Postgres 选项，如此少的时间

PostgreSQL 是一个非常流行的开源关系数据库平台，但它也已经成为许多专有系统的事实上的标准。谷歌自己的全球分布式数据库 Cloud Spanner 提供了 Postgres 兼容模式，谷歌云 SQL 托管多个关系系统，包括 PostgreSQL 本身。[cocroach db](https://www.cockroachlabs.com/product/)，一个独立的云原生地理分布式 RDBMS，也提供了 Postgres 兼容层。 [EDB](https://www.enterprisedb.com/) 提供 Postgres 的标准、企业、分布式和高级商业发行版，以及名为 [BigAnimal](https://www.enterprisedb.com/products/biganimal-cloud-postgresql) 的托管 Postgres 云服务，可在 AWS 和微软 Azure 上使用。

说到这些云提供商，微软的 Azure 数据库和 AWS 的关系数据库服务都提供类似于 Google Cloud SQL 的托管 Postgres 服务。AWS 的上述 Aurora 专有分布式数据库提供 Postgres 兼容性作为其两种操作模式之一。亚马逊的云数据仓库平台 [Redshift](https://aws.amazon.com/redshift/) 也是 Postgres 兼容的，其他一些数据仓库平台也是如此。微软最近发布的 [Cosmos DB for PostgreSQL](https://learn.microsoft.com/en-us/azure/cosmos-db/postgresql/introduction) 将该公司从 [Citus Data](https://www.citusdata.com/) 获得的基于 Postgres 的横向扩展数据库技术与其全球分布式 [Azure Cosmos DB](https://azure.microsoft.com/products/cosmos-db/) 数据库服务的后端存储基础设施相结合(在发布之前，该服务是一项纯粹的非关系型服务)。

## 在顾客所在的地方吸引顾客

为什么有这么多兼容 PostgreSQL 的选项？因为现在有许多客户在运行自我管理的基于 Postgres 的系统，并且希望将它们迁移到云、完全管理的服务，或者两者都有。有了所有 Postgres 兼容的代码，许多数据库供应商和所有的云提供商都希望提供他们的平台作为迁移目标，只需要最少的重新编码。

PostgreSQL 定义了一个生态系统，但是平台本身给客户留下了各种各样的遗留问题清单需求选项。这创造了大量合格的潜在客户，而有了 AlloyDB，Google Cloud 正全力追赶他们。它很可能会成功，但有了三个独立的关系操作数据库服务，所有这些服务都提供 Postgres 兼容选项，谷歌将不得不努力帮助其客户浏览何时使用什么的决策树。

## (不久)不免费的，如在啤酒中

AlloyDB 正式上市，立即生效。谷歌云表示，它将在本月底之前保持免费服务，预览价格将在下一个日历年的*期间(即直到 2023 年 12 月 31 日)保持有效，之后“将开始正常计费”价格细节在[在线](https://cloud.google.com/alloydb/pricing)提供，尽管还不清楚提供的价格数据是否适用于 2023 年，或 2024 年及以后。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>