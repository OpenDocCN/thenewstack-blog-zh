# Platform9 通过托管 KubeVirt 将虚拟机引入 Kubernetes

> 原文：<https://thenewstack.io/platform9-brings-vms-to-kubernetes-with-managed-kubevirt/>

SaaS 一家为私有云和边缘云提供托管 Kubernetes 和 OpenStack 的提供商 Platform9 已经将开源项目 [KubeVirt](https://kubevirt.io/) 添加到其托管服务列表中，该项目将虚拟机(VM)引入 Kubernetes。

[Platform9 Managed KubeVirt](https://platform9.com/managed-kubevirt/) ，今年早些时候首次[引入测试版](https://platform9.com/blog/kubevirt-tearing-down-another-silo/)，对所有 Platform9 用户开放，包括那些使用该公司免费层的用户，并允许他们在 Kubernetes 的容器旁运行更适合虚拟机的应用程序。

Platform9 的产品经理克里斯·琼斯解释说，电信行业只是他们看到组织在 Kubernetes 上运行虚拟机时发现价值的一个例子。

“我们看到一种趋势，即用户希望获得一个单一的融合堆栈来管理他们的应用程序，特别是在 4G 和 5G 领域。电信运营商正在 Kubernetes 中运行新的本地容器化网络功能，但还有其他辅助控制应用程序与这些功能相邻，这些功能仍然主要是更适合作为虚拟机运行的单片应用程序，”Jones 说。“在采用 5G 的时间范围内，他们无法将这些应用容器化，或创建微服务架构来取代这些单一应用。这些运营商特别希望能够运行单个堆栈，在同一个基础架构中运行一个虚拟机，不再需要运行重复的基础架构。”

借助 Platform9 的 KubeVirt，用户可以在集群创建期间以及之后的集群生命周期中，直接从 [Platform9 托管的 Kubernetes (PMK)](https://platform9.com/managed-kubernetes/) UI 创建虚拟机。当这项服务在今年早些时候首次推出时，用户被送到命令行与 KubeVirt 进行交互，但 Platform9 团队知道这不是他们想要的。

“有很多用户希望有一种方式登录到应用程序，只需指定一个虚拟机并单击“创建”，琼斯说，因此他们花了过去四个月的时间来构建这一功能。

[https://www.youtube.com/embed/iDamP00M-T4?feature=oembed](https://www.youtube.com/embed/iDamP00M-T4?feature=oembed)

视频

除了简单的界面，Platform9 的托管 KubeVirt 还提供了许多其他功能，包括 Prometheus 的自动监控、虚拟机管理功能、正常运行时间保证以及其他企业功能，如 RBAC 和多租户。

在一份新闻稿中，该公司表示，新功能是“业内首个托管的 KubeVirt 解决方案，提供了一个统一的平台来运行虚拟机(VM)和容器。”虽然去年，Red Hat [推出了同样基于 KubeVirt 的 OpenShift 虚拟化](https://www.redhat.com/en/about/press-releases/red-hat-brings-virtualization-cloud-native-era-latest-version-red-hat-openshift)，但 Jones 解释说 Platform9 采用了不同的方法来管理服务。

“我们的管理方面不仅仅是 Kubernetes 在运行吗？KubeVirt 启用了吗？如果在启动 KubeVirt 虚拟机时确实出现了问题，我们的支持团队会赶到现场，帮助启动和运行。这不仅仅是说，“软件在这里，它已经部署并运行，您可以开一张传统的罚单，”在支持方面。我们不会用那种方式对待我们的客户。这是非常非常专业的实践，包括一个确保他们投资的平台取得成功的过程。"

至于与容器一起运行虚拟机是暂时的还是长期的，Jones 选择了后者，他说在 Kubernetes 中支持虚拟机是一个“长期的游戏”

“随着越来越多的企业开始习惯运营 Kubernetes，我认为他们会涉足并问一个问题‘为什么我们还在运营两个平台？’”琼斯说我敢肯定，首席财务官们会开始问这样一个问题:如果我们 90%的创收软件都是在 Kubernetes 上运行的，那我为什么要花这么多钱把这些软件作为虚拟机来授权呢？"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>