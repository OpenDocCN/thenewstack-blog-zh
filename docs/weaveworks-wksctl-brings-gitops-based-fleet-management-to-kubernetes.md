# Weaveworks 的 WKSctl 为 Kubernetes 带来了基于 GitOps 的车队管理

> 原文：<https://thenewstack.io/weaveworks-wksctl-brings-gitops-based-fleet-management-to-kubernetes/>

如今似乎所有东西都有一个“Ops”，而 [GitOps](/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 正在引领下一代 BlankOps。如果 git 是您分布式系统中版本控制和真实性的唯一来源，那么 GitOps 就是您在复杂的异构环境中管理和部署的方式。

为了帮助促进 GitOps 环境，[weaver works](https://www.weave.works/)发布了[wks CTL](https://github.com/weaveworks/wksctl)(weaver works Kubernetes 系统控制)，这是其 GitOps 套件中的一个开源组件。WKSctl 希望为 Kubernetes-hybrid 组织找到自动化和控制之间的快乐平衡。您只需要 IP 地址和 SSH 密钥就可以启动并运行它。

“你有一个系统模型，然后有自动化工具确保系统处于理想状态。这些工具将检测你是否处于不正确的状态，它应该自己修复状态，或者至少应该告诉你，”Weaveworks 创始人 Alexis Richardson 说。

“企业喜欢干扰正在运行的系统，认为他们正在使它更加安全。但实际上，通过让人们接触运行系统，他们正在使它变得更不安全，”他说。

这就是为什么 GitOps 方法是一种云原生运营模式，提供按需企业治理，包括策略实施、部署、管理、监控和可重用性。

这与行业钟摆从开发人员独立摆回护栏和最佳实践执行是一致的。以及支持这一切的工具。

### WKSctl 在 GitOps 行动中，跨云和跨空气间隙

[Weaveworks 将 WKSctl](https://www.weave.works/oss/wksctl/) 描述为一个命令行界面，带有使用 GitOps 配置和管理应用集群、运营自动化等策略以及 Kubernetes 集群的跨云管理的后台服务。

WKSctl 和整个 Weaveworks 堆栈希望将 GitOps 应用于单个 Kubernetes 集群并用于车队管理。一个机群通常是一组具有一组公共属性的集群，如应用交付集群或数据库集群。这些 Kubernetes 集群中的每一个都有相似的安全性、审计和合规性要求，并且可以而且通常应该以相同的方式对待。

Richardson 说 WKSctl 满足了对单一可安装工具的需求，该工具可以与上游的 Kubernetes 一起工作，但允许企业治理。WKSctl 在云中或您自己的计算机上、裸机上、虚拟机上，甚至在空气间隙环境中为开源 Kubernetes 工作。

这个 air gap 应用程序在边缘情况下特别有趣，因为它允许您即使在没有连接到互联网的情况下也可以管理集群——比如在自然灾害期间。

Weaveworks 首席技术官科妮莉亚·戴维斯(Cornelia Davis)说，公司在断开连接时保持正常运营的方式“非常定制”

她将此描述为 WKSctl 的核心租户，并继续说道，“Kubernetes 已经成为一种适用于空气间隙和边缘的统一层，但它确实需要特定的方法来处理零星的连接。”

Davis 说，WSKctl 希望确保企业部署策略支持开箱即用的连续交付的不连续的、通常是异构的本质。

Richardson 解释说，WSKctl 被设计为本质上订阅一个包含策略的存储库，这些策略涉及如何配置它，你想要哪些附加组件——比如用于[渐进式交付](https://thenewstack.io/the-rise-of-progressive-delivery-for-systems-resilience/)的服务网格——以及它将在什么操作系统上运行。

“这不是一个均匀分布的整体。这是上游分布的组合，”他说。

## 补丁与真正的企业安全

“我们认为，确保在对集群进行关键更改时更新模型(在 git 中)非常重要。这可以是添加一个应用程序，更新一个配置——对所有东西进行更新，”理查森说。

理查森说“这不仅仅是修补安全。在我们的架构中，我们已经将所有的安装和管理机制从代码本身中分离出来。很明显，当它处于上游时，你可以将它与更多的附加产品混合在一起。”

Richardson 指的是 WKSctl 的管理交付，包括通过 GitOps 方法实现的升级、补丁和更新，该方法强制执行正确的集群状态。

WKSctl 然后跟踪版本，在适当的时候修改模型中的版本，然后客户立即知道何时有了新的版本升级。发生在封面下的协调循环将自动应用升级。

遵循 [GitOps 操作方式](https://thenewstack.io/gitops-git-push-all-the-things/)，WKSctl 希望在不增加风险的情况下实施治理——有权限的人越少越好。

## Kubernetes 的集群和车队管理

戴维斯说 git 只是让它更加安全。

她说，“每一件事都被记录下来。你不能在 git 中回到过去改变事情。这是新一代应用程序的一次写入式审计日志，“比如分解的微服务和 Kubernetes。

然后，使用 WKSctl 这样的工具作为管理集群的一部分，使您能够为一个组织统一应用这些组件，该组织通常具有云内、内部甚至边缘计算、裸机和空隙环境的异构混合。

Kubernetes 车队管理有助于回答一些基本问题，例如:您如何知道是否可以关闭集群？如何知道集群是否应用了所有与安全相关的补丁？当确实需要应用安全补丁时，车队管理可让您快速、全面地完成任务。

戴维斯指出，Zalando 电子商务网站是最早以这种方式规划 it 组件的公司之一。它在每个微服务上运行大约 100 个不同的 Kubernetes 集群，应用一致的策略，为他们提供合理的方式来执行集群升级，并解决常见的漏洞。

这是限制这些复杂系统变得多复杂的一种方式。

他看到了未来的克隆人战争，在那里你可以以基本上零成本或零努力的方式拆卸或丢弃正确配置的集群。如果需要 40 秒来启动你的手机，这是大多数集群应该很快就要花的时间。

当然，会有强化的连接——比如存储和生产——但是，理查森说，对于其他方面，它必须那么快。

## 如何运行 WKSctl

有三种方法可以运行和安装 WKSctl。

首先，如果你已经是 Weaveworks 的商业客户，你购买 GitOps 平台，公司将为你管理这一切。

你也可以使用 [Weave Firekube](https://www.weave.works/oss/firekube/) ，其中 Weaveworks 提供了一个名为 Weave Ignite 的工具，该工具利用 [亚马逊的微虚拟机技术鞭炮](https://firecracker-microvm.github.io/)来自动供应虚拟机。然后， Firekube 结合 WKSctl 引导您的 git 存储库，并提供 Kubernetes 集群生命周期管理，包括基础设施自配置。

但是利用 WKSctl 最常见和推荐的方式是将一个配置与 GitHub 和 GitOps 配对。您需要首先提供您的机器，以及允许访问的 SSH 密钥。然后将机器列表和 SSH 密钥发送给 WKSctl。

WKSctl 会将您的机器转换成 Kubernetes 节点，然后形成一个 Kubernetes 集群。WKSctl 是一个集群 API (CAPI)提供者，它只需要 SSH 密钥和机器的 IP 地址。

Weaveworks 并不是唯一一家采用 GitOps 风格的 Kubernetes 管理的公司，谷歌也为谷歌 Kubernetes 引擎发布了一项专注于 GitOps 的服务，名为[应用管理器](https://cloud.google.com/blog/products/containers-kubernetes/announcing-application-manager-for-google-kubernetes-engine)。

由 [Jonathan Saleh](https://unsplash.com/@jonathansaleh?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash 上制作的专题图片。](https://unsplash.com/s/photos/fleet?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>