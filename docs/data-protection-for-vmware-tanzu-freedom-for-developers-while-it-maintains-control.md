# VMware Tanzu 的数据保护—在 IT 部门保持控制的同时，为开发人员提供自由

> 原文：<https://thenewstack.io/data-protection-for-vmware-tanzu-freedom-for-developers-while-it-maintains-control/>

[](https://www.linkedin.com/in/nivasiyer/)

 [尼瓦斯伊耶

尼瓦斯是戴尔技术公司的产品经理和战略合作伙伴领导，以提供创新产品而闻名。他热衷于了解客户需求并提供解决方案。凭借卓越的市场洞察力，Nivas 能够提取关键信息，并快速制定精确的产品响应。](https://www.linkedin.com/in/nivasiyer/) [](https://www.linkedin.com/in/nivasiyer/)

[VMware Tanzu](https://tanzu.vmware.com?utm_content=inline-mention) 为已经拥有 VMware 基础的组织采用 Kubernetes 提供了一种简单的方法。Tanzu 本质上是一个“Kubernetes 即服务”平台，允许客户使用来宾集群的概念在 vCenter 中运行多个 Kubernetes 集群。该术语借用了来宾操作系统的概念，IT 运营人员可以将 CPU、内存和存储等资源分配给不同的开发团队，就像他们为虚拟机环境所做的那样，而不需要很长的学习曲线。此外，开发人员拥有自己的“即服务”框架来按需构建新的 Kubernetes 客户环境，因为他们需要满足 IT 的资源限制。

VMware Tanzu 的信息吸引着那些努力在数字化转型和开发运维时代寻找相关性的 IT 组织。许多公司正在利用 VMware Tanzu 来创建一个基础架构平台，该平台还可以作为一种轻松启动和管理 Kubernetes 环境的方式，允许开发人员使用它们。

在这段旅程中，我与许多客户交谈过，包括大型财富 100 强公司。我听到的一致反应是，这个平台非常好。但是，它仍然缺少一个引人注目的功能，即数据保护。IT Ops 的角色不仅仅是创建一个平台和实施资源约束，以确保团队可以独立工作并友好地共享资源。当出现问题时，您如何确保可用性和可恢复性？如果发生硬件故障和灾难，您能保证应用程序的可用性吗？当数据丢失或损坏时，您能恢复吗？

这里快速概述了为什么可恢复性是关键，以及企业级数据保护如何融入 Tanzu 的故事。

在戴尔，我们提前预料到了这些问题。它们是开发 PowerProtect Data Manager 的指导原则，power protect Data Manager 是一款面向 Kubernetes、云原生应用程序、VMware 应用程序和第 1 层应用程序的集成式企业级数据保护解决方案。PowerProtect Data Manager (PPDM)提供了与 VMware Tanzu 环境的深度集成，以便为部署在这些环境中的 TKG 来宾群集或用户应用程序提供足够的数据保护。PPDM 源于与 VMware 团队的联合工程设计以及数十年的戴尔 EMC 数据保护经验，旨在创建一个用于保护这些环境的云原生解决方案。

从企业 IT 的角度来看，VMware Tanzu 数据保护解决方案的关键要求包括以下功能:

1.  使用企业级用户界面集中管理整个企业(内部或云中)的多个 Kubernetes 和 Tanzu 环境的能力。
2.  能够自动发现需要保护的应用程序和数据；它还可以自动定义策略，包括备份计划、保留和副本复制。
3.  强制实施法规遵从性以确保应用程序能够恢复到策略中说明的 RPO 和 r to 的能力。
4.  能够将拷贝分层到对象或云，以实现长期保留。

此外，该解决方案还包括 Kubernetes 和容器部署独有的功能，包括:

1.  面向云原生数据库部署(如 MySQL、MongoDB 等)的无代理应用程序一致性。
2.  保护应用程序定义和部署，以消除配置偏差。
3.  保护集群中的自定义资源和 PaaS 本机对象定义，如图像标签。
4.  支持将应用程序迁移到另一个 Kubernetes 集群，本地或云中。
5.  支持容器存储接口(CSI)等 CNCF 标准，以确保跨环境的兼容性并支持版本控制。
6.  使用 Kubernetes 本机 CLI 和 API 支持为开发人员和开发人员提供自助服务支持，包括基于关键程度自动将应用程序与适当的策略相关联的标记，以及对自助恢复的支持。
7.  支持 RBAC 和其他认证和授权框架，以实现合规性。

此外，有些功能是 VMware Tanzu 独有的，包括:

1.  主管和客户群之间的细分概念；数据保护解决方案需要深入集成到这一层。
2.  与 Velero 项目整合。
3.  支持 VMware 云本机存储快照和恢复。

最后，并非所有数据都需要移植到容器中。其中一部分可以留在虚拟机中，继续由容器使用。我用一个三层楼的类比来解释这个概念。在第一层，您有裸机应用程序，如 SAP、Oracle 等。第二层是您的虚拟化数据库应用程序，包括 SQL Server 和 Exchange。第三层相对较新，即 Kubernetes 和容器化应用，其中每个微服务在集群中维护其数据存储。

客户正在寻找一个单一的解决方案来保护每一层的应用程序，同时提供集成到 Kubernetes 本机工具、VMware 本机工具等的独特自助服务功能。也就是说，如果您正在考虑将 VMware Tanzu 作为您的平台，请不要忽视对数据保护解决方案的需求，原因如上所述。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>