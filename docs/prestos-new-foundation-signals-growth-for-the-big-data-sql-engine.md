# Presto 的新基础标志着大数据 SQL 引擎的发展

> 原文：<https://thenewstack.io/prestos-new-foundation-signals-growth-for-the-big-data-sql-engine/>

很快，开源的 SQL 查询引擎有了基础，它宣称能够在任何地方利用数据。

支持 Presto 的 [Starburst Data](https://www.starburstdata.com/) 的联合创始人兼首席执行官[贾斯汀·博格曼](https://www.linkedin.com/in/justinborgman/)表示，这是努力的一部分，以显示该项目已经真正发展成为一个超越单一企业利益的国际社区，并将在未来继续存在。

“从一开始，我们就强调代码质量、架构可扩展性和与社区开放合作的重要性，”马丁·特拉弗索说，他与[戴恩·松德斯特罗姆](https://github.com/dain)和[大卫·菲利普斯](https://github.com/electrum)一起在脸书创建了 Presto。

“随着 Presto 用户群和 Presto 开发者社区在过去几年中的快速扩张，建立一个非营利组织来将这些价值观制度化是确保该项目经得起时间考验的下一个合理步骤。”

这三位创作者以及来自 Starburst data 的团队将成为创始成员。除了博格曼，Starburst 的创始人——[卡米尔·巴杰达-帕夫利科夫斯基](https://github.com/kbajda)、[马特·富勒](https://github.com/mattsfuller)和[沃伊切赫·比拉](https://github.com/ilfrin)——都来自 Teradata，该公司在 2014 年收购了他们的 SQL-on-Hadoop 公司 [Hadapt](https://www.bloomberg.com/research/stocks/private/snapshot.asp) 。他们在 2017 年成立了总部位于波士顿的 Starburst Data。

## 速度、并发性

基于 Java 的 [Presto](https://prestosql.io/) 被创建为一个更快的 [Hive](https://hive.apache.org/) ，用于针对 Hadoop 提取 SQL 查询。然而，Presto 也可以跨 Hive 和 MySQL 进行查询，脸书也是其中的大规模用户。

自从 2013 年开源以来，它现在可以[跨数据源](https://docs.starburstdata.com/latest/connector.html)查询本地和云存储库，包括 HDFS、亚马逊 S3、Kafka、Cassandra、Postgres、Oracle 和 Redis。

Presto 可以运行完整的 ANSI SQL，是为高性能、高并发和低延迟而设计的。 [Airbnb](https://medium.com/airbnb-engineering/airpal-a-web-based-query-execution-tool-for-data-analysis-33c43265ed1f) 、[网飞](https://medium.com/netflix-techblog/using-presto-in-our-big-data-platform-on-aws-938035909fd4)、Treasure Data 和[优步](https://eng.uber.com/presto/)都是早期采用者和贡献者，也是运行数百个节点处理数 Pb 数据的公司之一。

部分性能提升来自于不使用 MapReduce，MapReduce 将结果写回磁盘。相反，Treasure Data 警告说，Presto 动态编译部分查询，并在内存中进行处理，这带来了有限的容错能力。

https://www.youtube.com/watch?v = 2J7Amu1UtsU & t = 145s

Presto 将计算和存储分开。

“Presto 认为数据库或其他存储数据的地方只是简单的存储，而不是自己的数据库，”Borgman 说。

Starburst 的一个客户，一家媒体公司，在 Hadoop 中存储观看数据，在 Teradata 中存储计费数据。Borgman 说，Presto 认为这些只是存储数据的两个地方，作为这些不同数据源之上的一个抽象层，允许用户查询这些数据源并跨它们连接。

“可能是 Hadoop，像 Oracle 或 Teradata 这样的传统数据库，或者转移到 S3 的云和查询数据，”他说。

“我认为随着时间的推移，S3 将成为新的数据湖。一直是 Hadoop，但现在 S3 或类似的东西——微软的 Blob 存储，谷歌的谷歌云存储——这些正在成为让你的数据存活的低成本地方。如果您可以在那里查询数据，而不必将其加载到其他平台，这将为您节省时间和金钱。我认为这是普雷斯托腾飞的一大动力。”

Presto 可以与任何风格的 Hadoop 一起工作，也可以不使用它。Kubernetes 可以通过 Presto 和其他数据技术进一步简化事情， [Iguazio 首席技术官 Yaron Haviv](https://thenewstack.io/will-kubernetes-sink-the-hadoop-ship/) 最近为新堆栈写道。

像其他关系数据库系统一样，它可以被虚拟化为一个与多个工作节点同步工作的协调器节点。它的元数据 API、数据位置 API 和数据流 API 使它能够跨多个存储源进行连接。

通过这些 API，它向数据源请求表或列的列表、数据类型和数据的位置，以便将数据分配给并行执行工作的工人。

可以在其上添加可视化和其他 SQL 工具。

它的内置功能包括支持正则表达式函数、lambda 表达式和函数以及地理空间函数。它可以处理复杂的数据类型，包括 JSON、数组、map 和 row/struct。

Borgman 说，Starburst 目前的大部分工作是帮助客户在本地和云数据的混合环境中使用 Presto。

他指出 [Snowflake](https://www.snowflake.com/) 是其在云数据方面最接近的竞争对手，但用户必须以自己专有的格式将数据载入其中。他说，Presto 直接以开源格式查询数据。

AWS 还在其平台上提供 Presto 项目，作为其 [EMR](https://aws.amazon.com/emr/) (弹性地图缩减)产品的一部分。

Presto 的最新发展包括一个基于成本的优化器，它使用 CPU 成本、内存需求和网络带宽使用等属性来确定如何以最少的资源尽可能快地执行查询，以及基于角色的访问控制和安全增强。它现在可以在 Azure 和 AWS 上使用。

专题图片:[加雷斯·威廉姆斯](https://www.flickr.com/photos/gareth1953/)的《[国王十字车站翻新——2014 年 1 月——等火车](https://www.flickr.com/photos/gareth1953/12844001634/in/photolist-kyYSd3-dZRqf7-jaQiE9-6W6H4n-aa1RSX-3mMqDu-3DdJVu-qjUAbk-Vgo5BN-6RdQaK-4qoeBT-6pYcwb-21DQAhs-9znLoD-23sbfvC-amewui-gptmxB-4wbFf1-gAwHG8-7KbKHr-fKTVFN-V3reyU-28X1zYc-6y2adt-f8UoTj-Kz1vvj-ba3qdD-Fw2AE-27u3Q9X-aMSetv-qFXbqi-bXhhWK-oanhaD-3D9ndi-wGYYdk-n9G83-2cppN-27JrawS-2dGGjkE-kesUTN-c8uW7N-7kGsdk-Uys5RM-9xTgyY-3qiugZ-Y84eaH-9uzLn1-7vEzW1-GyfLCM-R1krB9)》。根据 CC BY-SA 2.0 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>