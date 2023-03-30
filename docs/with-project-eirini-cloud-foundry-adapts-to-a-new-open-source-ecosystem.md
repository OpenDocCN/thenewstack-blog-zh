# 通过项目 Eirini，Cloud Foundry 适应了一个新的开源生态系统

> 原文：<https://thenewstack.io/with-project-eirini-cloud-foundry-adapts-to-a-new-open-source-ecosystem/>

Cloud Foundry 的年轻时代已经过去了。这一点在本周费城举行的云铸造峰会上显而易见。现在，从用于启动 12 因素应用程序的开源平台到尊重其根源但继续通过[项目 Eirini](https://www.cloudfoundry.org/project-eirini/) 扩展的平台的持续过渡，ei rini 是一个用于 Cloud Foundry 的 Kubernetes 后端，它使用 OCI 映像和 Kubernetes 部署将 Cloud Foundry 应用程序部署到 Kubernetes 后端。

在 GitHub 上被描述为“[Orchestrator Provider Interface](https://github.com/cloudfoundry-incubator/eirini)”(OPI)，Eirini 可以用来翻译为 Diego 编写的运行时指令，Diego 是为 Cloud Foundry 构建的调度程序，因此它们可以被 Kubernetes 理解。Eirini 是作为一个后端调度程序构建的，带有一个 API，从 Cloud Foundry 的控制平面抽象出编排。它可以与任何调度程序，无论是迭戈，Kubernetes 或 Docker 群。在其核心，OCI 拥抱长期运行过程(LRP)的概念和映射到编排器的任务。目前，这意味着对 Kubernetes 的支持。只要有针对目标平台的 OPI 层的实现，就可以集成其他编排器。

Eirini 最初是由 IBM 开发的，它在由 [Jason McGee](https://twitter.com/jrmcgee) 和 [Briana Frank](https://twitter.com/FranklyBriana) 主持的云铸造峰会主题演讲中展示了一个用例。

在 Cloud Foundry 峰会上，Eirini 是关注的焦点。它反映了随着成员组织的成熟和开发他们的开发团队所带来的变化和适应。随着开源社区成为应用程序开发的中心，供应商正在适应这些变化。这种变化对所有参与者来说都是外在的。这些社区开发技术，然后开发人员使用这些技术构建现代应用程序，这些应用程序使用多种服务，我们通常称之为微服务方法。

## 云铸造打造未来

Cloud Foundry Foundation 不得不适应这些年，尤其是像 Kubernetes 这样的开源技术受到了如此多的关注。Cloud Foundry 领导人经常会喜欢谈论 Kubernetes 是如何被炒作的。他们的观点是，不总是新的和闪亮的是需要的。财富 500 强公司的客户需要不断发展的开发团队所需的基础知识。对于刚接触持续集成和持续交付的组织来说，12 个因素的应用程序仍然足够复杂。解决办法一直是提供专业服务，帮助会员组建团队，并开始大规模开发、部署和管理流程。

领先的 CF 提供商 Pivotal 构建了一个平台，该平台使用结对编程模型来帮助组织建立开发人员团队。该公司的方法受到康卡斯特(Comcast)等客户的欢迎，他们利用这种模式超越了有线电视提供商的范围，成为多频道娱乐提供商。

因此，关于云铸造的未来的讨论仍在继续。以及它的方向。但这不再仅仅是关于 Cloud Foundry，而是 Cloud Foundry 如何与不同的运行时、云服务、调度程序和编排引擎进行互操作。Kubernetes 可能会得到很多关注，但它的未来也受到质疑，以至于即使 Kubernetes 享有如此广泛的人气，客户仍然希望迭戈活着，过得好。

《财富》500 强中约有一半的公司使用 Cloud Foundry，如 Comcast、Liberty Mutual 和 Home Depot。即使它不再是过去的“一个”平台，它仍然生机勃勃。

认为只有一个平台是荒谬的。当有如此多的其他服务相互依赖时，专注于一个平台的宣传也是荒谬的。CF 必须适应这个新的世界，它的客户也是如此，他们长期以来一直依赖 Diego 作为他们的调度选择。但是 Diego 与 CF 紧密相关，并且这种转变，正如多年来一样，是为了跨分布式系统的更松散耦合的架构。

尽管如此，离开迭戈的担忧是真实的。开发人员传统上使用 Cloud Foundry API (CAPI)将他们的代码推送到他们的应用程序中。此外，Diego 对于使用 Diego 来监控应用程序、其弹性和许多其他因素的平台运营商来说是至关重要的。

但现实是，经济在很大程度上发挥了作用。没有一家公司能开发这种软件。他们只是没有足够的人力来构建、部署和支持技术堆栈，然后以数十万美元的价格出售。这对他们来说太贵了，开发商有太多的选择。

对于开源社区来说，这也是一个经济问题。像 Cloud Foundry 这样的组织必须进行调整，以满足他们的社区和 Pivotal 这样的大型供应商的需求，这些供应商将工程师投入到项目中。

而用户本身呢？对于 Cloud Foundry Foundation 的赞助商来说，比如 Comcast，对开发人员工具的关注带来了好处。

[https://www.youtube.com/embed/wT1ZImIYkrs?feature=oembed](https://www.youtube.com/embed/wT1ZImIYkrs?feature=oembed)

视频

Cloud Foundry 和 Pivotal 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>