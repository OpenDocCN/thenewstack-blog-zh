# 解开数据将大数据应用程序性能管理带到了云中

> 原文：<https://thenewstack.io/unravel-data-takes-big-data-application-performance-management-to-the-cloud/>

[解开数据](https://thenewstack.io/unravel-data-tackles-application-performance-management-big-data-stack/)因其作为大数据堆栈的应用性能管理(APM)平台而闻名，包括 Hadoop、Spark、Kafka、Impala、Cloudera 等。

最近，它一直在帮助客户将他们的大数据应用程序带到云上。对大多数人来说，这是一段旅程。

“没有人会在某一天关掉本地开关，第二天又打开云开关，”unlaurer 首席执行官 [Kunal Agarwal](https://www.linkedin.com/in/kunalkunal/) 说。

“他们经历这种混合环境。他们需要几年的时间才能完全实现云计算，而有些公司则只能在有生之年保持混合模式，因为有些使用案例和数据集更适合在内部运行。”

unallow 在日志数据的基础上使用机器学习和人工智能来监控应用程序性能，检测异常行为，并提供补救建议。

解开告诉你，“这就是问题，这就是今天发生的事情，这就是你如何解决它，”阿加瓦尔解释说。

无论是在本地还是在云中，都可能存在类似的问题:应用程序今天很慢，昨天还不是，或者运行成本太高，等等。

虽然云中的工具可能是相似的——你可能运行 [AWS Kinesis](https://aws.amazon.com/kinesis/) 而不是 Kafka， [Amazon EMR](https://aws.amazon.com/emr/) 或 [Azure HDInsight](https://azure.microsoft.com/en-us/services/hdinsight/) 而不是 Hadoop 或 Spark， [Redshift](https://aws.amazon.com/redshift/) 用于快速 SQL——但它们仍然是不同的。相关问题也是如此。

借助云，您可以选择环境、加载数据，然后在其上运行分析。工作负载可以是批处理过程，也可以是像物联网这样的实时过程。可能是快速 SQL 查找。任何一种都有一系列共同的问题。

“如果你有一个失败，你必须挖掘 20 个不同的工具，因为原因可能在堆栈的任何地方。这可能是因为你的代码不好，因为你的容器大小不合适。在多节点环境中，如果你有 100 台机器，那可能是因为 84 号机器昨天没有工作，”Agarwal 说。

unallow 采用所有完整的堆栈数据，并使用其分析引擎运行算法来检测这些问题，查明它们，然后提供建议或自动修复。

分析引擎了解您的生态系统。它学习你的集群的季节性。它将根据用户配置文件或这些作业的可重复性来了解应用程序的优先级。阿格沃尔说，当它提出建议时，它会将这些建议放在它对你的环境所了解的范围内。

“我们想了解这个生态系统中可能存在什么，然后我们如何推荐正确的参数，或正确的输出，以便我们提高整个生态系统的整体性能和可靠性，”他说。

云中的自动伸缩机制是存在的，但是您如何知道您的应用程序需要 100 台机器而不是 64 台呢？

unflare 不仅可以告诉你需要多少个应用程序，供应商可能有 40 种不同的机器选项，都有不同的规格、不同的内存、CPU 和价格。

“[用户]今天是盲目的，使用一些猜测。(所以他们订购了一大堆东西)然后在月底大吃一惊，”他说。

“亚马逊不分解使用情况；它只是说你的 EC2 成本是 X，你的 EMR 成本是 Y，你的 S3 成本是 Z，这等于 5000 美元。”

unfraud 可以帮助客户按应用程序分解账单。

“auto-scaling——帮助公司计算出他们在一周的任何一天、任何一天的任何给定时间需要什么资源，这正是 Unravel 所做的事情。然后，我们使用相同的数据来帮助客户将账单分解为电话账单，以了解他们是否真的需要花费这么多，以及他们是否可以以任何特定的方式降低账单，”Agarwal 说。

尤其是在微服务时代，[确定成本](https://thenewstack.io/microservices-pricing-whats-it-all-going-to-cost/)一直是一个棘手的问题。举例来说，总部位于特拉维夫的初创公司 [Lumigo](https://www.lumigo.io/) 吹嘘其在 AWS 上分解每笔交易的[成本的能力。](https://thenewstack.io/lumigo-end-to-end-serverless-monitoring-and-troubleshooting/)

它还可以帮助他们确定哪些工作负载适合云。这通常是指某一天的性能发生巨大变化的任何工作负载，或者经常耗尽资源的应用程序。

它可以帮助公司单独确定每个应用程序的资源足迹，并确定，例如，将它们中的某一组(例如，营销部门)作为一个整体迁移到云是否是一个好主意。

专题图片:[丽贝卡·东加罗](https://www.flickr.com/photos/rebdon/)的《绳结 2 》。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>