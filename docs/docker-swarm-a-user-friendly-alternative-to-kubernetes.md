# Docker Swarm，Kubernetes 的一个用户友好的替代品

> 原文：<https://thenewstack.io/docker-swarm-a-user-friendly-alternative-to-kubernetes/>

对 Swarm 的兴趣正在上升。我们在内部指标、与团队关于 Swarm 支持的对话，以及关于 Swarm 相对于 Kubernetes 的简单性的一系列问题中看到了这一点。

你可能会认为 Docker 创建的开源项目 Docker Swarm 会随着 Kubernetes 的上升而成比例下降，但这并没有发生。事实上，除了影响这两种技术的大流行后的平静期——也许每个人都只是筋疲力尽，正在恢复！正如 Kubernetes 一样，Swarm 也在继续它的上升之旅。

在 [Mirantis](https://www.mirantis.com/?utm_content=inline-mention) ，我们对人们为什么选择使用 Swarm 有很好的感觉，因为我们每天都在生产环境中看到它。超过 100 家 Mirantis 客户使用 Swarm 处理生产工作负载，包括葛兰素史克、大都会人寿、加拿大皇家银行和标准普尔全球。这意味着超过 10，000 个节点分布在大约 1，000 个集群中，支持超过 100，000 个由 Swarm 编排的容器。

JetBrains 的年度软件工具调查发现 [10%的被调查组织](https://www.jetbrains.com/lp/devecosystem-2022/devops/#what-container-orchestration-services-do-you-use-in-production-if-any-)使用 Swarm 管理他们的容器，这个数字在过去几年保持稳定。

[Mirantis Kubernetes 引擎](https://www.mirantis.com/software/swarm/)，它是[Mirantis](https://www.mirantis.com/?utm_content=inline-mention)Swarm 的企业分发版，使客户能够部署 Kubernetes 和 Swarm 节点(或两者都部署)，因此他们可以选择最适合他们的方式。将这些与我们的服务和支持结合起来，以及事实上 [ZeroOps](https://www.mirantis.com/zeroops/) 致力于使我们的客户免于与基础设施作斗争，我们已经在他们所说的话中看到了一些共同的线索。

归结起来就是:随着 Kubernetes 掌握了开发领域，处于软件价值链各个层次的人们不仅认识到了容器化的价值，也认识到了容器编排的价值。Kubernetes 提供了大量的选项，涵盖了广泛的用例——但这带来了大量的复杂性，可能会阻碍快速交付，尤其是在不需要这种复杂性的时候。

进入蜂群。

## Kubernetes 对 Swarm

在许多方面， [Swarm 与 Kubernetes](https://thenewstack.io/kubernetes-vs-docker-swarm-whats-the-difference/) 相似，它们都编排容器化的应用程序。它们都使您能够创建一个包含多个节点的集群，容器化的应用程序可以在其上运行，它们都使您能够以声明的方式定义您希望这些应用程序如何工作。

然而，这两个系统之间存在一些差异，导致一些人选择 Swarm 而不是 Kubernetes。

## 复杂性或易用性

Kubernetes 和 Swarm 之间最明显的区别是复杂性；虽然 Kubernetes 旨在为几乎任何不测事件做准备，但 Swarm 旨在让您尽快启动并运行。这就像专业的 DSLR 相机和你手机上的相机之间的区别，前者几乎可以完成任何事情，但即使是勉强过得去的照片也需要专家的帮助，而后者几乎可以完成普通人拍摄精彩照片所需的任何事情，而不需要学习摄影课程。

这两个系统都依赖于 YAML 标记语言，但是 Kubernetes 使用了对象的概念，例如 pod、服务、部署等等，所有这些都是独立创建的，然后放在一起组成整个应用程序，Swarm 更全面地定义应用程序，以一种人类更可读(和可理解)的方式一次定义所有内容。

Swarm 在其他方面也更简单。例如，Swarm 使操作挑战变得简单一些，因为相同的 Swarm 配置可以在多个环境中运行。Swarm 中的网络也更简单，它可以是一项资产(更容易理解)或一项负债(功能和/或灵活性要小得多),这取决于你试图完成什么。

## 安全性

应用安全是 Swarm 使事情比 Kubernetes 简单的另一个地方，尽管有时是以更复杂的功能为代价。例如，Swarm 包括开箱即用的 TLS 网络，所有访问控制都通过它来处理。因此它很容易使用，但您无法获得 Kubernetes 通过 RBAC、准入控制器、策略等给予您的完整粒度控制。

## 缩放比例

当涉及到扩展基础设施时，Kubernetes 和 Swarm 是可比的 K8s 的最大节点数为 5000，而 Swarm 为 4700——但当涉及到扩展应用程序时，Swarm 也可以使事情变得更简单。Swarm 不包括自动伸缩(Kubernetes 包括)，但它包括使用 DNS 的开箱即用的负载平衡(Kubernetes 需要一个外部组件，如 NGINX Ingress)。

## 生态系统

另一方面，为 Kubernetes 构建的应用程序和组件要比为 Swarm 构建的多得多。回到负载平衡的问题，例如，像 Istio 这样的服务网格通常是为 Kubernetes 而不是 Swarm 构建的。此外，Kubernetes 可以使用任何符合容器运行时接口的容器运行时，其中 Swarm 只使用 Docker 引擎运行时。也就是说，容器运行时的选择不是典型的开发人员会考虑的事情。再次强调，简单胜过额外的功能。

所有这些都引出了一个问题:为什么是现在？

## **为什么是现在？**

那么，如果 Swarm 是一个如此好的选择，为什么我们现在只看到这种激增？根据我们从客户那里看到的情况，我相信这可以归结为几个并发的因素，使得 Swarm 现在成为一个理想的选择。

kubernetes——以及容器编排的想法——不再新奇，已经进入了 Gartner 炒作周期的“[幻灭低谷”阶段](https://thenewstack.io/ubuntu-server-struggles-with-post-docker-kubernetes-installs/)。这意味着它准备好爬上启蒙的斜坡，到达生产力的高原，这意味着大多数人现在都听说过它，知道他们为什么需要它——而且它不一定容易使用。

除此之外，在撰写本文时，世界经济不确定，公司不能或不愿意在员工身上花费超过必要的费用，熟练的集装箱运输人才已经稀缺。在这种环境下，有一个易于使用的工具的位置，这些工具只需很少的准备就可以完成工作。

所有这些使得 Swarm 对那些不需要 Kubernetes 的额外功能的人和那些不需要它们的人都有吸引力*。*

 *幸运的是，现在使用 Swarm(或针对某些工作负载)并不排除同时或未来使用 Kubernetes。“如果你已经在容器中了，”[我们的一个客户告诉我们](https://www.mirantis.com/cloud-case-studies/societe-generale/)，“从 Swarm 迁移到 Kubernetes 并不复杂。”

事实上，采用 Kubernetes 并不一定代表一个难度峰值；Swarm 可以作为使 Kubernetes 开发更容易的工具(如 Lagoon、Knative 等)的垫脚石，或者作为 Kubernetes 培训的垫脚石，使您的开发团队轻松进入更复杂的容器编排。

## 最后一句话(暂时)

Swarm 在云原生生态系统中为自己定义了一个易于使用、安全的容器编排器，可以作为那些还不需要 Kubernetes 所有功能的人的培训场所(现在)。那么，为什么我们看到对 Swarm 的兴趣在上升呢？因为随着云原生范式变得正常化，以及财务问题的出现，现在是仔细评估工具箱中所有工具并选择适合特定工作的工具的好时机。

对我们许多人来说，这个工具就是 Swarm。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*