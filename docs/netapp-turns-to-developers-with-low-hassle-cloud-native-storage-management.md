# NetApp 向开发人员求助低难度的云原生存储管理

> 原文：<https://thenewstack.io/netapp-turns-to-developers-with-low-hassle-cloud-native-storage-management/>

感受到市场的变化， [NetApp](https://www.netapp.com/) 正在将其潜在用户群扩展到存储管理员的核心受众之外，通过承诺在配置和管理存储方面提供更大的灵活性和更少的麻烦来吸引云原生开发人员。

本周在拉斯维加斯举行的公司年度 [NetApp Insight](https://insight.netapp.com/) 用户大会上，存储巨头淡化了高速存储设备的话题，转而讨论 DevOps、Kubernetes 和云原生计算。

NetApp 高级经理 [Eduardo Rivera](https://www.linkedin.com/in/eduardorivera/) 在一次演示中解释说，如今，存储管理员的角色不再是配置卷，而是将自动化构建到 DevOps 平台中，通过代码定义公司应用程序所需的访问权限，并且可以被开发人员轻松征用。

NetApp 的王牌是其 NetApp 的 [OnTap 数据管理](https://www.netapp.com/us/products/data-management-software/ontap.aspx)软件，该公司在过去几年中开发了该软件，以便与主要的云提供商密切合作。实际上，OnTap 提供了将工作负载迁移到云甚至跨不同云的入口。NetApp 高级副总裁兼公司云业务部门总经理 Anthony Lye[在接受新堆栈采访时指出，它通过 NFS 和 Windows SMB 协议提供对云存储服务的快速访问，即使是在同一个存储卷中。](https://www.linkedin.com/in/anthonylye/)

NetApp 还在流行的开源容器编排引擎 Kubernetes 上投入了越来越多的开发人员。该公司的 [Trident 软件](https://netapp.io/persistent-storage-provisioner-for-kubernetes/)解决了运行 Kubernetes 最困难的挑战之一，[通过提供一个中央网关来管理 Kubernetes pods 使用的所有存储](https://thenewstack.io/stateful-workloads-in-kubernetes-with-trident-the-netapp-way/)。这款完全受支持的软件已经在不同地点为 400 家客户运行了 19，000 个集群，访问了 3.5PB 的数据。

Lye 指出，NetApp 被要求为 Microsoft Azure 和 Google 云平台构建中小企业和 NFS 功能。对于这些用户，“没有存储管理员，”他说。开发人员可以轻松地自行调配所需的存储。他怀疑企业很快也会效仿这种模式。

在大会上的演示中，Lye 展示了 OnTap 如何成为内部数据中心和云的主要存储接口，以及如何帮助客户节省云配置成本，同时提高性能，甚至添加新功能。

他演示了如何使用 OnTap 将快照和非活动数据等不太重要的数据从快速但昂贵的基于闪存的存储阵列转移到云服务上。他还展示了企业如何将其整个灾难恢复操作迁移到云中。NetApp 自己通过将其灾难恢复数据迁移到云中，无需更改应用程序，并保留 95%的功能，每月节省了 48，000 美元。

“如果您将任何工作负载放在亚马逊上，并在其上放置 OnTap，您的亚马逊账单就会下降，”Lye 断言。它还带来了新的 DevOps 风格的功能。Lye 说，希望根据生产数据库测试应用程序的开发人员可以很容易地旋转数据库的镜像(正如 Lye 所说的那样，用众所周知的“鼠标点击”)，并随时准备好一个。Lye 认为，用过去的传统企业存储安排，这根本不可能，否则管理员可能需要几个月的时间来设置。

参加会议的人似乎很欣赏 NetApp 的方向，即使他们自己在云原生之旅中并没有走多远。锡拉丘兹大学基础设施服务副首席信息官 Eric Sedore 指出，该大学发现容器对其研究人员来说是最方便的，他们可以轻松打包和重新打包他们的科学应用程序以供短期使用。该组织依赖虚拟机和平台服务来处理大多数其他工作负载。在主要存储供应商(包括戴尔/EMC、惠普和 IBM 等巨头)中，只有 NetApp 制定了管理多种存储资源的一致战略。他说，大多数仍集中在存储阵列层面。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>