# Kubernetes 1.11 增加了自定义资源定义

> 原文：<https://thenewstack.io/kubernetes-1-11-ramps-up-custom-resource-definitions/>

开源 Kubernetes 容器编排引擎的最新版本——版本 1.11 将于周三上线——包括许多重大变化，包括动态配置 [Kubelet](https://kubernetes.io/docs/reference/command-line-tools-reference/kubelet/) 的能力，一个新的 Kubernetes DNS 子项目，以及用于[自定义资源定义](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/) (CRDs)的新功能。这些变化表明了 Kubernetes 的长期计划，因为它们侧重于扩展项目的开发，并提高 Kubernetes 处理定制和企业资源的能力。

红帽公司 Kubernetes 负责人 [Josh Berkus](https://www.linkedin.com/in/josh-berkus-1792412/) 说，这次发布是正在进行的重写 Kubernetes 底层管道的努力的一部分。在过去的几个版本中，该平台的内部已经得到了很好的检查，以确保更高的稳定性和模块化。这个版本中增加模块化的一个例子是 [CoreDNS](https://kubernetes.io/docs/tasks/administer-cluster/coredns/) 项目。

CoreDNS 用一个由自己的团队组成的专门子项目取代了 KubeDNS。这将允许 CoreDNS 在 Kubernetes 核心团队之外独立发展，该团队现在将专注于平台的核心功能。

“CoreDNS 只是又一次更新换代。这是一个单一的 Go 二进制。它更小、更简单、更可靠。我预计人们会在接下来的几个版本中过渡到 CoreDNS。这是一个独立的项目，在 CNCF 有自己的团队，优势是实际上有一个团队专门负责维护它，而不是 Kubernetes 特别兴趣小组，”Berkus 说。

在这个版本的其他地方，由于 Kubernetes 1.11 增加了动态 Kubelet 配置功能，kube let 变得更容易维护。以前，当对特定节点进行更改时，需要完全重启该节点或 Kubelet。随着 Kubernetes 1.11 的发布，底层 Kubelet 的配置可以在不需要重启的情况下完成。

“库伯莱是运行每个系统的恶魔。Kubelet 下载并运行特定节点所需的任何东西。到目前为止，改变 Kubelet 配置的方法是使用 SystemD 或其他工具用不同的标志重新启动它，”Berkus 说。

他转述道，这种方法有几个问题。首先，这意味着该过程完全超出了 Kubernetes 配置的范围。第二个问题是用户必须重启它们，即使是很小的改动，而且在整个 Kubernetes 基础设施上滚动重启对任何人来说都不好玩。

“现在，您可以通过更改配置文件来更改 Kubelets 配置的某些方面。我们已经从命令行转换到配置文件，”Berkus 说。他接着补充说，这对在裸机上运行 Kubernetes 的用户特别有用。

对于需要更多定制 Kubernetes 体验的用户，CRD 允许团队扩展其 Kubernetes 安装的功能，以包括定制资源。“如果你把某样东西定义为 CRD,”Berk us 解释道,“那么它就变成了 Kubernetes 对象。”。这意味着它可以通过 Kubernetes 界面进行控制。

“人们正在用自己的控制器和自己的后端组件创建自己的 CRD，”Berkus 解释道。“这使得 Kubernetes 能够控制 KVM 虚拟机等。这个 Kubernetes 对象有自己的报告，它接受命令；有些是相同的，有些是不同的。”

“我们一直致力于将 Kubernetes 中任何人都想使用的东西转化为 API，”他说。“如果有人将 Kubernetes 转变为一个 HPC 平台，这些人会想要一些在他们的 web 主机上运行 Kubernetes 的人不会想要的东西。有了这种扩展机制，我们就可以填充很多功能。”

在版本 1.11 中，CRDs 获得了对端点监控的支持，以及对 CRD 资源进行版本控制的能力。这意味着 Kubernetes 的 CRD 扩展现在可以提供自己的状态和资源消耗遥测。用户还将能够更好地跟踪他们的 CRD，因为它们是版本化的，并以滚动升级的方式在集群中推出。Berkus 说，在未来，团队可能会在他们的集群中运行多个 CRD，因此需要有工具来管理、控制和监控这些资源。

[云本地计算基金会](https://www.cncf.io/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>