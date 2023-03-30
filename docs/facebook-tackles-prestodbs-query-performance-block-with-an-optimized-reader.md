# 脸书用一个优化的阅读器解决了 PrestoDB 的查询性能问题

> 原文：<https://thenewstack.io/facebook-tackles-prestodbs-query-performance-block-with-an-optimized-reader/>

这是一个大海捞针的问题，除了你要寻找多种针匹配一个特定的类型。你如何接近干草堆？在你的头脑中，你可以把谷仓分成几块，每块又分成几个小方块。然后你可以从左到右，从上到下，依次搜索公寓中的每个立方体和街区中的每个单元。在网络中立问题上，你会比国会更慢地得出结论。

如果你需要的只是对实际有多少根针的可靠估计，那么你可以采用抽样策略。最简单的策略假设针的分布总是均匀的。但在实践中，应用简单的抽样策略可能无法帮助您估计您正在寻找的特定类型的针的数量。尽管如此，你可能不喜欢评估针的类型，直到你已经从干草中分离出所有的针。

至少，这是逻辑会告诉你的。谓词逻辑建立在 Edgar F. Codd 博士在 20 世纪 60 年代首先奠定的基础上，但实际上并不是这样的。它可能更喜欢您从干草和其他针中分离出确切的针类型，并且它可能会在让您开始按块细分之前将该上下文应用于整个谷仓。

因此，可以想象，将为关系数据库系统创建的查询应用于庞大的半结构化数据集可能会产生差的结果或慢的结果——随你挑。

## 迅速改变

PrestoDB，[正如我们在之前的帖子](https://thenewstack.io/airbnbs-airpal-reflects-new-ways-to-query-and-get-answers-from-hive-and-hadoop/)中所讨论的，是脸书针对将快速查询应用于存储在 Hadoop HDFS 中的巨大数据集的问题而开发的解决方案。脸书的工程师们发现他们自己在构建 PrestoDB(或者只是“Presto”)，原因很简单，Hadoop 的查询引擎 Hive 在处理大型数据集时太慢了。

使脸书的 Presto 开发更快的是它的开发者与更大的开源社区分享他们的经验。它仍在积极开发中。正如脸书最近宣布的，为了获得更快的速度，它已经更换了 Presto 的一个关键组件。

这样的声明听起来就像汽车工程师鼓吹更换化油器以获得更大的排量。但是现在世界上越来越多的巨大工作量依赖于脸书技术，我们可以使用新的汽化器，谢谢。

具体来说，这是 Presto 的优化行/列阅读器，它从 Hadoop 的 HDFS 文件格式中提取记录。在一篇博客文章中，脸书软件工程师 Dain Sundstrom 解释说，他的团队一直在使用“兽人的一个分支”(他可能写了整篇文章，所以他可以这么说)，叫做 DWRF。但 Presto 的分析任务需要列读，这可以比作将所有针堆叠起来而不必从干草中单独提取每一根针的能力。DWRF 提取行或记录，而不是列。

## DWRF 推下:这一次，它是个人的

此外，DWRF 不支持脸书迫切需要的一个关键特性，称为谓词下推。

我们请 Arshak Navruzyan,[Argyle Data](http://www.argyledata.com/)的产品管理副总裁解释这是什么。Argyle 是 PrestoDB 的主要第三方客户之一，也是 Presto 开源项目的贡献者。它在为主要电信提供商提供实时欺诈检测服务的过程中使用 Presto。你可以在这里找到我们关于阿盖尔使用急变戏法[的故事。](https://thenewstack.io/how-argyle-data-uses-facebooks-prestodb-to-detect-fraud/)

Navruzyan 告诉我们，Argyle 在 Presto 和 [Apache Accumulo](https://accumulo.apache.org/) (分布式键/值存储)之间的连接器确实使用了谓词下推。“因此，查询的 WHERE 子句实际上被下推到索引存储中，也就是 Accumulo 中，”他说。"然后 Accumulo 就可以进行范围查询了."

向下推是一种延迟，但完全是正确的延迟。它的意思是:不要开始寻找精确的东西，直到先把一般的东西分离出来。

Navruzyan 说，Presto 的主要优势之一是进行近似查询的能力，这是建立在加州大学伯克利分校研究人员的 [BlinkDB 项目](https://www.cs.berkeley.edu/~sameerag/blinkdb_eurosys13.pdf) [PDF]的基础上的。几年前，正是这个团队首次尝试平衡效率和实用性的需求，提出了一个合理的折衷方案。

“以前的解决方案都不太适合今天的大数据分析工作负载，”伯克利团队在 2013 年写道。“OLA [online aggregation]为稀有元组的查询提供了相对较差的性能，而采样和草图对工作负载的可预测性做出了强有力的假设，或者极大地限制了它们可以执行的查询类型。… BlinkDB 允许用户对存储的数据提出基于 SQL 的聚合查询，以及响应时间或错误限制。因此，超过数 TB 数据的查询可以在几秒钟内得到回答，并伴有相对于查询在完整数据上运行时得到的答案的有意义的误差界限。”

这是脸书工作背后的灵感的一部分，自柏克莱以来，它已经发展了至少几代。根据脸书的计算，Presto 的新 ORC 阅读器移植到位后，对内存中 ZLIB 压缩数据集的端到端单线程查询速度比 DWRF 快 3.5 到 4 倍。(脸书大学的 Sundstrom 警告说，你的结果可能会有所不同。)

Sundstrom 写道:“我们一直在挑战规模和性能方面的极限。实际上，他可能低估了自己的情况。那个信封，尽管如此，却被丢在了几英里以外。在后视镜中，你仍然可以看到灰尘，还有一些干草斑点和一些弯曲折断的针。

特色图片[通过](https://www.flickr.com/photos/cernaovec/15671888594/in/photolist-pSSwtL-6WCq3s-hf9Hz-6MMYqU-4VkN3R-2x8mvr-8MBG8c-34krtF-4xczrV-7u4pup-N39Y6-dbo2AB-5fYpMA-a9pd8s-5LdHDQ-o5ef8W-6Yz7Lz-oT5uXE-xVtw2-aa8HLR-dFwGvP-dFC7Lw-P5BSr-4xgNLU-4xgNwW-dNiF3Z-5gPQjp-5fYoRf-3HBdU-6FMtWX-a6kSVB-4MqrHF-abxBzG-abuAvB-abukxc-abuj9R-54RxSJ-54MkjZ-54MjQg-54Rtgw-54Rrsq-54MdR2-5DXrkY-5DT9Ta-5DXpWJ-dNpf11-bR3Fbx-4peuUA-5DT8ni-5DT7Mg) Flickr 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>