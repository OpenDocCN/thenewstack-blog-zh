# NSX-T: VMware 面向现代多云应用的网络解决方案

> 原文：<https://thenewstack.io/nsx-t-vmwares-networking-solution-modern-multicloud-applications/>

[VMware](https://www.vmware.com/cloud-solutions/app-modernization/cloud-native-apps.html) 在通过虚拟化计算帮助转变数据中心方面发挥了关键作用。该公司在网络虚拟化方面也做了同样的事情。

VMware 的网络虚拟化平台名为 [NSX](https://www.vmware.com/products/nsx.html) ，创建路由、负载平衡、防火墙等网络服务。所有这些都是在软件中完成的，只要它支持 IP 传输，就可以在任何底层基础设施上实现。从更高的层面来看，VMware 基本上将 NSX 从底层物理基础架构中分离出来，这是该产品的关键优势。

VMware 产品管理高级总监 [Suresh Thiru](https://www.linkedin.com/in/suresh-thirunavukkarasu-2b87b1/) 表示:“因此，我们可以在不同的环境中提供相同的网络和安全服务，并通过单一平台进行管理。“这适用于集装箱之间和集装箱之间的东西交通和南北交通。NSX 可以在粗级别和粒度级别进行微分段。”

另一个重要的区别是容器和数据中心应用程序和服务之间的无缝连接。这是通过在创建容器时动态提供逻辑路由器并与物理网络对等来实现的。

“无论客户现在使用什么工具来进行 IT 运营和管理，他们都可以继续对虚拟机和容器甚至裸机使用相同的工具。同样的工具可以扩展到云。不需要改变，”Thiru 说。

## 面向 vSphere 的 NSX(“NSX-V”)和 NSX-T

VMware 在 NSX 家族中有两款产品:[用于 vSphere 的 NSX](https://docs.vmware.com/en/VMware-NSX-for-vSphere/index.html)和 [NSX-T](https://docs.vmware.com/en/VMware-NSX-T/index.html) 。每一个都有完全不同的代码基础，并迎合不同的用例。NSX 五号已经存在四年多了。它与 vSphere 和 VMware 基础架构密切相关。它为在 vSphere 上运行的应用程序提供网络服务。但是随着容器即服务(CaaS)、平台即服务(PaaS)和公共云的出现，许多工作负载不再在虚拟机中运行。

VMware NSX 产品线经理 [Sai Chaitanya](https://www.linkedin.com/in/saichaitanya/) 表示:“我们正处于旅程的下一阶段，应用程序开始在虚拟机之外的环境中运行。“这些可能是在公共云上的 vSphere 之外运行的容器或应用程序。这就是 NSX T 的用武之地。”

到目前为止，VMware 已经在 NSX-T 上工作了两年多。这是一个通过软件实现的单一网络平台，可以连接任何类型的应用程序。它可以是虚拟机、容器或裸机；它可以运行在私有或公共云上。“单一网络、单一抽象和单一策略管理方式——这是 NSX-T 的基本价值，”柴坦尼亚说。

Thiru 表示:“借助 NSX-T，我们正迈向支持终端或应用以及 PaaS 框架的第二阶段。“我们已经将 NSX-T 从 vCenter 中分离出来。NSX-T 是一个独立的解决方案，可以支持 vCenter、vSphere 注册、KVM、公共云、容器；它还可以与 Red Hat OpenShift 和 Pivotal 等应用程序框架集成。”

## NSX-T 确保应用程序在容器中的连接和访问

NSX-T 为所有类型的终端(虚拟机、容器和裸机)提供无缝连接和安全服务，无论这些终端位于何处。它可能位于数据中心、远程办公室、分支办公室或云中。可以通过一个中央管理器来应用和管理相同的策略。

NSX-T 具有 IP 地址管理( [IPAM](https://blogs.vmware.com/networkvirtualization/2017/02/nsx-winter-releases.html/) )功能，它主要是通过与 IaaS 环境(如 OpenStack 和 container 环境)的集成来驱动的。它还不支持 DNS。

在建立连接方面，是通过网络覆盖来完成的。“这是网络的忠实再现，就像你有一个主要基于 VLAN 技术的局域网段一样。我们只是碰巧使用 Geneve 作为网络虚拟化覆盖协议，”柴坦尼亚说。

> Kubernetes 网络政策只是一个预期的定义，它们不是政策的实施。你仍然需要一个适配器，比如 NSX-T，来实现这些策略的预期状态。

NSX-T 与 [CNI(集装箱联网接口)](https://github.com/containernetworking/cni)完全兼容，并与 CNI 集成以获得与集装箱联网的能力。“除了 CNI 之外，它还实施网络策略和负载平衡，”Chaitanya 说。“因此，从 IPAM 到 L2/第三层连接，再到安全策略和负载平衡，这是启动应用程序所需的一站式 API。”

它与数据中心基础架构的其余部分无缝集成。Thiru 说:“即使有人已经构建了一个运行在 Kubernetes 上的应用程序，它可能仍然需要一个数据库服务或其他一些仍然驻留在传统基础设施中的服务。" NSX-T 确保应用程序有适当的连接和访问这些服务."

但是 Kubernetes 有它自己的政策，那么 NSX-T 是如何处理的呢？事实上，Kubernetes 网络政策只是一个预期的定义，而不是政策的实施。你仍然需要一个适配器，比如 NSX-T，来实现这些策略的预期状态。

NSX-T 采用这种意图定义，并将其转化为基于每个 Kubernetes pod 的有状态防火墙实现。所以有状态防火墙在 Kubernetes pod 运行的任何地方实现。

“有些供应商说‘我们执行 Kubernetes 政策’这很好，但是根据我们的经验，应用策略是一个基本要求。柴坦尼亚说:“监控策略需要大量的工具。这就是我们为企业客户带来 VMware 所有运营专业知识的地方。我们带来了监控 Kubernetes 网络策略等操作工具，可以是防火墙、系统日志、仪表板或其他工具。因此，围绕监控安全策略建立了大量的工具，我们使其变得更容易，以便您可以在生产中运行应用程序。"

VMware 确实提供了自己的控制面板和可视化，但是客户可以通过无缝的 NSX-T 集成使用任何第三方工具。

## 选择哪个 NSX？

很明显，NSX 五号和 NSX 五号是两种不同的野兽。一个与 VMware 生态系统相关，另一个则无关。但是，如果客户正在使用 VMware 解决方案，如何决定是使用 NSX-T 还是 NSX-V？这真的取决于用例以及您在哪里运行它。

如果客户在数据中心有一个虚拟化应用程序，并且他们的唯一要求是为现有应用程序创建网络虚拟化，那么 Thiru 会推荐 NSX-v。Chaitanya 同意道:“它有许多与 vSphere 紧密集成的功能，这将使用户受益匪浅。”

但是，如果在 vSphere 上运行传统应用程序的同一客户表示，他们计划基于 Pivotal Cloud Foundry 或 OpenShift 构建现代应用程序，那么 Thiru 会向他们推荐 NSX-T。“它可以支持 vSphere 注册，但如果您想迁移到云，您可以将相同的 NSX-T 扩展到云，”Thiru 说。“如果我们的客户有多种虚拟机管理程序、云和容器需求，他们会选择 NSX-T。”

这归结于客户在迈向现代应用程序和公共云部署的旅程中处于哪个阶段。当你听到现代应用时，NSX-T 就是答案。

像任何其他网络产品一样，NSX 支持许多分布式服务，如逻辑交换、路由、防火墙、负载平衡、NAT……不胜枚举。Thiru 说:“我们还集成了第三方安全服务，例如 Palo Alto Firewall 和 Checkpoint Firewall。

NSX-T 与 Kubernetes、VMware Pivotal Container Service(PKS)、OpenShift 和 EC2 networking 完美集成。它唯一没有集成的 orchestrator 是 Docker Swarm，但如果有足够的需求，这是一种可能性。

Thiru 说:“我们以这样一种方式构建我们的架构，即我们可以不断为不同的容器编排器和 PaaS 框架添加适配器。因此，数据平面保持不变，控制平面保持不变

NSX-T 的核心是一个单一的网络平台，连接所有类型的应用程序，并在所有环境中普遍可用。这是现代、基于多种云的应用的最佳选择。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>