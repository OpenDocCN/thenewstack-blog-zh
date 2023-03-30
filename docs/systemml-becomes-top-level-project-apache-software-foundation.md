# SystemML，即“机器学习的 SQL”，现在是一个顶级的 Apache 项目

> 原文：<https://thenewstack.io/systemml-becomes-top-level-project-apache-software-foundation/>

IBM 创造的机器学习技术 SystemML 已经成为 Apache 软件基金会的顶级项目。

IBM 开发 SystemML 是为了提供从小型笔记本电脑到大型集群的数据分析能力，而不需要重写整个代码库。

它旨在与 [Apache Spark](https://spark.apache.org/) 和机器学习库 [MLlib](http://spark.apache.org/mllib/) 一起使用，这使得编写一个适用于多个行业和平台的代码库成为可能，允许开发人员定制应用程序并将深度智能集成到他们的专业流程中。

> “SystemML 就像机器学习的 SQL。”

[IBM Analytics 开发副总裁罗布·托马斯](https://www.linkedin.com/in/robertdthomas/)在[博客文章](https://www.ibm.com/blogs/think/2015/11/introducing-a-universal-translator-for-big-data-and-machine-learning/)中解释了三者之间的关系:

“可以把 Spark 想象成任何利用海量流数据的应用程序的分析操作系统。MLib …为开发者提供了一套丰富的机器学习算法。SystemML 使开发人员能够翻译这些算法，以便他们能够轻松地消化不同类型的数据，并在不同类型的计算机上运行。”

运行在 Spark 之上，SystemML 自动逐行缩放数据，以确定代码应该在驱动程序上运行还是在 Apache Spark 集群上运行。

[IBM Watson Health VBC](https://www.ibm.com/watson/health/value-based-care/) 服务在一个非常大的电子健康记录数据集上使用 SystemML 和 Spark 来预测高风险患者的急诊就诊情况。IBM 基于价值的护理平台副总裁 Steve Beier 表示，这一想法是为了改善对这些患者的护理，并防止昂贵的急诊室费用。

“SystemML 就像机器学习的 SQL 它使数据科学家能够专注于手头的问题，使用像 R 这样的高级脚本语言工作，所有的优化和重写都由非常强大的 SystemML 优化器处理，该优化器考虑数据和可用资源，为应用程序产生最佳的执行计划， [IBM Spark 技术中心](http://www.spark.tc/)和 Apache SystemML 孵化器导师的架构师 [Luciano Resende](https://www.linkedin.com/in/lresende/) 说。

虽然许多数据科学问题可以在一台机器上解决，但 SystemML 会处理那些不适合在一台机器上解决的问题，该项目发起地加州圣何塞的 [IBM Research Almaden](https://www.research.ibm.com/labs/almaden/) 的工作人员 [Fred Reiss 解释道。](http://researcher.ibm.com/researcher/view.php?person=us-frreiss)

他在项目网站上的一个视频中说，它以其规模运行的能力而与众不同，同时保留了高效处理小数据的能力。

而且因为它使用了 Python 和 R，数据科学家不用学习新的语言就能使用。

SystemML 通过将算法语义从底层数据表示和运行时执行计划中分离出来，简化了 ML 算法的开发和部署。这使得数据科学家能够灵活地创建和定制独立于数据和集群特征的 ML 算法，IBM Research [的一篇论文](http://www.vldb.org/pvldb/vol9/p960-elgohary.pdf)解释了它如何使用压缩线性代数将更大的数据集放入内存。也就是说:

SystemML 的语言表达能力足以涵盖一大类 ML 算法:描述性统计、分类、聚类、回归、矩阵分解、降维以及用于训练和评分的生存模型。通常，可以使用矢量化运算表达的算法非常适合 SystemML。

*“SystemML 基于成本的编译器自动生成混合运行时执行计划，该计划由单节点和分布式操作组成，具体取决于数据和集群特征，如数据大小、数据稀疏性、集群大小、内存配置，同时利用底层数据并行框架的功能，如 MR [MapReduce]或 Spark。”*

Apache 软件基金会为顶级项目提供资金和支持。获得顶级地位包括证明项目有足够的提交者社区来推动项目向前发展，以及提交者的多样性，这样项目就不会被一家公司控制。

2015 年 11 月，SystemML 被 Apache 孵化器接受，同年，IBM it 宣布将在未来几年向 Apache Spark 投资 3 亿美元。

大约在同一时间，谷歌也开源了其 [TensorFlow](http://www.tensorflow.org/) 机器学习软件，脸书向现有的 [Torch](http://torch.ch/) 开源项目捐赠了人工智能和机器学习工具，微软向开源社区发布了其机器学习工具包分布式机器学习工具包。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>