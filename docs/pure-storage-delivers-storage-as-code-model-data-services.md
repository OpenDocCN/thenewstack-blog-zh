# 纯存储提供云存储、数据服务

> 原文：<https://thenewstack.io/pure-storage-delivers-storage-as-code-model-data-services/>

[Pure Storage](https://blog.purestorage.com/products/introducing-the-industrys-first-self-service-storage-as-code-platform/) 正在推出存储即代码平台和数据服务计划，因为官员们希望在日益以数据和云为中心的 IT 世界中扩大供应商的存在。

最近推出的新产品将 Pure 通过其存储产品组合和云功能提供的大部分内容整合到一个平台上，并利用了该公司去年底以 3.7 亿美元收购 [Portworx](https://portworx.com/?utm_content=inline-mention) 时继承的 [Kubernetes](https://thenewstack.io/why-developers-should-learn-kubernetes/) 技术。

该公司推出了 [Pure Fusion](https://www.prnewswire.com/news-releases/pure-storage-introduces-pure-fusion-a-self-service-autonomous-storage-as-code-platform-built-for-limitless-scale-301386651.html) ，这是一个包括软件即服务(SaaS)管理平面的平台，该管理平面在类似云的可用性区域中汇集存储阵列，即使在公共云中也能轻松扩展，并自动执行工作负载放置、配置和设备群重新平衡等任务。

按需存储即代码模式通过一个异步和可操作的 API 框架实现，集成了开发人员工具，如 [Terraform](https://thenewstack.io/a-better-way-to-provision-kubernetes-using-terraform/) 和 [Ansible](https://thenewstack.io/red-hat-brings-ansible-automation-to-kubernetes/) ，加快了配置和部署时间。Pure Fusion 旨在消除手动后端工作，使企业能够快速使用存储卷、文件系统和复制等数据服务。

该平台将首先集成 Pure 的 [FlashArray//X NVMe](https://www.purestorage.com/products/nvme/flasharray-x.html) 和 [FlashArray//C 全 QLC](https://www.purestorage.com/products/nvme/high-capacity/flasharray-c.html) 闪存以及 [Pure 的云块存储](https://www.purestorage.com/products/cloud-block-storage/cbs.html)。未来的集成将包括 Portworx 和 FlashBlade，后者旨在整合文件和对象数据。

“Pure Fusion 提供了一种全新的、近乎无限的横向扩展存储模式，可以统一阵列并动态优化存储池，”Pure flash array 业务部门的产品管理副总裁[丹·科岗](https://www.linkedin.com/in/dan-kogan/)在[的博客文章](https://blog.purestorage.com/products/introducing-the-industrys-first-self-service-storage-as-code-platform/)中写道。“它通过按需消费和后端配置，将云运营模式的简单性带到了任何地方。”

## **纯数据服务**

与此同时，Pure 推出了 Portworx 数据服务，官员们称之为 Kubernetes 的数据库即服务平台，可实现管理自动化，并为 DevOps 工程师提供了一种在 Kubernetes 上部署生产级数据服务的方式，并从一系列选项中进行选择，包括 SQL、NoSQL、搜索、流媒体和分析服务。

数据服务的出现正值微服务、容器和 Kubernetes 成为构建现代应用和服务的基础。Portworx 产品营销高级总监 Michael Ferranti 表示，微服务倾向于使用各种数据服务，而不是像 Oracle 或微软的 SQL Server 那样的单一数据库。相反，现代应用程序使用专门的数据服务，包括 Postgres 和 MySQL 等 SQL 选项和 MongoDB、Cassandra、Elasticsearch 和 Kafka 等 NoSQL 选项。

“但这些数据服务都有自己的部署方式、自己的监控方式和自己的备份和恢复管理方式，”Ferranti 在一篇博客文章中写道。“这给负责管理这些服务的开发运维团队带来了巨大压力。他们不仅要管理许多数据库实例，还要管理大量的数据库类型。因此，DevOps 团队专注于消防部署和运营，而不是提供创新。一种自助式、按需配置这些关键服务的方式使它们易于扩展、可用且安全。”

## **推云一把**

根据 Moor Insights and Strategy 的高级分析师 [Steve McDowell](https://moorinsightsstrategy.com/steve-mcdowell/) 的说法，Pure Fusion 将于今年年底进行预览，并于 2022 年上半年正式推出，Portworx 数据服务(早期访问计划的注册可在[此处](https://ask.portworx.com/portworx-data-services-early-access/)找到)是 Pure 努力提供简单和类似云的功能的关键步骤。

“云给 IT 世界带来的最大影响之一是，人们期望一切都可以从一个屏幕上管理，”麦克道尔告诉新堆栈。“纯存储可以实现这一点。该公司一直专注于可用性和体验的简单性，而(该公司的)声明只是强化了这一点。”

此外，IT 管理的发展“包括一剂健康的基础架构即代码，IT 管理员可以开始将存储资源调配和管理集成到可编程操作工具中，这些工具已成为企业 IT 管理的支柱。Pure 的新 Fusion 正好插入那个环境，”他说。

## **纯粹的进化**

12 年前，Pure 以其 Purity 操作系统成为全闪存存储提供商，近年来，该公司接受了 IT 向[多云](https://thenewstack.io/the-pros-and-cons-of-multicloud/)和[混合云](https://thenewstack.io/ibm-expands-hybrid-cloud-portfolio-with-power10-e1080-server/)环境的持续转变，包括提供其产品组合即服务。它在 2017 年开始为块存储提供灵活的消费模式，一年后推出了 Evergreen 存储服务，通过订阅提供其技术。该计划在 2019 年更名为 Pure as-a-Service，提供云运营和云经济。

作为大型混合云部署的一部分，Pure 的“即服务”和云推动与其他存储和 IT 硬件供应商正在努力满足内部环境中类似云的功能需求的做法是一致的。Hewlett Packard Enterprise、Dell Technologies、Lenovo 和 Cisco Systems 等供应商已经启动了将他们的产品组合(包括他们的存储产品)作为服务的计划。

麦克道尔说，在 Pure Fusion 和 Portworx 数据服务发布之前，Pure 已经拥有最好和最完整的管理体验，此次更新巩固了这一地位。

“其他存储供应商倾向于根据服务级别(例如，中端与企业)对存储产品进行细分，向每个细分市场提供不同的产品，”该分析师说。“这种方法使得简化可管理性和在整个产品系列中提供一致的云式管理体验变得非常困难。因此，许多较大的存储供应商对不同的产品有不同的管理经验，这使得每个人的工作都变得更加困难。”

据 McDowell 称，Pure 从一开始就在其产品中提供了一定程度的简单性，使其能够提供跨平台和云环境一致的存储和管理体验。简单性超越了资源管理，进入了新存储和服务的采购和交付模式。

收购 Portworx 及其基于 Kubernetes 的 multicloud 平台使 Pure 能够扩展其数据服务能力，并在蓬勃发展的 Kubernetes 和 containers 领域占据更大份额。McDowell 说，业界仍在努力理解 IT 管理员希望从这些工具中得到什么，与 Portworx 的结合使 Pure 朝着一个坚实的方向发展。

“我喜欢 Pure 没有试图将 PortWorx 与其存储产品捆绑得太紧，”他说。“云原生的价值在于它为 it 架构师和管理员带来的灵活性，这只有通过平台无关的方法才能真正实现。这并不是说 Pure 不能与 Portworx 和 Pure 的阵列实现“更好的合作”,我们在 3 月份就看到了这方面的声明，但他们将继续保持这种独立性。这对每个人都有好处。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>