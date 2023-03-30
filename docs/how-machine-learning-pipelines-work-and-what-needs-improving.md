# 机器学习管道如何工作以及需要改进的地方

> 原文：<https://thenewstack.io/how-machine-learning-pipelines-work-and-what-needs-improving/>

编者按:本文是

[a series](https://thenewstack.io/build-and-deploy-a-machine-learning-model-with-azure-ml-service/)

将持续集成和部署(CI/CD)实践引入机器学习。查看新的堆栈，了解未来的部分。

无论是开发机器学习系统还是在生产中运行模型，都有越来越多的数据处理工作流。管道从摄取和清理数据，通过交互式工作台环境中的特征工程和模型选择，到训练和实验(通常带有共享结果的选项)，到部署训练好的模型，再到提供预测和分类等结果。

机器学习开发和部署管道通常是分开的，但除非模型是静态的，否则它需要根据新数据进行重新培训，或者随着世界的变化进行更新，并在生产中进行更新和版本控制，这意味着一次又一次地经历管道的几个步骤。

管理这些管道的复杂性[变得越来越困难](https://blog.algorithmia.com/machine-learning-engineers-and-data-scientists-biggest-challenge-deploying-models-at-scale/)，尤其是当你试图使用实时数据并频繁更新模型时。机器学习有几十种不同的工具、库和框架，每个数据科学家都有自己喜欢使用的特定工具集，它们都以不同的方式与数据存储和机器学习模型运行的平台集成。

当你问数据科学和机器学习团队他们最常用的工具是什么时，他们会提到 Hadoop、Spark、Spark Streaming、Kafka、云服务、R、SAS 和一系列 Python 工具，尽管它们出现在管道的不同阶段。还有像 Google Cloud DataFlow 和 Azure Stream analytics 这样的云服务，它们覆盖了典型管道的多个阶段。

捕获数据需要一个持久的、可扩展的、高吞吐量的数据摄取系统，如 Apache Kafka 或云服务，如 Azure Event Hubs 和 AWS Kinesis，该系统接受来自各种来源的数据并将其分发到正确的位置。

下一步是处理原始数据的数据转换层；过滤、聚集、扩充或合并它，然后将其转移到永久数据存储。O'Reilly 在 2018 年[对用于分析和人工智能](https://www.oreilly.com/data/free/evolving-data-infrastructure.csp)的工具和技术的调查显示，Apache Spark 在进行数据转换方面很受欢迎，但它仍然需要一个数据存储，无论是 Hadoop 分布式文件系统(HDFS)和 HBase，Apache Cassandra，像亚马逊 S3 和 Azure Blob Storage 这样的云存储还是其他数据库存储。

在数据库中就地处理机器学习的数据是可能的；像 SQL Server 和 SQL Azure 这样的数据库正在添加特定的机器学习功能来支持这一点。更常见的是流式处理数据的子集；Spark 内置了 Spark Streaming，可以从 HDFS、卡夫卡和其他来源读取数据，但也有 Apache Storm 和 Apache Heron 等替代产品。不管还有什么在进行中，对数据的初步探索通常是在交互式 Jupyter 笔记本或 R Studio 中完成的。

对于许多人来说，大型云提供商已经成为主要的数据科学平台，微软的高级产品营销经理 Nishant Thacker 告诉 New StackAzure ML 服务、AWS SageMaker 和 GCP 云 ML 引擎，以及 SAS、RapidMiner 和 Knime。(如果你不熟悉最后两个，它们在 [Gartner 的数据科学和机器学习平台魔力象限](https://www.kdnuggets.com/2018/02/gartner-2018-mq-data-science-machine-learning-changes.html)中一直显示为领导者。)

“更新的云平台提供了一个开放的生态系统和多种框架选择，如 Spark、PyTorch、TensorFlow、Scikit-Learn 等。萨克说:“像 SAS 这样的传统平台周围有一个成熟但有粘性的生态系统。

## 数据湖和流

Spark 受欢迎的一个原因是它包含了多少，比如内置的 MLib 机器学习库。这很方便，也很容易上手，因为它包括常见的学习算法和实用程序，并在 Spark 核心上运行，但它并不总是足够强大，足以满足所有需求——尤其是当你从更传统的机器学习算法转向深度学习时。有很多替代品，比如 H20 平台，它有内存中的机器学习算法，包括可以从 Python 和 R 调用的深度学习(可以通过 Sparkling Water 与 [Spark 集成)，以及过多的机器学习工具和库。](https://www.h2o.ai/products/h2o-sparkling-water/)

“我们确实看到 Spark 非常普遍，”Streamlio 营销副总裁 Jon Bock 告诉《新堆栈》，“但也有越来越多的多样性。这并不是说他们不再使用 Spark，而是人们正在利用越来越多的工具。”

部分原因是 Python 在数据科学方面越来越受欢迎，这需要一套不同的工具，但博克表示，还有一个更大的趋势是更实时地处理数据的系统，无论是处理物联网数据，理解潜在买家在他们仍在考虑选择你的产品或服务时的行为，还是在他们与客户交谈时向客户支持人员提供见解。

“我们看到分析处理的某些方面正被推向流媒体系统；因此，Spark 仍然经常被用于培训和探索，因为人们正在开发他们的模型，但当他们想要执行这些模型时，我们看到人们的目光超越了 Spark，我们还没有看到 Spark 流(为此)的广泛采用。”Streamlio 的平台基于 Heron、Apache Pulsar 发布-订阅消息系统和 Apache BookKeeper 中的持久消息存储。

“从事更高级机器学习的人不仅仅是获取一批历史数据，并试图建立只看这些数据的模型；他们正在建立模型，可以在数据到达时查看数据，这需要更复杂的管道，”博克说。

“我们经历了一个五到十年的阶段，在这个阶段，数据湖被认为是数据管道的基石，所以你的工作是尽快将数据放入数据湖，然后想出如何处理它，但我们最终在数据工程中创造了这个巨大的瓶颈，最终让数据科学家们抓狂。Bock 说:“我们现在看到的是从数据湖向更大的转变，如果我们现在开始在数据到达时对其进行处理，而不是先将其倾倒在某个地方，然后再回来清理它，会怎么样呢？”

## 规模问题

甚至在 2019 年，大多数数据科学家都在他们的笔记本电脑上工作，并受到他们硬件的限制，” [Anaconda](https://www.anaconda.com/) 的产品营销总监 [Thaise Skogstad](https://www.linkedin.com/in/thaise-s-b03a8025/) 指出对于不适合其笔记本电脑的数据集，他们仍在使用传统的数据湖，并在十年前开创性的 Spark 或 Hadoop 上以巨大的成本运行作业。然而，大多数公司现在都在寻找一条通向现代的、潜在的基于云的解决方案的道路。"

微软 Azure Containers 团队的 Lachlan Evenson 指出，深度学习的流行，你更有可能使用 TensorFlow 或 CNTK 等框架，而不是 Spark 工作负载，这使得瓶颈变得更严重，特别是对于图像识别或生物化学问题等大型模型。“今天，他们有专门提供的带 GPU 的硬件，放在桌子下面，无法扩展到其他地方。”

“对于遗留系统，扩展、框架的灵活性、工具的选择、利用更新的基础设施(GPU、FPGAs)和部署的容易性都是挑战，”Thacker 同意。“对于云平台来说，将所有这些整合到一个易于使用的外形规格中，并提供高级功能，如超参数扫描、开发运维功能、部署灵活性等，同时又不使数据科学家离开他们的核心工作，这是一个巨大的挑战。”

到目前为止，IaaS 的可用性(越来越多地使用 GPU 和其他加速器)一直是扩展机器学习的关键，但现在正转向云原生技术，如容器化和微服务，以实现规模和关注点分离。

“对于训练和推理机器学习模型，你需要非常大的计算量。Kubernetes 提供了一种非常简单的方法来管理和扩展 ML 模型的计算。“Kubernetes 的可预测性、可靠性和可负担性使其成为一个显而易见的工具，尤其是在推理需求方面，这种需求是不可预测的，并且需要自动扩展。与虚拟机集群或物理计算集群相比，Kubernetes 易于设置，可灵活扩展，并提供更多控制。”

“Kubernetes 重要的另一个原因是，机器学习模型通常在具有某些其他程序集和库或框架的环境中执行。为了使这个执行更简单，我们为模型和它的依赖项创建一个“容器”来一起执行。容器是 Kubernetes 所固有的，可以非常容易地在 Kubernetes 集群上执行，从而提供了两个世界的最佳之处。”

Bock 说，Kubernetes 的基础设施管理显然适合机器学习的操作阶段，Kubernetes 的灵活性和可扩展性也在管道的早期变得有用。“Kubernetes 是 Streamlio 的一个非常常见的部署环境，因为人们希望能够以更快的速度提升接收数据的能力，他们希望能够以更快的速度处理数据，他们希望能够提升保留数据流以供以后重放和培训的能力，然后再恢复。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>