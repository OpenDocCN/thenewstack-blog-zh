# Portworx 提供了管理有状态应用程序的容器级方法

> 原文：<https://thenewstack.io/portworx-provides-container-level-approach-stateful-applications/>

Portworx 通过提供一种自动化的、 [DevOps](/category/devops/) 风格的方法来解决持久性和运行有状态应用程序的其他关键问题，在容器网络和存储领域取得了成功。

像 Mesos、[、Kubernetes](/category/kubernetes/) 或 Docker Swarm 这样的调度器提供了在多个节点上管理容器的能力。但是，据首席执行官兼联合创始人 [Murli Thirumale](https://www.linkedin.com/in/murlithirumale/) 称，开发者仍然面临着大量“如何做”的问题:

当 Docker 容器从一个节点移动到另一个节点时，我如何确保数据的持久性？我如何确保数据的高可用性？我如何确保每个容器获得所需的 IOPs 性能？我如何保护我的数据？如何在我的容器环境中自动实现这一点？

他说，Portworx 本身运行在一个容器中，允许开发者管理数据服务，就像他们用 Docker 或 Mesos 部署应用程序一样。

“它不是依附于旧基础设施的东西；这是 DevOps 工作流程的一部分。一切都是为容器专门构建的，所以所有的数据功能——持久性、性能、高可用性——都是在每个容器或每个应用程序的基础上进行管理的，”他说。

他说，它可以运行在任何云或任何本地服务器架构上，并且无论基础设施如何，都将以相同的方式运行。

Portworx 提供容器级快照、复制和存储策略；多集群可见性和管理；预测能力管理；和全局文件命名空间。

Thirumale 喜欢将 MySQL 容器与运行在同一台主机上的 WordPress 容器进行类比。MySQL 可能需要更高的存储性能、更好的数据保护和更频繁的备份。由于事务性很强，它可能比 WordPress 容器使用得更频繁。诀窍是以自动化的方式为每个容器提供它所需要的东西。

他这样解释波特沃克斯:

“在节点上，我们创建一个聚合节点……然后从存储的角度对该节点下的所有内容进行指纹识别。我们查看任何连接的存储，并将其转变为一个大型池。将所有存储聚合到一个大型数据块池中。然后，我们可以将其分为高、中、低性能层。然后，我们研究容器生态系统，并能够根据每个容器的应用程序需求划分虚拟卷。然后把它直接连接到那个容器上。”

它使数据在所有节点上都可用，无论数据驻留在哪里，因此当新容器启动时，它可以找到数据。

## 云原生

Portworx 平台与一个调度程序(Mesos、Docker Swarm、Kubernetes)紧密集成，因此尽管它是单独部署的，但数据是通过该调度程序管理的。这一切都是作为 DevOps 工作流的一部分在带内完成的，并且是完全自动化的端到端操作。

这是一个云原生解决方案。他说，旧的存储阵列制造商基本上是在为容器构建 Docker 或定制设备的连接器，这种方法实际上无法扩展到数千个节点。

Gartner 的一份报告指出，人们对有状态应用程序的共享存储基础架构选项越来越感兴趣，根据这份报告[的说法，在企业中采用容器来处理生产工作负载的最大障碍之一是保持数据的高可用性和数据保护。它称集装箱存储基础设施市场为“商业模式不清晰的混乱市场”](https://www.gartner.com/doc/3597439/docker-containers-impact-enterprise-storage)

[Sapphire Ventures](http://sapphireventures.com/) 董事总经理 [Jai Das](https://twitter.com/jai_das?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) 指出，手动调整基础设施和定制脚本来维护有状态容器的持久性，抵消了能够快速启动容器的好处。Portworx 消除了有状态应用程序将存储卷映射到主机的需要，而是提供了对共享存储池的自动访问，他在一篇博客文章[中解释道，概述了其在最近一轮 2000 万美元融资中的原因。](https://medium.com/sapphire-ventures-perspectives/portworx-enabling-devops-to-build-and-manage-stateful-container-based-applications-6c10cb18b941)

他说:“支撑其产品的理念是，存储管理和配置应该既简单又全面，既能满足 DevOps 对简单性和可扩展性的需求，又能满足安全性和性能可靠性等企业 it 需求。”。

通用电气在其 [Predix](https://www.ge.com/digital/predix) 平台中使用 Portworx，该平台提供给希望提供自己物联网服务的客户。

它也用于汉莎航空公司的 BoardConnect 娱乐系统，该系统提供给全球 300 家航空公司。每个网站都有自己的内容管理系统，运行在 Azure 云上。他说，汉莎航空公司对服务的可用性和性能提出了很高的要求，但也希望它不受云和存储的限制，并提供内部选项。

## 历史

这家总部位于加州洛斯阿尔托斯的公司是由 Ocarina Networks 的创始团队于 2014 年创立的，Ocarina Networks 是一家存储优化公司，于 2010 年被戴尔收购。其最近的融资使投资总额达到 2850 万美元。

“企业终端用户对容器应用程序的数据持久性的需求和关注似乎越来越多，”451 Research 分析师 Jay Lyman 说。“Portworx 等供应商对此做出了回应，因为随着容器应用程序从 web 和无状态应用程序转向数据库和其他以数据为中心的应用程序，以及从开发和测试转向生产，这种需求也在增加。”

它的竞争对手包括像[迪亚曼蒂](https://diamanti.com/)、[赫德威格](https://www.commvault.com/software-defined-storage)、[罗宾系统](https://robinsystems.com/)和[存储系统](http://storageos.com/)这样的公司。

在去年夏天撰写的一份报告中，Lyman 指出，Portworx 支持快速部署有状态的分布式应用程序，允许 DevOps 以一种以容器为中心的方式自动化存储供应，但该公司可能需要开源其一些软件。

“我们相信，超越特定厂商的社区软件将在这个市场赢得最大的吸引力，”他写道。

Portworx 是包括 Docker、Kubernetes、Mesosphere 和 Cloud Foundry 在内的一个团体之一，他们正在讨论[容器生态系统是否会受益于用于寻址和管理存储卷的标准化 API](https://thenewstack.io/containerization-leaders-explore-possible-data-storage-interface-initiative/) 。被称为容器存储接口倡议，目前它基本上是 GitHub 文档。

该小组的第一次辩论是关于编排者或调度者是否应该承担数据容器或数据量生命周期管理的角色。

Thirumale 说:“我们真的认为，存储决策更多地是由应用程序的需求而不是调度程序的需求驱动的。

[Cloud Foundry](https://www.cloudfoundry.org/) 是新堆栈的赞助商。

专题图片:[莫言·布伦](https://www.flickr.com/photos/aigle_dore/)的《日落极光》，授权于 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>