# 学习排序:机器学习搜索的关键信息检索工具

> 原文：<https://thenewstack.io/letor-machine-learning-web-search-technique-thats-turned-key-information-retrieval-tool/>

排名不仅适用于搜索引擎，甚至企业搜索，尽管 Airbnb、Etsy、Expedia、LinkedIn、Salesforce 和 Trulia 等服务经常使用它来改善搜索结果。

Learning To Rank (LETOR 或 LTR)机器学习算法——首先由雅虎开创，然后由[微软研究院](https://www.microsoft.com/en-us/research/project/letor-learning-rank-information-retrieval/)为必应开发——被证明对诸如[机器翻译和数字图像取证](http://www.sciencedirect.com/science/article/pii/S0925231216301060?via%3Dihub)、计算生物学和[遗传学中的选择性育种](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0128570)等工作很有用——你需要的任何东西都是一个已排序的项目列表。排名也正迅速成为数字作品的基石。

除了文档检索，LTR 还可用于专家搜索、定义搜索、协作过滤、问题回答、关键短语提取、文档摘要、专家查找、反网络垃圾邮件、情感分析和产品评级。LTR 方法既适用于图像，也适用于文本(Etsy 使用图像和文本搜索的组合来区分仅基于文本描述就会获得非常相似排名的产品，LTR 可以[区分质量较高和较低的图像](http://ieeexplore.ieee.org/document/7014257/))，或者用于对图中的节点进行排名。无论您是在寻找 Python 库还是像 Apache Solr/Lucene 这样的全面企业搜索平台，开发人员都可以越来越多地使用它们。( [Lucene LinkedIn 的旧搜索框架](https://www.slideshare.net/lucenerevolution/how-lucene-powers-the-linkedin-segmentation-and-targeting-platform-28381245)；它不再在那里使用，而是开源的，被像 Pandora，Soundcloud 和 Wikipedia 这样的网站使用。 [Solr](http://lucene.apache.org/solr/) 是建立在 [Lucene](https://lucene.apache.org/) 之上的开源企业搜索平台。)

Airbnb 工程经理[Ganesh Venkataraman](https://www.linkedin.com/in/npcomplete/)(LinkedIn 前相关主管)告诉新堆栈:“LTR 几乎适用于任何你可以找到无偏见训练数据的领域。“它特别适合有大量难以手动调整的功能的情况。”

“LinkedIn 在几乎所有的垂直搜索领域都使用 LTR 人员搜索、工作搜索、招聘人员搜索等等。文卡塔拉曼说:“我们已经证明，这种方法非常有效，性能大幅提升，并且已经看到了它的规模。对于像求职这样的工作，这种技术与另一种算法——查询理解(QU)有着非常密切的联系，它根据查询来预测用户的意图。例如，如果工作搜索查询是“谷歌软件工程师”，LinkedIn 将理解该成员最有可能在“谷歌”公司寻找标题为“软件工程师”的工作。

使用 LTR 将搜索查询与微软 Bing 上的相关广告进行匹配，在头两个月内将在线广告收入提高了 400 万美元。用它来对 LinkedIn 上的招聘广告进行排名不仅让更多的人点击查看搜索结果；搜索是为了找到人们正在寻找的工作，因为申请率在前三周上升了 5%(到项目结束时上升了 50%)。当彭博为 Solr 开发了一个 [LTR 插件时，它不仅比他们之前使用的手工制作的排名系统快了三分之一，而且结果更加相关，点击量立即上升了约 10%。](https://lucene.apache.org/solr/guide/7_0/learning-to-rank.html)

## LTR 如何工作

[学习排序](https://www.jstage.jst.go.jp/article/transinf/E94.D/10/E94.D_10_1854/_pdf/-char/ja)使用监督机器学习来训练模型，不是为了通常的单个项目分类或预测，而是为了发现一系列项目的最佳顺序，使用从每个项目中提取的特征来给它排序。它不是看每个项目的精确分数，而是相对顺序——一个项目是高于还是低于另一个项目。

对于 web 结果，特征可能包括域或 PageRank、页面标题是否与查询匹配、页面的年龄或受欢迎程度、它是否有标准的文档部分，如简介或摘要、它有多长以及人们花多长时间阅读它，或者甚至它是否会在手机屏幕上呈现或者只是在桌面浏览器上呈现。为了提高排序效率，需要自动提取特征；它们应该是你可以编写脚本的东西，而不是你必须手工编码的东西。

三种主要的 LTR 技术是逐点、成对和列表。逐点 LTR 使用回归或分类来发现各个结果的最佳排名。你可以把分类想象成把相似的文档放在同一个类里，回归想象成给相似的文档一个相似的函数值，所以排名给相似的文档分配相似的偏好。

成对 LTR 使用分类或回归来一次发现一对项目的最佳顺序，将列表中项目的所有不同配对分类为正确或不正确的排序，并通过它们来获得整个组的排序。有多种方法对成本函数和学习算法使用不同的技术，包括神经网络、随机森林、boosting 和支持向量机(SVM)。

早期的成对方法，如 [RankNet](http://research.microsoft.com/pubs/132652/MSR-TR-2010-82.pdf) 使用成本函数和[随机梯度下降](http://ufldl.stanford.edu/tutorial/supervised/OptimizationStochasticGradientDescent/)来训练神经网络，成本函数是关于最小化较低评级的项目排名高于较高评级的项目的次数。 [LambdaRank](https://www.quora.com/What-is-the-intuitive-explanation-of-Learning-to-Rank-and-algorithms-like-RankNet-LambdaRank-and-LambdaMART-In-what-types-of-data-variables-can-these-techniques-be-used-What-are-their-strengths-and-limitations) 使用该成本的梯度(一个项目是否应该因为其排名而向上或向下移动，以及移动多少)获得更快、更准确的结果，而 [LambdaMART](https://staff.fnwi.uva.nl/e.kanoulas/wp-content/uploads/Lecture-8-1-LambdaMart-Demystified.pdf) 使用梯度增强决策树对此进行了改进。

像 ListNet 这样的列表式 LTR 方法对整个列表进行排序，而不是使用概率模型对成本进行配对。对于图像，使用图像列表的子集[可以更好地工作](http://adsabs.harvard.edu/abs/2015arXiv151108951F)，并且组合所有三个成本函数也可以提高排序性能。

第一个使用 LTR 的搜索引擎是 AltaVista(已被雅虎收购)，LTR 的关键工作是在 2008 年至 2011 年期间完成的，雅虎和微软发布了训练数据集并举行比赛，那个时代的技术是常用的技术，但仍有大量正在进行的研究。文卡塔拉曼称“深度学习和 IR(信息检索)的交集”尤为重要；他说，最近，“单词嵌入(将查询标记转换到更高维的空间)以及神经网络得到了相当多的关注。”

也有对 LTR 的半监督版本的研究。监督学习依赖于来自人类专家的良好标记的训练数据(就像谷歌用来获得其搜索算法变化测试分数的人类法官)，这提供了高质量的数据——但它很昂贵，并且只覆盖了你想要排名的一小部分。分析搜索日志和点击率更便宜，而且适用范围更广，但这种隐含数据往往存在偏差(最靠前的结果会获得更多点击，但可能不是最佳匹配，如果没有结果被点击，你就得不到有用的信息)。

## **LTR 工具**

提交给雅虎、微软和 Yandex [举办的 LTR 挑战赛的几个 LTR 工具可以作为开源](https://sites.google.com/site/rtranking/)获得，而 [Dlib C++机器学习库](http://dlib.net/ml.html)包括一个用于训练 SVM 排名[的工具](http://dlib.net/dlib/svm/svm_rank_trainer_abstract.h.html#svm_rank_trainer)。pyltr 库是一个 Python LTR 工具包，带有排名模型、评估指标和一些方便的数据工具。

对于大多数开发者来说，搜索工具和服务中的 LTR 工具会更有用。LinkedIn 开源示例代码，用于在使用 LTR 的 [Elasticsearch 上构建端到端‘即时’搜索系统。用于构建定制搜索引擎的](https://github.com/linkedin/instantsearch-tutorial) [Azure 搜索服务](https://azure.microsoft.com/en-us/services/search/)内置了相关性排名的 LTR 功能；安永为美国税法创建定制搜索引擎[的定制代码](https://www.microsoft.com/developerblog/2017/08/07/developing-a-custom-search-engine-for-an-expert-system/)[以 Python 脚本和 Jupyter 笔记本](https://github.com/CatalystCode/CustomSearch)的形式发布。这是一个结合 LTR 和自然语言处理(在这种情况下使用微软的 LUIS Language Understanding Service API)来提取文档排名特征的好例子。

彭博的 LTR 插件现在内置在 Solr 中；它扩展了平台中现有的 RankQuery，并使用您的排名模型(作为 Solr 管理的资源部署)和特性信息对大量文档进行重新排名(因此可以在 Solr 中使用简短的脚本和丰富的搜索选项(如同义词和短语匹配)来构建特性)。这使得复杂的结果排名在一个流行的搜索平台上变得相对简单。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>