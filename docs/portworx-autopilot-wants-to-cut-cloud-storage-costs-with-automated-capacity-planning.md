# Portworx Autopilot 希望通过自动化容量规划削减云存储成本

> 原文：<https://thenewstack.io/portworx-autopilot-wants-to-cut-cloud-storage-costs-with-automated-capacity-planning/>

Portworx 赞助了 New Stack 在圣地亚哥的 KubeCon + CloudNativeCon 的报道。

New Stack 最近的民意调查表明 [10%的公司](https://thenewstack.io/ux-is-kubernetes-biggest-short-term-challenge/)认为存储是 Kubernetes 需要改进的首要领域。即使你不担心让存储与 Kubernetes 一起工作，期间，你可能会因为大部分预算[转向云存储](https://thenewstack.io/wasting-money-on-public-cloud-storage/)而失眠。

“在云中，有这样一句口号:你只为你使用的东西付费，”[Portworx](https://www.linkedin.com/in/ferrantim/)的产品营销副总裁 Michael Ferranti 说。“那其实不是真的。您为您提供的东西付费。如果您调配 EBS 卷，即使您不使用它，也需要付费。”

当然，云仍然需要底层基础设施。随着 Kubernetes 规模的扩大，最终你会耗尽基础设施。向任何云服务提供商的现有服务器添加存储都需要应用程序停机。也经常是手动完成的。这意味着存储空间不足也会导致停机。

因此，大多数公司都会过度调配存储。“虽然我可能只需要 1tb 的存储，但我会提供两到三个以获得一些扩展空间，”Ferranti 说。“这意味着我支付的价格是我所需价格的两到三倍。”

为了应对这一挑战，容器原生存储公司 Portworx 发布了用于容量管理的 PX-Autopilot，这是一种在检测到 Kubernetes 上运行的应用程序存储容量不足时提供更多存储的工具。其理念是为客户提供一种方式，让 Portworx 不仅可以管理应用存储，还可以自动化管理底层存储基础架构。

Autopilot 是一个策略引擎，当消耗达到预先确定的阈值时，它会自动添加 EBS 卷或调整应用程序卷的大小。这使得公司可以大幅减少存储资源调配的“空间”,他们可以确保可用存储始终领先于消耗，而不必担心值班管理员会睡过头或外出度假。 Autopilot 还完全消除了调整服务器大小或向服务器添加存储的停机时间。

“根据我们对一些早期接入客户的计算，我们估计普通客户可以通过 Autopilot 将云存储成本削减一半，”Ferranti 说。考虑到一家大公司每年通常会在云存储上花费数亿美元，即使存储成本降低 25%也意义重大。一个早期用户一直在绘制软件巨头 ESRI 的地图，该公司一直在部署 Autopilot，以便在达到预定阈值时自动提供和调整大小。

自动驾驶仪将于 11 月 19 日正式上市，客户可以在 KubeCon 期间注册。Ferranti 说，该产品可以大幅降低云存储成本，但前提是公司必须在 Kubernetes 上运行应用程序。

“这是一个互利的循环，”费兰蒂说。“Portworx 平台的其余部分解决了业务需求，如灾难恢复、备份和数据安全，防止应用程序在 Kubernetes 上运行。一旦应用程序转移到 Kubernetes，我们就可以降低您的存储成本。”

KubeCon + CloudNativeCon 和 Portworx 是新堆栈的赞助商。

2019 年圣地亚哥 KubeCon + CloudNativeCon 上 Portworx 展台的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>