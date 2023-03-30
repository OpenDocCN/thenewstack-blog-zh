# 库马:孔更简单的服务网络，适用于虚拟机和 Kubernetes

> 原文：<https://thenewstack.io/kuma-kongs-simpler-service-mesh-for-vms-and-kubernetes/>

Portworx 赞助了 New Stack 对 KubeCon+CloudNativeCon 北美 2019 的报道。

“我不喜欢' [service mesh](https://thenewstack.io/category/service-mesh/) '这个名字，”当被问及该公司新的开源[服务 mesh](/primer-the-who-what-and-why-of-service-mesh/) 时，孔首席技术官[马可帕拉迪诺](https://www.linkedin.com/in/marcopalladino)说的第一句话是，该服务 mesh 于 9 月发布，并于上周在圣地亚哥举行的 KubeCon+CloudNativeCon 北美 2019 的 Zero 活动中展示。“真正的问题是连通性。”

帕拉迪诺说，他不喜欢“服务网格”这个名字有两个原因首先，新的名字意味着它是一种前所未见的全新事物。其次，它使它听起来像一个“服务网格”——换句话说，一个用于管理应用程序之间的入口和出口的 sidecar 代理系统——只有在您有一个服务网格的情况下才有用。他说，两者都不完全正确。

帕拉迪诺说，孔制作并发行《库马》有几个原因。首先和孔的核心 API 网关产品有关。API 网关和服务网格都是控制和保护服务之间以及应用程序和最终用户之间通信的方式。区别在于它们是如何实现的:API 网关是基础设施中位于用户和服务之间的一个单独的层，而服务网格是使用附加到各个容器的 sidecar 代理创建的，形成了一个“网格”而不是单独的层。“服务网显然是人们使用孔的延伸，”帕拉迪诺说。

首先，Kong 研究了现有的服务网格选项，但决定构建单独的服务网格——尽管它是基于 Envoy 的。帕拉迪诺说，他们的目标是创造一种既能在 Kubernetes 上运行的分布式容器化应用程序中工作，又能对许多仍在虚拟机上运行的公司有用的东西。该公司称库马为通用服务网，公司可以将其用于传统应用以及新的云原生应用。

帕拉迪诺说，使用库马相对于其他服务网格选项的另一个优势是高级用户界面。其他服务网格具有不成熟的控制平面，使其过于复杂。最后，Kong 希望确保对多租户的支持，这是许多其他服务网格所缺乏的。

帕拉迪诺希望，库马是一个适应企业组织现实的服务网。这种类型的公司仍然处于 Kubernetes 成熟之旅的开始，数百个团队以不同的速度和不同的技能水平前进。

“库马是一个运行和部署非常简单的应用程序，”帕拉迪诺说。“只有一个移动的部分。你可以水平缩放库马。很好操作。您可以从一个控制面板支持每个团队。”

已经有公司在生产中使用库马，包括一家大型欧洲电信公司。

来自 Pixabay 的 Alexas_Fotos 的特写图片。

KubeCon+CloudNativeCon 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>