# 收购有利于开发者生态系统

> 原文：<https://thenewstack.io/acquisitions-are-good-for-the-developer-ecosystem/>

今天有很多关于收购和合并的讨论，尤其是在技术领域，对于参与其中的人来说，这可能会感到非常不安。但最终，一次成功的收购真的会成为社区的财富。

我不一定要谈所有的收购，但作为 Docker 当时的工程总监，我可以谈谈 Mirantis 对 Docker Enterprise 的收购，以及该公司对 Lens 的收购，后者是最初由 Kontena 开发的 Kubernetes 平台，以及它在过去两年中为开发人员和 Kubernetes 生态系统带来的巨大好处。

## “之前”状态

 [尼克·蔡斯

Nick 是 Mirantis 的技术和营销内容主管。他是一名前软件开发人员，Oracle 讲师，数百本教程的作者，以及十几本关于各种编程主题的书籍的作者或合著者，包括*理解 OPNFV* 、 *OpenStack 架构指南*和*面向普通人的机器学习*。](https://www.linkedin.com/in/nickchase/) 

我们先来看看收购前的生态系统状态。

在收购之前，大多数容器开发人员，包括使用 Kubernetes 的开发人员，都在使用 Docker 软件的社区版，这很棒。Docker 企业平台是一个很棒的产品，但是有一种广泛持有的——也是不正确的——观点认为它只适用于那些想要使用 Swarm 的人，如果你想要 Kubernetes，你必须去别的地方。Swarm 本身也被错误地认为是 Kubernetes 的失败竞争对手，而不是它被设计成的更简单的替代品。

此外，Docker Enterprise 是一个单集群工具；虽然您可以使用它在任何云提供商上创建 Swarm 或 Kubernetes 集群，但您不能使用它来创建多集群或多云环境。

所有这些导致了第二个连锁效应:containerd 从 dockerd 中提取并诞生，并开始取代它在 Kubernetes 中的用法，因为它是作为容器运行时专门构建的。社区最终否决了与 Docker 运行时交互所需的 dockershim 代码。(Docker 容器仍将在 Kubernetes 中运行，但有一部分用例需要这些代码，比如安全容器运行时。)

那是在服务器端。在开发人员方面，最初由一个小型但创新的云原生技术先锋团队开发的 Lens IDE 正在获得发展势头。当时，大多数开发人员还在纠结于 kubectl 和 YAML 文件，并首先学习如何使用 Kubernetes。Lens IDE 消除了复杂性，使新用户更容易学习 Kubernetes，并提高了更有经验的用户的工作效率。然而，来自一个资源有限且没有盈利能力的小公司是一个问题。

同时，Mirantis 在 OpenStack 领域非常成功。该公司没有放弃 OpenStack 的计划，但很明显，Kubernetes 正在成为云计算行业的标杆。

对于所有三家公司来说，都必须做出一些让步。

## “之后”状态

我不会说实际的收购不令人兴奋；任何收购都是。(好的，收购我们的镜头团队，发生在 Docker Enterprise 之后不久，相当顺利，因为他们是由 Miska Kaipiainen 领导的一个小团队，Miska Kaipiainen 现在是米兰蒂斯产品工程副总裁，他说:“米兰蒂斯的工作方式与我们非常相似，所以我们只是继续做我们正在做的事情。”)但现在，两年多一点后，我们可以看到它的结果，以及它不仅为相关各方，而且为整个生态系统带来的好处。

Docker Enterprise 已被重命名为 Mirantis Kubernetes Engine，它现在已经成为 Kubernetes 工具，但不仅如此，它目前还可以单独使用，并作为 Mirantis Container Cloud 的一部分，Mirantis Container Cloud 提供 GUI 和 API 驱动的方法，用于控制多个公共云提供商以及内部云基础架构上的多个集群。而且都是“免费增值”模式。

当 Docker Enterprise 收购案发生时，客户担心对 Swarm 的支持会停止，鉴于其声誉，这似乎不是没有道理的。但是相反的事情发生了；Swarm 经历了一次复兴式的开发，包括一个新的容器存储接口。即使是 Mirantis Kubernetes 引擎也有一个(不可否认令人困惑的)“群体专用”模式。

社区和企业空间都有明显的改善；客户互动的净推广得分(NPS)上升了 40 分。

Kubernetes 本身现在有了一个 Docker 运行时的前进方向，它与 Mirantis/Docker Inc .建立了合作伙伴关系，最初致力于维护 dockershim，并已导致容器运行时接口符合 FIPS 140-2 安全标准的 Mirantis 容器运行时。

而镜头呢？这个小程序现在是一个开源的发电站，每月有近 50 万次下载和 50，000 名活跃用户。Lens 现在在其 Kubernetes 友好的 IDE 中添加了 Spaces 和 development clusters，这使得集群的共享变得更加容易。

所以总的来说，受益的不仅仅是个别公司，甚至不仅仅是 Docker Enterprise(现在的 Mirantis Kubernetes Engine)的客户；因为 Lens 是开源的，所以整个开发者社区现在可以更容易地使用 Kubernetes，从而减少压力，加快开发速度。

## 总结

我知道这次收购对前 Docker Enterprise software 及其客户有多重要，但我问了一下这对 Lens 和 Kubernetes 社区意味着什么，他说得很清楚。“哦，那很容易，”他说。“在业余时间维护一个重要的开源项目非常困难。如果我们没有与 Mirantis 联手，Lens 就不会像今天这样存在，Kubernetes 社区也不会从 Lens 获得好处。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>