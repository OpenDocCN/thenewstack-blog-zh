# 预测机器学习项目推动智能发展

> 原文：<https://thenewstack.io/predictionio-machine-learning-project-propels-intelligent-development/>

PredictionIO 是 Apache Software Foundation 的最新项目之一，被提升到了顶级项目的地位，就像许多这样的项目一样，它是在挫折中成长起来的。

“每次我们需要建立一些智能的东西——做新闻推荐或简历分析，产品匹配，诸如此类的事情——我们每次都必须从头开始建立机器学习技术栈，”[预测](https://predictionio.apache.org/)的联合创始人[西蒙·陈](https://twitter.com/simonchannet)，以及[唐纳德·司徒](https://twitter.com/kpszeto?lang=en)、[陈启泰](https://twitter.com/ckhkenneth)和[托马斯·斯通](https://www.linkedin.com/in/thomasrorystone/)说。

“如果你不需要从零开始构建你的数据库，为什么你要从零开始构建你的机器学习服务器呢？…我们的想法是开发一些没有博士学位的开发人员也能使用的东西。”

他说，他们当时受到 MySQL 模型的启发，决定提供一个开源版本。

Salesforce [在 2016 年初收购了](https://techcrunch.com/2016/02/19/salesforce-acquires-predictionio-to-build-up-its-machine-learning-muscle/)他们的公司，并在当年晚些时候向 ASF 捐赠了开源版本。此后，它成为 Salesforce [Einstein](https://thenewstack.io/salesforce-mixes-automated-ai-custom-data-models-einstein/) 的支柱，使客户能够构建自己的人工智能工具。

日本高管工作网站 [BizReach](https://www.linkedin.com/company/bizreach/) ，生命周期管理公司 [LiftIQ](http://www.slb.com/services/production/artificial_lift/advanced_lifting/lift-iq.aspx) ，在线开发人员培训公司 [Pluralsight](https://www.pluralsight.com/) ，机器学习咨询公司 [ActionML](http://actionml.com/) 也在使用它。

[https://www.youtube.com/embed/OhqBECqifhA?feature=oembed](https://www.youtube.com/embed/OhqBECqifhA?feature=oembed)

视频

该项目的最大资产之一是一个名为[模板图库](https://predictionio.apache.org/gallery/template-gallery/)的概念。它允许用户以模板的形式共享他们的项目。现在担任 Salesforce Einstein 产品管理高级主管的 Chan 说，开发类似应用程序的公司可以简单地下载你的模板，照原样运行它，或者修改一些组件。

模板包括推荐、分类、自然语言处理和其他工具。回归模板包括预测能源使用、电力负荷和波士顿房价。

他在[的一篇博客文章](https://www.salesforce.com/blog/2017/10/apache-predictionio-graduates-top-level-project.html)中说，建立一个推荐引擎，一个通常需要一个专家数据科学家团队几个月才能完成的项目，在一两个具有预测能力的工程师的帮助下，可以在几周内完成。

## 不仅仅是算法

Chan 解释说，PredictionIO 最初是建立在 Hadoop 上的，但随着它变得更加成熟，已经切换到了 [Spark](https://spark.apache.org/) 。它使用 HBase 作为数据存储；Spark ML 库[ML lib](https://spark.apache.org/mllib/)；[喷](https://github.com/spray)，Scala 中的 JSON 实现；某些模型中的 HDFS 和存储元数据的 Elasticsearch。

事件服务器从您的应用程序中实时或批量连续收集数据，用于模型训练和评估。事件服务器还可以统一来自多个来源的数据进行分析。

然后，预测引擎使用这些数据通过一种或多种算法构建模型。在它被部署为 web 服务之后，它会侦听来自应用程序的查询，并通过 REST API 实时响应预测的结果。

Chan 表示，虽然 ASF 拥有机器学习库，如 [Mahout](https://en.wikipedia.org/wiki/Apache_Mahout) 和 [MLlib](https://spark.apache.org/mllib/) ，但机器学习仍处于早期阶段，需要研究人员、开发人员和公司为其做出贡献，才能取得成功。

“如果你不是真的[了解]机器学习栈，你真的不能只用算法做很多事情，”Chan 说。PredictionIO 需要处理整个流程，包括准备数据、构建算法、培训、管理和评估模型。

IBM 创建的另一个 ASF 项目 SystemML 也是基于 Spark 和 MLlib 构建的。它提供了从小型笔记本电脑到大型集群的[扩展](https://thenewstack.io/systemml-becomes-top-level-project-apache-software-foundation/)数据分析的能力，而无需重写整个代码库。

其他开源的机器学习项目，比如 [TensorFlow](https://www.tensorflow.org/) 、 [Caffe](http://caffe.berkeleyvision.org/) 、 [Vowpal Wabbit](https://github.com/JohnLangford/vowpal_wabbit/wiki) 、 [scikit-learn](http://scikit-learn.org/stable/) ，都是 ML 库。

Chan 说，PredictionIO 已经扩展到支持任何 JDBC (Java 数据库连接)数据存储和多种其他算法。

作为顶级地位的结果，他看到了更多与 ASF 项目的项目间合作，如 Spark 和 [Beam](https://beam.apache.org/) 。

“可用性仍然是机器学习中的一个大问题。我们需要使开发过程更加简单，这将需要开源社区的大量资源，”他说。

Chan 说，看到公司如何使用开源和内部 Salesforce 实现 PredictionIO 令人鼓舞。

例如，在最近的 Dreamforce '17 会议上，来自苏格兰阿尔斯特银行的员工[谈论了](https://success.salesforce.com/sessions?eventId=a1Q3A00000stRRuUAM#/session/a2q3A000001yt0dQAA)它如何使用 PredictionIO 和 Einstein 来预测[下一个最佳报价](https://www.irishtimes.com/business/financial-services/ulster-bank-turns-to-ai-to-understand-customers-better-1.3260966)——使用过去的客户行为来了解下一步应该建议哪些银行服务。

阿根廷的巴勒莫大学已经使用 PredictionIO 来预测特定课程的辍学率。

特征图:树皮的 [40+37 魔 8 球](https://www.flickr.com/photos/barkbud/4165385634/in/photolist-7m5G2G-3L2cDX-9bk8tQ-beyUee-34Ydj3-5kHT4P-f9o9TQ-5X4jXi-ck983w-6Ano5Y-ck98oC-2ubWp-4EoDaX-4KcNEB-ck97RL-bZQnHs-vtdAr-kHLeh-ck98wA-UXYS44-dzzqP7-CcacD-eL1dNo-5EhVBP-7ss3CH-fTNgVn-4GqdtE-)，CC BY-SA 2.0 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>