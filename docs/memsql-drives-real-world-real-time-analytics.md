# MemSQL 如何推动现实世界的实时分析

> 原文：<https://thenewstack.io/memsql-drives-real-world-real-time-analytics/>

正如该公司首席营销官[加里·奥伦斯坦](https://twitter.com/garyorenstein?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)所说， [MemSQL](http://www.memsql.com/) 数据库系统完全是为了“快速捕获数据，并允许人们立即分析数据，以便他们能够根据业务需要尽快做出决策”。

在最近于加州圣何塞举行的 [Strata+Hadoop 会议](https://conferences.oreilly.com/strata/strata-ca)上，MemSQL 客户展示了他们如何利用数据库的这些实时数据功能。

让 MemSQL 发挥作用的方法包括:

移动广告盈利平台 [TapJoy](https://my.tapjoy.com/) 谈到它如何每分钟运行超过 200，000 次的查询，以确定它应该如何对广告[进行竞价](http://eng.tapjoy.com/blog-list/moving-to-memsql)以驱动一定数量的应用程序下载，开发者为此获得报酬。

[优步](https://conferences.oreilly.com/strata/strata-ca/public/schedule/detail/58258)解释了如何使用 MemSQL 的地理空间功能，该公司可以为该公司设计仪表板，直至各个城市的特定视图。在其内部 Apollo 项目中，它实施了一种用于实时地理空间分析的自定义查询语言，允许本地管理人员在他们自己的地区运行特定查询。

[Macys.com](https://www.macys.com/)还使用 [Tableau](https://www.tableau.com/) 、 [Cognos](https://www.ibm.com/analytics/us/en/technology/products/cognos-analytics/) 、定制仪表板和 MemSQL 的组合创建了一个 JavaScript 仪表板，允许销售经理按部门深入销售。他们可以看到哪些产品是热门产品、交易情况、购物车中放了什么、废弃了什么等等。它还与公司的供应链和库存相联系。

然而，梅西公司的首席工程师[钱丹·约德尔](https://www.linkedin.com/in/chandanjoarder/)和梅西公司的数字数据工程经理[拉杰·斯里拉姆](https://www.linkedin.com/in/rajsriram/)解释说，这个项目并不是从上面的命令开始的。他们没有这个项目的预算，所以他们寻求志愿者，并试图让它变得有趣——它已经有了一些意想不到的结果。

例如，仪表板上有一个十大畅销商品的列表，包括最受欢迎的[迈克高仕手袋](https://www.macys.com/shop/featured/michael-kors-handbags?cm_kws_ac=michae)。当有人注意到它不在仪表板上的前 10 名之列时，查看网站会发现该项目不可用。当电子商务团队被问及网站的潜在问题时，得到的回答是，“你怎么知道的？”

该系统通过一个 API 消费数据，数据进入[卡夫卡](https://kafka.apache.org/)，然后进入数据库。Joarder 说，MemSQL 的摄取引擎意味着它可以消费数据，而无需 Kafka 的任何代码。数据以 10 到 15 分钟的序列出现。

Joarder 解释说，该公司以前整夜进行批处理，供经理们第二天使用，但仪表板提供了更频繁的问题可见性，这些问题可能会极大地影响[苦苦挣扎的零售商](http://www.marketwatch.com/story/after-a-harrowing-holiday-season-struggling-department-stores-reach-a-tipping-point-2017-01-06)的底线。

Joarder 说，该公司每天消费约 5000 万张唱片，但今年将增长到每天约 1 亿张唱片。

同样在会议上，MemSQL 首席执行官兼联合创始人 [Eric Frenkiel](https://twitter.com/ericfrenkiel) 强调了[公司与 Thorn](https://www.youtube.com/watch?v=LFTznWxLhbk&index=4&list=PL055Epbe6d5ZsQVJRV2FQQvsgDt0Ci5Zy) 的合作，Thorn 是一家在[打击对儿童的性剥削](https://www.wearethorn.org/child-sexual-exploitation-and-technology/)中使用面部识别和图像映射的公司。奥伦斯坦说，该组织在 2016 年确认并归还了 2000 名失踪儿童给他们的父母。

类似于巨人橡树打击人口贩卖的工作，索恩每天分析 10 万个发布在网络上的三陪服务广告。西雅图 MemSQL 工程团队负责人 Eric Boutin 在一篇博客文章中解释说，Thorn 面临的最大挑战是将一张照片的指纹与成千上万张照片的指纹进行匹配，同时有大量新照片进入其数据库。他添加了数据库操作符来对向量进行线性代数运算，以专注于机器学习中的评分，从而实现实时图像匹配并减少延迟。

Frenkiel 说，通过向数据库中添加 vector_dot 产品，图像匹配已经从 20 分钟减少到 200 毫秒。

## 变得真实

MemSQL 于 2011 年推出，在世界其他地区似乎迷恋 MongoDB、Cassandra 和 HBase 等 NoSQL 替代品追求规模的时候，它接受了 SQL。

另一家基于 SQL 的初创公司 [FaunaDB](https://fauna.com/) 的首席执行官埃文·韦弗说，公司已经“严重受损”,他们对自己的数据库感到失望，就像十年前他和 Twitter 的其他团队一样。

“……在很大程度上，[NoSQL 用户]已经逃回传统的关系数据库，因为他们知道这是个魔鬼。但是它只能扩展到目前为止，并且有各种各样的隔离和可用性问题。手术很痛苦，但至少他们知道尸体埋在哪里。或者他们已经逃到云端，那里是别人的问题，”他最近说。

谷歌的[云扳手](https://thenewstack.io/google-cloud-spanner-view-field/)是另一个新发布的基于 SQL 的数据库。

MemSQL 自称是一个实时数据仓库。它的三个部分——摄取引擎、针对实时数据的内存优化表、针对历史数据的磁盘表——意味着客户可以构建数据管道，而无需集成工作来使用传入数据和历史数据进行交易和分析。

Frenkiel 指出，实时对不同的用户有不同的含义。一些客户希望每小时或几分钟更新一次，而另一些客户则寻求持续的实时更新。

他指出，一个社交网络客户每秒钟将 1gb 的数据输入 MemSQL 进行实时处理，一个内容交付网络客户每秒钟处理近 1000 万次更新。

在 2 月份的 Spark Summit East 上，产品经理[Steven camia](https://spark-summit.org/east-2017/speakers/steven-camina/)概述了[建立数据管道](https://www.youtube.com/watch?v=gapTJYxyV2E&feature=youtu.be)的必要条件:一个消息队列，如 Kafka，用于不同格式的数据；一个转化层，如 Spark 数据持久层；和实时可视化。

它去年秋天发布的 5.5 版本增加了 [MemSQL Pipelines](http://siliconangle.com/blog/2016/09/26/memsql-calls-its-new-streaming-technology-a-game-changer/) ，引入了 SQL“create pipeline”语法，从命令行构建流管道，以立即使用正在流入 Kafka 等消息代理的数据。

专题图片:[艾米·尼尔森](https://www.flickr.com/photos/amyn-design/)的[圣诞漩涡](https://www.flickr.com/photos/amyn-design/5549226120/in/photolist-9sneAq-cCXWcs-zGGrs-o7k61k-SzEpRJ-T7K9Uj-STnMCR-pbaFs-qxSyer-7andG-4bq1gA-a7RfpH-5QnH34-28fdNY-9T5BYj-7rQtE6-RGpryZ-RS7FoN-dXZEBG-frjdN6-6iMPtb-4p4iEF-aLYVJM-mj59Xr-dAgLN1-5jJmrE-7GUjN1-pWyT5X-FJtNVt-BxmeD6-phQtYM-fvu1Qm-gbXoyS-51WV9r-e918uo-5MpyKs-ao4TWX-rtLrNQ-vsWfk-4VqweH-aSXwA2-jnTMUj-reBka4-6AZXdr-5k7WU7-Sa7ka3-4Raa6G-nedn2-8ADuSk-S2GC2z)，授权**下的 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>