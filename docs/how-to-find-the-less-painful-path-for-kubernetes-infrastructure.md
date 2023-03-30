# 如何为 Kubernetes 基础设施找到一条不那么痛苦的道路

> 原文：<https://thenewstack.io/how-to-find-the-less-painful-path-for-kubernetes-infrastructure/>

[戴尔科技](https://www.delltechnologies.com/en-us/index.htm)赞助了这次播客。

Kubernetes 对容器集群和容器的安排是这位作者观察到的更令人惊奇的计算结构之一。从许多方面来说，它作为容器编排器的简单性回避了这样一个问题:为什么这样一个简单的系统如此难以发明？无论如何，除了 Kubernetes 提供的资源节约功能，对其多功能性和可伸缩性的宣传也是当之无愧的。

[芯片佐勒，Boskey sav la——如何为 Kubernetes 基础设施找到不那么痛苦的路径](https://thenewstack.simplecast.com/episodes/chip-zoller-boskey-savla-how-to-find-the-less-painful-path-for-kubernetes-infrastructure)

但是，当您的组织决定将云原生迁移到 Kubernetes 时，DevOps 突然意识到前方的学习曲线非常陡峭，因为他们面临着管理 Kubernetes 基础架构的巨大挑战。

[VMware](https://www.linkedin.com/in/boskey)现代应用技术产品线营销经理 Boskey Savla 认为，例如，DevOps 团队开始考虑确保特定堆栈在 Kubernetes 上安全可靠的可怕前景。Savla 说:“这些是客户[在采用]云原生架构时]开始考虑的事情，他们往往会在事后才想到这一点。“他们在 Kubernetes 上全押。但后来他们意识到，‘好吧，我们需要处理好这一切。“我该如何扩展集群？”"

在本[播客中，新的堆栈制造商](/podcasts/makers)萨维拉和[芯片佐勒](https://www.linkedin.com/in/chipzoller)，戴尔技术[的高级首席工程师](https://www.delltechnologies.com/en-us/index.htm)，讨论了与云原生和 Kubernetes 相关的基础架构挑战，以及正确的工具选择如何有助于减少迁移的痛苦。

虽然开发人员会注意到当他们的 DevOps 支持基础设施迁移到云原生时的差异，但他们作为软件工程师的工作——无论他们是用 Python、Go 还是任何其他编程语言创建应用程序——将在很大程度上保持不变。一旦他们过了学习曲线，他们的工作主要还是像以前一样继续。

“大多数时候，开发人员甚至不了解底层基础架构在哪里，以及他们是如何管理它的。他们对这一过程完全透明，”萨夫拉说。“Kubernetes 所做的是[它]真正与后端基础设施对话，并自动化开发人员定义的许多这些任务，以实现这一神奇的事情。因此，在那个时间点上的基础设施必须是流动的和兼容的，Kubernetes 本身需要了解如何与特定的基础设施合作，以使这些事情成为可能。”

但对于运营人员来说，与开发人员的体验相比，云原生基础架构是一种非常不同的动物，尤其是在从传统数据中心结构进行转变时。复杂性增加了，因为组织的任务不是管理一个集群，而是管理许多 Kubernetes 集群。

Savla 说:“通常，开始时简单的项目会变得非常复杂，因为现在突然之间，仅仅上游项目无法帮助你…确保访问社区 API 的开发者获得授权。”她解释说，例如，每个集群都有自己的控制策略，必须定义这些策略的规则和策略。为了安全，例如，必须分配打开端口或创建服务的访问，这只是要考虑的众多基础设施管理任务中的一个。

[https://www.youtube.com/embed/afcFTYL1MEU?feature=oembed](https://www.youtube.com/embed/afcFTYL1MEU?feature=oembed)

视频

对于第 2 天的生产就绪，Kubernetes 需要基础设施、工具和平台来帮助实现这一转变。[例如，戴尔 EMC 的 VxRail](https://www.delltechnologies.com/en-us/converged-infrastructure/vxrail/index.htm) 旨在帮助促进 VMware 云的采用。佐勒说，VxRail 消除了“运行企业基础设施固有的”许多复杂性。他说，在第一天的设置过程之后，VxRail 就像一个“向导，甚至被封装在基础设施代码中”，在第二天，“在大多数情况下，它使更新和升级成为一项微不足道的任务，因此 Kubernetes 被置于其上”。然后，VxRail 可以通过 VMware“在存储和网络等方面”充分利用这些功能

借助 [VMware vSphere](https://www.vmware.com/products/vsphere.html) ，组织可以在用于 Kubernetes 部署的各种 VxRail 拓扑中进行选择。“这归结于客户的使用案例，以及他们希望如何部署他们的 VxRail rail，知道 Kubernetes 部署在其上时，可以与它一起工作，”佐勒说。

[VMware](https://www.vmware.com/company.html) 是新堆栈的赞助商。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>