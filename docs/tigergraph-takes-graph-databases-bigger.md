# TigerGraph 建立了一个更大的图形数据库

> 原文：<https://thenewstack.io/tigergraph-takes-graph-databases-bigger/>

历时五年， [TigerGraph](http://www.tigergraph.com/) 于本月早些时候发布，其[图形数据库平台](https://thenewstack.io/introducing-tigergraph-native-parallel-graph-database/)具有并行处理和分析功能。

其[原生并行图形技术](http://www.tigergraph.com/wp-content/uploads/2017/09/WP_NativeParallelGraphs_Final_web.pdf) (NPG)为试图绘制和处理*真正*大数据的企业提供实时深度链接分析。它标榜自己是市场上唯一一个将实时分析与大规模离线图形数据处理相结合的系统。

创始人兼首席执行官徐雨表示，TigerGraph 已经过世界上一些最大的图形用户的测试，他预计它的功能将产生无数新的用例。他在之前为新堆栈发布的[帖子](https://thenewstack.io/introducing-tigergraph-native-parallel-graph-database/)中解释了它们。

它已经被用于中国在线支付公司[支付宝](https://intl.alipay.com/)号称世界上最大的交易图。该图包括超过 1000 亿个顶点、6000 亿条边和 20 亿次每日实时更新。

其他早期用户包括 Visa，移动电子商务公司 [Wish](https://www.wish.com/) ，日本电信[软银](https://www.softbank.jp/en/)，电力公用事业[国家电网公司](http://www.sgcc.com.cn/ywlm/index.shtml)。

该软件已经被用于打击欺诈和洗钱，用于客户和供应链情报以及智能电网用例。

这家总部位于加州雷德伍德城的公司成立于 2012 年，名为 GraphSQL。当时，所有的讨论都是围绕着的数据库，但徐专注于 SQL，并希望在名称上有所区别。他说，时代变了，标志着公司需要重塑品牌。

徐拥有加州大学圣地亚哥分校的计算机科学与工程博士学位，拥有 26 项分布式系统和数据库专利，曾在 Twitter 和 Hadoop MapReduce 担任分析工程师，并在数据仓库公司 Teradata 担任团队领导。

他的公司的支持者包括雅虎、沃尔玛实验室和 Data Collective 等公司的创始人。它刚刚从包括中国科技巨头百度和蚂蚁金服在内的投资者那里获得了 3100 万美元的首轮融资。

## 更快的图形遍历

早期的本地图技术不能跨多台机器存储一个图。徐认为 Neo4J(T1)是一个本地图数据库，它将数据存储为节点，并通过边来表达它们的连通性，这是“图 1.0”的一个例子然而， [Neo4J 已经与 IBM](https://neo4j.com/blog/neo4j-on-ibm-power8/) 合作解决可扩展性问题。

他说，大多数早期的图形数据库都是以存储为中心，分析能力有限，而不是提供公司希望针对图形数据库运行的工作负载所需的计算能力。大多数时间在两跳，而 TigerGraph NPG 是建立遍历 10 或更多。

他称 [Apache Giraph](http://giraph.apache.org/) 和其他位于 NoSQL 之上的并行图形数据库为“图形 2.0”——它们缺乏实时更新的能力。

该公司将 TigerGraph 称为“图形 3.0”，这是一个“完整的分布式图形分析平台，支持网络规模的实时数据分析。”它表示，对于只使用图形一小部分的有限快速查询以及涉及图形中每个顶点的复杂分析，它也同样适用。

尽管有人抱怨 Hadoop 和 MapReduce 的缺点，但徐把 TigerGraph 建立在 MapReduce 的基础上，并说这完全取决于它是如何实现的。

“使用 C++从头开始构建一切，因此我们可以控制整个堆栈。我们建立了自己的存储引擎，我们自己的交叉交流引擎，”他说。

图表存储在磁盘和内存中，允许系统利用磁盘、内存和 CPU 缓存中的数据局部性。

它还允许用户不断向数据库添加数据，而无需重新运行提取、转换和加载(ETL)过程。

在自己的基准测试中，该公司声称与 Neo4j 和另一个图形数据库 [Titan](http://titan.thinkaurelius.com/) 相比，图形遍历和查询响应时间要快 4 到 100 倍。

它还声称其并行计算能力将加载速度提高了 10 倍——每台机器每小时 50 到 150 GB 的数据。

它提供了多种加载数据的方式，包括 RESTful 应用程序接口、逗号分隔值和 JavaScript 对象符号文件到图形顶点的高级映射以及到流行数据源的连接器。

该公司还宣布在亚马逊 EC2 和其可视化软件开发工具包 GraphStudio 上提供 TigerGraph 的托管版本。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>