# OpenStack 'Stein '承诺在 5 分钟内完成 Kubernetes 部署

> 原文：<https://thenewstack.io/openstack-stein-focuses-on-kubernetes-bare-metal-nfv-and-more/>

在下个月于丹佛举行的[开放基础设施峰会](https://www.openstack.org/summit/denver-2019/)之前， [OpenStack](https://www.openstack.org/) 发布了 [Stein](https://www.openstack.org/software/stein/) ，这是其开源云基础设施软件的第 19 个同名版本。Stein 带来了数十项增强功能，包括裸机网络和管理的新功能、使用 GPU 运行高性能工作负载的能力、改进的容器和 Kubernetes 功能，以及支持 5G、边缘计算和网络功能虚拟化(NFV)用例的网络升级。

OpenStack 基金会执行董事[黄邦贤·布莱斯](https://twitter.com/jbryce)解释道:[这一版本体现了云的发展轨迹。](https://www.openstack.org/foundation/)

Bryce 说:“当我们开始使用云时，无论是 AWS 还是 OpenStack 或其他什么，我们都主要关注计算层的虚拟化。“随着时间的推移，我们虚拟化了存储、网络，然后应用程序开始容器化，我们开始将它们分发到边缘位置。当您查看 OpenStack Stein 版本时，您会发现这体现在社区在过去六个月中所做的一些工作中。”

OpenStack 目前在一份公司声明中“为超过 75 个公共云数据中心和数千个私有云提供支持，规模超过 1000 万个计算核心”。云服务提供商[vexhost](https://vexxhost.com/)已经在生产中使用 Stein。

Stein 的部分重点是为最终用户带来增强的 Kubernetes 功能，这体现在 OpenStack 认证的 Kubernetes 安装程序 Magnum 的性能大幅提高，该程序将每个节点的容器部署时间从 10-12 分钟减少到 5 分钟，而不管节点数量如何。Bryce 解释说，这是 OpenStack 社区发展方向的结果。

“在我们做的最近一次调查中，61%的人说他们在运营 Kubernetes。自从 Kubernetes 出现以来，这个数字一直在稳步增长，”布莱斯说。“我认为这说明了一个事实，即容器和 Kubernetes 正在真正成为主流，并获得了大量的采用和关注。在 OpenStack 世界中，社区一直致力于为 Kubernetes 提供真正强大的支持。现在，在大约五分钟内，您就可以在 OpenStack 云中部署非常大规模的 Kubernetes 环境。能够说你可以在五分钟内从零到大规模 Kubernetes，这是人们可以利用的一个很好的功能。”

Stein 的另一个突出特点是其通过 OpenStack Ironic 改进的裸机功能，允许用户控制从 bios 到操作系统到网络配置和存储的一切。Bryce 说，OpenStack 近年来随着这一功能的增加，裸机部署的数量也在增加。Vexxhost 首席执行官 Mohammed Naser 解释说，作为云服务提供商，裸机提供了灵活性和性能，而容器消除了某些级别的虚拟化需求。

“有一种在裸机上运行并避免任何中间层的文化。通过在裸机上运行你的容器，你消除了一个不再需要的层。你通常会在虚拟机内部运行应用程序，这就是你如何进行分离的。现在你在容器中运行你的应用程序，”Naser 说。“所以突然之间，虚拟机不再有任何意义了。如果你要跨容器运行和扩展你的基础设施，你最好跳过一层复杂性，直接在裸机上运行。”

Naser 也是 OpenStack 技术委员会的主席，他也在一份声明中表示，Stein 在易用性方面已经超越了其前辈，Vexxhost 在发布日之前的生产使用就是一个例子。

“几年前，不难找到用户或行业观察家告诉你 OpenStack 很难部署和升级。对代码的稳步改进和增加操作者友好的特性使得升级到最新版本成为一个简单、易管理的过程。“老生常谈的抱怨‘open stack 很难’已经不复存在，作为证据，我们已经使用 OpenStack Ansible 向我们的生产客户交付了 Stein，在发布日为他们提供了该软件的新特性和功能。”

开放书库基金会是新书库的赞助商。

来自 Pixabay 的 David Mark 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>