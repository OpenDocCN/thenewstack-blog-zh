# CRI-O，运行无码头集装箱的项目，达到 1.0

> 原文：<https://thenewstack.io/cri-o-project-run-containers-without-docker-reaches-1-0/>

开源项目 t， [CRI-O](http://cri-o.io/) ，以前被称为 OCID(简称 OCI 守护进程)，它使 Kubernetes 开源容器编排引擎能够在不依赖默认 Docker 运行时的情况下运行容器，现已达到 1.0 状态。

[CRI-O](https://github.com/kubernetes-incubator/cri-o) 允许用户直接从 Kubernetes 大规模启动和管理任何符合[开放容器倡议](https://www.opencontainers.org/) (OCI)的容器，无需额外的代码或工具。

到目前为止，CRI-O 使用 runc 和 Intel 的 Clear Containers 作为容器运行时，但它被设计成允许插入任何符合 OCI 标准的运行时。

该项目“为更容易地在 [kubelet](https://kubernetes.io/docs/admin/kubelet/) 中插入替代的容器运行时打开了大门，而不是依赖默认的 docker 运行时。这些新的运行时可能包括基于虚拟机的运行时，如 runv 和 Clear Containers，或标准的 Linux 容器运行时，如 rkt，” [Red Hat](https://www.openshift.com/) 高级工程师 [Antonio Murdaca](https://twitter.com/runc0m?lang=en) 在 [Project Atomic 博客](https://www.projectatomic.io/blog/2017/02/crio-runtimes/)上写道。

按照最初的设想，该项目将使 Kubernetes 成为容器的完整生命周期管理器，而不需要任何品牌的容器引擎。

创始团队希望使 kubelet 能够与 Docker、 [CoreOS'](https://coreos.com/) rkt、基于中国的容器供应平台 Hyper.sh、CRI-O 等进行通信。

“有许多不同的容器运行时，它们都对与 Kubernetes 交流感兴趣。因此，我们没有试图将每个容器运行时的每个接口都构建到 kubelet 本身中，而是创建了一个更抽象的接口，其他人可以插入其中，而无需直接参与 Kubernetes 的上游工作，[CoreOS 首席技术官 Brandon Philips](https://twitter.com/brandonphilips) 此前向新堆栈介绍了[容器运行时接口](https://github.com/kubernetes/kubernetes/blob/242a97307b34076d5d8f5bbeb154fa4d97c9ef1d/docs/devel/container-runtime-interface.md) (CRI)。这是一个插件[接口](https://thenewstack.io/oci-specification-1-0-arrives/)，让 kubelet 能够使用不同的 OCI 兼容容器运行时，而无需重新编译 Kubernetes。

CRI-O 项目位于 Kubernetes 孵化器中，涉及 IBM、Intel、SUSE 和其他公司的贡献。它支持 OCI 格式和 OCI 运行时，但它本身不是 OCI 项目的一部分。

## 不匹配的版本

该项目被视为容器生态系统分裂的证据，尽管参与其中的人坚持认为它不是“Docker fork”但是当 Docker 开发了自己的编排引擎 Docker Swarm，并将其作为 Docker 引擎的一部分时，社区内部的紧张局势加剧了。

“Docker 被大量集成到 Kubernetes，反之亦然。他们严重依赖特定的版本，这是一种粗糙的界面，”Red Hat Linux 容器高级布道者 Joe Brockmeier 说。

“他们都以不同的速度移动。Docker 的新版本可能会打破 Kubernetes …随着 Docker 试图创新和改变事物，很明显需要一种方法让 Kubernetes 与容器运行时对话，允许容器运行时以自己的速度移动，同时保持与 Kubernetes 兼容，并允许 Kubernetes 以自己的速度工作。”

红帽的[丹尼尔·沃尔什](https://medium.com/cri-o/cri-o-1-0-is-here-d06b97b92a98)在发布的博文中写道:“我们当时觉得上游 Docker 项目变化太快，正在让 Kubernetes 变得不稳定。我们觉得，或许通过简化容器运行时，我们可以做得更好。”

他说，该项目的目标是比其他容器运行时更轻，占用空间更小，并且 Kubernetes 的性能比其他容器运行时更好。

CRI-O 可以从任何容器注册表中提取图像，并使用[容器网络接口](https://github.com/containernetworking/cni) (CNI)来处理网络，这样任何 CNI 兼容的网络插件都可以使用它。

当 Kubernetes 需要运行一个容器时，Kubelet 通过 CRI-O 接口与容器运行时对话。它将与 CRI-O 守护进程对话，然后与容器映像库和存储库对话以获取映像并准备好，在存储上设置它，然后与 runc(或另一个 OCI 兼容的运行时)协调以启动该映像。Brockmeier 解释说，当 Kubernetes 需要停止容器时，CRI-O 也会处理。

“这为什么有趣？我们的回答是，在某种程度上不是。太无聊了，”他说。“作为用户，这是你不必担心的。想做容器编排的人并不真正关心这个层面。如果你在一个 Linux 机器上运行一个脚本，你真的不在乎这个机器是否被设置成使用[科恩谢尔](http://www.kornshell.com/)或者 [Bash](https://www.gnu.org/software/bash/) ，你将会写一个脚本来运行所有这些。如果你有一个兼容 OCI 的容器，你只需要让 Kubernetes 运行它。

“Docker 进行了创新，增加了一系列远远超过这一水平的东西，但对 Kubernetes 来说，这是一种过度的做法。它冒着使 Kubernetes 的容器运行复杂化的风险。

## 不是开发工具

在一篇博客文章中，Brockmeier 解释说 CRI-O 不是构建图像的开发工具。

虽然 CRI-O 包含命令行界面(CLI ),但它主要用于测试 CRI-O，而不是作为一种在生产环境中管理容器的方法。

它一直专注于最近发布的 [Kubernetes 1.7](https://thenewstack.io/kubernetes-1-7-brings-extensibility-security-hardening-network-policy-api/) ，因为 OpenShift 的下一个版本基于该版本。用 OpenShift online 做一些测试，如果进展顺利，可能会在生产中的 OpenShift online 上看到它。它将是 OpenShift 3.7 中的技术预览版。

他说，CRI-O 的第一个版本基于 Kubernetes 1.7，因为下一个版本的 OpenShift 是基于这个版本的。Red Hat 计划对 OpenShift online 进行一些测试，如果进展顺利，客户可能会在生产中的 OpenShift Online 上看到它。他说，这将是 OpenShift 3.7 的技术预览版。CRI-O 的未来版本将与它们支持的 Kubernetes 的版本号相匹配。

尽管这个项目与红帽和[谷歌](https://cloud.google.com/kubernetes-engine)有渊源，但它也鼓励其他潜在的贡献者参与进来。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>