# KubeDirector，BlueData 用于大数据任务的定制控制器

> 原文：<https://thenewstack.io/kubedirector-bluedatas-custom-controller-for-big-data-tasks/>

专注于帮助企业加速大数据和机器学习部署的 BlueData 发布了其 BlueK8s 计划下第一个项目的源代码。你可以在 [GitHub](https://github.com/bluek8s/kubedirector) 上找到。

这家总部位于加州圣克拉拉的公司在 7 月宣布 [BlueK8s](https://www.bluedata.com/blog/2018/07/operation-stateful-bluek8s-and-kubernetes-director/) 作为开源项目的保护伞，帮助将分布式有状态应用程序的企业级功能带到 Kubernetes。其中第一个项目是 KubeDirector，这是一个用于 Kubernetes 上大数据和人工智能工作负载的定制控制器。在 alpha 测试之前，BlueData 已经花了大约六个月的时间来编写代码。

KubeDirector 是一个定制资源，允许用户在 Kubernetes 上部署和管理任何类型的大数据或机器学习集群，而无需修改应用程序。

联合创始人兼首席架构师 Tom Phelan 表示，Hadoop、Spark 和 TensorFlow 等大数据和机器学习应用程序不同于 Kubernetes 设计的基于微服务的应用程序。

他将这些有状态的应用程序描述为“一堆紧密集成的相互依赖的进程，这些进程没有得到很好的理解，它们的状态分布在多个配置文件中。”没有大量的工作，它们不能被轻易地分解成微服务。

部署到 Kubernetes 中后，KubeDirector 会监视在一些 K8s 名称空间中创建和修改的给定类型的定制资源。GitHub 页面解释说，然后它使用 Kubernetes APIs 来创建或更新集群的资源和配置，使其符合自定义资源中定义的规范。

与其他一些定制控制器实现不同，KubeDirector 没有将定制资源定义绑定到特定类型的应用程序，也没有在控制器中包含硬编码的特定于应用程序的逻辑。相反，应用程序特征是由元数据和相关的配置工件包定义的。

“在 Spark 和 Hadoop 中，每个节点上都有存储在/etc 或/user 文件目录中的配置文件，这些文件包含给定节点的特定配置信息，”Phelan 解释道。“现在的持久卷不允许您以整个系统都支持的一致方式挂载/etc 或/user。因此，这种特定于节点的状态不容易从一个容器转移到另一个容器，这使得今天在 Kubernetes 中运行大数据应用程序具有挑战性。”

因此，运营商是另一个步骤，使运行 Spark 和其他一些应用程序成为可能。

“人们一直在使用掌舵图、Kubernetes 运算符、有状态集、持久卷计划——它一直在发展，但仍不足以用于大数据和人工智能应用，”他说。

“今天，如果我是 Spark 专家或 Hadoop 专家，如果我想编写一个运算符，我也必须成为 Kubernetes 专家，才能为这个 Kubernetes 运算符编写 Go 代码。

“有了 KubeDirector 项目，我们不需要数据科学家编写任何 Go 代码。除了已经是 Spark、Hadoop 或 Tensorflow 的专家之外，我们不要求他们成为 Kubernetes 的专家。他们只是在 YAML 提供了一个简单的配置文件，KubeDirector 将其转换成相当于该应用程序的 Kubernetes 操作符，”他说。

他说，在 KubeDirector 之后，下一个项目将专注于改善持久存储在 Kubernetes 中的实现方式。

“永久卷非常适合存储应用程序根文件系统之外的数据。BlueData 将推出一种机制来持久化根文件系统中的数据。这对于运行大数据应用程序至关重要，因为它们的配置信息存储在根文件系统和这些选项驱动器中，”他说。

该公司还在研究改善人工智能和机器学习应用程序工作流程的技术。他说，数据科学家倾向于使用自主开发的方法在他们之间交换人工智能模型或模式。这项新技术将使他们能够更容易地分享他们的人工智能模式和模型。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>