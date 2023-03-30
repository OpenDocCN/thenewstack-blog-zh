# Faust，基于 Python 的分布式流处理库

> 原文：<https://thenewstack.io/faust-a-python-based-distributed-stream-processing-library/>

股票和加密货币的自由交易平台 Robinhood 已经开源了其基于 Python 的流处理库 [Faust](http://faust.readthedocs.io/) 。

Faust 是在 [GitHub](https://github.com/robinhood/faust) 上可用的 Python 3 库，利用了 Python 最近的性能改进，并与新的 [AsyncIO](https://docs.python.org/3/library/asyncio.html) 模块集成，用于高性能异步 I/O

“Faust 具有 Python 的优势——入门非常简单，”它的开发者之一、数据基础设施工程师 [Vineet Goel](https://www.linkedin.com/in/vineet-goel-a373a258/) 说。“Robinhood 有一个相对较小的团队来构建许多不同的系统，因此入门的简单性和易用性是对你有帮助的事情。”

总部位于加州门洛帕克的公司[希望](https://robinhood.engineering/faust-stream-processing-for-python-a66d3a51212d) it 能够被分发，以帮助应对其面临的扩展挑战。首席软件工程师 Ask Solem 说，它做了大量的批处理，所以它希望用 Python 做一些容易使用的东西，因为它是一个 Python 商店。

Solem 是任务队列 [Celery](https://github.com/celery/celery) 的创建者，他有大规模 Python 项目的背景，Goel 有分布式系统的背景，所以有了 Goel 对 [Apache Kafka](https://kafka.apache.org/) 的研究，他们说他们有信心实现这一点。

浮士德同时提供了流处理和事件处理，类似于[卡夫卡流](https://kafka.apache.org/documentation/streams)、[阿帕奇火花](http://spark.apache.org/)、[风暴](http://storm.apache.org/)、[萨姆扎](http://samza.apache.org/)和[弗林克](http://flink.apache.org/)。

“虽然现有的流媒体系统使用 Python，但 Faust 是第一个在流媒体方面采用 Python 优先方法的人，这使得几乎任何使用 Python 的人都可以轻松地构建流媒体架构，”Goel 说。

《浮士德》从卡夫卡的作品中汲取了大量灵感，但采取了不同的方法，值得注意的是，它没有使用特定于领域的语言。作为一个 Python 库，它可以放入任何现有的 Python 代码中，支持 Python 开发人员喜欢使用的所有库和框架，如 NumPy、PyTorch、Pandas、NLTK、Django、Flask 和 SQLAlchemy。

Faust 支持任何类型的流数据:字节、Unicode 和序列化结构，但也附带了使用现代 Python 语法描述流中的键和值如何序列化的“模型”。

它的“代理”的[概念来自](http://faust.readthedocs.io/en/latest/introduction.html#introduction) [actor 模型](https://en.wikipedia.org/wiki/Actor_model)，根据它的文档，这意味着流处理器可以在许多 CPU 内核上并发执行，并且可以同时在数百台机器上执行。

它要求 Python 3.6 或更高版本在同一进程中运行多个流处理器，以及 web 服务器和其他网络服务。它也不需要使用资源管理器，如 Yarn 或 Mesos。

该公司使用 Faust 来实时传输 Robinhood 应用程序上的所有事件，如数据分析、风险、欺诈和安全。它充当 Robinhood 提要的后端，robin hood 提要是一个聊天工具，用于监控执行质量。

“这对于编写后端服务很有用，尤其是对于那些拥有 iOS 应用、Android 应用，或许还有 web 应用的公司。他们需要一个进行数据分析的后端，并且可以通过一个解决方案完成所有这些工作，”Solem 说。

Jay Kreps 是 Kafka 的联合创始人之一，他在推特上发布了关于这个项目的消息:

Django 的联合创始人西蒙·威廉森是另一位:

在上周二宣布后，它成为 GitHub 上最热门的 Python 项目之一，已经收到了超过 1500 颗星，超过 50 个分叉，以及来自 Robinhood 以外的贡献者的三个拉请求。浮士德在发布当天在黑客新闻上排名第三。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>