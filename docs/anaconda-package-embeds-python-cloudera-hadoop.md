# 新的 Anaconda 包在 Cloudera Hadoop 上嵌入了 Python

> 原文：<https://thenewstack.io/anaconda-package-embeds-python-cloudera-hadoop/>

总部位于德克萨斯州奥斯汀的 Continuum Analytics 是专注于数据分析的 Anaconda Python 发行版的幕后公司，该公司已进一步扩展到大数据领域。

该公司发布了用于 Cloudera 的 Anaconda 包，使用户能够在 Cloudera 集群上轻松构建和运行基于 Python 的应用程序，并与 Spark jobs 一起运行。

Cloudera 用户以前必须在 Hadoop 集群上手动安装完整的 Python 数据科学堆栈，并自己管理运行时依赖关系。现在通过 Cloudera Manager 安装了 Anaconda 包，用户不必一个节点一个节点地安装 Python。

Spark 也将从该方案中受益。据该公司称，大约一半的 Spark 用户也在使用 Python。

“Spark 清楚地证明了 Python 是现代开放数据科学中最重要的技术之一，”Continuum 首席技术官兼联合创始人王蒙杰在声明中写道。

“我们对 Hadoop 中的底层技术进步感到兴奋，例如 [Parquet](https://parquet.apache.org/) 【柱状数据存储】，以及 Cloudera 在 [Impala](https://www.cloudera.com/products/apache-hadoop/impala.html) 和 [Kudu](http://getkudu.io/) 上的开创性进步。这些进步为我们的下一代 Hadoop 创新奠定了基础，这些创新将 Python 从 Hadoop 上的数据科学接口扩展到了一个成熟的 Hadoop 本地分析计算平台。”

Python 在二月份的流行编程语言 Tiobe 指数中排名第五。

“人们会说，‘我无法从 Python 中获得我需要的性能’，尽管它非常简单，非常容易实现，”CMO 和 Continuum Analytics 产品副总裁 Michele Chambers 说。她认为 Python 提供了与 C 和 C++几乎相同的性能。Anaconda 还可以扩展到在多核和 GPU 上运行，并支持完全扩展到集群。

“在企业中，数据科学确实是一项团队运动。数据科学家、业务分析师、统计学家、数据工程师、数据运营和开发人员都必须协同工作。他们必须仔细协调，非常流畅地一起工作。然而，他们今天可用的工具真的不允许他们这样做，”钱伯斯说。

她说:“你希望将他们聚集在一起，充分利用他们的所有数据、所有开源分析工具和现代计算基础设施——Hadoop、Spark、GPUs 你希望在一个互联的生态系统中做到这一点。”“事实是，大多数企业的数据都在这些传统环境中，所以您希望为他们搭建一座桥梁。开放数据科学不仅仅是给他们开出一种方法，而是将他们与他们的数据联系起来，这样他们就可以快速获得见解，非常有影响力、高价值的见解。”

她说，Anaconda 的一个优势是它可以引入传统代码——C、C++、Java、Fortran 或其他——并在现代应用程序中赋予它新的生命。

## **性能提升**

本月早些时候，Continuum 发布了 Anaconda 2.5，其中包括英特尔数学内核库(英特尔 MKL)。与[微软 R Open](https://mran.revolutionanalytics.com/open/) 捆绑的 R-Essentials 包将于 2 月 25 日推出。该公司表示，这两个软件包的结合为数学密集型分析提供了高达 7 倍的性能提升。

它还增加了 Anaconda Enterprise Notebooks，在治理环境中提供了 [Jupyter](http://jupyter.org/) (以前称为 IPython)笔记本的好处。笔记本将代码、注释和可视化都封装在一个地方。该公司增加了协作锁定、版本控制等企业功能。该平台包括 AnacondaXL，它提供对流行 Python 包的访问，如用于机器学习的 [scikit-learn](http://scikit-learn.org/stable/) 和 [Pandas](http://pandas.pydata.org/) ，以实现预测分析和数据转换，并与 Microsoft Excel 集成。

例如，开源政策中心(Open Source Policy Center)正在重写专有模型，以创建一个用 Python 编写的名为 [TaxBrain 的税收模型工具，这将允许记者和政策倡导者等非技术人员更容易地检查，例如，政治家关于税收政策效果的声明。](http://www.ospc.org/taxbrain/)

它拥有理解模型的经济学家和开发模型的数据科学家。钱伯斯解释说，笔记本是他们在模型上合作和分享结果的一种方式。

有了[散景](http://bokeh.pydata.org/en/latest/)(读作“花束”)交互式可视化库，用户有了比通过 Excel 提供的更广泛的可视化选择。

“假设你是一名油气生产工程师，”钱伯斯说。“你一直在用 Excel。你正在做一些非常强大的分析。你可能会关注生产质量控制或生产输出，试图找出如何优化[这些]，但你在 Excel 中的可视化设置非常有限。

“因此，你通常会在 Excel 中进行大量分析，然后将数据转储到某种图形工具中，这样你就可以创建该行业使用的可视化效果。通过四行代码，Bokeh 可以让你做出这些漂亮的可视化效果，让你以你想要的方式创建坐标轴，你可以制作各种图表。他们很富有，因为他们有大量的数据，你可以看到数据的细节和可视化，”钱伯斯说。

她说，它们与上下文相关，因为它们为特定行业的人所熟悉。

## **快速增长**

Continuum Analytics 成立于 2012 年，已经三轮融资 2800 万美元。据报道，客户年增长率为 60%，收入增长了 87%。2015 年，每月下载量达到 25 万次。

该公司去年 9 月在 Strata+Hadoop World 上宣布了 Anaconda for the Enterprise。钱伯斯说，该公司有大约 30 家企业客户。11 月，它补充说，该平台将在 AMD 的加速处理单元上运行。

在另一个有趣的使用案例中，国防高级研究计划局(DARPA)的 Memex 项目使用 Continuum Analytics 的技术来窥视“深层网络”，以[逮捕人口贩子](http://www.scientificamerican.com/article/human-traffickers-caught-on-hidden-internet/)。

*特征图片* [分形视觉 27-蓝色电流](https://www.flickr.com/photos/qthomasbower/2693880867/in/photolist-573QVR-87NDji-8vjrQR-8H6rvU-7SUM47-8CNF5o-8Af9hA-7Pjd9Q-7HP4kd-uwNFpP-uwNEAe-vu135n-85DFsk-83sSqQ-83pJrF-83pGhg-83pFgK-83sHQ9-83sGv7-68f8YA-9Cz3Z2-53QRLH-9tiV6V-9tmM9J-8o5VnB-C3sZf-87RMXA-83sGDs-8qNndW-7V35Fd-68b11n-8Af7FU-8dpeZZ-4YKWfV-87NBVF-9tmLM3-7DuGyE-5QY2kD-eZtq3Z-ax8z4B-8tguyi-8eTKca-89aKhX-899mtK-85GWwE-85DH9p-85DG88-dQBX3y-dQwmeB-dQwmaX)由 [QThomas Bower](https://www.flickr.com/photos/qthomasbower/) ，*在 **CC BY-SA 2.0** 下授权。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>