# Jepsen 提供了大规模测试数据库的全系统方法

> 原文：<https://thenewstack.io/jepsen-offers-system-wide-approach-testing-databases-scale/>

大规模数据库的重要性和事件驱动架构(包括[物联网环境](https://thenewstack.io/designed-cratedb-realtime-sql-dbms-internet-things/))的增长，将意味着更加依赖于分布式系统，使其强大并能够高效、准确地维护交易记录。

维护分布式数据库的记录系统可能会受到网络分区、部分故障或时钟偏差的影响，其中任何一种情况都可能会在稍后的输入上重写较早的数据，将存储数据的不同副本保存到备份中，或者读取陈旧的数据。特别是对于金融和物联网系统，这可能会产生重大的生产影响。[分布式系统很难](https://thenewstack.io/distributed-systems-hard/)，哟。

直到最近，能够测试和确保分布式系统的健壮性还依赖于单元测试和分布式测试。但是单元测试倾向于关注跟踪一个过程，并且作为维护代码库的一部分在内部使用，并且用于连续交付。分布式测试可以观察数据库集群，但往往被写成一系列步骤，检查执行许多典型数据库活动的健壮性，如写入数据、向集群添加节点，然后检查数据写入是否得到维护。

其他方法，如网飞的[混沌猴子](https://github.com/Netflix/SimianArmy/wiki/Chaos-Monkey)，可以引入随机数据库故障，旨在帮助内部开发人员确保他们正在大规模构建高性能、可靠的系统，如果一个组件神秘地倒下，可以保持功能。

但是仍然需要测试来提供对系统级控制的洞察。这就是杰普森的用武之地。

“Jepsen 是一个在压力下分析分布式系统并了解并发问题是否会出现的项目，不仅在应用程序中，而且在数据库和队列等中，”创作者 Kyle Kingsbury 说。" "我们希望验证在给定并发性、不确定性和部分失败的情况下，分布式系统的安全属性是否成立。"

该软件创建了一个数据库实例，然后设置了一些测试，这些测试通过通常可能在大规模分布式数据库上执行的示例操作来运行。然后检查验证日志并创建报告，以确保这些操作的结果保持了数据记录的同步。

Jepsen 包括:

自 2015 年末以来，大多数分析都看到数据库供应商雇佣 Kingsbury 进行独立测试，尽管开源项目文档足以独立使用。例如，无论是 [Datastax](https://www.datastax.com/dev/blog/testing-apache-cassandra-with-jepsen) 还是 [彭博](https://github.com/bloomberg/jepsen-training-vpc) 都使用了独立于金斯伯格参与的 Jepsen。

“Jepsen 现在正在成为一个更通用的工具，”Kingsbury 说。“但是文档仍然很少，API 仍然有点生疏，”他承认道。金斯伯里在这里可能是谦虚的。GitHub repo 的快速回顾显示了一系列教程，解释如何设置 Jepsen 环境(包括 [如何从 AWS](https://aws.amazon.com/marketplace/pp/B01LZ7Y7U0?qid=1486758124485&sr=0-1&ref_=srh_res_product_title) )启动 Jepsen 集群，如何编写 Jepsen 测试，设置和拆除数据库实例，编写客户端，将故障引入系统，以及分析结果。

Kingsbury 说，他在客户中使用 Jepsen 的大部分工作都集中在想要分析其产品可靠性的数据库供应商身上。“但在一些公司，我会帮助进行内部测试，”金斯伯里说。工程师可能有一个他们想要测试的内部产品，使用通用测试设计或端到端分析

金斯伯里说，出发点是帮助工程师正式确定他们想在测试中使用的变体，例如确保强大的交易需求。“它非常适用于任何拥有分布式系统并希望验证系统可靠性的情况。您希望进行单元和集成测试，然后将 Jepsen 用于整个集群。”

特别是，Jepsen 测试利用了三种系统测试的原则:

*   ***黑盒系统测试:*** 在不知道操作的实际数据计算的情况下测试系统。因此，生产中观察到的任何错误都可以被记录下来，但是没有提供正确的数据值，例如
*   ***故障模式测试:*** Jepsen 旨在测试网络故障、时钟不同步和部分故障等事件后数据更新的可靠性，指出数据库系统在紧张时的行为，而不是评估健康的集群行为
*   ***生成性测试:*** 通过运行随机操作和记录结果历史来进行测试。然后可以对照工程团队的模型进行检查，以确定系统的运行情况。

到目前为止，Kingsbury 已经对 Aerospike、Cassandra、CockroachDB、Kafka、MongoDB、Redis、Riak 和其他系统进行了超过 22 次测试，他分享了一些关于他所分析的数据库系统的想法:

*   **[cocroach db](https://github.com/cockroachdb/cockroach):**“我合作过的许多供应商都非常重视安全性，并且非常关注陈旧的读取。例如， [VoltDB](https://www.voltdb.com/) 做了一个重大改变，为了确保安全，让他们的读取速度慢了很多。同样，CockroachDB 也是这样做的，但是他们围绕需要时钟同步做了一些有趣的假设。在云环境中，您可能需要长达三秒钟的读取等待时间。CockroachDB 猜测，未来人们对时钟同步会有很大的兴趣，你可以在市场上看到这一点，谷歌最近发布了针对 Spanner 的 [Truetime API。](https://research.google.com/pubs/pub45855.html)
*   **[elastic search](https://www.elastic.co/):**“我不会把它作为一个记录系统，所以你会把你的数据放在 S3 或 Postgres，并有一个复制工具，以便它重复这些数据。这就是你想要设计健壮系统的方式。你不需要直接向 Elasticsearch 写数据，你只需向主数据库写数据，然后有一个工具不断地向辅助数据库写数据。最大的问题将是碎片再平衡，因为如果 Elasticsearch 构建在一个碎片中，它可能会在高负载下崩溃。很多人可能正在丢失数据，但他们并不知道。”
*   **[etcd](https://github.com/coreos/etcd) :** “我的松散印象是，如果你打算使用下一代共识系统，我知道[consult](https://www.consul.io/)已经关闭了大规模系统，至少在中断方面。Zookeeper 是最好的选择，它已经存在了很长时间，并且已经完善了边缘用例。但 etcd 用户界面更好用，对一些人来说可能更接近了。”

虽然官方的 Jepsen 开源项目元素是用 [Clojure](https://clojure.org/) 编写的，但其他人正在将这个库改编成他们自己的语言，例如，彭博和软件工程师 [米兰·西蒙诺维奇](http://milansimonovic.com/2016/12/26/jepsen-testing-rabbitmq-with-python/) 都使用 Python。

来自 Datastax 的乔尔·奈顿写道，Jepsen 鼓励在准备系统测试时使用定义良好的模型和不变量。

“这鼓励了明确的设计和交流，也使测试的目的变得清晰。第二，Jepsen 使测试人员能够通过测试可组合性在现实条件下轻松测试这些不变量；同一核心测试可以与节点崩溃、网络分区或其他病理故障同时运行。最后，通过拥抱生成测试，它承认了使用确定性的、手工选择的例子来彻底测试分布式系统的困难，”奈顿 [写道](https://www.datastax.com/dev/blog/testing-apache-cassandra-with-jepsen) 。

Kingsbury 将在 9 月 18-20 日举行的柏林[软件架构峰会](https://software-architecture-summit.de/softwarearchitektur/jepsen/)上发表关于 Jepsen 的主题演讲。他今年早些时候在 Scala Days 的主题演讲可以在网上看到:

[https://www.youtube.com/embed/eSaFVX4izsQ?feature=oembed](https://www.youtube.com/embed/eSaFVX4izsQ?feature=oembed)

视频

专题图片:今年早些时候凯尔·金斯伯里在 Scala 关于 Jepsen 的主题演讲截图。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>