# Airbyte:轻松构建数据连接器

> 原文：<https://thenewstack.io/airbyte-building-data-connectors-made-easy/>

即使公司正在扩大试图从数据中获取洞察力的角色，一个特殊的痛点仍然存在:将数据放在一个地方，并以一种可以使用的格式保存。

这是根据 [Airbyte](https://airbyte.io/) 的联合创始人所说，这是一个开源数据集成平台，旨在标准化和简化数据源之间连接器的构建。

一项[马蒂兰和 IDG 研究调查](https://pages.matillion.com/ebook_optimizing-business-analytics.html)发现每个组织的平均数据源数量是 400 个。超过 20%的受访公司从 1，000 个或更多的数据源中提取数据。超过 90%的受访者表示，以可用于分析的格式提供数据在某种程度上具有挑战性。

Airbyte 的联合创始人[米歇尔·特里科特](https://github.com/michel-tricot) **[](https://github.com/michel-tricot)**和[约翰·拉弗勒尔](https://github.com/johnlafleur)在他们之前的创业公司经历过这种痛苦。

Tricot 是 LiveRamp 的工程总监和集成主管，处理大量市场技术数据。

“这是我真正接触到建立大量数据管道意味着什么的地方。我们管理着成千上万个不同的数据集成，因此将数据从我们的客户那里提取到他们的基础设施中，并将其发送给所有不同的[广告和营销技术 APIs。我们每天都在移动数百万亿字节的数据，”他说。

然后他去了 rideOS，一家在地图和交通数据方面做类似工作的公司。

在他的第一次创业中，Lafleur 在工程工具的基础上建立了一个工程管理平台。

“不再需要使用六种工具来获取数据，您可以在一个工具中获得所有信息。所以我们必须建立所有这些 ETL(提取、转换、加载)管道。那是一场噩梦。我仍然有那次的伤疤，”他说。

尽管数据集成领域非常拥挤，但他们认为一定有更好的方法。因此，他们着手创建一个，去年刚刚成立了这家总部位于旧金山的公司。

去年夏天，他们与 five tran T1、T2 Stitch Data T3 和 T4 Matillion T5 的 45 名客户进行了交谈，他们表示，尽管使用了这些技术，他们仍然在内部制造连接器。这让两人相信[开源](https://medium.com/sapphire-ventures-perspectives/what-is-the-open-data-ecosystem-and-why-its-here-to-stay-60c06f19011b)是正确的选择。

## 连接器集线器

Airbyte 希望众包连接器的长尾，因为他们坚持认为这不仅仅是建立连接器的问题，而是维护它们的问题。一个公司的投资回报通常没有意义去维护一些模糊的连接器，而可能有五个公司需要它。该公司希望创建一个最新连接器的资料库，这些连接器可以免费获得，以便公司复制他们自己的工作。它的目标是在年底前提供 200 个连接器。

使用 REST APIs，用户可以从数据库、脸书广告、Salesforce、Stripe 等来源提取数据，并将其移动到 Redshift、Snowflake 和 BigQuery 等目的地。

[技术](https://docs.airbyte.io/understanding-airbyte/high-level-view)是基于 Docker 的，允许开发者用任何语言编写连接器。它提供了模板，使那些喜欢使用 Python 或 Java 的人更容易做到这一点。使用容器可以更容易地应用更新。

它的图形界面使不太懂技术的用户能够配置操作，如从 API 创建源、目的地和连接。它使用默认的 Postgres 数据库作为 Docker 服务的一部分；一个[临时](https://temporal.io/)服务为调度器管理任务队列和工作流。它支持 Kubernetes、Airflow 和 [dbt](https://blog.getdbt.com/what-exactly-is-dbt/) ，这是一种使用 SQL 执行数据转换作业的方法。

[https://www.youtube.com/embed/sKDviQrOAbU?feature=oembed](https://www.youtube.com/embed/sKDviQrOAbU?feature=oembed)

视频

“所有这些[连接器](https://docs.airbyte.io/integrations)，它们作为 Docker 映像运行，因此它们可以在任何系统上运行，如 Kubernetes 或 Fargate 或任何支持运行容器的系统。这使您可以实际运行它，而不必考虑它在什么环境中。或者我需要什么来使连接器工作？因此，这实际上是优化它，使它非常容易使用，”特里科特说。

该公司最近发布了它所谓的 [CDK](https://airbyte.io/connector-development-kit) ，这是一个连接器开发套件，使构建一个连接器成为两个小时的工作。它声称从这个过程中去掉了 75%的代码，只剩下对特定于连接器的代码的需求。它提供了编写源连接器的 Python 框架；写入 HTTP 的通用实现，包括写入 REST APIs、GraphQL、Singer Taps 和其他通用 Python 源代码的特定助手；测试套件和代码生成器。

## EL 和 T 去耦

该公司希望成为将数据从应用程序、API 和数据库同步到仓库、数据湖和其他目的地的开源标准。5 月，它宣布了 2600 万美元的 A 轮融资，就在几个月前，它宣布了 520 万美元的种子轮融资，使今年的融资总额超过 3100 万美元。

Tricot 和 Lafleur 看到了仓库和数据湖之间的融合，但认为即使是从传统 ETL 向 ELT 转移的[,基于云的存储使用户不必在加载前预先知道他们想对数据做什么，也有其缺点。他们坚持认为，转换必须与提取和加载功能分离，因为基于数量的定价会妨碍充分利用公司的数据，因为成本问题会成为障碍。](https://airbyte.io/blog/why-the-future-of-etl-is-not-elt-but-el)

Lafleur 说:“数据集成的方式是封闭的，从某种意义上说，它并没有真正解决集成问题。“这些公司仍然需要建设和维护，此外，基于数量的定价成本很高。这意味着你不能复制数据库。一旦你有了数百万行，你就不能真正使用它们，因为它变得太昂贵了。这就是开源方法可以接管的地方。”

GitLab 似乎同意这一点，它刚刚发布了开源平台 Meltano。

到目前为止，Airbyte 专注于开源社区版，建立一个保持最新的连接器中心，这是联合创始人指责竞争项目 [Singer](https://www.singer.io/) 未能做到的。

最终，？他们说，该公司将奉行开放的核心战略，提供一个企业版，包括数据质量协议、合规性功能、角色和访问管理以及单点登录。他们说，托管版本是他们最需要的功能，但那是将来的事了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>