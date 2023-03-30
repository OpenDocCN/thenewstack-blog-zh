# Apache Ignite 机器学习:大规模计算

> 原文：<https://thenewstack.io/apache-ignite-machine-learning-computing-in-place-at-scale/>

[Apache Ignite](https://ignite.apache.org/) 提供了高效训练机器学习模型的能力，因为它能够消除提取、转换和加载(ETL)并最大限度地减少可扩展性问题。

据 [GridGain](https://www.gridgain.com/) 的产品管理副总裁 [Denis Magda](https://www.linkedin.com/in/dmagda) 和 Ignite 项目管理委员会主席在最近于拉斯维加斯举行的 [ApacheCon 北美](https://www.apachecon.com/acna19/)会议上的发言，Ignite 消除了一些常见的基本痛点:即必须将数据移动到单独的系统(提取、转换、加载或 ETL)以及太大而无法在一台机器上运行的数据集。

该项目为最常见的用例创建了算法— [线性回归](https://apacheignite.readme.io/v2.5/docs/ols-multiple-linear-regression)、[决策树分类](https://apacheignite.readme.io/v2.5/docs/decision-trees)、[最近邻](https://apacheignite.readme.io/docs/knn-classification)、 [K-Means](https://apacheignite.readme.io/docs/k-means-clustering) —专门设计为在其分布式系统上运行。

### 速度和规模

GridGain 在 2014 年末开源了这项技术；同年，它被 Apache 孵化器项目接受。GridGain 提供了开源技术的商业产品。

Magda 解释说，Ignite 是作为一个内存计算平台出现的，它将数据存储在高速缓存中，然后为事务提供 API，以实现高度可扩展的分布式系统。许多供应商现在都在提供这种服务。

实际上，Ignite 是一个混合事务/分析处理( [HTAP](http://www.enterpriseappstoday.com/data-management/how-htap-database-technology-can-help-you.html) )数据库，宣称它提供了 Pb 级的内存速度。它支持事务和分析以及流数据。因为它在以主机内存为中心的分布式数据库上运行代码，所以它可以训练、部署和更新机器学习模型，而不必将数据转移到另一个系统，例如像 [Apache Mahout](https://mahout.apache.org/) 或 [Apache Spark](https://spark.apache.org/) 。

例如，Spark 必须从其他数据源获取数据。

“对于开发人员来说，分布式系统的主要瓶颈之一是网络。如果你能消除在网络上移动数据，你就能获得巨大的性能优势，”他说。

较小的数据集可以单独存储在内存中，而过大的数据集可以存储在磁盘上，使用内存作为缓存层。“即使所有东西都适合内存，这样做也可能负担不起。玛格达说:“把所有东西都存在内存里可能不太合理。

“作为开发人员，您不必知道所有数据是如何分布的，RAM 中有多少数据。如果 Ignite 看到 RAM 里少了什么东西，就会去磁盘拉。”

然后可以存储该模型，Ignite 支持一个更新接口，允许在新数据进入时重新训练该模型，从而提供近乎实时的更新。

它完全支持 SQL，使其与其他大数据工具兼容。

### 分割

数据分区是 Ignite 的基础。数据存储在键值记录中。

要添加记录，您需要分配一个主键，然后它会分配一个分区。每个缓存被分成多个分区，每个分区属于一个特定的集群节点。

Ignite 不使用主节点和从节点。所有节点都是平等的。

当您添加一个节点时，该分区可能会被重新分配到一个不同的节点。玛格达说，作为应用程序开发人员，所有这些都在后台进行。

您可以运行 SQL 和其他操作，Ignite 会将所有查询定向到正确的节点。

Ignite 提供了内置的容错功能。它在不同的节点上分配额外的数据副本以实现冗余。它还将训练上下文与数据一起存储在节点上，因此在失败的情况下，您可以从停止的地方重新开始训练。

他说，在你的笔记本电脑上，你可能认为你在一个节点上，但它可能是成千上万个。

机器学习模型嵌入在存储中，所以当你开始训练时，它知道数据是如何分布的。计算发生在服务器节点上，数据移动最少。

GridGain 的技术布道者[阿克毛·b·乔德里](https://www.gridgain.com/resources/videos/machine-and-deep-learning-apache-ignite)称其处理能力为“MapReduce light”，其内存文件系统[类似于 HDFS。](https://ignite.apache.org/features/igfs.html)

Ignite 是用 Java 写的，支持。NET、C++和 Scala，R 和 Python 也在开发中。机器学习算法是专门为利用集群计算而设计的。

玛格达说，该项目有意退出深度学习，选择为最常见的用例提供算法，如欺诈检测、预测和建议。

对于深度学习，它专注于与 [TensorFlow](https://medium.com/tensorflow/tensorflow-on-apache-ignite-99f1fc60efeb) 的集成。根据[文档](https://apacheignite.readme.io/docs/tensor-flow)，在 combo 中，两者提供了“处理运营和历史数据、执行数据分析以及基于神经网络构建复杂数学模型所需的完整工具集”。

该集成称为 Ignite Dataset，使其能够成为 Tensorflow 的数据源，用于神经网络训练、推理和其他计算。它可以为 Tensorflow 提供对 Ignite 分布式数据库的快速访问，通过提供来自任何结构的对象来消除预处理。Ignite 还支持 SSL、Windows 和分布式培训。

Magda 说，该项目还将包括从 Spark 和 XGBoost 导入模型的能力，以及用于机器学习功能的完整 [Python API](https://github.com/gridgain/ml-python-api) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>