# Kubernetes 如何编排机器学习管道

> 原文：<https://thenewstack.io/how-kubernetes-could-orchestrate-machine-learning-pipelines/>

本文是中的一篇文章

[a series](https://thenewstack.io/build-and-deploy-a-machine-learning-model-with-azure-ml-service/)

将持续集成和部署(CI/CD)实践引入机器学习。查看新的堆栈，了解未来的部分。

作为一个可扩展的编排平台，Kubernetes 被证明是云或您自己的基础设施上的机器学习部署的良好匹配。

对于机器学习和数据科学来说，云是一个越来越有吸引力的地方，因为在训练模型或提供训练模型的结果时按需扩展的经济性，所以数据科学家不会浪费时间等待长时间的训练运行完成。Ovum 一直预测，到 2019 年，所有新的大数据工作负载将有一半在云中运行，在最近的一项调查中，约 45%的组织表示，他们至少在云中运行一个大数据工作负载。

这可能意味着云机器学习平台，如 Azure Machine Learning Studio、Amazon SageMaker 和 Google Cloud AutoML，它们提供内置的数据准备工具和算法，或者现有工具的云版本，如 Databricks(用于在 Azure 或 AWS 上运行 Spark 工作负载)或即将推出的 [Cloudera Machine Learning](https://www.cloudera.com/campaign/mlx-sign-up.html) 服务，这是一个将在公共云 Kubernetes 服务上运行的 Cloudera 数据科学工作台版本。

## 编排机器学习

Hadoop 和 Spark 在数据科学领域如此受欢迎的原因是，它们使用集群和并行处理来加速数据处理管道的可并行化部分。它们是专用的软件栈，其中集群由项目自己的集群管理解决方案管理，如 Apache Yarn 或 Mesos Marathon。

但是，随着 Kubernetes 作为创建可扩展分布式系统的协调者越来越受欢迎，它作为一种获得数据科学家希望使用他们选择的不同机器学习库和框架的灵活性、在生产中运行机器学习系统的团队所需的可扩展性和可重复性的方式，开始变得越来越有吸引力——同时控制运营团队所需的资源分配(包括用于快速训练和推理的 GPU)。这些都是 Kubernetes 已经为其他工作负载解决的问题，现在它正被应用于机器学习和数据科学。

在独立的数据科学和部署路径中，数据科学家使用一套工具和基础设施进行实验，开发团队在不同的基础设施上使用不同的工具在生产系统中重新创建模型，而团队可以拥有一个组合管道，数据科学家可以使用 [Kubeflow](/primer-kubeflow-streamlines-machine-learning-with-kubernetes/) (或基于 Kubeflow 构建的环境，如英特尔的开源 [Nauta](https://github.com/intelAI/Nauta) )使用 Kubernetes 来训练和扩展在 Kubernetes 上的 PyTorch 和 TensorFlow 等框架中构建的模型，而无需成为基础设施专家。

不同于给每个人提供自己的基础设施，将昂贵的 GPU 系统藏在桌子下面，多个用户可以共享相同的基础设施，Kubernetes 名称空间用于逻辑隔离每个团队的集群资源。来自微软 Azure Containers 团队的[拉克伦·艾文森](https://github.com/lachie83)解释道:“分布式培训可以大大缩短培训周期。“你想要一个训练有素的模型，具有一定的准确性，数据科学家正在改变模型，直到他们获得他们想要的准确性，但对于大型数据集，需要很长时间来训练，如果他们没有基础设施来扩展，他们就只能坐以待毙。”

“近年来，存储和计算资源的价格大幅下降，GPU 变得更加可用；这与 Kubernetes 相结合，使得大规模的机器学习不仅成为可能，而且具有成本效益，”Anaconda 产品营销总监 Thaise Skogstad 说。“像 Anaconda Enterprise 这样的平台结合了数据科学家所需的核心 ML 技术、IT 部门所需的治理，以及使大规模运行 ML 成为可能的云原生基础架构。”

一旦经过训练，该模型可以在相同的基础设施上提供服务，具有自动缩放和负载平衡；NVidia 的[tensort 推理服务器](https://devblogs.nvidia.com/nvidia-serves-deep-learning-inference/)使用 Kubernetes 来部署 tensort、TensorFlow 或 ONNX 模型。当您需要比自己的基础设施更多的资源时，可以选择使用云 Kubernetes 服务进行培训或推理。OpenAI 在一个混合模型中混合使用 Azure 和本地 Kubernetes 基础设施，并带有一个[批量优化的自动缩放器](https://github.com/openai/kubernetes-ec2-autoscaler)。

机器学习开发者使用广泛的框架和库；他们希望获得最新版本的工具，但他们可能还需要在特定项目中使用一个非常特定的旧版本，以便在每个环境中都可用。当您从开发阶段转移到部署阶段时，您可能最终会在不同的环境中运行同一模型的不同版本。这导致了再现性、编排和可伸缩性方面的问题，特别是如果在实验不成功的情况下更新到新模型或恢复到旧模型很复杂的话。

没有可再现性，就很难追踪问题是由管道还是模型引起的。但是，如果您能够可靠地将您的模型及其数据管道部署到生产中，将它们打包为微服务，公开其他系统可以调用的事件驱动的 API，则更容易将组件模块化，以便它们可以被重用或抽象服务，以便您可以支持多种工具和库。

Streamlio 营销副总裁 Jon Bock 表示:“我们看到了一个大趋势，即考虑将单个模型或子模型部署为服务，而不是在一个环境中运行的复杂整体，更复杂的集合模型可以调用这些服务并组合这些结果。

将不同的语言、库、数据库和基础设施整合到一个微服务模型中，需要一个能够提供可靠的消息传递、部署和协调的结构。在生产中运行该模型的团队还需要协调生产环境，并将资源分配给不同的模型和服务，其需求可能会随季节甚至全天而变化。

这是一个新兴趋势；在我们的 [2017 年 Kubernetes 用户体验调查](/ebooks/kubernetes/state-of-kubernetes-ecosystem/)中，23%的受访者在 Kubernetes 上运行大数据和分析，而在 hept io 2018 年关于[的报告中，Kubernetes 的状态](https://hello.heptio.com/the-state-of-kubernetes/)上升到 53%运行数据分析，31%运行机器学习。彭博正在 Kubernetes 上为其分析师建立一个机器学习平台。当微软想要以足够快的速度交付其实时文本到语音 API 以便聊天机器人和虚拟助手在现场对话中使用它时，它将该 API 托管在 Azure Kubernetes 服务上。

使用 Kubernetes 进行机器学习可能并不意味着像你想象的那样改变你的管道。您已经可以使用 Spark 2.3 中添加的原生 Kubernetes 调度程序在 Kubernetes 上运行 Spark(这是 Cloudera 用于其新云服务的程序)。调度器[仍处于试验阶段](https://spark.apache.org/docs/latest/running-on-kubernetes.html)，但 Spark 2.4 在 Kubernetes 上增加了对 Python 和 R [Spark 应用程序的支持](https://github.com/apache/spark/tree/branch-2.4/resource-managers/kubernetes/docker/src/main/dockerfiles/spark/bindings)，像 Jupyter 和 Apache Zeppelin 笔记本这样的交互式客户端应用程序为开发人员提供了可再现的沙盒环境，可以在 Kubernetes 上运行他们的计算。谷歌云平台(GCP)已经有一个针对 Spark 的(测试版) [Kubernetes 运营商](https://cloud.google.com/blog/products/data-analytics/data-analytics-meet-containers-kubernetes-operator-for-apache-spark-now-in-beta)来管理和监控 Kubernetes 上 Spark 应用的生命周期。

Apache Hadoop 社区已经[致力于将](https://hortonworks.com/blog/bringing-cloud-native-architecture-to-big-data-in-the-data-center/) Hadoop 从 Hadoop 文件系统(HDFS)中分离出来，以允许 Hadoop 通过 [Ozone](https://hadoop.apache.org/ozone/) 使用云对象存储，这是为 Kubernetes 这样的容器化环境设计的，在 Kubernetes 上运行[HDFS](https://databricks.com/session/hdfs-on-kubernetes-lessons-learned)以加速在 Kubernetes 上运行的 Spark，并在 Kubernetes 上运行 Hadoop 本身。

## MLops

还有大量新的机器学习工具和框架，它们依赖 Kubernetes 进行大规模的基础设施和模型部署。这肯定比使用[云机器学习服务](https://blogs.technet.microsoft.com/machinelearning/2018/05/02/kubernetes-load-testing/)需要更多的工作，但这意味着数据科学团队可以从比特定云机器学习服务可能支持的更广泛的语言和模型中进行选择，同时组织可以在部署和运行模型的位置上有更多的选择，以便他们可以平衡运行模型的需求和成本。

如果这听起来很熟悉，那是因为机器学习管道涉及 devops 在其他开发领域解决的相同类型的持续集成和部署挑战，并且有一个机器学习操作(“MLops”)运动产生工具来帮助解决这一问题，其中许多工具利用了 Kubernetes。

[Pachyderm](https://www.pachyderm.com/) 是一个端到端的模型版本化框架，有助于创建可重复的管道定义，每个处理步骤都打包在 Docker 容器中。 [MLeap](https://github.com/combust/mleap) 是一个帮助序列化多个学习库的框架，所以你可以通过 MLeap 包对同一个数据层使用 Spark 和 TensorFlow。 [Seldon](https://www.seldon.io/) 协调机器学习模型的部署和服务，将它们包装在容器中作为微服务，并为部署创建 Kubernetes 资源清单。ParallelM MCenter 是一个机器学习编排和监控平台，它使用 Kubernetes 来扩展模型部署。

像 [Polyaxon](https://github.com/polyaxon/polyaxon) 、 [MFlow](https://www.mlflow.org) 、 [Daitaku](https://www.dataiku.com/) 和 [Domino 数据科学平台](https://www.dominodatalab.com/platform/)这样的平台方法旨在覆盖从实验到部署和扩展的整个管道和生命周期，同样将 Kubernetes 作为部署选项。 [Lightbend](https://www.lightbend.com/) 将 Spark 和 SparkML 与 TensorFlow 混合，用于制作事件驱动的实时流和机器学习应用程序，Kubernetes 是部署选项之一。Streamlio 的社区版用于构建实时数据分析和机器学习，可作为 GCP 上的 Kubernetes 应用程序进行快速部署。

尽管 Streamlio 发现 Kubernetes 非常有用，但 Bock 警告说，因为 Kubernetes 是一个相对年轻的项目，仍在快速发展，采用它进行机器学习可能意味着要做更多的工作来跟上这些变化。“例如，您在 Kubernetes 中处理存储的选项正在快速发展，这确实对您如何构建应用程序产生了影响，因为您可能会发现您必须重新构建它们，因为现在有了更好的方法。”

例如，如果你将机器学习数据集存储在廉价的云存储中，有一个名为 [Nezha](https://kccna18.sched.com/event/GrWB/nezha-a-kubernetes-native-big-data-accelerator-for-machine-learning-huamin-chen-red-hat-yuan-zhou-Intel) 的新项目，这是 Kubernetes 的按需缓存，通过从 GCloud Storage、S3、Azure Data Lake 和 Storage Blobs 预取数据来加快训练性能。

他指出，如果你是 Kubernetes 的新手，你还需要从不同的角度思考如何访问数据。“如果你习惯于登录机器并获取日志，那么你在 Kubernetes 环境中获取数据的方式肯定是不同的。”

Bock 指出，MLops 工具也相对较新，尚未被广泛采用。“在如何部署环境的工具方面，我们需要更多的成熟和更多的创新；如今，许多人都在编写自定义配置文件，如舵图，以定义培训环境，但应该很容易指定该环境，并以可重复的方式进行部署，而不必深入到更改脚本行的层面。”

最佳实践仍在不断涌现，但 Kubernetes 正在成为如何成熟构建数据科学和机器学习管道的实践的选项之一。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>