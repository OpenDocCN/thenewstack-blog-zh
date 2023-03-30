# Pachyderm 用容器化的数据湖挑战 Hadoop

> 原文：<https://thenewstack.io/pachyderm-aims-displace-hadoop-container-based-collaborative-data-analysis-platform/>

Pachyderm 公司的人认为，当谈到数据分析，即 Hadoop 的弱点时，房间里有一头大象。因此，他们着手构建一个基于容器的 Hadoop 替代方案，其中一个版本刚刚发布。

[Pachyderm stack](https://medium.com/pachyderm-data/lets-build-a-modern-hadoop-4fc160f8d74f#.v28bvka1b) 使用 Docker 容器以及 CoreOS 和 Kubernetes 进行集群管理。它用厚皮文件系统取代了 HDFS，用厚皮管道取代了 MapReduce。

该公司专注于[的基本原则](http://pachyderm.io/dsbor.html)，包括可再现性、数据来源，以及最重要的协作——据首席执行官兼联合创始人 [Joe Doliner](https://twitter.com/jdoliner) 称，他们认为这是大数据世界严重缺失的一个特征，也是潜在用户最感兴趣的一个特征。

为此，开发人员希望使用 Git 模型来创建一个记录良好的、可重用的分析管道库，这样团队就不再需要从头开始构建所有东西。

“我们认为容器不可避免地会导致 Hadoop 的终结，因为它们会让你彻底反思早期 Hadoop 的所有假设，”联合创始人 Joey Zwicker[说。](https://github.com/JoeyZwicker)

作为一个例子，他指出，在 Hadoop 中，人们用 Java 编写他们的作业，而这些作业都在 JVM 上运行。

“这在当时是一个伟大的假设，因为 Java 是领先的平台，有很多人在上面。但是快进到今天，我们有了容器。它们是更好的工作工具，因为你可以使用世界上任何一种工具。我们已经建立了一个系统，让你可以把任何东西放进一个容器，并将其用于大数据，”他说。

不需要使用特定于 Hadoop 的工具，比如 Hadoop 图像处理库，您可以使用任何现有的图像处理库。您可以使用任何开源计算机视觉工具，如 OpenCV、ccv 或 VXL。

“我们相信人们会希望使用一流的工具。集装箱允许他们这样做，”兹维克说。

他们说，虽然是用 Go 编写的，但数据科学家可以使用任何最适合他们需求的语言或库。

## **最新消息**

Pachyderm 为堆栈开发的两个组件是文件系统和管道系统。

Pachyderm Pipelines 是一个将容器串在一起并使用它们进行数据分析的系统。您可以使用自己选择的工具创建一个容器化的程序，该程序可以读写本地文件系统。它使用 FUSE 卷将数据注入容器，然后自动复制容器，向每个容器显示不同的数据块。根据 Zwicker 的说法，这项技术使 Pachyderm 能够扩展您编写的任何代码，以并行处理大量数据集。它根本不需要使用 Java:如果它适合一个容器，您就可以用它来进行数据分析。

Pachyderm 文件系统是一个分布式文件系统，它从 git 中获得灵感，提供对所有数据的版本控制。它是向容器传递数据的核心数据层。数据存储在通用对象存储中，如亚马逊的 S3、谷歌云存储或开源的 Ceph 文件系统。像苹果的时间机器一样，它提供了不同时间点数据的历史快照。

“它让你看到事情发生了怎样的变化；它让人们一起工作，”Zwicker 说。“它让人们不仅可以在代码上合作，还可以在数据上合作。一个数据科学家可以构建一个数据集，另一个可以派生并构建它，然后将结果与原始结果合并。这是数据科学工具中完全没有的东西。”

有很多技术——Spark、Pig、Hive 和其他——被认为是 Hadoop 中处理层 MapReduce 的替代品。

“我们认为所有这些工具的存在表明 MapReduce 从一开始就是一个错误的想法。这是一种过于严格的分析方式，”兹威克说。

“Hadoop 发现 MapReduce 可以做很多事情，但他们需要在此基础上发明其他东西，如猪和蜂巢等，”Zwicker 说。“Hadoop 有点像我们所做的，它被称为 [Hadoop Streaming](https://hadoop.apache.org/docs/r1.2.1/streaming.html) ，但它是后来添加的非常二等的公民，而不是我们让我们的容器化工作负载成为每个人都使用的核心层。”

Doliner 补充说，Spark、Hive 和其他工具仍然建立在 Hadoop 基础设施的核心部分之上，如 Zookeeper、YARN、HDFS，这些基础设施都是 Hadoop 的弱点。

## **码头工人被‘啊哈’了一瞬间**

Doliner 和 Zwicker 于 2014 年创立了这家总部位于旧金山的公司，并于 2015 年初参与了 Y Combinator。它已经从 Data Collective、Blumberg Capital、Foundation Capital 和其他公司筹集了 200 万美元。

大胆地说出自己要取代 Hadoop 的计划可能会显得野心勃勃——创始人声称，他们拥有唯一一家正在打造全新产品的公司。

“如果你看看[其他人]在构建什么，所有这些仍然是以某种方式重新包装的相同的 Hadoop 原语。我们从一开始就认为，问题不在于 Hadoop 没有以正确的方式打包，而是 Hadoop 有内在的缺陷，”Doliner 说。

公司在 Docker 发布之前就开始了。创始人最初知道他们想建立一个 Hadoop 的替代品，但在他们的前雇主 RethinkDB 看到了 Docker 的早期演示。

“那是‘啊哈’的一刻，”兹威克说。“我们知道 Hadoop 将被取代，而 saw 容器是实现这一目标的完美工具。我们知道他们会创造整个生态系统，我们可以用它来代替。当我们将所有这些放在一起时，事情才真正开始为我们工作。”

Doliner 补充道:“我们不只是说，‘嘿，集装箱是一项热门的新技术。“让我们把所有东西都塞进一个容器里，突然间，这就成了一种新产品。”

他说，由于在容器运动中处于领先地位，这一切都在一起发展。

他们说，Pachyderm 的一个关键优势是，它不需要一个拥有 Hadoop 所需的特定专业知识的大型团队来提高生产率。据首席执行官卡米尔·科萨克说，这对它的客户 Fogger 来说是一个有吸引力的功能。

Fogger 开发了一个软件平台，用于处理太阳能发电场和风力涡轮机等工业机械的传感器数据。它的雾计算平台允许在靠近机器的小型 Linux 机器上处理数据，并通过对等网络将数据推送到中央云中心。它使用 Pachyderm 在通往云的途中进行本地数据处理。

“在 Fogger，我们相信集装箱正在重新定义基础设施，它们将用于所有类型的部署，”科萨克说。

“Pachyderm 拥有设计非常精良的技术体系。我们喜欢用容器和简单的类似 Git 的触发系统构建 map/reduce 管道的想法。

“当我偶然发现 Pachyderm 时，我们正在评估是必须自行构建解决方案，还是使用 Hadoop/Spark 之类的解决方案。我们选择 Pachyderm 是因为 Hadoop/Spark 的学习曲线和基础设施开销明显比 Pachyderm 难；它正好无缝地适合我们的集装箱化堆栈，”他说。

容器允许 Fogger 用任何编程语言构建数据处理算法，“这极大地简化了我们的生活，因为除了 Pachyderm CLI 本身，我们不必学习任何新技术，”Koziak 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>