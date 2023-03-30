# Wallaroo 实验室承诺提供易于扩展的大数据处理基础设施

> 原文：<https://thenewstack.io/wallaroo-labs-marries-best-serverless-big-data/>

Wallaroo Labs 希望让大数据处理变得更容易。像 [Pepperdata](https://thenewstack.io/peppercorn-spark-kubernetes-ticket-off-big-data-island/) 一样，它希望[消除传统 it 堆栈和大数据技术之间的鸿沟](https://thenewstack.io/peppercorn-spark-kubernetes-ticket-off-big-data-island/)。

但与 Spark 和 Storm 不同，它想在没有 Java 和 JVM 的情况下做到这一点。

创始人兼首席执行官 [Vid Jain](https://www.linkedin.com/in/vidjain/) 在获得为美林开发交易算法的经验后，于 2014 年创办了这家公司。

“我们发现构建算法是最简单的部分，”他说，在计算中，必须处理大量数据，大规模运行，而不损失交易或打乱顺序。

“我们发现，每次部署算法时，我们都在解决相同的基础设施问题。我们大部分时间都花在了扩展上。”他还看到，算法正成为包括网络安全、广告和约会在内的无数业务的差异化因素。

与此同时，他预见到未来会有更多的数据以更快的速度从更多的来源进入，使数据处理变得更加复杂。“每个人都已经花了太多时间在基础设施上，而不是创新上，我们想解决这个问题，”他说。

## 建在小马上

这家总部位于纽约的公司成立于 2014 年，之前名为 [Sendence](https://techcrunch.com/2017/07/11/sendence-closes-1-5m-seed-seed-round-to-simplify-deployment-of-real-time-applications/) ，去年秋天以其唯一的产品命名，更名为 Wallaroo Labs。贾恩说，更名标志着从咨询公司到产品公司的演变——其员工更愿意穿 Wallaroo T 恤，而不是名为 Sendence 的 t 恤。

它从几个高层次的目标出发:

*   允许开发人员关注他们的业务逻辑，而不是分布式计算“管道”
*   以提供便携式、高性能和低延迟的数据处理。
*   管理应用程序的内存状态。
*   允许应用程序按需扩展，甚至在运行时也是如此。

它决定从头开始，除了构建一种叫做 [Pony](https://www.ponylang.org/discover/#what-is-pony) 的语言，一种面向对象的、 [actor-model](https://en.wikipedia.org/wiki/Actor_model) 高性能开源编程语言，与 c 兼容。

在一篇关于构建自己的 Kafka 客户端(该软件支持两种类型的源和接收器:TCP 和 Kafka)的[博客帖子](https://blog.wallaroolabs.com/2018/01/why-we-wrote-our-kafka-client-in-pony/)中，该公司解释说，Pony 提供了可靠、低开销和数据安全的并发性，尽管由于涉及的开销，它不是与 JVM 一起使用的实用选项。

Wallaroo Labs 平台以 Go API 和 Python API 原生支持 Go 和 Python，并提供自己的处理引擎。

“假设你是一名 Python 开发人员。您将使用 Python API 来实现业务逻辑:这是什么数据？我如何写这些数据？我需要对数据做哪些操作？对其应用一些机器学习。输入一些结果或警告。开发人员可以编写这些作为业务逻辑的代码片段。就这样。他们不必处理任何扩展问题或管道问题或消息传递问题，或者如果某个东西崩溃了如何重启它。所有这些都由我们负责，”贾恩解释道。

该代码在 Wallaroo 实验室引擎中运行，该引擎分布在您需要的任意多台服务器上。

“它可以在你的笔记本电脑上，在 20 台装有 AWS 的机器上，在 5 台本地机器上，在 50 台谷歌云上。它可以在任何需要的地方运行，这对开发者来说是完全透明的，”他说。

“我们希望为未来构建一个框架，结合无服务器和大数据堆栈的优势，”Jain 说。

有了 Amazon Lambda 或功能即服务，就很容易实现，也很容易扩展。您实现业务逻辑；他解释说，你不需要担心它在哪里运行，你可以用 Python、Go 和 JavaScript 等现代语言工作。但是现有的无服务器框架性能不是很高，不能处理具有复杂工作流的复杂应用程序，合并和拆分不同的数据源。如果你使用的是无服务器，你就有云锁定。

与此同时，大数据解决方案更难使用，更难扩展，而且它们大多都是用 Java 编写的。如果你想写一些 Python 或 Golang 代码，它们并不是为此而设计的。但是它们是可移植的，你可以在任何地方运行它们，你可以在任何云中运行它们。

根据 Jain 的说法，Wallaroo 易于扩展，允许您使用 Python 和 Go 等现代语言，甚至比大数据解决方案的性能好得多。它可以在任何地方运行并处理复杂的应用程序。

他说，它消除了用 Python 或 Go 开发然后翻译成 Java 进行生产时所需的性能影响——来回发送数据的整个设置变得复杂且难以扩展。

## 处理状态

[actor 模型方法](https://doc.akka.io/docs/akka/2.5.3/scala/guide/actors-intro.html)封装数据，最小化协调并保持应用程序状态接近计算。

Jain 说，管理有状态应用程序是 Wallaroo 的关键，这是大多数无服务器框架不能很好处理的。

“作为应用程序开发人员，您不必考虑这种状态的弹性或可伸缩性。这是我们的引擎和 API 为您处理的事情之一，”Jain 说。

“StateComputation”是 Wallaroo 应用程序的组成部分之一。更新被写入事件日志，在出现故障时可以重放。一次性消息处理是消除重复的另一种选择。

该公司最接近的竞争对手是 DIY 人群，这是最大的一块，然后是那些追求无服务器和基于 Spark 和 Storm 的 Java 开发人员。Jain 说，拥有大量 Java 投资的公司不是它的目标。

“这是一个完整的统一体。与无服务器相比，有些人有更复杂的工作流或更高的性能需求。有些人有复杂的工作流程或更高性能的需求，但他们希望使用 Golang 或 Python，”他说。Wallaroo 可能是他们的答案。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>