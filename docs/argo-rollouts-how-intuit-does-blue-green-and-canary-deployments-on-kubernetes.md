# Argo 部署:Intuit 如何在 Kubernetes 上部署蓝/绿和淡黄色

> 原文：<https://thenewstack.io/argo-rollouts-how-intuit-does-blue-green-and-canary-deployments-on-kubernetes/>

如果 Kubernetes 中没有对蓝/绿和金丝雀部署的本机支持，开发人员只能靠自己来解决这个问题。

分析师[贾纳基拉姆·MSV](https://thenewstack.io/author/janakiram/)写过两种开源方法:使用 [Spinnaker](https://thenewstack.io/getting-started-spinnaker-kubernetes/) ，这是在网飞开发的多云开发平台，以及使用服务网格 [Istio 和 Kubernetes](https://thenewstack.io/tutorial-blue-green-deployments-with-kubernetes-and-istio/) 。

Intuit 软件工程师 Danny Thomson 和 Alex Matyushentsev 在今年早些时候的 KubeCon Europe 展示了第三种方法，称为 Argo Rollouts。

## GitOps 方法

Intuit 在 2018 年初收购了 Applatix，该公司是 Kubernetes 的 [Argo 工作流引擎](https://blog.argoproj.io/introducing-argo-a-container-native-workflow-engine-for-kubernetes-55c0b4b76fac)的背后公司，并专注于该团队将金融软件公司迁移到云原生技术的努力。

在 18 个月内，它在 Kubernetes 上运行了 2000 项服务。现在[宣称](https://www.cncf.io/case-study/intuit/)创建或升级一个服务只需要不到 10 分钟，包括建立自动构建和部署管道，以及不到 5 分钟的 QuickBooks 软件回滚。

Thomson 说，Intuit 有 1200 名工程师使用 Kubernetes 每天进行大约 1300 次部署。他们使用两种部署策略:重新创建(版本 A 被终止，然后版本 B 被推出)；以及滚动更新(B 版慢慢铺开，取代 A 版)。但它发现其遗留软件无法进行滚动更新，此外它还想采用新的应用程序和策略。

它使用 GitOps 方法作为基础架构和应用程序所需状态的单一真实来源。所有 Kubernetes 清单都存储在 Git 存储库中，它使用开源工具 [Argo CD](https://github.com/argoproj/argo-cd) ，将清单与集群中的内容进行比较，识别差异，并帮助用户协调这些差异。

Intuit 遇到的一个问题是 [GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 是声明性的，blue/green 和 canary 方法是必需的。

“我们希望更多的是一种声明性的方法，并与 CI 工具集成，这样开发人员将拥有一个简单、干净的从提交到部署和掌握的管道，”Thomson 说。

它的第一个蓝/绿和金丝雀部署方法涉及 Jenkins 脚本，但这不适合 GitOps 模型。

“[这是]采取了很多国家，并把它纳入我们的管道，这意味着我们有两个不同的真相来源。詹金斯有很多假设。如果有任何变化，如果集群有任何不同，管道就会失败。用户将不得不进入并修改集群，以使其回到正确的状态，”他说。

这也是非常脆弱的，需要更多的工作比他们想要的。

接下来，它试图将 Jenkins 逻辑推入部署挂钩。Jenkins 仍然有很多假设，它仍然不是幂等的和透明的，仍然需要大量的工作。它仍然没有遵循 GitOps 模型。

“这很有效，但我们并不满意，”汤姆森说。

前两种方法非常必要。“我们说，‘做这个，做那个。“但我们想利用让 Kubernetes 如此伟大的东西:它的声明性质，”他说。

### 定制控制器

因此，他们着手建立一个自定义控制器，经过六个月的工作，成为 Argo 推出。它的设计要求是:

*   在控制器中编写部署编排。开发人员不必担心部署逻辑。
*   GitOps friendly (idempotent) —不管集群的状态如何，它都应该能够处理它并回到稳定的状态。
*   在 Kubernetes 集群内部运行——无需向外部资源提供凭证。
*   易于采用和从部署中迁移。
*   功能等同于部署。

您安装一个名为卷展栏的自定义资源，然后安装一个在该资源上运行的控制器。它处理[副本集](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/)的创建、缩放和删除——副本集的整个生命周期。他们还希望有一个单一的期望状态作为 Podspec。它支持手动和自动提升，并与[水平 Pod 自动缩放器](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/) (HPA)集成。

由于开发人员对 canary 部署的方法各不相同，他们希望尽可能地灵活。它允许用户定义从旧版本过渡到新版本所需的步骤。

Thomson 在一篇[博客文章](https://blog.argoproj.io/introducing-argo-rollouts-59dd0fad476c)中解释说，Argo Rollouts 控制器通过管理副本集和通过修改服务选择器过滤流量，使新旧版本能够在蓝/绿部署中同时运行:

*副本集是从卷展栏的 spec.template 字段创建的，服务是在 spec.strategy.blueGreen 字段指定的。由卷展栏创建的每个副本集都有一个唯一的哈希(在标签的卷展栏-pod-template-hash 中),控制器会将该哈希添加到服务的选择器中，以限制该副本集的流量。*

*当 spec.template 字段改变时，卷展栏将创建一个新的副本集，并等待它变得可用。一旦发生这种情况，控制器将修改预览服务的选择器，将流量发送到新的副本集，并通过将 spec.paused 字段设置为 true 来进入暂停状态。在此期间，卷展栏将暂停并等待，直到外部操作员(如 CD 系统或用户)将该值更改为 false。取消暂停卷展栏后，卷展栏将修改活动服务的选择器，使其指向新的副本集，并缩小旧的副本集。*

你可以定义一个流量与金丝雀的比率，或者你可以添加一个步骤来暂停你的首次展示一段预定的时间，或者它可以继续进行。当引入新版本时，Argo 卷展栏控制器将执行这些步骤，然后将卷展栏中的当前模板标记为新的稳定资源。

在这个演示的时候，它还没有使用服务网格，但是在夏天开始与 Istio 合作。它后来发布了 [**Admiral**](https://github.com/istio-ecosystem/admiral) ，这是一个开源项目，为多个 Istio 部署提供自动配置，以作为单个网格工作。

自从收购以来，Intuit 已经发布了许多 Argo 项目，包括:

*   **[Argo CD](https://github.com/argoproj/argo-cd)** **，**为 Kubernetes 的声明式连续部署。
*   **[Argo Events](https://github.com/argoproj/argo-events)** ，与投资管理公司 BlackRock 合作开发，black rock 是 Kubernetes 基于事件的依赖管理器，用于触发工作流和应用程序。
*   **[Argo Workflows](https://github.com/argoproj/argo)**，一款高度可扩展的 Kubernetes 原生工作流编制器。
*   **[Keikoproj](https://github.com/keikoproj/keiko)** ，一组用于在生产中大规模管理 Kubernetes 的声明性自定义资源定义(CRD)。
*   [**Keiko**](https://github.com/keikoproj/keiko) —一套独立的开源声明性工具，用于在生产中编排和管理多租户 Kubernetes 集群。

在今年晚些时候的 [KubeCon+CloudNativeCon 北美](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/)大会上，Intuit 宣布了 **[Argo Flux](https://www.itopstimes.com/gitops/itops-open-source-project-of-the-week-argo-flux/)** ，这是一项与 AWS 和 Weaveworks 的合作，旨在将云原生计算基金会沙盒项目 [Flux](https://github.com/fluxcd) 和 Argo CD 统一为开源 GitOps 持续交付工具。

[https://www.youtube.com/embed/yeVkTTO9nOA?feature=oembed](https://www.youtube.com/embed/yeVkTTO9nOA?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>