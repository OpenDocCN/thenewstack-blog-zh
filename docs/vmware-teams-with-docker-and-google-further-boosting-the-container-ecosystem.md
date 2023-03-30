# VMware 与 Docker 和 Google 合作，进一步推动容器生态系统

> 原文：<https://thenewstack.io/vmware-teams-with-docker-and-google-further-boosting-the-container-ecosystem/>

VMware 与 Docker 和 Google 合作的消息有一定的真实性。所有美好的事物都会成熟，但最好在为时已晚之前拥抱年轻的新方式。

VMware 今天宣布，它决定拥抱容器技术，并接受 Docker 和 Google Kubernetes 作为集成合作伙伴，而不是压制。 [Pivotal](https://thenewstack.io/docker-is-driving-a-new-breed-of-paas/ "The New Stack") ，也是新闻的一部分，正在拥抱 Docker。

也许是 Docker 接受度的惊人提高刺激了这种广泛的合作关系。这毫无疑问是真的。但从 VMware 的角度来看，此举代表了更多。看看 VMware 的战略，有一个共同的主题:追求数据中心的主导地位，这只能通过开放、可互操作的模式来实现。

VMware 将在其网络和其他产品方面与 Docker 密切合作。此外，VMware 也在拥抱 [Kubernetes，](https://googlecloudplatform.blogspot.com/2014/07/welcome-microsoft-redhat-ibm-docker-and-more-to-the-kubernetes-community.html)加入谷歌两个月前宣布的快速崛起的社区。Kubernetes 为 VMware 提供了一些不同的东西，允许它扩展到另一个网络框架。此外，它允许与 Cloud Foundry 进行更深层次的集成。Kubernetes 和 Cloud Foundry 都运行在 [etcd](https://thenewstack.io/about-etcd-the-distributed-key-value-store-used-for-kubernetes-googles-cluster-container-manager/) 上，这是一种编排容器的配置管理服务。

正如我们两个月前所写的，Kubernetes 是 Google 的一个开源容器集群管理器，它利用了 etcd 分布式键值存储。CoreOs [的 Blake Mizerany 在一篇文章](https://thenewstack.io/about-etcd-the-distributed-key-value-store-used-for-kubernetes-googles-cluster-container-manager/ "The New Stack")中为我们写道:“它(etcd)负责存储和复制 Kubernetes 在整个集群中使用的数据，由于 Raft consensus 算法，etcd 可以从硬件故障和网络分区中恢复。除了 Kubernetes，Cloud Foundry 还使用 etcd 作为他们的分布式键值存储。”

https://www.youtube.com/watch?v=06cTPhi-3_8

集群通常由大量能够在任何给定时间运行任何工作负载的机器组成。为了让集群高效运行，有必要在集群中的所有机器之间适当地分配工作负载。集群需要一种相互协调的方式。

今天，Ben Golub 在接受采访时表示，Docker 将与 VMware 合作进行兼容性测试，以确保有一个基础虚拟机可以运行 Docker。Golub 是 young container 技术公司的首席执行官。这两家公司还将协调 libswarm、libchan 和 libcontainer 的开发。根据 GitHub Docker 页面，libswarm 是一个组成网络服务的极简主义工具包，libchan 是一个超轻量级的网络库，libcontainer 指定了容器的配置选项。

Golub 说:“我们正在努力将 Docker Hub 与 VMware 的管理工具集成在一起。“他们(VMware)也有 Fargo 项目，让虚拟机变得更加轻量和灵活。”

Golub 说，Docker 目前的状态是为可以在少量 Docker 容器中表示的应用程序设计的。“我们想要的是创建应用程序，这些应用程序是为跨多个主机的大量 Docker 容器而构建的。”

Golub 说，VMware 将贡献代码并支持该标准。重要的是——让 libswarm API 背后的人加入正在出现的网络框架。

Docker、VMware 和 Google 之间的合作覆盖了很多领域。它涵盖了从 VMware vSphere 到 VMware vCloud Air，以及在 libswarm、libcontainer 和 libchan 上的协同工作。

对谷歌来说，这种合作关系让它更深入企业内部。VMware 将向其客户提供 Kubernetes 的模式、API 和工具。VMware 还将向 Kubernetes 贡献代码，并使探索容器管理的客户更容易获得 VMware vSphere。

此外还有 Pivotal，其以虚拟机为中心的平台即服务(PaaS)环境岌岌可危。VMware、Pivotal 和 Docker 将添加 libcontainer 集成。这意味着连接 Warden，这是最初为 Cloud Foundry 开发的 Linux 容器，当时它还是一个 VMware 项目。

Red Hat 已经将 Docker 集成到 OpenShift 及其 PaaS 中，并且有许多新的 PaaS 产品使用了 Docker 技术。

VMware 覆盖了它的所有基础。它拥有成熟的技术，在未来一段时间内仍将发挥作用。但是 Docker 是一个强大的年轻竞争对手，现在随着开源的接受而腾飞。有了 VMware，它现在可以打开一个相当大的市场。而谷歌呢？那里有网络连接。这再次表明，VMware 着眼于一种新型的数据中心，这种数据中心需要虚拟机和新容器环境的联网。

图片来自 Flickr 知识共享

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>