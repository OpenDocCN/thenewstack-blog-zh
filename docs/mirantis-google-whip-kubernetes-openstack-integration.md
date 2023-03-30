# Mirantis，Google Whip Up Kubernetes，OpenStack 集成

> 原文：<https://thenewstack.io/mirantis-google-whip-kubernetes-openstack-integration/>

Mirantis 计划在本周展示一个 Kubernetes 与 OpenStack 的集成，这是它与谷歌合作的结果。该集成自动化了底层基础设施的创建和配置，允许开发人员只需点击几下鼠标就可以在 OpenStack 上部署 Kubernetes 集群。该项目使用 Murano(open stack 中的应用程序目录)来部署和配置 Kubernetes 集群，并将 Docker 容器部署到这些集群中。

“企业不一定拥有谷歌那样的工程人才，但他们非常希望使用 Docker 等容器技术来加速软件开发周期。因此，我们所做的是将谷歌在大规模管理容器方面的专业知识与 Mirantis 在构建和运行大型云方面的经验结合起来，从而让企业充分利用容器技术，”Mirantis 首席执行官 Adrian Ionel 说。

他说，除了使管理容器变得更加容易，混合云还允许内部部署和谷歌云部署来管理可以在公共云和私有云之间移动的工作负载。

“企业需要一个容器故事，它具有企业期望的安全性、网络和存储功能，并且非常易于使用，这正是我们推向市场的内容，”Ionel 说。“谷歌也证实了 OpenStack 是企业正在标准化的私有云技术。”

## 易于配置

Murano 应用商店允许开发者为 Kubernetes 集群自动配置底层网络；它还为 OpenStack 负载平衡器和防火墙提供集成，并添加了监控和日志收集服务。

Kubernetes 的任务包括提供实现 Docker 服务的 pod，监控 pod 的可用性和负载，以及根据 Kubernetes 的配置放大和缩小 pod。根据 Mirantis 的博客文章，它使用 OpenStack 的 Heat orchestration 来提供 Kubernetes 需要的资源，并协调 pod 和底层基础设施之间的连接。

