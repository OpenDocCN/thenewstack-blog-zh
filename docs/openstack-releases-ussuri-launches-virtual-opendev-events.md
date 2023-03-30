# OpenStack 发布 Ussuri，启动虚拟 OpenDev 事件

> 原文：<https://thenewstack.io/openstack-releases-ussuri-launches-virtual-opendev-events/>

周三，美国中部时间上午 10 点， [OpenStack 基金会](https://www.openstack.org/foundation/)将发布 [OpenStack Ussuri](https://www.openstack.org/software/ussuri/) ，这是现已有十年历史的开源云基础设施软件的第 21 个版本。该版本对许多单个项目进行了广泛的更改，这些更改遵循三个主要主题:核心基础架构层的可靠性、安全性和加密功能的增强，以及对新出现的用例的支持。

在一次虚拟新闻发布会上，OpenStack 基金会首席运营官 [Mark Collier](https://www.linkedin.com/in/markcollier) 解释说，OpenStack 的方向实际上是由运行它的硬件和这些新出现的用例的需求在许多方面驱动的。

“就路线图而言，我认为我们继续看到的只是基础架构层的需求因堆栈其他层发生的事情而不断变化。因此，你会看到人工智能和机器学习方面的工作负载需求越来越多，这从计算的角度出发，为新的架构提出了要求，”科利尔说。“在这些不同的层面上，创新的数量惊人。我们有时会独立思考它们，但事实是，正是运行在云上的工作推动了创新。”

到目前为止，开源软件经历了来自 188 个不同组织的 1，003 名开发人员的 24，000 次代码更改，根据积极贡献，这使其成为三大开源项目之一。

传统上，OpenStack 的最新版本可能会在开放基础设施峰会期间发布，OpenStack 开发人员会亲自聚集在一起展示变化并规划未来一年的里程碑，但今年的发布是单独发布的，同时还有整个夏天的虚拟 [OpenDev 活动系列](http://openstack.org/events/opendev-2020/)和虚拟[项目团队将于 6 月 1 日至 5 日聚集](http://openstack.org/ptg) (PTG)，以取代将在峰会上亲自举行的 PTG。

虽然原定于 6 月初举行的温哥华开放基础设施峰会已经取消，但另一场峰会暂定于 10 月在柏林举行。目前，科利尔解释说，转向纯虚拟活动有一些好处。

“众所周知，多年来，我们一直在世界各地聚会和组织活动。这是我们的社区如何联系和规划软件未来版本的重要组成部分，并讨论我们希望从这里走向何方。像其他人一样，我们正在适应，”科利尔说。“虽然我们很遗憾不能亲临现场，但我们也很兴奋，因为这确实提供了一些灵活性，可以包容那些以前可能无法乘坐飞机的人。飞越世界并不总是容易的。它非常昂贵、耗时，因此将其转移到网上有一些不利之处，但也有很多有利之处。”

OpenDev 系列活动将由三个独立的活动组成，每个活动都关注云基础设施中的一个不同挑战，并探讨如何利用开源软件(而不仅仅是 OpenStack 软件)应对这一挑战。该系列将包括:

*   开放基础架构软件的大规模使用—6 月 29 日至 7 月 1 日
*   硬件自动化—7 月 20 日至 22 日
*   生产中的容器—8 月 10 日至 12 日

至于 Ussuri 版本中包含的 OpenStack 的更新，它们为数众多，包括:

*   **电子人**(加速器生命周期管理)与 Nova(计算服务)的整合已经完成。用户现在可以使用 Nova 通过由 Cyborg 管理的加速器来启动服务器实例。参见[加速器操作指南](https://docs.openstack.org/api-guide/compute/accelerator-support.html)了解支持哪些实例操作。
*   **讽刺**(裸机服务)增加了自动化裸机硬件供应。
*   **Kolla**(open stack 的容器化部署)增加了对后端 API 服务 TLS 加密的初始支持，提供 API 流量的端到端加密。目前支持 Keystone。
*   **Kuryr**(open stack 和容器网络之间的桥梁)增加了对 IPv6 的支持。
*   **Nova** (计算服务)增加了对在 Nova 单元之间冷迁移和调整服务器大小的支持。
*   **奥克塔维亚**(负载平衡器服务)增加了对在特定可用性区域部署负载平衡器的支持，这使得能够将负载平衡功能部署到边缘环境。此外，奥克塔维亚用户现在可以指定侦听器和池可接受的 TLS 密码，这允许负载平衡器强制执行安全合规性要求。
*   Zun(容器服务)增加了对 Kubernetes CRI 运行时的支持。Zun 使用 CRI 运行时来实现胶囊(pod)的概念。因此，Kubernetes 可以使用 Zun API 来创建 pod，包括在安全的 [Kata 容器](https://katacontainers.io/)中。

除了最新发布的消息和虚拟事件，OpenStack 基金会执行董事 Jonathan Bryce 花时间描述了一个名为 [OpenInfra Labs](https://openinfralabs.org/) 的新项目，他说该项目最初是在学术和研究环境中形成的。OpenInfra Labs 页面将该项目描述为“一个由运营商创建并为运营商服务的社区，在生产中测试开源代码，发布针对现有和新兴工作负载的完整、可复制的堆栈，以推进开源基础设施”，并提供了一份宣言来进一步描述其目标。

专题图片:[乌苏里江](https://en.wikipedia.org/wiki/Ussuri_River)，安谢尔拍摄， [CC BY-SA 3.0](https://commons.wikimedia.org/w/index.php?curid=16031482) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>