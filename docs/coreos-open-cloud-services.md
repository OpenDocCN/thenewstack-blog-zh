# CoreOS 的开放云服务可以为容器原生应用带来云的可移植性

> 原文：<https://thenewstack.io/coreos-open-cloud-services/>

随着 structural 1.8 的发布， [CoreOS](https://coreos.com/) 提供了一种将容器原生应用作为服务轻松部署的方式，甚至可以跨越多个服务提供商和内部资源。

CoreOS 首席技术官 [Brandon Philips](https://twitter.com/brandonphilips) 说:“我们采用开源 API，使它们非常容易使用，并创建了一个在 Kubernetes 上运行的这些东西的目录，这样无论你去哪里，它们都是可携带的。

在上周于奥斯汀举行的[云本地计算基金会](https://www.cncf.io/)的 Kubecon 2017 活动上，[公司推出了](https://coreos.com/blog/tectonic-18-with-open-cloud-services)[构造](https://coreos.com/tectonic/#get-started)的最新版本，这是其 [Kubernetes](/category/kubernetes/) 开源容器编排引擎的商业发行版。

这个想法是应用程序目录服务，称为开放云服务，在整个应用程序生命周期中像持续集成和部署管道一样工作。“应用程序目录中的每个应用程序都有多个版本，”飞利浦说。这种分类将使监控、日志记录和其他跨应用程序问题的基础设施标准化变得更加容易。

[https://www.youtube.com/embed/nEzR8UVFXvA?feature=oembed](https://www.youtube.com/embed/nEzR8UVFXvA?feature=oembed)

视频

这些服务将通过 Kubernetes 的运营商模式处理，这是 CoreOS 在 2016 年带给 K8s 的[。运营商在 Kubernetes 集群内的单一命名空间中管理软件。](https://thenewstack.io/coreos-contributes-operators-containers-configure-kubernetes/)

一个组织可能有多个名称空间，每个名称空间专用于一个应用程序的部署，例如一个用于测试，一个用于开发，一个用于部署。飞利浦说:“我们本质上是让你能够使用容器本地 API 来消费软件，并在你的应用程序的每个部署的基础上这样做。”

最初，CoreOS 被打包成服务支持工具，往往与大多数应用程序一起使用，如 Prometheus monitoring toolkit 和 [Vault security store](https://www.vaultproject.io/) 。这样，无论部署什么云提供商来运行云原生应用，无论是 Azure 还是 Amazon Web 服务，用户都可以在应用旁边运行相同的支持工具。

“当您迁移到云时，最大的应用锁定可能是身份管理，这些帐户您只能从云提供商那里获得。通过引入 Vault，我们[提供了一种方式]针对 Vault API 进行编程，而这个 API 是你可以带到 Azure、AWS 或你自己的数据中心的东西，”飞利浦说。

CoreOS 将在服务中添加更多的云原生应用，并从客户那里获得关于优先考虑哪些应用的反馈。飞利浦表示，日志服务、数据库和 Kafka 等流媒体服务是非常适合纳入的应用类型。

“人们希望在一个可控的环境中运行这些东西。他们不想成为专家，”飞利浦说。在即将发布的版本中，该公司还将为用户提供用他们自己的应用程序来扩展我们的服务的方法。

该服务的一个潜在卖点是它将负责升级过程。升级金库尤其是一项复杂的任务。“我们已经把它转化为代码，所以你只需要告诉保险库服务升级到一个新的版本，我们会为你完成所有的步骤，”飞利浦说。

由于支持多种环境非常容易，该服务可能会激发组织创建更多的环境来测试和部署应用程序。

“这就是我们在 CoreOS 的工作。每当我们将一些东西签入代码时，我们都有一个 QA 环境。我们可以看到最后一次提交或最后 20 次提交，”飞利浦说。或者，如果生产中正在进行某项操作，我可以进入目录，查看生产中正在运行的版本，并在新的命名空间中创建一个新拷贝，记录生产中正在进行的操作，这样我就可以尝试重现它

服务目录可以帮助促使容器操作更接近应用程序管理级别。

Kubernetes 拥有丰富的支持工具，如 [Helm](https://github.com/kubernetes/helm) 和 [ksonnet](https://github.com/ksonnet) ，但很少有人提供任何方式来理解应用程序级别正在发生的事情，飞利浦解释道。“它们改善了 Kubernetes 中容器的工作流程，但不能让你一键查看你想了解的关于应用程序的所有信息，”他说。

Philips 看好 Kubernetes API 将成为未来几年云原生可移植性的基础。

“我们一直大力提倡扩展 Kubernetes API 来做更多的事情，”Philips 说。Kubernetes 命令行, [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) 可能是从开发人员到网络工程师的每个人的中心访问点。“它给了人们自助的控制权，”他说。

structural 1.8 基于上个月发布的 Kubernetes 1.8。

[CoreOS](https://coreos.com/) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>