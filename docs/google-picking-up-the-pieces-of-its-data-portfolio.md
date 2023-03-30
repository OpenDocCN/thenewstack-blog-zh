# 谷歌收拾其数据组合的碎片

> 原文：<https://thenewstack.io/google-picking-up-the-pieces-of-its-data-portfolio/>

云的一个关键优势是它可以帮助企业简化 it 运营，特别是 SaaS(软件即服务)产品，可以消除跑腿工作以及配置和内务管理的麻烦。但是，SaaS 服务在数据、分析和人工智能领域的扩散会不会是一件好事呢？

已经有很多[呼吁](https://www.zdnet.com/article/data-2022-outlook-part-i-will-data-clouds-get-easier-and-streaming-get-off-its-own-island/)云提供商开始理清混乱的局面，让他们的云更容易使用:从客户肩上卸下整合所有服务的负担。[谷歌云](https://cloud.google.com)，在本周的[数据峰会](https://cloudonair.withgoogle.com/events/summit-data-cloud-2022)上，宣布了一些新的结缔组织，应该可以解决一些问题。

## 头条:大湖

标题是谷歌宣布预览大湖，谷歌称之为“存储引擎”。它实际上是一个 API。它概括了 Google 最初为 BigQuery 开发的 API，以在 Google Cloud (object)存储中存储的数据上投影一个表结构。这反过来允许分析和查询工具访问数据，并提供数据的粒度视图，在此基础上可以实施治理和访问控制。

一方面，BigLake 是 Google 对数据湖库的回答，这是一种迅速出现的方法，可以消除数据湖和数据仓库之间的区别。

BigLake 支持所有流行的数据湖格式，包括 JSON、CSV 和 Parquet 这些格式已经成为可变结构数据的 SQL 的事实上的标准替代。API 使这些格式的数据看起来像 BigQuery 读取的关系表和聚集表。此外，与谷歌之前通过 [BigQuery Omni](https://cloud.google.com/blog/products/data-analytics/introducing-bigquery-omni) 将 BigQuery 扩展到外国领域一致，这意味着存储在任何亚马逊 S3 兼容对象存储中的数据都将注册为可读数据源。

谷歌并不是第一个到达那里的公司。[亚马逊红移](https://aws.amazon.com/redshift/)、[微软 Azure Synapse Analytics](https://azure.microsoft.com/en-us/services/synapse-analytics/) 和其他公司处理存储在对象存储中的多语言数据，而 Databricks(它开创了 lakehouse 概念)一直在[稳步提升其游戏](https://www.zdnet.com/article/databricks-tpc-ds-benchmark-results-and-the-analytics-platform-wars/)以获得其 Spark 数据湖的更多数据仓库般的性能。但 BigLake 的关键不仅仅是它从云存储中提供了类似数据仓库的体验，正如 BigQuery 已经在做的那样，而是扩展了这一结构，以便客户可以与其他谷歌和开源引擎保持一致的访问，如 [Spark](https://spark.apache.org/) 、 [Presto](https://prestodb.io/) 和 [Trino](https://trino.io/) ，并有望在长期内获得第三方 BI、AI 和分析服务。

实际上，BigLake 使所有数据看起来就像在 BigQuery 中一样，但不要求您是 BigQuery 用户。它将支持开源数据湖构造，包括[三角洲湖](https://delta.io/)和[冰山](https://iceberg.apache.org/)，路线图上还有[胡迪](https://hudi.apache.org/)。Vertex AI、Dataproc 和无服务器 Spark 等谷歌服务都将能够访问这些数据。

BigLake 建立在去年秋天发布的 Dataplex 的基础上，这是谷歌的数据结构项目。虽然 BigLake 提供了在表中公开数据的 API，但是 Dataplex 用于从数据湖中将数据逻辑地分类到层次区域中，数据湖定义了数据池；数据区，在逻辑上将相关的数据资产组合在一起(可以理解为工作区的一种形式)；在最细的层次上，数据资产(特定的数据实体)。通过对数据进行逻辑组织，可以更容易地对其进行标记和管理。作为定义数据的一部分，它收集元数据，这些元数据有助于对数据进行分类，并使数据可被数据目录发现。

## 连接运营和分析数据

连接难题的另一部分是融合运营数据和分析。在本周的声明中，谷歌推出了[扳手变化流](https://cloud.google.com/blog/products/databases/track-and-integrate-change-data-with-spanner-change-streams)的预览版。这是集成 Spanner 和 BigQuery 的第二个难题，因为去年，Google 为 BigQuery 引入了在 Spanner 中进行联邦查询的能力。去年的公告侧重于静态数据，这增加了实时更新 BigQuery 的能力，使其成为客户必须构建自己的代码的更强大的替代方案。

当然，变更数据捕获流并不新鲜。但是在大多数情况下，客户必须编写他们自己的集成，比如说，将一个 DynamoDB 流导出到一个关系表端点。或者，客户必须使用混合工作负载数据库，这种数据库有条件地将传入的行复制到并行的内存列存储中。对于像谷歌这样提供专业数据库的云提供商来说，内置的变化数据捕获流功能对于连接运营和分析系统至关重要。对于谷歌的下一步行动，我们希望看到类似的与流媒体的集成，消除云数据流客户[编写自己的桥梁](https://hevodata.com/learn/dataflow-to-bigquery-2-easy-steps/)的需要。

## 收拾残局

向平均白色带致敬，我们很高兴看到谷歌从其数据和分析组合中捡起碎片，并开始将它们编织在一起。在这种情况下，它扩展了对数据进行精细查看、查询和管理权限的能力，否则这些数据将被埋在云对象存储中，这是一种专为经济存储而设计的技术，但不是访问或管理的更精细方面。谷歌没有重新发明轮子，而是利用了它已经为 BigQuery 开发的功能。

在数据平面之外，Google 发布了相关公告，耦合了[数据工作室](https://datastudio.google.com/)、 [Looker](https://www.looker.com/) 和 [Connected Sheets](https://cloud.google.com/blog/products/g-suite/connected-sheets-is-generally-available) 。这不是添加新功能的例子，因为用户已经可以在 Looker 中开发数据可视化；在 Data Studio 中从连接的工作表生成可视化效果；或者[将连接的板材数据导入 Looker](https://help.looker.com/hc/en-us/articles/360023860613-How-to-use-Google-Spreadsheets-to-Input-Data-into-Looker) 。但是它添加了缺失的链接，这样 Data Studio 用户可以从 Looker ML 数据模型中生成可视化效果，Looker 用户可以从连接的表中探索数据。去年秋天，谷歌宣布无需用户注册 Dataproc 就可以访问无服务器 Spark。

当然，下一步是扩大所有这些功能的覆盖范围，首先是在谷歌云产品组合中，但最终也会扩展到第三方生态系统。今天，BigLake 只支持少数几种数据文件格式，但它们显然是早期的目标，Google 还没有完成。同样，Dataplex 旨在使数据可被发现并促进一致的治理，它支持 Google 的部分数据和分析服务，包括 BigQuery、Dataproc 和 Data Catalog 这使得 Firestore 和 Dataflow 等其他谷歌数据平台和服务成为合乎逻辑的下一个目标。

除此之外，还需要与第三方建立临界质量；显而易见的目标是那些属于谷歌[开源数据合作伙伴](https://venturebeat.com/2019/04/09/google-cloud-announces-7-open-source-partners-seoul-and-salt-lake-city-regions/)的数据库。除了开放数据库之外，还有谷歌已经涉足其中的第三方，如 [Collibra](https://www.collibra.com/) (谷歌风投持有其股份)或 Trifacta(谷歌将其 OEM 为[云数据准备](https://cloud.google.com/dataprep))。更不用说第三方 BI 工具的广阔前景了。

正如安德鲁·布鲁斯·T2 指出的那样，这就是他所说的分析堆栈冗余。“在商业智能方面，将本地技术和收购的技术结合在一起很容易让人想起微软、IBM、SAP 和甲骨文在 21 世纪初的做法。”云改变了许多事情，但有一件事它没有改变，那就是需要有一套可以结合在一起的解决方案。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>