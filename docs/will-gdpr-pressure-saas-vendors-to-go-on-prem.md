# GDPR 会向 SaaS 供应商施压，让他们进行内部部署吗？

> 原文：<https://thenewstack.io/will-gdpr-pressure-saas-vendors-to-go-on-prem/>

[](https://www.influxdata.com/)

 [克里斯·丘里洛，InfluxData 技术产品营销总监

克里斯·丘里洛在 InfluxData 负责技术产品营销。在 iPass 担任产品管理副总裁后，她曾在 Centroid 定义和设计了一个 SaaS 监控解决方案。她还担任过多个云服务的业务线角色，这些云服务要求她跟踪运营指标和分析，以帮助识别和解决系统问题。](https://www.influxdata.com/) [](https://www.influxdata.com/)

自从《通用数据保护条例》( GDPR)于 5 月 25 日生效以来，人们疯狂地试图让数据操作变得有条不紊。

GDPR 背后的意图似乎是一套合理的法规来保护用户。然而，我们中的许多人，如果不是大多数人，对如何实施该法规中的一些要点感到有点困惑。

InfluxData 的客户 gravity 在其网站上发布了一篇精彩的博文，提供了对 GDPR 的[解读，解释了该法规的许多模糊术语。它还介绍了 GDPR 合规性如何增加 SaaS 提供商的成本，并可能最终引导 SaaS 供应商考虑提供其 SaaS 解决方案的本地版本。](https://gravitational.com/blog/gdpr-impact-on-saas-vendors/)

原因很简单:一旦 SaaS 供应商收集了欧盟(EU)居民的数据，法规就会生效，必须实施对这些数据的潜在新控制措施。此实施的成本可能会很高，因此可能需要向欧盟客户提供本地版本，以将收集的数据保存在欧盟内部，并置于客户自己的数据中心或私有云的保护之下。

然而，构建 SaaS 解决方案的本地版本传统上非常困难，而且成本高昂。这是因为这样做需要部署不同版本的基础架构，并且面临运行基础架构版本的复杂问题，而 SaaS 供应商不一定能够控制这些版本。

gravity 认识到了这一问题，并决定创建一项服务来帮助 SaaS 提供商在多种环境中部署和管理他们的应用，包括本地、私有云和公共云。它还认识到，该解决方案需要为分布式基础架构中复杂的多层应用程序提供多区域部署和管理，以及监控系统和应用程序性能的方法。

通过其 Telekube 产品，gravity 解决了 SaaS 的便携性和安全性问题，让 SaaS 提供商加入 Kubernetes，并帮助他们将 Kubernetes 传送到各种远程环境。由于这些 SaaS 提供商依赖 Telekube 的赚钱解决方案，因此保持整个环境正常运行至关重要，包括 Kubernetes、微服务、数据库和应用程序。这样做需要为所有级别的所有这些组件以及几个冗余监控系统收集指标和事件。

让我们看看他们在做什么。gravity 部署用于监控的第一个东西是 Kubernetes 本身，它可以提供关于集群状态的有趣信息。它还在 Kubernetes 内部提供文件系统监控，检查节点是否准备好。除此之外，gravity 还提供了一个名为 Satellite 的独立分布式检查器，部署在集群中。Satellite 旨在结合 Kubernetes、操作系统和各种其他组件的指标，以便在低级组件出现问题时发出警报。这样，如果主要监控解决方案或 Kubernetes 出现故障，Satellite 仍能传播关键指标

令人印象深刻的是，gravity 在其监控系统中为网络组件、数据库、存储、CPU 等建立了类似的冗余。正是这种努力以及在其产品中使用的 Kubernetes 组合，使 gravity 能够为其 SaaS 客户提供可用性、便携性和安全性，从而帮助他们遵守监管要求。

构建 SaaS 平台的本地版本只是 SaaS 供应商为实现 GDPR 合规性而可以实施的许多事情之一，而通过类似 gravity 构建的解决方案使其易于管理可能是答案。在任何情况下，肯定会有许多其他有趣的解决方案来帮助任何组织遵守法规，并成功地保护用户数据的隐私和安全。

InfluxData 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>