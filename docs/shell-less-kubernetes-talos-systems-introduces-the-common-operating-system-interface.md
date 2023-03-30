# 无外壳 Kubernetes: Talos Systems 引入了通用操作系统接口

> 原文：<https://thenewstack.io/shell-less-kubernetes-talos-systems-introduces-the-common-operating-system-interface/>

按照惯例，我们在标准的 Linux 发行版上运行 Kubernetes。例如，有运行在[红帽企业 Linux (RHEL)](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux) 上的[红帽](https://www.openshift.com/try?utm_content=inline-mention)和运行在 [SUSE Linux 企业服务器(SLES)](https://www.suse.com/products/server/) 上的[牧场主](https://rancher.com/)和 [SUSE 容器作为服务平台。但是，你不必这样做。Talos 系统公司采取了一种完全不同的方法。其固执己见的特定于容器的操作系统(CSOS)Talos OS 完全由应用编程接口(API)驱动，现在 Talos 希望在新的通用操作系统接口(COSI)项目下标准化 API 驱动的操作系统。](https://www.suse.com/)

Talos 在本周举行的[kube con+CloudNativeCon 2021](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)上虚拟展示了这项技术的最新成果。

在潜入 COSI 之前，你需要了解塔罗斯是怎么回事。根据 Talos 的首席执行官史蒂夫·佛朗西斯的说法，在 CSOS 上运行 Kubernetes 比在通用的 Linux 上运行更好，因为它避免了不必要的开销，也避免了缺乏与 Kubernetes 的任何内置协调。

另一方面，CSOS 可以避免这些问题。正如[国家标准与技术研究所(NIST)](https://www.nist.gov/) 所述:“特定于容器的主机操作系统是一种[极简操作系统，明确设计为仅运行容器，](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-190.pdf)禁用所有其他服务和功能，并采用只读文件系统和其他强化措施。当使用特定于容器的主机操作系统时，攻击面通常比通用主机操作系统小得多，因此攻击和损害特定于容器的主机操作系统的机会较少。因此，只要有可能，组织应该使用特定于容器的主机操作系统。”

塔罗斯操作系统，跟随最初的科洛斯(T2)的脚步，将不变的基础设施(T4)发挥到了逻辑的极致。没有 SSH 或控制台访问。一切——我是说一切——都是 API 驱动的，并且是为运行 Kubernetes 而专门设计的。甚至连 Linux 系统也被重写，只为了做一件事:启动 Kubernetes。其他一切，比如用户定义的服务，都必须通过 API 或 Kubernetes 来管理。

通过 COSI，Talos 希望使用 Talos 作为模型来标准化分布式系统的下一代 Linux 发行版。

在这个项目中，COSI 的目标是为操作系统交互定义一个新的 API 接口。通过使用支持操作系统声明性配置的 Kubernetes 风格的 API，您将能够控制 DNS 解析、内核参数、挂载点、网络配置等的设置。像其他声明性模型一样，您在 COSI 模型中定义您想要的操作系统配置，并且您的操作系统控制器会将它的设置驱动到您想要的状态。

[Kris Nóva](https://www.linkedin.com/in/kris-nova/) ， [Twilio](https://www.twilio.com/) 高级首席软件工程师解释说:“用户领域存在明显的空白，管理支柱(存储、网络、运行时)不一致。COSI 是我们为运行在分布式环境中的操作系统定义清晰界面的机会。这样做，我们迈出了第一步，要求完全控制 Kubernetes 中的用户区域，而不是我们今天看到的操作系统支柱的部分控制。”

如果这听起来很熟悉，那应该是。正如 Talos 软件工程师 Sean McCoy 解释的那样，“COSI 的一个主要概念是资源和控制器的使用。控制器使用资源(静态或动态)不断尝试达到期望的状态。这个概念是 Kubernetes 本身的核心，也是自愈和分布式系统的重要设计概念。它也恰好为操作系统提供了非常好的东西。”

其他的，传统的方法如 [kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/) 和[控制器-管理器](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-controller-manager/)，因为它们天生就更脆弱。两者都不会从运行的 Kubernetes 配置中得到反馈。对于 kubeadm，这使得再现运行配置变得困难。而且，使用 controller-manager，您可能会遇到这样的情况，即“更新被推出并继续推出，在坏的组件有机会表明它们实际上是坏的之前，用坏的组件替换好的组件。”

现在，将这些相同的概念应用到底层的 Linux 操作系统中，可以更容易地快速构建安全的 Kubernetes 集群。弗朗西丝在博客中写道:

*有了 Talos (COSI)管理的控制平面，即使是单个控制平面节点集群现在也变得坚如磐石，Kubernetes 可以安全简单地升级。您的所有控制平面配置都是以声明方式管理的，COSI 将不断驱动状态以匹配声明的配置。COSI 给 Talos 带来的另一个好处是，Talos OS 现在可以对机器配置的某些部分做出反应:Kubernetes 控制平面可以在不重启的情况下重新配置，并且坏的更改可以很容易地恢复。*

其他人会加入 Talos 的行列，对 Kubernetes 和 Linux 堆栈都采用 COSI 的方法吗？敬请关注。我们很快就会知道了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>