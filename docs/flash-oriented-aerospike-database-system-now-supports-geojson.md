# 面向闪存的 Aerospike 现在支持 GeoJSON

> 原文：<https://thenewstack.io/flash-oriented-aerospike-database-system-now-supports-geojson/>

在联合创立 Aerospike *、*之前，布莱恩·布尔考斯基在一家广告行为分析公司工作，他发现几乎一半的员工都在维护 MySQL。他认为一定有更好的方法，并看到了闪存的兴起，他和 Srini V. Srinivasan 在 2009 年创建了这家公司。最初名为[西瓜叶](http://www.itworld.com/article/2728332/big-data/citrusleaf--the-fastest-nosql-db-you-ve-never-heard-of.html)，2012 年更名为 Aerospike。

现任该公司首席技术官的 Bulkowski 说:“我们知道闪存将会出现，并相信我们可以建立第一个真正针对闪存优化的数据库，它不仅像文件系统一样对待它，也不像 RAM 一样对待它，而是真正像对待闪存一样对待闪存。”。

被要求进一步解释，他说:“你不能只把它映射成 RAM 它需要更多的并行性。Flash 非常适合数据库中的日志结构模式，所以您可以使用一些您通常会使用的技巧，但肯定不是全部。你当然不能像有些人那样，简单地使用文件系统或者基本上是内存映射来完成这个任务。我们发现，直接进入设备级，我们可以获得巨大的性能提升。”

该公司早期吸引了广告公司，但后来扩大了客户群，包括威廉姆斯索诺马、阿尔卡特朗讯和 Kayak 等公司。

“想象一下这样的情况，你有一个巨大的分析层，你在计算洞察力，你在计算谁喜欢什么，你在做预测。然后你需要把它转移到实时应用程序中，因为你在互联网上。也许你在做产品推荐，就像 Williams-Sonoma 对 Aerospike 做的那样。也许你正试图根据喜好来决定出租车应该载谁。又或者你做的是广告个性化。

“这些情况下，你需要大量的数据库马力，你可能会开始寻找一个 NoSQL 数据库，而不是关系数据库，以及你可能会使用 Aerospike，”Bulkowski 说。

数据库系统的最新版本， [Aerospike 的版本 3.7](http://www.einnews.com/pr_news/308728424/aerospike-announces-latest-version-of-its-high-performance-nosql-database) 加强了对地理空间的支持。

在气塞公司，我们的行军命令是“规模速度”。“我们认为地理空间数据应该得到同样的对待，”产品副总裁 Alvin Richards 在一篇博客文章中写道，他说我们正在进入“移动物联网”的时代

在新版本中，Aerospike 可以存储 [GeoJSON](http://geojson.org/geojson-spec.html) 对象并执行各种类型的查询。它增加了谷歌的 S2 图书馆和地理哈希来编码和索引点和区域。查询可以与[用户定义的功能](http://www.aerospike.com/docs/udf/udf_guide.html) (UDF)相结合，以过滤结果，例如搜索你附近的酒吧、餐馆或教堂，并进一步优化它们，例如，那些开放的。

它在 [Github](https://github.com/aerospike/geospatial-samples/tree/master/delivery) 上添加了一段演示代码，在这段代码中，用户试图管理一队无人机来递送信件和包裹。

“这是一个至关重要的类别，但它的性能一直缺乏，”Bulkowski 说，现有数据库上的地理空间功能之前。他说，S2 图书馆“允许我们使用我们拥有的超级快速存储层，然后使用大量我们的核心 C 技术将 RAM 索引用于数据库内部的地理空间层。”

他说 Aerospike 每秒可以处理“数万到数十万个请求，甚至是地理空间查询。

“我们的更新速度特别快，所以需要跟踪某些东西的人，如位置不断变化的出租车公司或物流公司，许多旧系统都是基于分析的，所以你可以以合理的速度进行查询，但你的书写速度不够快。这就是 NoSQL 系统的新时代，这些参与系统。”

对于开发人员，该公司表示，其最近发布的 Async C Client 4.0 提供了批处理功能，大大提高了批量读写的效率。

其他新功能包括:

*   **服务器端列表操作** — Aerospike 可以存储和检索列表和地图，并允许开发人员通过服务器上的一组命令直接操作列表，同时保持可预测的大规模性能。
*   **高级公共云稳定性** —用于提高 Google Compute Engine 和 Amazon EC2 等环境的集群稳定性的新算法，以及包括改进的数据迁移管理、基于每个集合添加停止写入阈值的能力和动态更改单播心跳地址的能力在内的新功能。

“我们发现，就我们所知，云环境尤其具有非常具有挑战性的网络和运营环境。因此，我们必须建立新的集群算法，不仅要处理企业内设计和维护相当良好的网络，还要处理公共云上出现的嘈杂、拥塞的网络，”Bulkowski 说，他说 Aerospike 拥有非常高的可用性和在运营上进行实时维护的能力。

“我们所说的自适应集群从所处的环境中学习，即使在这些环境中也能保持数据库正常运行。”

## 数百万次读写

总部位于印度的 Anya Soft 是早期采用者，专注于消费品包装行业的智能，该公司表示，其移动应用程序需要比当前 MongoDB 基础设施提供的速度更快的速度。

Anya Soft 首席执行官 Rakesh Reddy 表示，实际上有两个移动应用程序:一个是用于超市的简单移动销售点(mPOS)系统，另一个是提供一个界面，让公众使用其软件访问每个商店的可用库存、价格和报价数据。都是免费的。

当被问及他们如何使用地理空间数据时，Reddy 说，在 200 毫秒以下的延迟目标下工作，没有其他数据库比 Aerospike 更好地满足其目的。

“我们绘制了每家与我们有联系的商店的准确位置，这将是数以百万计的，我们还按每种产品实时绘制了这些商店中发生的每笔交易。我们向普通消费者实时提供他们想要购买的各种产品的供应情况和价格细节，或者只是查看供应情况以便以后购买，”他说。

“除此之外，我们还为每家商店、每条街道或每个区域、特定制造商可能生产的一系列产品或一系列制造商竞争对手的产品实时生成实际和分析数据，主要是将数据标记到地理位置，为销售人员提供视角和对底层数据的更好理解。

“我们实际上是在谈论每秒在几百万个节点上处理几百万次读写。简而言之，目前市场上没有比 Aerospike 更好的产品，可以在如此短的延迟窗口内处理如此大量的数据。”

特征图片: [Suedehead](https://www.flickr.com/photos/suedehead/) 在超市拍摄的[，持 **CC BY-SA 2.0** 许可。](https://www.flickr.com/photos/suedehead/5967027562/in/photolist-a6hzpy-5ogxZ2-njoJPy-suidEm-dvyD4s-5okPe7-52Y7hN-9Mzv2-pD1MED-nNH6cd-qyGvGj-kjQcUa-5RDxaF-kjSBGL-7y2mno-nJGNt9-nLG1x5-7fyqLh-oAJrZ4-C4S9Kj-kt2v3Y-mBHyWJ-gx8eBH-nygNPZ-nygNBz-7yDxrs-ik7KG-e3H6dy-4CNAtv-3X9zLE-5ianP4-dNUgnv-72ueyL-rGXW4-4nRRSJ-8wu45-8M486Y-51uPUU-6mmzZR-b4N8ci-9FdoKr-7D2v1s-Q6tCU-dNZSJy-6UQHz1-3aFaS8-54LDUN-8x5MMh-nRF4vG-t37m8z)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>