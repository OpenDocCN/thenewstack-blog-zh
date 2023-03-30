# 覆盖网络如何为无缝混合云铺平道路

> 原文：<https://thenewstack.io/containerizing-makes-hybrid-cloud-easier-adopt/>

[](https://www.weave.works/)

 [马修·洛奇

马修·洛奇在云计算和产品领导领域拥有超过 20 年的丰富经验。他是 Weaveworks 的首席运营官，最近是 VMware 云服务集团的副总裁。他为国际空间站等项目构建编译器和分布式系统，帮助六个国家首次接入互联网，并在思科管理价值 6.3 亿美元的路由器产品线。在加入 VMware 之前，Mathew 是赛门铁克价值超过 10 亿美元的信息管理部门的高级主管。](https://www.weave.works/) [](https://www.weave.works/)

在过去的几个月里，我看到了一个有趣的趋势:容器和容器覆盖网络使混合云(内部数据中心和外部公共云的混合)变得更加容易。

许多开发团队在采用公共云时会趁机更新或重构应用程序。但公共云的工作方式与传统数据中心不同:它们拥有内部不可用的新应用服务，并有不同的习惯用法来处理规模、冗余和恢复等问题。当开发团队寻求重构和构建新组件时，他们越来越多地寻求容器化，因为他们这样做是为了获得速度和可移植性的好处，因为他们希望向微服务架构发展。

[Weaveworks](https://www.weave.works/) 在早期开创了覆盖容器网络，作为一种使应用程序开发人员生活更简单的方式:不是容器试图共享 VM 或服务器(Docker 主机)的 IP 地址，而是每个容器在一个只有容器的虚拟网络上有自己的 IP 地址。该容器中的进程可以使用 80 和 443 这样的标准端口，并且使用容器名称的简单的基于 DNS 的服务发现使得查找任何其他容器的 IP 地址变得轻而易举，不管它在哪里。

事实证明，这些品质也使得向混合云的过渡更加简单。

## 混合云是企业的新常态

重构整个企业应用程序，将其全部迁移到公共云，或者在一夜之间过渡到微服务，这是非常罕见的。应用程序的某些部分将继续在数据中心运行，因为没有充分的理由移动应用程序，或者团队有更好的事情要做，而不是进行复杂的迁移，不增加新的功能。不像初创公司，没有“干净的石板”。

因此，新的和重构的应用程序组件最终出现在容器中。其中一些将在公共云中运行，一些将在数据中心运行，应用程序的其他部分将完全不包含在内。

接下来的问题是如何将所有在内部和外部运行的容器编织在一起，并将它们连接到其他(未包含的)服务，而不会变成配置混乱和安全噩梦。

## 集装箱虚拟网络拯救世界

集装箱覆盖网络基本上是现在事实上的标准，因为它们避免了配置毛球。容器虚拟网络建立在底层 IP 网络之上，因此无论底层网络技术有何不同，它对应用程序来说看起来都是一样的。数据中心网络的工作方式与 AWS 虚拟私有云不同。本质上，管理差异的问题被推到了容器网络层。这意味着应用程序本身不需要配置或代码:它可以只使用常规的网络结构，如 TCP/IP 和 DNS。

在[编织网络](https://www.weave.works/products/weave-net/)的情况下，覆盖网络看起来就像一个以太网。在每个 Docker 主机上，容器都有一个虚拟以太网接口，就像开发人员习惯在 Linux 机器上看到的 **eth0** 接口一样，它连接到一个虚拟以太网交换机。容器不必关心包如何到达其他容器，或者它们在哪个主机上，或者 IP 地址如何分配。广播和组播就像你期望的那样工作。

## 安全呢？

许多覆盖网络将状态信息存储在外部集群存储中，例如 etcd、Consul 或 Zookeeper。这意味着网络中的每个 Docker 主机都必须拥有与集群存储对话的凭证。由此产生了两个安全问题:安全地管理凭证(存储和凭证轮换)，以及从主机到存储的连接的安全性。在混合云场景中，这些问题更加严重，因为主机位于不同的安全域中。

> 我们能够从运行在 AWS cc 4.8 x 大型“网络优化”实例中的单个容器通过 10G 网络推送 7 gbit/秒的流量。

有两种解决方案:使用配置管理工具管理凭证和连接，或者取消集群存储。Weave Net 采用后一种方式:网络状态由 Weave 缓存在每个主机上，并最终在整个集群中保持一致，而不是集中存储。这也使得集群在出现连接问题或分区时(当容器网络由于链路故障或拥塞而分裂成多个部分时)更加可靠。)

容器网络流量的安全性可以由网络本身或底层网络来处理。例如，在数据中心和公共云提供商之间的链接上使用 IPSec。

## 现实世界中的例子

国际证券交易所(ISE)运营期权交易所，并使用容器和覆盖网络为其“随处交易”服务实施新颖的灾难恢复。该应用程序在 ISE 的数据中心和 Amazon Web Services 上运行，因此它可以提供完全不同地理位置的灾难恢复。

这提出了一个新的挑战:如何将市场数据分发到所有组件，而不管它们在哪里运行？ISE 转向 Weave Net 来解决这个问题，使用它来承载多播数据馈送，并将其传送到运行在 AWS 和 ISE 的数据中心中的交换组件。

## 对速度的需求:覆盖网络不是很慢吗？

但是等一下，覆盖意味着你在某个地方添加了一个包头(封装),那么这对网速有什么影响呢？

具有讽刺意味的是，覆盖层和计算机网络一样古老，并且因为开销很小和很值得上升而经久不衰。例如，IP 网络最初是作为覆盖层在 X.25 网络上提供的，后来成为以太网上的覆盖层——今天仍然是这种方式。

当使用容器覆盖网络时，同一主机上的容器之间的包没有开销，因为它们通过虚拟以太网桥，不需要封装。为了在宿主之间穿梭，它们被放在隧道里。为了提高效率，最流行的隧道封装是 VXLAN。VXLAN 是一种非常简单的 IP-over-IP 隧道形式，就像 IPSec 一样，它只是一个 IP 报头，所以添加它的开销非常低。交换硬件内置了 VXLAN 支持，服务器网卡为其提供硬件加速。

好吧，那么它会产生什么样的影响，为什么我们不应该关心呢？在 Weaveworks 工程师进行的测试中，我们能够从运行在 AWS cc 4.8 x 大型“网络优化”实例中的单个容器通过 10G 网络推送 7 gbit/秒的流量。我们选择这个实例大小是因为它占据了整个服务器，所以没有“噪音邻居”的影响。

## 结论

容器的采用正在帮助组织更快地交付新的云应用，在企业中，内部和公共云部署的混合正在成为新常态。覆盖容器网络使网络可移植到应用程序，降低了复杂性，并以一种安全的方式消除了配置毛球。

Weaveworks 是新堆栈的赞助商

专题图片:弗吉尼亚州里士满[针织厂 M . e . g .](http://knitoriousmeg.com/)的街道标志纱线炸弹。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>