# VMware 让数据中心为容器的冲击做好准备

> 原文：<https://thenewstack.io/vmware-prepares-data-centers-for-the-onslaught-of-containers/>

了解 Scott Fulton 之前对 VMworld 2016 的报道

[here](https://thenewstack.io/vmworld-las-vegas-2016-keys-conference-scrambling-foundation/)

,

[here](https://thenewstack.io/vmware-pitches-nsx-virtual-networking-foundation-every-workload/)

，以及

[here](https://thenewstack.io/vmware-integrated-containers-may-introduce-docker-enterprise/)

.

当世界其他地方在争论容器生态系统是否应该成为一个重心的棘手问题时，位于虚拟化世界轴心的公司将自己描绘成中立领域的守护者和和平的先驱。

在拉斯维加斯举行的 VMworld 2016 的第二天，VMware 展示了 vSphere Integrated Containers 的生产就绪版本，作为解决开发人员在引入容器化时无意中给企业带来的混乱和无序的唯一实用解决方案。

“我可以向你保证，今天在场的每一个组织，都有人开始玩容器，”VMware 云平台首席技术官 Kit Colbert 说。“这既创造了机遇，也带来了挑战。

“开发人员的容器，在开发中，超级简单。这是一个很大的价值主张:开发人员可以拿一台笔记本电脑，得到 Docker，然后就可以开始运行了。立即看到价值。但是你们知道，为了在生产中运行任何东西，必须满足一系列企业运营要求。我们看到许多客户都在努力应对容器化应用的挑战，”科尔伯特说。

## 伙计，你没有超收敛！

Colbert 讲述了一个 VMware 客户在生产中运行一个且只有一个容器化应用程序的故事。他询问该客户运营团队是如何完成监控的，并被告知他们不会。

“‘您不使用生产应用程序进行监控吗？“伙计，这可不好！”他说，‘老兄，我知道！’我当时就想，‘老兄！’我们度过了一段亲密的时光。事实是，客户在这些事情上很纠结。"

首席技术官的故事发生在他演示最新版本的 vSphere 之前，客户很快就会看到它是 [VMware Cloud Foundation](http://www.vmware.com/products/cloud-foundation.html) 的一部分，为容器驱动的应用程序的暂存创建虚拟容器主机。这些主机在 vSphere 中显示为普通虚拟机，直到操作员深入了解详细信息。这种共存是由一个包装器提供的，一旦容器部署在这些主机中，vSphere 就会将该包装器应用到容器中，开发人员无需干预。

> VMware 似乎已经意识到，在这一点上，它将无法向开发人员社区销售其品牌…相反，它满足于将开发人员和运营商不仅视为不同的市场，而且视为围绕同一基础架构轴运行的不同世界的居民。

VMware 在这里传达的信息是，开发人员应该被允许使用他们无论如何都要使用的任何工具(Docker 是主要的例子)，IT 操作员应该以一种最大限度地减少他们与安全控制和合规协议的交互的方式来简化开发人员的方法。该消息称，开发人员根本不关心这些问题，那么为什么要让开发人员担心首席信息官希望运营商管理和控制的事情呢？

“如果它在生产中运行，我们首先需要什么？”科尔伯特反问道。“对，网络和安全。你会非常想把这个东西锁起来，确保它是安全的。”

这使得 Colbert 能够将 VMware 的 NSX 网络虚拟化技术融入其中，围绕一个容器化的应用程序和一个关联的数据库创建一个安全组。接下来，他可以将 [vRealize Operations](http://www.vmware.com/products/vrealize-operations.html) 带入与管理控制台相同的画面中。他可以看到安全组中组件之间的网络拥塞，并应用补救性的重新路由—所有这些都不需要开发人员参与。

## 一些熟悉的伙伴

科尔伯特周二还透露，VMware 实施集成容器的战略得到了两个非常以容器为中心的合作伙伴的帮助: [CoreOS](https://coreos.com/) 和 [Mesosphere](https://d2iq.com/) 。与 Pivotal 共同制作的 VMware 容器平台 Photon 的即将到来的版本将集成 Vmware 的 NSX 以及作为容器协调器的 Kubernetes。

“当我们谈论应用交付的速度和速率时，许多企业都在考虑如何重新思考一切以大幅提高速度，”Colbert 说道，并提出了光子平台的话题。“这种反思是自上而下的，一直到基础架构……他们利用他们拥有的所有物理资源，将它们汇集到计算、网络、存储的逻辑池中，他们在分布式控制平面和调度程序的基础上构建一个单一的逻辑 API 端点，供应用程序团队利用。然后，他们将基础架构分成几个部分，分成几个可用性区域。不存在任何单个主机的假设可用性，事实上，许多整个数据中心都可能停机。因此，您必须向应用程序公开可用性概念。”

这就是 Colbert 承认正在为多租户和安全性设计新的应用程序类别的原因——开发人员*确实*关心性能、可用性和其他关键性能指标，这些指标在 VMware 的主流中与开发人员截然不同。“光子平台的想法，”他说，“是推动这些架构的基础设施方面的彻底简化。”

光子平台将实现软件级的超融合，将整个数据中心资源(包括来自公共云的资源)汇集在一起。虽然这超出了 vSphere 和 Cloud Foundation 的范围，但它仍然会将 NSX 带入组合中，作为这些池中资源之间连接的促进者。

VMware 似乎已经意识到，在这一点上，它将无法向开发者社区销售其品牌。所以它不应该尝试；相反，它满足于将开发商和运营商不仅视为不同的市场，而且视为不同世界的居民，这些世界围绕着相同的基础设施轴，但在其他方面彼此联系有限。

VMware 没有将 vSphere management 定位为 container orchestrator 的替代品，而是选择将流程编排和管理描述为正交的主题，每个主题对应一个部门。这可能不是 DevOps *本身*，但话说回来，VMware 在其当前的营销策略中毫不犹豫地省略了“DevOps”一词。事实上，它的整个信息是呼吁运营商，开发者将是开发者，围绕他们建立流程比继续再教育他们更容易。

[CoreOS](https://coreos.com/) 和 [Mesosphere](https://d2iq.com/) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>