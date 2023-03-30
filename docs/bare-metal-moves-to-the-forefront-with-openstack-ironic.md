# 裸机凭借 OpenStack 走向前台颇具讽刺意味

> 原文：<https://thenewstack.io/bare-metal-moves-to-the-forefront-with-openstack-ironic/>

[红帽 OpenShift](https://www.openshift.com/) 赞助本帖。

在研究技术趋势和周期时，重要的是永远不要忽视某项技术已经过时。例如，当亚马逊去年秋天推出其鞭炮管理程序时，互联网上迅速充斥着[一场经常是半开玩笑的关于容器的未来的辩论](https://thenewstack.io/this-week-in-programming-kubernetes-future-in-virtual-machines/)，实际上是[虚拟机](https://tech.paulcz.net/blog/future-of-kubernetes-is-virtual-machines/)——一些人认为这种技术已经成为过去。本周，在科罗拉多州丹佛市举行的[开放基础设施峰会](https://www.openstack.org/summit/)上，类似的现象正在发生，但这次与会者的言论将事情从虚拟化又向前推了一步，回到了“裸机”

尽管计算基础设施的几乎每个方面都朝着抽象和虚拟化的方向发展，但裸机具有各种优势，并且一直是 OpenStack 最新发布的 [Stein](https://releases.openstack.org/stein/) 的焦点，该产品于上个月[发布](https://thenewstack.io/openstack-stein-focuses-on-kubernetes-bare-metal-nfv-and-more/)。根据 OpenStack 基金会的一份声明，其[裸机供应和管理工具讽刺](http://openstack.org/bare-metal)近年来获得了快速采用，“现在有 24%的生产部署依赖于它，而 2016 年只有 9%。”声明继续说，讽刺“允许用户像管理虚拟机一样管理裸机基础设施，并提供一个理想的基础设施来托管高性能的云应用程序和框架，包括 Kubernetes 等流行的容器编排框架。”

“我们生活在一个 API 驱动的世界里，”OpenStack 讽刺项目组负责人、红帽公司首席软件工程师 Julia Kreger 在声明中说。“在提供基础架构即服务方面超越虚拟机是很自然的事情。这就是为什么我们创造了讽刺:提供一个供应商中立的 API，使数据中心运营商能够可靠地管理大规模的基础设施，无论他们需要虚拟机还是裸机。该项目的目标是增强运营商的能力，这体现在新特性中，如所有者和节点描述信息的存储或定制模板的能力。这对运营商来说是巨大的改进，有助于解决大规模运营的难题。”

在一次采访中，Kreger 提出了裸机正在复苏的各种原因，主要原因仍然是性能和成本节约。

“大多数人直接使用裸机的驱动因素要么是性能、合规性，要么是他们需要消耗机器上所有资源的能力。虽然人们可以通过虚拟化来完成这项工作，但大多数人并不真的想拥有一个可能有吵闹邻居的环境，”Kreger 解释道。“我开始越来越多地看到对科学合作的兴趣。虽然大多数人可能不会想到虚拟化花费了您大约 3%的开销，但是如果您在数千个节点的规模上运行，这 3%就会越积越多。它开始成为一项主要成本。”

然而，除了性能和成本，Kreger 指出合规性是选择裸机而不是云中虚拟化资源的主要驱动因素。

“人们仍然使用裸机的很多原因是法规遵从性之类的。在有些情况下，数据中心会因为一台机器的内容而遭到搜查。联邦探员不了解技术。如果有必要，他们会拿走一切，”克雷吉说。“法官可能理解计算机，但他们可能不理解分层的软件堆栈，然后你可能会创建一个数据中心。”

Kreger 解释说，在这种情况下，受监管的数据可能会被共享，这些数据不应该被看到，例如存储在同一共享云资源上的医疗记录，这对所有参与者来说都是昂贵而复杂的。最终，裸机提供了多租户云环境中无法提供的工作负载和所有权的隔离，OpenStack 已经采取措施，通过讽刺性的方式使裸机配置更接近虚拟化服务器的配置。

OpenStack 是新堆栈的赞助商。

来自 Pixabay 的 Parker_West 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>