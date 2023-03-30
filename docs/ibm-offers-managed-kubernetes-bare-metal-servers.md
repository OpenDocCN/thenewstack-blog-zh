# IBM 在裸机服务器上提供托管 Kubernetes

> 原文：<https://thenewstack.io/ibm-offers-managed-kubernetes-bare-metal-servers/>

IBM 引入了一种托管服务，用于直接在“裸机”服务器上运行 Kubernetes 开源容器编排引擎。在一篇[博客文章](https://www.ibm.com/blogs/cloud-computing/2018/03/managed-kubernetes-bare-metal/)中，[IBM 副总裁兼 IBM Cloud 研究员 Jason McGee](https://www.ibm.com/blogs/cloud-computing/author/jrmcgee/) 详细介绍了这个新的包以及将围绕容器编排引擎构建的许多新功能和计划服务。

这包括 IBM Cloud 中托管的容器直接访问 GPU 的能力，以及简化在裸机上运行 Kubernetes 的体验。“在 IBM Cloud 上，Kubernetes 现在可以融入一个组织的云战略，不管它看起来像什么；无论是建立一个完全云原生的机器学习应用程序，直接访问服务器来处理大数据工作负载，还是将数据密集型应用程序迁移到云，”McGee 写道。

在本周于拉斯维加斯举行的公司 THINK 大会上，IBM 进一步展示了基于云和容器的功能，包括一个新的云安全顾问。实验性云安全顾问允许 IT 团队通过主动漏洞测试评估其系统的状态。

该公司还与安全服务提供商 [Cloudflare](https://www.cloudflare.com/) 合作，推出了 IBM 云互联网服务。IBM Cloud 现在有能力在 DDOS 攻击和其他类型的外部攻击影响服务性能之前阻止它们。云互联网服务包括 Web 应用防火墙、全局负载平衡和 SSL。

“企业可以专注于从云到边缘的创新，花更少的时间担心性能问题和安全威胁，”Cloudflare 首席执行官兼联合创始人 Matthew Prince 说，他在 IBM 网站的[博客中引用了他的话。“在整个行业，我们刚刚开始打破强大的优势和云战略将在企业中产生的表面影响，结果将是惊人的。”](https://www.ibm.com/blogs/cloud-computing/2018/03/security-performance-ibm-cloudflare/)

在 IBM 开发自己的云以及其中包含的服务的背后，是对 Kubernetes 项目和面向客户未来的平台的不断投入。IBM cloud container services 杰出工程师 Daniel Berg 表示，IBM 的许多垂直行业如今都在生产中使用 Kubernetes。

他说，扩展遗留架构以支持现代要求苛刻的工作负载比简单地学习和实现容器更难。一年前，Kubernetes 主要由 IBM 的零售客户用于生产，但今天，Berg 说，“现在我们看到多个不同的行业在生产中使用容器。”

Berg 说，IBM 现在大量参与了 Kubernetes，并且从 1.0 版本开始就这样了。

“可以准确地说，IBM 已经尽可能地接近了 Kubernetes 最初的影响点，”Pund-IT 负责人查尔斯·金在给新团队的一封电子邮件中写道 IBM 对 Kubernetes 做出了稳定的贡献和投资，包括几个月前宣布的[云私有解决方案](https://www.ibm.com/cloud/private)(这为其新的云私有数据解决方案提供了基础。"

IBM 致力于 Kubernetes 的一个原因是系统固有的复杂性。“这是一项复杂的技术，因此服务专业人员和其他专家的帮助对许多客户来说都很有价值。对于正在考虑或计划大规模部署的企业来说尤其如此。有趣的是，你可以对企业级虚拟化说同样的话。所以我不认为这种趋势会很快改变，”金写道。

## Kubernetes 1.10 到来

Kubernetes 的最新预定版本将于本周发布。版本 1.10 包含了许多旨在增强 Kubernetes 与常见企业环境(iSCSI、Windows 和 Java)的整体兼容性的修复和特定更改。这个版本对[大页面](https://kubernetes.io/docs/tasks/manage-hugepages/scheduling-hugepages/)的支持也升级到了测试版。

[平台 9](https://platform9.com/) 的首席架构师 Bich Le 表示,“这一版本标志着 Kubernetes 平台随着每一个新版本的发布而变得更加成熟和稳定，带来了更加稳定和渐进的变化。在这个版本中，没有什么我称之为头条新闻的功能，但在各个领域有许多增量增强功能。”

乐说，最近，Kubernetes 的发布变得很无聊:这是一件好事。“Kubernetes 正在变得无聊，无聊是好的。对此的一种解读是，Kubernetes 就像一个操作系统。如果你把它与 Linux 相比较，焦点正变得越来越集中在使核心 Kubernetes 相当于 Linux 内核上，”乐说。“我们希望核心尽可能小、稳定、可靠和安全，我们希望定义许多扩展点。您可以用运行在更高层的东西来增强 Kubernetes 核心。我们希望 Kubernetes 很小，但非常灵活和可扩展。”

不幸的是，Kubernetes 仍然有些难以理解，即使它仍然是无情的重点。乐和他的团队开发了一个开源工具来解决这个问题。

“Kubernetes 以开发人员难以学习而闻名，因为开发人员需要学习太多概念才能启动一个非常基本的应用程序。他们必须学习容器、pod、服务、部署和负载平衡器，这只是为了开始开发一个简单的应用程序。你在生态系统中看到的许多创新都是围绕着层和简化这些概念的东西，或者是从开发者那里抽象出来的。Decco 就是一个例子。

“我们创建 Decco 来解决我们自己的部署问题，我们希望这将成为对一般社区有用的东西。Decco 通过让开发人员只学习两个概念来简化事情。一个是应用。另一个是空间。它允许开发人员以一种易于理解的方式描述应用程序。清单描述了应用程序在网络安全和日志文件收集方面的需求。清单提交给 Decco，Decco 构建运行和部署应用程序所需的底层 Kubernetes 资源，”Le 说。

“总的来说，我认为 Kubernetes 正在继续扩大其对企业环境和平台的支持。您可以从改进对 Windows 的支持、更好地支持 Java 应用程序以及其他对更传统的应用程序或传统企业环境更重要的事情中看到这一点。最初，Kubernetes 非常关注 Linux 工作负载，”Le 说。

金在一封电子邮件中写道，“它应该会导致越来越多的采用，特别是如果技术背后的社区保持热情的话。从这里看，Kubernetes 的未来非常光明。"

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>