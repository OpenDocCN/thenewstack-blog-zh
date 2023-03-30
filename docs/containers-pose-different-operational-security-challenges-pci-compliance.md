# 容器为 PCI 合规性带来了不同的操作和安全挑战

> 原文：<https://thenewstack.io/containers-pose-different-operational-security-challenges-pci-compliance/>

尽管人们对容器技术越来越感兴趣，但是关于在涉及信用卡数据的应用程序中使用容器的信息却很少。

最新版本的[支付卡行业数据安全标准](https://en.wikipedia.org/wiki/Payment_Card_Industry_Data_Security_Standard)，版本 3.2，根本没有提到容器，唯一提到容器的[云计算指南](https://www.pcisecuritystandards.org/pdfs/PCI_DSS_v2_Cloud_Guidelines.pdf)指的是虚拟机。

Gartner 分析师 [Joerg Fritsch](http://blogs.gartner.com/joerg-fritsch) ，他说部署在容器中的应用程序[比部署在裸操作系统上的应用程序](http://blogs.gartner.com/joerg-fritsch/can-you-operationalize-docker-containers/)更安全，他也注意到容器“增加了合规性工作的复杂性”。(创建 PCI 标准的 [PCI 安全标准委员会](https://www.pcisecuritystandards.org/)拒绝了我们专门讨论容器和 PCI 的请求。)

It 管理咨询公司 [Atomic Inc](http://blog.atomicinc.com/) 的总裁 Avi Deitcher 指出，除了最前沿的第一个采用者，任何人都需要时间来适应任何新技术，监管机构和标准机构往往会落后。他说，容器和公共云的舒适度很低，尤其是敏感数据。

“我见过绝对没有人喜欢只用容器进行纯粹的分离。他们不相信我的敏感容器和你的不在同一个地方的容器能很好地共存。这需要一些时间，”他说。

他坚持认为，集装箱技术及其舒适度必须提高，才能实现这一目标。他指出内核级的安全性、工具和管理以及可靠性问题是目前的限制。

## 不同的挑战

PCI DSS 旨在保护持卡人数据并减少信用卡欺诈。它是由委员会开发的，其成员包括主要的信用卡，要求供应商遵守。

该标准适用于任何存储、处理或传输持卡人数据的公司。去年 4 月发布的 PCI DSS 版本 3.2 扩展了多因素认证的要求，修改了[安全套接字层](http://info.ssl.com/article.aspx?id=10241) (SSL)和早期[传输层安全](https://tools.ietf.org/html/rfc5246) (TLS)协议的终止日期，并呼吁更加关注卡数据安全中的人员、流程和策略。

尽管主要的云供应商已经接受了独立的审计，以确保他们遵守 PCI DSS，但这可能不会扩展到他们所有的服务。例如，Amazon Web Services 宣称自己是第一个符合 3.2 版本的云服务[宣布其 26 项服务](https://aws.amazon.com/blogs/security/aws-becomes-first-cloud-service-provider-to-adopt-new-pci-dss-3-2/)符合标准，尽管这并不意味着所有服务都符合标准。

基本上，PCI 兼容云供应商使客户能够建立自己的持卡人数据环境或 CDE。然而，使用 PCI 兼容的云供应商[并不等同于客户的合规性](http://searchcloudsecurity.techtarget.com/tip/How-does-Google-Cloud-Platform-affect-merchant-PCI-compliance)。最终，每个组织都要对自己的法规遵从性负责。然而，使用 PCI 兼容服务提供商的小商户可能只负责提交一份简单的[自我评估问卷](https://www.pcisecuritystandards.org/pci_security/completing_self_assessment) (SAQ)，服务提供商负责证明完全合规。

“从安全角度和 PCI 审计角度来看，虚拟机都很好理解。长期以来，虚拟环境一直是 PCI DSS 测量的一部分。容器要新得多，缺乏同等水平的安全性和 PCI 审查，这就是为什么你会看到许多初创公司争先恐后地解决容器安全性，风险投资家也在[它]上下赌注， [Andrew Nielsen](https://www.linkedin.com/in/anielsen/) ，前 [PCI 安全标准委员会](https://www.pcisecuritystandards.org/)成员，云信息管理供应商 Druva 的企业安全总监。

容器安全供应商 [Twistlock](https://www.paloaltonetworks.com/prisma/cloud) 发布了自己的容器和 PCI 合规指南，最近又发布了类似的容器和 HIPAA 指南，即医疗保健隐私法规。这些指南一步一步地介绍需求，但主要侧重于使用 Twistlock 自己的解决方案。

Twistlock 首席技术官 [John Morello](https://www.linkedin.com/in/john-morello/) 表示，容器对人们需要操作和保护它们的方式提出了不同的挑战，但这真的不是 PCI 特有的。

他说，通常情况下，集装箱会涉及更多的部件。一个使用两个或四个虚拟机的应用程序可能会使用 20 个、30 个或更多的容器。

> “如果您有一个 PCI 环境，您不会希望将面向客户的应用程序前端放在互联网上，而将典型的 web 端口放在存储所有后端数据的同一台主机上。你需要在那里做一些细分”——约翰·莫雷罗，扭锁。

“人们喜欢容器的原因之一是它们支持 [DevOps](/category/devops/) ，软件的快速迭代，但你管理的环境和软件基础比虚拟机的变化频率更高，”他说。

由于开发人员构建并移交这个密封的容器映像以在生产中运行，因此保护应用程序的责任在开发生命周期中比在虚拟机中更靠前。传统上，保护应用程序并对其进行管理是运营团队的职责，而开发人员必须保护容器映像并在必要时对其进行更新。

“所以这不是容器的缺陷，但你必须采用一种新的操作方式来保护应用程序，”他说。

## 不仅仅是数据库

他说，虽然大多数 PCI 数据存储在数据库中，但迄今为止，数据库的容器使用还没有普及。更常见的是，前端应用程序和分析层使用容器来使用和存储符合 PCI 的数据。

“PCI 不仅仅是静态数据，还包括动态数据和正在处理的数据。它实际上不是关于一个数据库，而是关于整个应用程序，”他说，并补充说，它可以应用于用于检测欺诈、监控性能、缓存和交易处理的用户界面和工具。

它甚至适用于[日志](https://www.pcicomplianceguide.org/security-logging-and-monitoring-pci-dss-requirement-10-why-all-the-fuss/)，Sumo Logic 声称 PCI 3.2 合规性是其多租户 [SaaS 安全分析](http://finance.yahoo.com/news/sumo-logic-delivers-industrys-first-140000394.html)解决方案的一部分。

## 固定所有组件

该标准的六个目标是:

*   构建和维护安全的网络。
*   保护持卡人数据。
*   维护漏洞管理程序。
*   实施强有力的访问控制。
*   定期监控和测试网络。
*   维护信息安全政策。

它描述了如何保护持卡人数据环境(CDE)中的系统组件的基准，包括处理持卡人数据的系统、隔离 CDE 的系统和控制 CDE 访问的系统。

Twistlock 指南指出，PCI DSS 评估的第一步是确定所有这些组件，其中可能包括为电子商务网站服务的容器化 Node.js 应用程序，存储持卡人数据以简化当前客户结账的容器化 MongoDB 数据库，或者验证对 CDE 主机和应用程序的访问的容器化 OpenLDAP 服务。

云安全厂商 [Armor](https://www.armor.com/) 的首席信息官 [Kurt Hagerman](https://twitter.com/KurtHagerman) 表示，所需的严格访问控制可以减少攻击者的进入点，网络分段虽然不是必需的，但可以减少您的合规范围，从而降低复杂性、审计成本和总体合规负担。

该标准并不禁止使用[多租户服务](http://info.townsendsecurity.com/bid/73683/Data-Protection-in-the-Cloud-PCI-DSS-Segmentation-Part-2)，但是规定，“在网络、操作系统和应用层可能需要确保适当隔离的机制；最重要的是，应该保证存储数据的隔离。”

Nielsen 解释说，容器依赖于操作系统和通用硬件，类似于 2 型虚拟机管理程序，然后在比虚拟机小得多的占用空间中提供多个不同的应用程序。考虑到容器的短暂性，当涉及到容器以及如何保护这些环境时，组织确实需要更好地了解攻击面。

因为多个容器存在于单个主机上，所以最特定于容器的 PCI 关注点之一可能是要求 2.2.1:每个服务器只实现一个主要功能，以防止需要不同安全级别的功能在同一服务器上共存。

Deitcher 表示，HIPAA 中的类似要求意味着，例如，在 AWS 上处理敏感医疗保健数据的公司必须有专用主机。

Morello 说，因为它被认为是一个操作系统实体，所以虚拟机被认为是一个可行的分段级别。

"您希望将相同分类级别的容器组合在一起。如果您有一个 PCI 环境，您不会希望将面向客户的应用程序前端放在互联网上，而典型的 web 端口放在存储所有后端数据的同一台主机上。你想在那里有一些细分，”他说。

他说，Twistlock 为 Docker 授权插件中使用的 Docker 开源项目贡献了访问控制功能，Twistlock 的商业产品使用该框架来提供基于角色的粒度访问控制。

例如，您可以在 Twistlock 中定义一个规则，只允许标记为 data tier 的容器在数据层主机上运行。

“如果有人试图在该主机上运行 web 层容器，这是不允许的。您还可以使用该框架来防止意外地混合开发或生产，或者运行该环境未授权软件，”他说。它允许用户明确定义哪些图像是授权的，以及可以使用哪些注册表。

尼尔森说，无论使用什么技术，合规性都归结为良好的安全性。

他敦促使用容器的组织将重点放在限制不必要的网络流量和与运行容器的系统的连接上，尽可能利用集中式身份验证和授权系统，在涉及用户帐户和进程时实施最小特权原则，并寻找能够扫描和执行专门针对容器技术的安全策略的第三方工具。

[Twistlock](https://www.paloaltonetworks.com/prisma/cloud) 是新堆栈的赞助商。

专题图片:[网购安全](https://www.flickr.com/photos/111692634@N04/11406965045/in/photolist-inZFi8-9PUh4s-nvKBxQ-7MYZnV-ctzBVm-neVHGf-9VxAFa-n5ofth-9HznR4-cJ7fPJ-qzuLYi-adRCJo-axoysW-7vEAbZ-nwu7fJ-cYzLnE-aNdY6e-5VaEyi-8yr1xJ-4DNeFh-cYzL6Y-7ySADh-cYzKNb-dT9uS4-92e5v5-nJtGcU-cYzKXL-cYzKA7-92e5wh-ctzyL7-oJNiUB-eP6jUk-cYzLw3-9VxBhR-cYzLGL-7AADC1-cYzKFo-dtsf7h-aNdBmZ-nwrLxy-aNdBfx-aNdAMt-DjFX3-aNdB14-neVySF-aNdATn-7ACaHB-9zF34Z-C51mm-aNdqYa)由[蓝衣照片](https://www.flickr.com/photos/111692634@N04/)，授权于 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>