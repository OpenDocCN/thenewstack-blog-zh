# Piston Cloud 构建可替代平台的明智之举

> 原文：<https://thenewstack.io/piston-clouds-smart-move-to-build-a-fungible-platform/>

[Piston Cloud Computing](http://pistoncloud.com/2015/04/introducing-cloudos-4-0/) 宣布其 Piston CloudOS 4.0 超越 OpenStack，Piston Cloud OS 4.0 是一种用于数据中心的操作系统，可将商用服务器集群转变为单一的统一环境。

到目前为止，这家总部位于旧金山的 4 岁公司一直致力于让部署 OpenStack 像下载应用程序到智能手机一样简单。新版本的 CloudOS 将该功能扩展到裸机上的 Hadoop 和 Spark，并计划在年中添加容器编制器 Kubernetes、Mesos 和 Docker Swarm。

首席执行官 Jim Morrisroe 将 Piston 描述为“集群编排和分布式系统自动化公司”,专注于云原生，由 VMware、n as a 和其他一直是 OpenStack 社区成员的人组成。

他说，Piston 带给市场的主要东西之一是，客户可以随着行业的变化而改变，而不必重建或购买新的基础设施。

“CloudOS 的工作方式是，你可以按下按钮部署 OpenStack 等基础设施，但这些基础设施仍然是可替代的，”他说。

“因此，如果您想要将 OpenStack 从 40 个节点缩减到 30 个节点，并在裸机上的这 10 个节点上放置 Spark，您可以通过单一操作完成，无论是从命令行还是在 UI 上。因此，如果 Kubernetes 起飞了，而 Docker Swarm 没有，如果你做出了错误的选择，这些东西在 CloudOS 级别上都变得非常可插拔和可替换。”

该公司宣传 CloudOS 是现代数据中心唯一的整体操作系统，包括主机操作系统、启动软件、资源管理器和服务管理器。此外，它还表示允许客户:

*   动态地将资源无缝地重新分配给数据中心内的多个框架和服务。

*   监控、调整、扩展和优化集群，为数据中心资源提供前所未有的可见性。

其客户包括瑞士电信、美国农业部、Zulily 和国王数字娱乐公司。它由 True Ventures、Hummer Winblad、Swisscom Ventures、Cisco Systems、Data Collective 和 Divergent Ventures 资助。

纯粹的 OpenStack 公司之一 Nebula 上周在[关闭，说明了初创公司在与财力雄厚的惠普、红帽、思科、IBM 和 Rackspace 竞争时遇到的困难。](http://www.networkworld.com/article/2905673/cloud-computing/openstack-company-nebula-shutters.html)

Morrisroe 说，Piston 大约一年前开始致力于这个新的愿景。

“所有传统提供商都加入了 OpenStack，社区发生了巨大的变化，从原生云转向传统的运营效率，某种程度上是因为他们的客户就在那里。…亚马逊、谷歌和 Azure 正在进行大量的云原生。他们不会从那些传统供应商那里购买任何东西，”他说。

“这个支点迫使我们说，OpenStack 擅长什么，我们如何使用它？但更重要的是，云原生部署还需要哪些工具？”他解释道。

“显然，容器是不可忽视的，大数据和 Hadoop 部署本质上是分布式系统，并在应用程序中内置了冗余，它们肯定是与云原生应用程序类似的环境。因此，随着 OpenStack 转向过去，拥抱这些工具成为了 CloudOS 的一个非常明显的扩展。”

IDC 云计算和虚拟化系统软件研究经理陈美威表示，Piston 的战略是一项重大举措。OpenStack 已经成为一个拥挤的市场，一个正在商品化的市场。

“为了建立一个可行的业务，供应商需要在 OpenStack 上和周围建立一个解决方案堆栈；OpenStack 本身已经不再是一门生意了。这就是 Piston 正在做的事情，构建一个可以托管 OpenStack 以及许多其他云平台和服务的平台。”

12 月，该公司宣布与平台即服务(PaaS)供应商 Apprenda 建立合作伙伴关系，帮助软件开发团队构建 Java 和。NET 云应用和微服务。

Kusnetzky Group 的创始人 Dan Kusnetzky 表示，他发现 Piston 最有趣的 OpenStack 功能之一是一个小型、严格控制、高度安全的虚拟机管理器，名为 [Iocane](https://www.zdnet.com/article/piston-cloud-adds-iocane-micro-os-to-openstack/) 。它将进程放在一个非常小的虚拟环境中，并控制进程如何访问系统和彼此。

他说，在他的研究中，Piston 的客户报告了在内部云环境中部署 OpenStack 的出色服务。

他表示:“看起来，在竞争环境下，他们在打‘我们规模更小，所以我们能更快做出反应’这张牌。”。

这是活塞的明智之举。它认可 OpenStack 的转换。但更重要的是，它认识到客户正在开发以数据为中心的体系结构，他们需要一种简单的方式来实现这一点。客户依赖开源社区，因此他们可以尝试新技术。但是他们也需要可替换的、松散耦合的平台。他们需要灵活地将集群划分到混合环境中，这些环境可能包括 OpenStack、Hadoop 或 Kubernetes 等编排服务。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/artlandstudio/6540856679/in/photolist-5og1fG-eCAXzD-9o2Qv8-aXZAP2-ieREYL-eCE8XL-5Fp5xi-eCE8g9-aDyPAi-ieRyx7-4huUF-pRkEqU-pCvXfV-7qtFF-2cJFv2-qMQahu-qb8rBZ-73tFNV-pRkEU9-pVBF5g)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>