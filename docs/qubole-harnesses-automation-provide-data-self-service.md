# Qubole 利用自动化来提供数据自助服务

> 原文：<https://thenewstack.io/qubole-harnesses-automation-provide-data-self-service/>

延迟的数据被拒绝。

这是在脸书建立自助服务数据平台的团队的口号。员工不得不通过数据团队获得他们需要的信息，这种挫折感已经被传递到 [Qubole](https://www.qubole.com/) ，这是一家总部位于加利福尼亚州圣克拉拉的初创公司，最近因其专注于自动化而在 ApacheCon 引起了轰动。

据该团队成员、现任 Qubole 首席执行官兼联合创始人 [Ashish Thusoo](https://twitter.com/ashishthusoo?lang=en) 称，脸书将数据作为其所做一切的核心。

然而，“如果获取数据太痛苦，他们就没有数据——他们想非常非常快地前进，”他说。“这对脸书来说是一个糟糕的架构，实际上，对任何公司来说都是糟糕的。…我们退一步说，“这种架构对于任何希望成为数据驱动型的组织来说都非常重要。””他说。

Thusoo 和[joy deep Sen Sarma](https://twitter.com/jsensarma?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)——他们也创造了现在的[Apache Hive](https://cwiki.apache.org/confluence/display/Hive/Home)——在 2011 年推出了 Quoble，并在 2013 年发布了他们的第一款产品。Qubole 旨在管理基础设施，让数据团队专注于分析和使用数据。

Thusoo 和 Sarma 提倡在操作和使用数据技术的人群中出现类似 DevOps 的趋势，他们还写了一本关于这一主题的书，由 O'Reilly Media 出版，名为《[用数据操作](http://go.qubole.com/LP---DataOps---Book-Offer.html)创建数据驱动的企业》。

在其核心，Qubole 提供托管 [Hadoop](http://hadoop.apache.org/) 、 [Spark](https://spark.apache.org/) 、Hive 和 [Presto](https://prestodb.io/) ，以及其他开源引擎，如 [Airflow](https://airflow.incubator.apache.org/) 和 [Pig](https://pig.apache.org/) 。

五月，该公司[宣布](http://sdtimes.com/qubole-unveils-first-autonomous-data-platform-cloud-data-platforms-2017/)其所谓的“自主数据平台”:其 Qubole 数据服务(QDS)为社区和企业版。

该公司声称，该平台可以自我管理、自我优化，并从你的使用中学习，以最有效和最经济的方式运行。它运行在亚马逊网络服务、微软 Azure 和甲骨文裸机云上。此外，该公司于 1 月份在[谷歌](https://www.qubole.com/blog/spark-google-cloud/)云平台上添加了 Spark。

据该公司称，使用 Qubole，数据科学家可以在他们选择的公共云上旋转数百个集群，让系统根据需要自动扩展到最佳计算水平，并在不到五分钟的时间内开始创建临时和/或批量查询。

云实现了计算和存储的分离，这是其架构的关键。

它在三个层面上实现自动化:基础设施管理、数据管理和工作负载管理。

它使用应用感知的自动扩展算法，该算法查看传入的工作负载并创建基础架构，包括异构集群、具有不同机器配置文件的集群等。

它提供了有关如何以最佳方式构建数据集的信息，以减少获得答案所需的时间并提高基础架构效率。它还指导用户管理工作负载，例如通过重用现有工作负载中的数据或连接数据集中的数据。

它还提供笔记本即服务和 SQL workbench 即服务，以及与 Tableau 等其他数据工具的 API 连接器。

该公司还发行了一套新的代理，包括:

*   **支持工作负载的自动扩展代理**，可根据工作负载需求精确优化集群规模，并根据实际处理负载进行动态扩展。
*   **Spot Shopper Agent** (仅限 AWS)，它在 AWS 云上购物，以最佳的性能和成本组合组装计算实例。
*   **数据缓存代理**，优化您数据的位置，实现快速、交互式的访问速度。访问频率较低的数据会在后台智能移动，以获得最佳性能。

其客户包括 [Pinterest](https://www.pinterest.com/) 、 [Lyft](https://www.lyft.com/) 和[安德玛](https://www.underarmour.com/en-us/)。

Elastic 和 MapReduce 经常被认为是 Qubole 的竞争对手，但是 Thusoo 说它们有几个不同之处:

*   选择:相同的平台在 Azure 上运行，在 AWS 上运行，在 Oracle Cloud 上运行，在 Google 上运行。如果客户想要在多个云上构建工作负载，或者他们想要在不同的云中构建不同的工作负载，则工作负载不需要重组。
*   分析师、数据科学家和开发人员都可以使用同一个平台。他说，竞争对手无法提供 Qubole 那样的自动化或自助服务水平。
*   它通过更有效地提高硬件利用率，以极低的成本提供这种访问。

一个账户上的用户针对不同的用例使用其多个“即服务”产品，如用于机器学习的 Spark、用于 ETL 的 Hive、Presto 和用于日志分析的 Hive。Thusoo 说，它一个月处理 750PB 的数据。

“我们的价值主张是，从一个平台上，他们可以包含所有这些用例，”他说。

[https://www.youtube.com/embed/PdWGIBgJk5U?feature=oembed](https://www.youtube.com/embed/PdWGIBgJk5U?feature=oembed)

视频

特征图片:[特雷弗金](https://www.flickr.com/photos/trevor-king/)的 [#43 条纹](https://www.flickr.com/photos/trevor-king/15812744721/in/photolist-q6js6F-qsq61V-qeKCVg-3tpXKH-539X3s-o3bMjJ-EbQjtx-SEe4mG-7mjZ3k-u4CfEi-dPuCEr-piVTrc-akzhqG-RJ436q-4rYQtC-pApPzk-dB7dcE-qHAmjC-dPAgKQ-7YULtw-zAZsp-7ps2t-dPAgxy-dPAggN-nGGV4j-s4ztmb-zAZsk-fNXvEK-dQvkXc-2ic8BZ-auzgkL-4NQ46R-N9uaw-8xNAv7-fNXvHk-ktTJ7H-nWxt7g-94vEkp-gCqTT1-RVrkoR-cYA9CN-6e7Rf-tX64vz-piqKGe-8QekS5-oAfEeA-pzW2DX-6yFenU-k4woYu-ciaHu9)，授权**CC BY-SA 2.0**。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>