# Apache Spark 1.6:强类型、更快的吞吐量

> 原文：<https://thenewstack.io/spark-1-6-strong-typing-greater-performance/>

据 Spark 赞助公司 Databricks 的联合创始人 Reynold Xin 称，Spark 1.6 的发布继续了数据分析平台向更高性能和可用性的发展。他指出，项目贡献者的数量已超过 1000 人，比去年增加了 50%。

他指出，自动内存管理是新版本简化用户生活的方式之一。

“现在，用户不必调整内存设置，它会为您计算出来。大多数用户不懂调音，”他说。

“过去，Spark 将记忆分成两个不同的区域。一种是缓存，Spark 临时保存用户数据，然后快速扫描。另一个是执行内存区域，用于执行算法，”他解释道。

“如果 Spark 聚合一些数据或将一些数据连接在一起，它需要内存来执行这些操作。这两类内存的大小在过去是静态划分的，”他解释道。“用户不知道如何对此进行调整，让它保持静态通常会导致其中一个利用率不足，而另一个利用率过高，这会减慢速度。因此，我们删除了该设置，您可以让 Spark 找出最佳设置。您可以让 Spark 了解工作负载，并尽可能设定最佳值。”

他说，由于 Spark 的使用比 Hadoop 简单得多，Spark 已经超越了传统 Hadoop 的受众。它的用户越来越多地是数据科学家和数据分析师，这些人不太懂技术。这凸显了进一步简化的必要性。然而，去年夏天进行的一项调查发现，性能是用户最关心的问题。

版本 1.6 包括一个新的 Parquet reader，它是从 Project Tungsten 发展而来的，这是一个重写大量 Spark 执行后端以绕过 JVM 中大量低效问题的努力。Parquet 是 Spark 中最常用的数据格式之一。在查看客户如何使用 Spark 的过程中，他们发现许多人将大部分时间花在格式规范库 parquet-mr 中一个称为记录组装的步骤上。

“record assembly 所做的是将一组原始字节转换成行。因此，我们使用一种称为矢量化读取的技术重写了整个记录集合，这种技术利用了许多更现代的 CPU 功能。例如，现在我们可以使用“发送到”指令在一条 CPU 指令中完成多个数据处理步骤。事实证明这对它有很大的好处，”辛说。

这个新的读取器绕过了 parquert-mr 的记录集合，并为平面模式使用了更优化的代码路径。该公司在一篇博客文章中解释说，它将 5 列的扫描吞吐量从每秒 290 万行增加到每秒 450 万行，提高了近 50%。

据辛说，这个项目还没有完成。他说，将于 3 月底或 4 月初推出的下一个版本的 Spark 将全面实现矢量化读取，读取拼花的速度可能会提高两到三倍。

它还宣称，通过一个新的 mapWithState API，流状态管理的速度提高了 10 倍，该 API 可以根据更新的数量而不是记录的总数线性扩展。

“Spark streaming 最广泛使用的功能之一是跟踪会话——特定时间段内有多少用户。它在内存中跟踪许多不同的状态，”他解释道。

“过去，它每隔几秒钟就试图了解宇宙的当前状态。它会检查状态管理过程中的每一项。我们实现它是为了使用一种新的算法，这种算法只在每次有更新时遍历一次，而且我们只遍历更新后的值。所以现在我们在跟踪会话增量。这从本质上减少了我们每隔几秒钟就要扫描的数据量，从所有数据减少到只扫描正在更新的数据。”

Spark 1.6 还引入了一个名为 Datasets 的 DataFrames API 扩展来解决编译时类型安全问题。

“当使用 Java 或 Scala 时，它会为您强制执行类型信息。这对于数据科学来说很棒，但是如果你真的想构建非常大的工程管道，编译器强制的类型安全是一个非常重要的特性。因此，我们采纳了[我们的客户]的反馈，构建了一个数据集 API，在数据帧之上增加了类型安全。所以这个想法是你现在可以添加 Datasets API 来获得由 Java 或 Scala 编译器执行的更强的类型保证，”他说。

辛说，新版本还包括许多新的数据科学功能，这些功能在很大程度上是临时的。

“其中比较有意思的是 Spark 用户可以坚持的方式。他们可以保存和回读机器学习管道和模型，作为管道的一部分，”他说。

“Spark 人习惯于训练模型，在那里你有数据，可以建立预测模型，并将模型与一些实时数据集联系起来。在过去，最后一步实际上非常困难。你必须自己建造很多机器来拯救这个模型。然后，您必须将它加载回您的生产应用程序中。

“机器学习的管道持久性功能实际上自动化了这一切，所以现在它只是你建立的管道中的一个保存功能。然后在您的生产应用程序中，只需通过一个 API 调用就可以加载回从这个管道构建的模型。这是构建端到端预测应用的关键一步。它让用户的生活简单多了。"

*专题图片:* [波光粼粼](https://www.flickr.com/photos/127437870@N08/15799034961/in/photolist-q57bEv-99WHhL-6xALnj-e8e2KY-4XC7bu-eib7VU-9RJqWS-A6L182-noKVTy-6yn4mM-8dy3xD-okmTRR-9w6usz-dgiimL-pzZRug-nCHLHR-jNzpa-2ifWY3-8NUE3b-bD562d-dNYKxY-9wn23H-5FpXcJ-2QKAJB-66r954-aDVGgz-9piByi-7ef4FB-7kVfn5-igt2vZ-6sRbeY-s6a1gw-bnKiyx-oSdjMW-7cJKfe-8Ct1ds-5TMY8g-pE1cSd-7cNE5A-bzfq4u-6Czh6X-hgiEsW-chM6ab-7ZyGoS-5WnnbE-CAWmu-iTm77J-mgy1yW-9uqKQe-41ZRN5)*BY*[James j 8246](https://www.flickr.com/photos/127437870@N08/)****CC BY-SA 2.0***。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>