# Pivotal 开源 HAWQ 将在 Hadoop 中构建 SQL

> 原文：<https://thenewstack.io/hawq/>

为了与开源其大数据产品组合的计划保持一致，Pivotal 周二宣布将向 Apache 软件基金会(ASF)贡献其 HAWQ SQL-on-Hadoop 分析引擎和 MADlib 机器学习技术。

根据数据产品工程主管 Gavin Sherry 的说法，It [在 3 月份贡献了其分布式内存数据库 Gemfire](https://thenewstack.io/pivotal-makes-in-memory-database-gemfire-open-source/) 用于与 ASF 一起孵化一个名为 Geode 的项目，并计划在大约五周内开源其 GreenPlum 数据库，该项目计划自行管理。

虽然它只开放了 Gemfire 的核心，但它将发布 HAWQ 的每一行代码和它在 5 月份推出的查询优化器。

“从[星期二]开始，Pivotal HAWQ 将成为阿帕奇 HAWQ，”他说。“这是在 Hadoop 中构建 SQL 的第一步，而不是在 Hadoop 上构建 SQL。它将是 Hadoop 原生 SQL。”

他说，它将由 Apache 管理，深度集成到 Hadoop 生态系统中，并且“以比 Pivotal 更大的方式”完全开源。

他说,“基于 Hadoop”的解决方案和“基于 Hadoop”的解决方案的区别在于解决与以下方面相关的问题:

*   降低响应性或可伸缩性的连接技术。
*   专有技术。
*   运行时技术不基于 Hadoop 的核心模块，如 YARN。
*   与用户直觉相反的操作体验。
*   关于项目治理的问题或它在单个供应商范围之外的影响。

他说，这些将是阿帕奇·HAWQ 的作品。通过将它移交给 ASF，将有来自许多公司的贡献者，它将是开源的，并围绕 Hadoop 的基本构建块构建，包括 HDFS、YARN 和 Ambari。

## 合作项目

当 Pivotal 在 2 月份宣布计划开源其大数据产品组合时，它还推出了一项名为开放数据平台(ODP)的计划。这是与其他供应商一起围绕核心技术进行标准化的举措，包括 Apache Hadoop 2.6，其中包括 HDFS、YARN 和 MapReduce 以及用于大规模管理 Hadoop 环境的 Apache Ambari 软件。

这一努力有其批评者，包括 Cloudera 和 [MapR](https://www.mapr.com/blog/our-view-open-data-platform#.VgmnAM4cHL4) ，他们称这一努力是多余的，“有供应商偏见”

然而，在周一的另一项举措中，Linux 基金会宣布，它将作为一个合作项目来管理这项工作，现在称为 ODPi。成员数量翻了一番，现在包括 SAS Institute、Splunk、Squid Solutions、SyncSort、Telstra、Teradata 等公司，总共超过 25 家。它已经发布了一个初始的 ODPi 核心规范，并计划了一个认证项目。

其中两家公司 Hortonworks 和 Altiscale 将与 Pivotal 合作提供商业 HAWQ 产品，Altiscale 将提供 HAWQ 云服务。

独立的分析平台面临挑战，因为它们缺乏数据的关键上下文。AVOA 首席信息官战略顾问分析师蒂姆克劳福德(Tim Crawford)表示，他们的成功将是将技术与作为数据来源的应用程序结合起来，他补充说，他们面临的障碍相当高。

他认为开源大数据平台的主要原因是围绕该技术创建一个更大的社区。

“我们已经向阿帕奇软件基金会做出承诺，我们将继续为[HAWQ]做出贡献，并计划围绕这一点建立一个繁荣的社区，”雪莉说。他说，Pivotal 在 2014 年从大数据组合中获得了超过 1 亿美元的订阅收入，并将继续在 HAWQ 提供服务。

此外，Pivotal 正在贡献 [MADlib 机器学习库](http://madlib.net/)，这是一套由 Pivotal 和加州大学伯克利分校的研究人员开发的强大的横向扩展并行机器学习算法；斯坦福大学；佛罗里达大学和 Pivotal 的客户。

他说，通过 SQL 访问，它们可以通过可视化和其他更高级的工具进行集成，并由熟悉 SQL，但不熟悉实现这种算法所需的数字编程和统计细节，以及不熟悉分布式系统方法的分析师使用。

这些算法已经广泛应用于金融、汽车、媒体、电信和运输行业。MADlib 库支持 HAWQ、Pivotal Greenplum 和 PostgreSQL。

## 《皇冠上的宝石》

HAWQ 是 EMC 数据仓库和 Hadoop 部门多年努力的结果，他们利用了 Hadoop 分布式文件系统(HDFS)的可扩展性和复制优势，实际上是让它能说 SQL。

Greenplum 的联合创始人 Scott Yara [在发布会上称 HAWQ 为这项努力的“皇冠上的宝石”](http://www.theregister.co.uk/2013/02/25/emc_pivotal_hd_hadoop_hawq_database/)，雪莉仍然使用这个词。

有了 HAWQ，你可以编写任何 SQL 查询，并让它在 Hadoop 上工作，而不是试图用 NoSQL 数据存储取代 HDFS。到目前为止，它是在数百到数千个服务器节点上基于 Hadoop(而不是在 Hadoop 内部)构建的。

HAWQ 和其他 Greenplum 资产在 2013 年剥离后成为 Pivotal 的一部分。

今年 5 月，该公司宣布对其大数据套件进行[升级，据称 Pivotal 查询优化器为 Greenplum Database 和 HAWQ 带来了高达 100 倍的性能提升。Sherry 说优化器代表了五年的工作，旨在有效地确定在集群中的许多机器和处理器上处理查询的成本。](https://thenewstack.io/pivotal-updates-hadoop-distribution-boosts-performance-of-big-data-suite/)

与此同时，它让 [HAWQ 可以在 Hortonworks 数据平台](http://www.dbta.com/Editorial/News-Flashes/Pivotal-HAWQ-Now-Certified-on-Hortonworks-Data-Platform-103547.aspx) (HDP)上使用，这是它在 Pivotal 生态系统之外的第一次冒险。

Pivotal 是新堆栈的赞助商。

特征图片:[大卫·奥夫](https://www.flickr.com/photos/67162482@N07/)的《[鹰柄](https://www.flickr.com/photos/67162482@N07/6122510599/in/photolist-ak2t6z-ctnQHN-rDJDhh-fL243t-hiZstT-j3EYL6-gdY5HD-o7sJ1p-w4p6eh-eb2e3R-j4ZEzd-dj2jNi-6r9t9Z-aeweRr-rWcXrY-oFGUVz-ataCCr-cz8mV5-dJ1azT-dPyK8s-6s2uQD-LMoM9-gW5A8w-9CEC6R-6jbEFv-c9CDNs-xF5hMW-c9CDFb-qq1HfG-rDv6nG-qxYUce-e81uDd-5WmoiW-g2CYaG-dL1a2C-fFDHS2-dKUF3x-5ngz2c-6TmTGS-n8wCop-oHqMzL-egJsaq-2GHYBV-neWDHU-wZzsoW-6wWP4C-dJ6HRA-5wJbuw-i5u2dG-28Xk3c)由 2.0 在 [CC 下授权。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>