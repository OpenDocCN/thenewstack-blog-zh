# 使用 Apache Beam 实现面向未来的大数据处理

> 原文：<https://thenewstack.io/apache-beam-will-make-big-difference-organization/>

[](http://www.jesse-anderson.com/aboutme/)

 [杰西·安德森

杰西·安德森(Jesse Anderson)是一名数据工程师、创意工程师和吸烟手的 CEO。他在从初创公司到财富 100 强公司的各种公司进行大数据培训。这包括 Apache Kafka、Apache Hadoop 和 Apache Spark 等前沿技术的培训。](http://www.jesse-anderson.com/aboutme/) [](http://www.jesse-anderson.com/aboutme/)

我在 [Strata SJC 2016](http://conferences.oreilly.com/strata/hadoop-big-data-ca) 坐在那里吃午饭，和两个工程师聊天。他们谈论着如何兴奋地回去工作，重新编写他们的系统以使用他们刚刚学到的新框架。我心中的工程师认为“太棒了！”我的商业头脑认为“我希望他们先经过经理的同意。这是一个巨大的时间陷阱，很可能是浪费时间。”

我很怀疑他们没有先征求经理的意见。他们可能花了几天时间编写和调试对企业底线没有帮助的代码。

你可能会坐下来想“我们的工程师比那更有纪律性。我们永远不必为新平台重写代码。”如果你的组织从 MapReduce 转向 Spark，那么，是的，你的团队为一个新的平台重写了代码。他们本不应该这么做。

## 停止重写

您团队的代码是直接使用 MapReduce API 编写的。他们使用 Spark 的重写是直接写在 Spark 的 API 上的。下一次有新的平台，会有另一个直接的 API 重写等等。

我们如何停止为一个新平台重写代码？我们开始使用中间 API，不再直接编写 API。

这就是阿帕奇光束的用武之地。您只需编写它的 API，然后选择一种技术来运行代码。编写代码和执行代码的实际方法是分离的。

Beam 会把上面的午餐对话改成“我了解了这项新技术。我将进行配置更改，看看我们的作业是否运行得更快。”您不再需要通过重写来从一种技术转换到另一种技术。

## 下艰难的赌注

技术领导者面临着一个艰难的决定，那就是对快速变化的技术进行长期投资。我们已经看到了从 Hadoop MapReduce 到 Spark 的转变。并不是那些选择 Hadoop MapReduce 的人犯了一个战略错误。后来出现了更好的批处理引擎，他们被迫重写。

现在，领导人面临另一个难题。我应该使用哪个批处理或流处理引擎？你应该使用 Spark、Flink、Storm 还是其他新兴技术？这就是 Beam 变得更加有趣的地方。它对批处理和流(实时)处理使用相同的 API。

这些技术中的哪一项是下一个大事件？哪一个会赢得社区，被普遍接受，并继续存在下去？我不能告诉你，但我现在不必告诉你。随着这些新技术的出现，您需要进行配置更改，并迁移到新的框架。

## 一个 API 来管理它们

简单性为企业节省了时间和金钱。想想你的工程师需要用多少 API 来编写数据处理作业。他们需要了解 Hadoop MapReduce API、Spark API、Flink API 和任何其他 API。有了单波束 API，你的工程师只需要知道一个 API。这个 API 可以处理 MBs 的小数据处理，一直到 TB 和 PBs 的大数据处理。

工程师只需要知道 Hadoop MapReduce 或 Spark 这样的框架在概念上是如何工作的。他们需要了解每个系统之间的一般权衡。然而，每一个的编码都是一样的。这将导致生产率的大幅提高。

## 未来

我不知道大数据未来会发生什么。对于流式框架来说尤其如此。我们过去必须预测接下来会发生什么，以防止下一次重写。Beam 使我们能够面向未来，而不必担心下一件大事。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>