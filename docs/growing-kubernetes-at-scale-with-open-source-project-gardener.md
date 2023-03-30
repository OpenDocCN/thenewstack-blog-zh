# 用开源项目 Gardener 大规模种植 Kubernetes

> 原文：<https://thenewstack.io/growing-kubernetes-at-scale-with-open-source-project-gardener/>

[SAP](https://developers.sap.com/) 赞助了这篇文章。

 [托马斯·赫兹

Thomas 是 SAP 的 SAP 开发人员体验主管。他最初是 Hybris software 的创始人之一，并在 2013 年 SAP 收购 Hybris 时加入 SAP。作为云原生开发的倡导者和 SAP 开源技术的负责人，他推动了 Kubernetes 在整个 SAP 的采用，使 SAP 及其客户的创新和数字化转型变得更加容易。](https://www.linkedin.com/in/thomashertz/) 

您知道吗，在为 Kubernetes 做出贡献的公司中，SAP 位列 2019 年[前 10 名提交者之一。](https://k8s.devstats.cncf.io/d/9/companies-table)

尽管 SAP 可能是世界上最大的专有软件公司之一，但我们也有着为[多样化的开源项目](http://opensource.sap.com/)做出贡献的悠久历史。在某种程度上，我们的目标是支持企业级工具的开放开发，并支持自由讨论和协作。在 SAP，我们认为参与制定事实上的标准是非常重要的，以确保不同工具和服务的互操作性。

我们对 Kubernetes 的承诺源于实用主义。无论我们的客户在哪里，SAP 都需要提供服务，这意味着提供多云战略和统一的部署体系。Kubernetes 符合要求；它支持 SAP 客户在过渡到公共云、私有云和混合云环境时在企业范围内采用所需的工具和服务。

## 园丁是什么？

[Gardener](https://gardener.cloud/) 是一个 SAP 驱动的开源项目，解决超大规模 Kubernetes 服务的现实需求，而不考虑基础设施。它提供了一个跨任何云提供商的层，以及并行使用一系列混合 Kubernetes 集群的方法。

其结果是云原生开发者的灵活性，他们可以在他们想要的环境中使用他们想要的工具。Gardener 为当今的技术堆栈提供了一个中立的工具箱，我们将它设计为具有足够的可扩展性，这样——只需相对较少的努力——它就可以额外适应未来的工具和基础设施。没人能说 Kubernetes 生态系统会朝哪个方向发展，但 Gardener 旨在保持开放和灵活。

Gardener 的一个关键原则是在其所有任务中坚持 Kubernetes 的概念，并提供一个消除锁定的公共开放平台。许多云服务提供基于 Kubernetes 的平台，许多供应商也提供自己品牌的 Kubernetes 发行版。然而，我们发现它们限制性很强，有时技术成熟度很低，并且受到其业务模型的限制(通常局限于单一供应商)。

借助 Gardener，SAP 客户可以以同构方式和最低成本自动管理跨多个基础架构(例如，阿里云、AWS、Azure、GCP、OpenStack、Packet、MetalStack 和 vSphere)的数千个异构一致性 Kubernetes 集群。

在 SAP 内部，Kubernetes 上的工作负载范围从数据库(SAP HANA)、大数据(SAP Data Hub)、物联网、人工智能和机器学习，到多样化的业务工作负载(SAP 商务云)。最近在 Kubernetes 上包含 Gardener 的成功案例有 SAP Business Application Studio、 [SAP HANA Cloud](https://blogs.sap.com/2020/03/13/at-your-service-sap-hana-2.0-an-introduction-2/) 和 SAP 云平台扩展工厂、 [Kyma Runtime](https://blogs.sap.com/2020/05/12/get-a-fully-managed-runtime-based-on-kyma-and-kubernetes/) 。

## 为什么我们有开源的园丁？

在 SAP 内部，我们多年来一直在运行基于 Gardener 的托管服务。我们决定开源 Gardener，因为它有可能填补公司开发多云战略的空白。虽然我们没有将 Gardener 作为公共托管服务提供，但公共项目受益于我们在为客户运行我们自己的托管 Kubernetes 服务时所做的持续改进。

我们决心对 Gardener 保持透明，开发公共空间中的所有内容，然后在内部采用较小的 SAP 特定集成。保持 It 厂商中立并坚持上游 Kubernetes 的实践、设计和流程一直是必不可少的。

## 还有谁参与了《园丁》？

Gardener 的大部分参与来自 SAP 生态系统内部。最近的一个例子是 Kyma 运行时，我在 SAP 社区博客上描述了这个例子[。正式名称为“SAP 云平台扩展工厂，Kyma 运行时”，它是另一个开源 SAP 项目](https://blogs.sap.com/2020/05/12/get-a-fully-managed-runtime-based-on-kyma-and-kubernetes/) [Kyma](https://kyma-project.io/?utm_source=SAP%20Community%20blog%20post&utm_medium=Blog%20post&utm_campaign=Kyma%20runtime%20release) 的完全托管的基于 Gardener 的运行时。

在幕后，Kyma runtime 使用 Gardener 进行集群和容器管理，使其可用于所有云提供商——尽管 2020 年 6 月的初始产品基于 Microsoft Azure，并计划在未来几个月内添加更多超大规模服务器。

我们也从与 SAP 无关的公司获得了采用，例如 PingCAP 和 Finanz Informatik Technologie Services GmbH。

### 平盖

[PingCAP](https://pingcap.com/) 选择了园丁为其产品提供托管服务: [TiDB](https://en.wikipedia.org/wiki/TiDB) (兼容 MySQL 的云原生分布式 SQL 数据库)及其姊妹项目 [TiKV](https://github.com/tikv/tikv) (云原生交互式景观项目)。

正如最近的一篇博客文章所描述的，PingCAP 以前使用过其他公共管理的 Kubernetes 集群服务，但是他们遇到了一些技术问题。他们认为自己受制于云提供商特定的 Kubernetes 系统升级，并对有限的支持和缺乏对问题修复时间表的控制感到沮丧。

另一个缺点是遵循多云策略所需的特定于云的集成工作的范围。对于托管的 Kubernetes 服务，有必要集成实例 API。PingCAP 团队对 Gardener 印象深刻，它为所有云提供了统一的抽象 API 层，并且完全消除了对特定于云的集成工作的需求。PingCAP 考虑了另一种选择——为自己构建一个托管的 Kubernetes 服务——但很快意识到这将是一个复杂且昂贵的选择。所以他们选择使用 Gardener 来构建他们的 TiDB 云。

### 金融信息技术服务有限公司

[Finanz Informatik Technologie Services GmbH](https://f-i-ts.de/)使用 Gardener 为德国金融行业的客户提供 Kubernetes 托管服务。他们的服务建立在“金属即服务”基础设施之上，从零开始实施，并考虑到 Kubernetes 的工作负载。

当团队开始寻找一个基础设施平台来运行他们的 Kubernetes 服务时，他们有了更高的要求。这些要求包括快速配置、与 Kubernetes 及其服务的紧密集成、针对敏感环境的高度隔离、现代网络设计，以及从自己的数据中心提供云原生体验的能力。

正如该团队的一名成员在最近的博客文章中解释的那样，“SAP Gardener 是一个与云无关的 Kubernetes 集群管理器，它为 Kubernetes 的安装和管理提供了一个 API。它是通过一个 [Inception design](https://kubernetes.io/blog/2019/12/02/gardener-project-update/) 实现的，遵循了我们设定为目标的相同的 Kubernetes 惯用原则。由于我们不想手动管理我们所有的 Kubernetes 集群，这成为我们架构的重要组成部分。”

## 开源的好处

时至今日，对 Gardener 的贡献中有很大一部分来自 SAP，但是这种贡献越来越受欢迎，也有稳定的非 SAP 贡献流。我们相信，我们可以通过透明度和建立睦邻友好的生态系统来增进信任。

在 SAP 内部，园丁正在影响和催化变革。我们已经有了很好的内部外包的例子，内部的利益相关者直接为开源软件项目做贡献，并且在公共场合做几乎所有的事情。一个这样的例子是新的 [gVisor 容器运行时](https://github.com/gardener/gardener-extension-runtime-gvisor)，它是我们的同事开发 SAP Business Application Studio 所需要的。SAP 中处理园丁事务的核心团队鼓励他们直接在社区中加强这一努力。这对每个人来说都是一次很棒的经历。

[园丁](https://gardener.cloud)、 [Kyma](https://kyma-project.io/) 、 [Luigi](https://luigi-project.io) 、 [UI5](https://openui5.org) 和其他开源项目正在改变人们对开源软件的看法，从消费和附加软件到基础软件，甚至在大公司中也是如此。

## 未来会怎样

在 SAP 内部，我们开发了 Gardener 来为我们的客户提供单一、一致的 Kubernetes 特性集，该特性集对资源和底层基础设施进行抽象，并且可以在任何地方被 SAP 解决方案使用。我们看到那些开发应用程序并在多个云中部署它们的人正在接受，并期待着与社区合作来扩展 Gardener 并为未来的工具和基础架构提供超大规模 Kubernetes 服务。

*访问* [*SAP 开发人员中心*](https://developers.sap.com/open-source.html) *了解有关 Gardener 和其他 SAP 驱动的开源项目的更多信息。*

通过 Pixabay 的特征图像。

*目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过推特或 T21 脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>