米兰蒂斯将于周三在[湾区 Kubernetes meetup](http://www.meetup.com/Bay-Area-Kubernetes-Meetup/events/220167517/?a=ea1_grp&rv=ea1&_af_eid=220167517&_af=event) 展示这项新技术，并在之后发布视频。Ionel 说，虽然它宣布了集成，但它还不是产品级的。据该公司称，它已经证明可以启动一个小型 Kubernetes 集群，并在该集群上运行一种特定类型的应用程序，但尚未进行大规模和跨不同场景的测试。

它计划在 4 月份发布技术预览版，并在几个月后发布企业级产品。

## 叙旧？

伦敦 CohesiveFT 首席技术官克里斯·斯旺(Chris Swan)认为，这种整合是对谷歌、微软、IBM 和其他公司宣布的基于公共云 Kubernetes 的服务的回应。

“这一切都是为了让 OpenStack 与这些环境对等，”他说。

事实上，IBM、Red Hat、VMware、Docker、Mesosphere、CoreOS 和 SaltStack 都有 Kubernetes 项目。举例来说，惠普也将 Kubernetes 与 OpenStack 相结合。

研究公司 IDC 的云和虚拟化系统软件研究经理陈美威指出，尽管最近有人担心供应商可能会通过他们的 OpenStack 产品锁定客户，但市场上有大量的 OpenStack 项目。

他说:“任何供应商都可以利用开源项目，创造任何他们想要的商业产品，开放的或封闭的，以及介于两者之间的任何产品。”。

谷歌产品经理 Kit Merker 说，自从 Kubernetes 成为开源软件以来，谷歌对它的使用表现出了极大的兴趣和兴趣。

当被问及公司是否对供应商使用它的方式感到满意时，他说:

“让 Kubernetes 开源意味着公司直接从用户那里获得反馈。我们有更多的手和眼睛在为我们的软件工作，所以它让我们从用户的角度看到事情的发展。维护项目会带来一定程度的控制，但人们可以根据我们的许可协议，以他们想要的任何方式自由获取和使用软件。”

## “纯粹的游戏”

Mirantis 自称是一家“纯粹的”OpenStack 公司，已经帮助思科、康卡斯特、DirectTV 和其投资者之一爱立信等公司建立和部署了一些最大的 OpenStack 云。

Ionel 表示，该公司去年 10 月宣布了由 Insight Venture Partners 牵头的 1 亿美元 B 轮融资，并仍计划在 2016 年进行 IPO。

此前投资过米兰蒂斯的红帽公司在新一轮投资中明显缺席。几周前， [Red Hat 宣布它将从](https://www.zdnet.com/red-hat-ceo-announces-a-shift-from-client-server-to-cloud-computing-7000033930/)客户机-服务器过渡到云计算，重点是 OpenStack。据报道，该公司称除了自己的 OpenStack 发行版之外，不会支持其他发行版。

与此同时，本月早些时候， [VMware 发布了 OpenStack 发行版](http://www.crn.com/news/cloud/300075604/vmware-unleashes-vmware-integrated-openstack-distribution.htm)，被[红帽斥为](http://www.businesscloudnews.com/2015/02/06/red-hat-slams-vmwares-openstack-play/)“存在根本性缺陷”

陈认为，Red Hat 的定位源于 OpenStack 中使用的嵌入式虚拟机管理程序(通常是 KVM 的一个版本)，这些虚拟机管理程序尚未获得与一起工作的认证，而不是一种公开的锁定尝试。不过，他想更多地了解红帽是如何处理这些认证项目的。

陈指出，VMware 显然想用 OpenStack 来宣传自己的技术。缩小其集成组件的范围简化了许多事情，如安装、配置、升级和支持，这使 VMware 有机会提高易用性，并提供经过更多测试、稳定和可靠的产品。陈说，这样做的代价是提供的产品在与其他技术集成的能力方面不够灵活。

例如，devo PS orchestration engine MaestroDev 的创始人兼 Apache Software Foundation 的成员 Carlos Sanchez 表示，企业可能更喜欢 Red Hat 提供的受支持版本的 OpenStack，因为他们已经运行了 Red Hat Enterprise Linux，而较小的商店可能更喜欢“无锁定”版本的 OpenStack，而不是 VMware 等其他虚拟化技术。

他说，与此同时，Docker 及其之上的技术，如 Kubernetes，可能最终实现可以在任何地方运行的应用程序的承诺。

“对于 Kubernetes，我们将在未来几个月内看到谁会成为首选的提供商，提供更好的支持和易用性——无论是谷歌容器引擎，基于 OpenStack 的 Kubernetes(以及哪个 OpenStack 供应商)，CoreOS，还是其他什么，”他说。“他们各自专注于不同的使用情形(公共云、私有云、裸机)，这肯定会影响采用决策。”

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/100895211@N02/9619608799/in/photolist-fE41y8-fE3WP6-fE3Nnr-fE3M4g-fE3L2t-fEkiz5-fE3QH6-fEkaAC-fE3zna-fE3z2F-fE3yM2-fE3ysX-fE3yaH-fEk8G1-fEk8iL-fE3wZa-fE3wJi-fE3wvR-fE3wcH-fEk6ZN-fEk6HN-fEk6qj-fE3uVn-fEk5Sh-fE3utz-fE3ueD-fEk56Y-fE3tE2-fE3tjz-fEk4af-fEk3Pu-fEk3xE-fE3s3n-fE3rKX-fEk2E7-fEk2pj-fE3qYB-fEk1Kb-fE3qmc-bhew7R-hv7PDM-ecug8h-pDH3PE-8TBwJC-niPRxJ-hv7ay9-pFcqoQ-pTbJTb-pVfLq8-nA5Cnw)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>