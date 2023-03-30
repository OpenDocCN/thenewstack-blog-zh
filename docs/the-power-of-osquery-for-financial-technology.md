# Osquery 为金融技术带来的力量

> 原文：<https://thenewstack.io/the-power-of-osquery-for-financial-technology/>

[](https://www.linkedin.com/in/jgcolvin/)

 [杰里米·科尔文

杰里米·科尔文是 Uptycs 的一名技术产品营销经理，他喜欢学习如何实现良好的安全性。在加入 Uptycs 之前，Jeremy 在德勤工作了两年，帮助客户设计、配置和实施安全系统。他毕业于普林斯顿大学，获得公共和国际事务学士学位，专注于隐私和信息安全政策。](https://www.linkedin.com/in/jgcolvin/) [](https://www.linkedin.com/in/jgcolvin/)

金融科技安全团队肩负着一项艰巨的任务:保护不断发展的攻击面，这种攻击面来自于在投资和消费者银行、加密货币等领域使用技术作为差异化因素，同时还要遵守多项联邦和州法规。

金融科技组织总是在寻求创新，这也体现在他们的安全团队中。向云原生环境的显著转变促使这些安全团队在扩展时采用能够提供可靠、灵活和深入覆盖的解决方案。

为了保护他们的 IT 生态系统，安全团队不仅对内部解决方案实施传统的安全控制，而且还关注云原生基础架构中出现的新威胁。在这篇博客中，我们将深入探讨金融科技安全团队隐藏的超能力，以及他们如何使用这种超能力的一些真实例子。让我们来分析一下为什么安全团队将 osquery 作为关键的安全解决方案。

## Osquery:金融科技安全团队的差异化优势

那么，他们是如何实现大规模云原生安全性的呢？当然，这一切都始于优秀的人员和流程。任何团队的第一个技术步骤都是了解您的环境和您正在保护的资产。在这一阶段，您将希望获得对您的资产的丰富可见性，为您提供执行最佳实践的清晰基础，如主动强化您的资产或检测整个环境中的异常。为了实现深入可见性的基础，团队正在使用 osquery universe 来支持强大的以分析为中心的安全计划。

对于不熟悉的人来说， [osquery](https://osquery.io) 是一个高效、可伸缩的代理，它从 macOS、Linux、Windows 和容器工作负载中收集大量遥测数据。轻量级代理将数据标准化为易于查询的 sql 表，从而可以轻松地询问您的资产、跟踪合规性配置、检测异常或恶意签名，以及深入了解您的安全状况的实时状态。

通过 [Uptycs](https://www.uptycs.com/) ( [kubequery](https://github.com/Uptycs/kubequery) 和 [cloudquery](https://github.com/Uptycs/cloudquery) 开发的两个扩展，osquery 的结构化安全分析概念已经扩展到支持 Kubernetes 和云服务提供商，如[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)，谷歌云平台和 Azure。经过深思熟虑的部署，该工具支持统一的端点和云原生应用程序保护计划，以全面覆盖您的资产群。

基于 osquery 的强大安全分析可以推动对几乎无限使用情形的支持:主动型(审计和合规性、软件资产管理)、反应型(检测和调查)和保护型(阻止、补救、治理)。

如果您想从零开始了解 osquery 领域，您可以从这里开始:

## Osquery 与 FinTech 安全团队合作

osquery universe 的一大优点是用户社区中的支持和知识共享。Uptycs 通过一年一度的 [osquery@scale](https://www.osqueryatscale.com/) 会议帮助引领这一趋势，该会议汇集了将 osquery 作为其 IT 生态系统核心部分来构建行业领先的安全计划的组织的故事。

下面是两个强调使用 osquery 的好处的演示:

## 条带检测

金融服务平台 [Stripe](https://stripe.com/) 在其所有部署中优先考虑主动、实际的安全可观察性，目标是自动化威胁检测和响应工作流。Stripe 安全工程师 Russ Nolen 的演示深入探讨了他们优化 osquery 的方法，以支持以下内容:

●大规模安全观察

●分析行为变化或异常的能力

●代码检测自动化

[https://www.youtube.com/embed/-9BfXMYn0wk?feature=oembed](https://www.youtube.com/embed/-9BfXMYn0wk?feature=oembed)

视频

Stripe 慷慨地分享了更多关于他们使用 osquery 的经验，以及为什么他们有信心将轻量级 osquery 代理部署到关键的生产服务器上。你可以在这里了解更多关于确保低资源利用率的步骤[。](https://www.uptycs.com/blog/optimizing-osquery-for-resource-utilization-at-scale)

## Ethos 的 DevOps 和集装箱安全

[Ethos](https://www.ethoslife.com/) 是一家快速发展的保险技术组织，致力于应对云原生环境的典型挑战。整个组织中的大多数生产力端点都是 macOS，开发人员在其中构建本地 IDE，然后通过 CI/CD 管道推动它们，最终形成 100%容器化的生产工作负载，在 Kubernetes 集群中运行。为了安全可靠地交付他们的应用，这种方法要求在整个开发运维流程中具有强大的端到端安全性可观察性。

在下面的视频中，Ethos 的安全副总裁[奥迪·卢佩斯库](https://www.crunchbase.com/person/ody-lupescu)讲述了如何使用 osquery 遥测技术来分析 DevOps 流程，以及如何改善工程师使用本地 IDE 的体验。讲座的后半部分将讨论如何从工程师的本地 IDE 开始跟踪 CI/CD 管道中的工作负载，直至将其推入生产环境。卢佩斯库帮助揭示了 osquery 如何帮助他的 DevOps 团队减少摩擦，以及如何安全地跟踪他们的每一个工作负载的开发、暂存和部署。

[https://www.youtube.com/embed/eNkch_yRYYo?start=12&feature=oembed](https://www.youtube.com/embed/eNkch_yRYYo?start=12&feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>