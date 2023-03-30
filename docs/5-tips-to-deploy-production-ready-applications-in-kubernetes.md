# 在 Kubernetes 中部署生产就绪型应用程序的 5 个技巧

> 原文：<https://thenewstack.io/5-tips-to-deploy-production-ready-applications-in-kubernetes/>

[](https://www.linkedin.com/in/javier-j-salmeron-garcia/?originalSubdomain=es)

 [哈维尔萨尔梅隆

哈维尔拥有计算机工程博士学位，多年来一直致力于研究和教授云原生技术在高性能计算中的应用。他目前在 Bitnami(现在是 VMware)担任工程师，在那里他打包准备在各种平台上部署的应用程序:裸机服务器、虚拟机、云实例、容器和 Kubernetes 集群。他的最新贡献之一是 Kubernetes Sandbox，这是一个一体化的单一虚拟机集群，可用于 Google Cloud、AWS 和 Oracle Cloud 等云提供商。](https://www.linkedin.com/in/javier-j-salmeron-garcia/?originalSubdomain=es) [](https://www.linkedin.com/in/javier-j-salmeron-garcia/?originalSubdomain=es)

“生产就绪”是什么意思？如果您希望生产工作负载出现最少的问题，这是您应该回答的第一个问题。

这个问题的答案可以从多个角度来讨论:安全性、可维护性、测试、可配置性、稳定性、可升级性、文档等。甚至有人将生产就绪解决方案定义为“生产中的生产代码”

我个人认为，一个生产就绪的应用程序应该解决上面提到的所有元素。

在生产中部署 Kubernetes 工作负载时，Kubernetes 用户选择开源项目 [Helm](https://helm.sh/) 作为*事实上的*选项。我很容易理解为什么:Helm 带来了几个与专家建议的方法相匹配的好处。它扩展了部署的适应性和可定制性，简化了测试过程，允许历史和回滚管理等等。

在两年多的时间里，我为[项目](https://github.com/bitnami/charts)做出了贡献，扩展了可用的目录，增加了各种基础设施应用程序，还审核了拉式请求，添加了功能，并处理了支持案例。根据我的经验，如果开发人员想要创建可以在生产环境中部署的图表，他们应该注意五个要素。

### 1)通过限制容器操作来确保安全性:运行非根容器

要部署容器化的应用程序，您必须将允许的操作数量限制到最低要求。为了确保这一点，**使用不同于 root 的随机用户启动容器。这些被称为非根容器。**这是一些基于 Kubernetes 的平台的强制性要求，比如 Red Hat 的 OpenShift。稳定存储库中大约一半的图表已经使用了非根容器，并且这个数字还在增加。如果应用程序允许，您可以更进一步，使用完整的只读文件系统或“暂存”容器(没有任何底层基础操作系统)。

### 2)限制对集群的访问:实施基于角色的访问控制策略(RBAC)

Kubernetes 集群的核心是它的 [API 服务器](https://kubernetes.io/docs/concepts/overview/kubernetes-api/) *(kube-apiserver)。*通过访问它，您可以获得关于集群当前状态和其上部署的工作负载的详细信息。开发人员正在采用这种方法:目前，有许多支持 Kubernetes 的应用程序访问 API 服务器进行自我发现之类的操作。然而，**拥有完全访问 Kubernetes API 服务器的容器可能会损害集群。**为了降低这种风险，您必须确保 pod 内的流程只能访问最少的必要数据集。

这就是基于角色的访问控制策略发挥作用的地方。例如，如果您在名称空间“test”中部署一个使用 *kube-apiserver* 进行自我发现的基础设施应用程序，那么您可能只需要允许对该特定名称空间中的 pod 对象进行“get”和“list”操作。过去，用户向 Helm client Tiller 等应用程序授予集群管理权限(即执行集群内所有操作的权限)。这种做法导致生产灾难。

不要忘记确保使用图表部署的应用程序具有尽可能小的 RBAC 特权集。

### 3)实施适当的测试流程，尤其是升级时

更新[状态集中的标签](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)可能会导致破坏*头盔升级*命令。为了处理这种情况，在您的管道中包含升级测试是一项优先任务。显然，你不能假设没有人工干预，主要版本之间的升级就能工作*–*这就是主要版本颠簸的原因。然而，确保升级将在次要版本之间工作是可行的。

向图表添加默认禁用的功能是另一个常见问题。由于这些功能在默认情况下被禁用，正常的*舵安装*测试可能无法检测到任何问题。

这种情况的一个例子是入口规则。默认情况下，这些参数是禁用的，因此您在日常测试中很容易忘记它们。我可以预见当大多数入口 API 对象使用的 API Group extensions/v1 beta——Kubernetes 1.20中的[被弃用时，稳定存储库中的几个图表会如何破裂。](https://kubernetes.io/blog/2019/07/18/api-deprecations-in-1-16/) **这个潜在的问题可以通过用多个*值. yaml* 文件增加图表的测试覆盖率来避免。**为了帮助解决这个问题，像 kubeval 这样的解决方案可以派上用场。

### 4)不惜任何代价避免滚动标签

您可能已经熟悉了容器映像，并且您可能至少执行过一次类似于*docker pull bitnami/redis:latest 的命令。*这个“最新”是滚动标签的一个例子(即标签将随着时间指向不同的图像)。

设想以下场景:您希望使用最新版本的 redis 部署“bitnami/redis”图表。为此，您使用“latest”标记，这样您就知道您将在集群中运行 Redis 5.0.5。部署图表时，一切都无缝运行。现在进一步想象一下，如果在未来的某一天，您需要使用新的 pods 来扩展您的 Redis 集群，这将下载“bitnami/redis:latest”映像。如果现在最新的 Redis 是 5.0.8 呢？您将拥有运行不同版本 Redis 的同一个 Redis 集群。更糟糕的是，如果 Redis 6.0.0 发布了怎么办？您肯定会以一个破碎的 Redis 集群而告终。

**如果您希望您的部署是可维护的并且在控制之下，确保您的图表使用不可变的图像**(例如:“bitnami/redis:5 . 0 . 5-debian-9-r10 ”)。使用这种方法，每次部署或扩展时，您都知道您使用的是什么映像。此外，您可以保证部署的图像已经用图表的特定版本进行了测试，这在使用滚动标签时是无法保证的。

### 5)监控您的部署

这个技巧很容易掌握:如果您希望您的工作负载可以投入生产，您需要对它们进行监控。大多数生产就绪图表都包括对指标导出器的支持，因此您的应用程序状态可以通过像[普罗米修斯](https://prometheus.io/)和[波前](https://www.wavefront.com/)这样的工具或者像[BKPR](https://kubeprod.io/)T8 这样的套件来观察。此外，确保您的工作负载也与日志堆栈(如 [ELK](https://www.elastic.co/what-is/elk-stack) )集成，以提高容器化应用程序的可观察性，这一点很重要。其优势不可胜数:早期故障预防、审计、趋势检测、性能分析或调试等等。

## Kubernetes 在生产是一个现实

按照上面的提示，你将涵盖 Kubernetes 生产准备的所有基础知识。但是，您应该探索更多的领域，例如稳定性、性能、网络、自动扩展等等。查看下面列出的资源，将您的应用程序推向生产部署。如果您想和我一起寻找真正的“生产就绪”定义，请联系我。

*要了解更多关于容器化基础设施和云原生技术的信息，请参加 11 月 18 日至 21 日在圣地亚哥举办的[kube con+CloudNativeCon NA](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/)。*

## 有用的资源

∏[官方掌舵图表良好实践指南](https://helm.sh/docs/chart_best_practices/)

CodeFresh 的 Helm 最佳实践

[Bitnami Kubernetes 生产运行时间](https://kubeprod.io/)

∏[Github 中的 Bitnami Helm 图表库](https://github.com/bitnami/charts/)

∏[kube apps Hub](https://hub.kubeapps.com/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>