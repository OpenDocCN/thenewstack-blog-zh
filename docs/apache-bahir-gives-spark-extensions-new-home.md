# Apache Bahir 给 Spark Extensions 一个新家

> 原文：<https://thenewstack.io/apache-bahir-gives-spark-extensions-new-home/>

Apache Spark 的一个分支，Apache Bahir 是 Apache 软件基金会的一个新的顶级项目，旨在管理与分布式分析平台相关的扩展和插件。

“Apache Spark 项目更侧重于运行时，并确保平台非常稳固、非常健壮。Apache Bahir 副总裁兼 IBM 架构师 [Luciano Resende](https://twitter.com/lresende1975) 说:“我认为开发一堆扩展并维护这些扩展可能会成为成员的负担。

“使它成为一个独立的项目提供了更多的灵活性，并使每个人都有机会专注于其成员认为最重要的事情，”Resende 说。

到目前为止，这个新生的项目包括四个扩展:

*   **streaming-akka** ，一个开源工具包和运行时，简化了 Java 虚拟机上并发和分布式应用的构建。Spark 和 stream processor [Flink](https://thenewstack.io/apache-flink-addresses-continuous-stream-processing/) 都是基于 Akka 构建的，强调基于 actor 的并发性。
*   **streaming-mqtt** ，一种用于小型传感器和移动设备的轻量级消息协议，针对高延迟或不可靠的网络进行了优化。它主要用于物联网市场的远程监控和控制，作为 WebSocket 协议的更高性能替代方案。
*   **streaming-twitter** ，支持处理来自 twitter 的社交数据。一个示例通过将流 Twitter 数据与用于情感分析的 [AFINN 单词列表](https://finnaarupnielsen.wordpress.com/2011/03/16/afinn-a-new-word-list-for-sentiment-analysis/)的静态 RDD(弹性分布式数据集)相结合来显示最积极的标签。
*   **streaming-zeromq** ，一个高性能异步消息传递库，旨在用于分布式或并发应用程序。它提供了一个套接字接口，允许用户快速构建他们的可伸缩消息传递系统。

这些用于集成不同外部流媒体资源的子项目[已于三月份从主 Spark 项目中移除](https://issues.apache.org/jira/browse/SPARK-13843)。

Resende 说，Apache Bahir 还与不同的存储层建立了密切的关系，并打算邀请其他 ASF 项目进行合作。

“我们从 Spark 开始，很多人来自 Spark，但我们对分布式平台的其他扩展持开放态度。如果来自 Apache Beam 或 Apache Flink 的人想用我们作为一个地方来合作他们的扩展，我们也欢迎他们，”他说。

它刚刚发布了第一个版本，名为 Bahir 2.0 预览版，它基于 [Apache Spark 2.0 预览版](https://spark.apache.org/news/spark-2.0.0-preview.html)，作为用户入门的一种方式。随着 Spark 2.0 的发布，它将紧随其后，不久[。](https://spark.apache.org/news/spark-2.0.0-preview.html)

“我们对用于遥感应用和控制/监控的 streaming-mqtt 非常感兴趣。我们在地球科学中有很多大数据需求，特别是在偏远和难以访问的环境中，Bahir 的 streaming-mqtt 等插件为此提供了一个易于访问的基于 Apache 的解决方案，”Apache Bahir 项目管理委员会成员兼 NASA 喷气推进实验室仪器和科学数据系统部门首席架构师 Chris Mattmann 说。

Resende 说，将扩展作为一个单独的项目是有好处的。

“比方说，你有一个 Apache HBase 项目的扩展，也是 Spark，”Resende 说。“与此同时存在的问题是，发布周期永远不会一致。HBase 可能会有新版本，Apache Spark 也可能会有新版本。如果两边的情况都发生了变化，你就会有点落后。通过对像 Apache Bahir 这样的第三方项目进行扩展，当两个项目都发布时，您就有了发布和更新扩展的工具。如果 HBase 出现，并且您必须快速为您的扩展提供一个新功能，您可以在另一个项目的发布周期之外做这件事，如果您与一个或另一个项目共处一地，您将无法做到这一点。”

除了 Bahir 的启动，ASF 还宣布了大数据中间件元数据框架 [Apache OODT](https://oodt.apache.org/) (面向对象数据技术)的 1.0 版本，用于科学数据处理、信息集成和检索。

它于 1998 年在美国宇航局喷气推进实验室创建，作为建立国家数据共享框架的一种方式，于 2010 年 1 月进入阿帕奇孵化器。并于 2010 年 11 月成为顶级项目。

被称为“元数据中间件”的 1.0 版特性包括数据接收和处理；自动数据发现和元数据提取；元数据和资源管理。

特征图片:[家甜蜜的家](https://www.flickr.com/photos/e3000/78156545/in/photolist-7UzdD-ecmeWS-fCQr8o-GCdpYX-4KXvXS-pTW4gF-e7Qemv-kHFAkR-gjUW7P-p362h6-bkLDCt-93u8mk-e4BU1S-9n2eEj-4uZmCs-pKWEd1-n16xx5-6cZRxG-aB98TR-oGqBYR-dUYhJN-6FGaov-auT4Sm-dQYzko-4Kpa1w-dGRm1W-dErQdY-fq45Q8-s5KTUR-6PuEMt-qSfGva-e23pSt-dCoDzT-h7WvCb-7tnMgs-GBaCfv-aW4KbR-9Vtkqm-btRgPg-aTmPMK-raYakL-FrNaEG-m4VVyd-e7VPBY-pckn5m-dEQduW-e2b53h-ePecSp-sqUgZk-paiHX9)，由[艾迪面包车 3000](https://www.flickr.com/photos/e3000/) ，持**牌照 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>