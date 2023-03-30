# Weave Ignite 为虚拟机带来了容器 GitOps 体验

> 原文：<https://thenewstack.io/weave-ignite-brings-a-container-gitops-experience-to-vms/>

在加入芬兰军队之前，[Lucas kld strm](https://fi.linkedin.com/in/luxas/en)一直致力于 Kubernetes。作为 SIG 集群生命周期的联合负责人，他领导了 kubeadm 工具，用于构建从开始到全面可用的 Kubernetes 集群。当他参军时，他带来了他的兴趣和技能，但“特殊要求”决定了他使用虚拟机(VM)而不是他已经习惯使用的云原生工具。kld strm 求助于亚马逊的鞭炮管理程序，并构建了后来成为 Ignite 的前身的东西，这是他在服完兵役后作为 Weaveworks 的一名员工构建的。

本月早些时候在[发布的](https://www.weave.works/blog/fire-up-your-vms-with-weave-ignite)alpha、 [Weave Ignite](https://github.com/weaveworks/ignite) 是一个开源 VM，具有容器 UX 和内置 GitOps 管理，它将[鞭炮微管理](https://aws.amazon.com/about-aws/whats-new/2018/11/firecracker-lightweight-virtualization-for-serverless-computing/)与 Docker / [OCI 映像](https://github.com/opencontainers/image-spec)结合起来，以统一容器和 VM。在接受新堆栈采访时，kld strm 解释说，Ignite 为虚拟机世界带来了许多云的固有优势。

“我们的想法是，我们需要一种简单的方法来运行真正快速和安全的虚拟机，使用的工具与您在容器世界中使用的工具相同，本质上是一种运行虚拟机的云原生方式。“我们发现鞭炮真的很擅长运行虚拟机，”kld strm 说，“它在几分之一秒内启动，它非常小巧轻便，非常适合容器环境。Ignite 的想法是在 bracket 的基础上构建一个更高的层次，通过 CLI 实现 Docker UX，并为 bracket 和类似 VM 工具的最终用户提供良好的体验。”

至于 GitOps 管理部分，Ignite 使您可以像 Kubernetes 和 Terraform 一样以声明方式自动管理虚拟机，weaver works CEO[Alexis Richardson](https://uk.linkedin.com/in/richardsonalexis)说这使它与众不同。

“这是虚拟机和容器世界统一的又一步。它的关键作用是帮助你布局虚拟机，在这方面，它有三个明显的优势，”理查森说。“首先，它有我们从 Docker 那里了解到的熟悉的用户体验。第二，它继承了庞大的 Docker 生态系统，这意味着启动 Ubuntu 镜像或联网变得更加容易。第三，我们将通过 Kubernetes 和 containers 了解到的运营管理理念应用于虚拟机，我们认为这是一种创新，可以更轻松地提供开箱即用的 GitOps 托管集群。”

## OpenStack 的替代品？

目前，Ignite 是在 Apache 2.0 许可下开源的，托管在 Weaveworks 的 GitHub 上，但 Richardson 表示，该项目的未来仍有待确定，云原生计算基金会(CNCF)和亚马逊的鞭炮组织都在可能的家园之列。目前，他说该项目将作为一个社区项目运行，直到它获得更多的临界质量，但他理解不同社区的成员有几个原因的投入的需要。

“我们已经看到了一家公司试图垄断一个容器和虚拟机实施的情况，它总是以糟糕的结局告终，因为没有人希望堆栈的这一层由一家供应商控制。理查森说:“如果多人一起努力，它更有可能成为普遍有用的东西。”。“我们可以拥有一个基于 Ignite 虚拟机的良好运营数据中心，但现在我们的愿望是快速、简单的测试和演示，这已经是一件非常有用的事情。其他人可能有他们自己的用例来驱动一个好的社区。”

作为 alpha 版本，Ignite 仍处于早期阶段，但 Richardson 和 kld strm 都表示，他们可以想象许多潜在的用例。在博客文章中，Richardson 列出了几个问题，例如以“闪电般的速度”设置大量安全虚拟机，用于测试、CI 和短期工作负载，甚至在轻量级虚拟机中运行传统和特殊应用程序，以实现多租户或“使用怪异/边缘内核”。

“你可以想象 Kubernetes 运行虚拟机作为 OpenStack 的潜在替代品。这不是我们想要做的事情。我们认为它现在实际上还不能用，但是一旦你可以像管理容器一样管理虚拟机，为什么不试试呢？”理查森说。“我认为那里有很大的潜力。因为虚拟机非常轻量级，所以您可以想象将它们与一个完整的打包应用程序集中在一起，这样您只需在命令行键入一个命令，就可以启动某些应用程序，而其他所有应用程序都不会打包。”

CNCF 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>