# 如何充分利用 GitOps

> 原文：<https://thenewstack.io/how-to-get-the-most-out-of-gitops/>

[](https://www.pexels.com/photo/wood-fishing-fashion-people-6478153/)

 [乔迪蒙公司

乔迪是 Weaveworks 的产品营销总监。他是一名开源产品专家、社区建设者和公共演说家。他是 OpenUK 和 PMM 联盟大使，常驻伦敦。](https://www.pexels.com/photo/wood-fishing-fashion-people-6478153/) [](https://www.pexels.com/photo/wood-fishing-fashion-people-6478153/)

GitOps 是 Kubernetes 应用程序和集群的操作模型。它集中并自动化了大部分配置工作负载，持续监控和纠正不一致。它通过将所有操作信息存储在 Git 这样的版本控制系统中来做到这一点，而不仅仅是将 Git 用于应用程序代码。结合 Kubernetes 的内置自动化功能和一些额外的监控软件，GitOps 有助于降低操作复杂性，加快新功能的部署，并提高整个交付流程的安全性。

如果发生最坏的情况，将应用程序回滚到以前的版本可以在几分钟内完成，而不是几个小时——即使这意味着破坏集群并从头开始重建。这是几乎每个组织都需要的超级力量，因为在这个世界上，几乎每个公司都是软件公司，你在交付软件方面做得越好，你就越有竞争力。

> 正如 Kubernetes 被认为是实现云原生应用的最佳方式一样，GitOps 也逐渐被认为是实现 Kubernetes 的最佳方式。

由于这些原因，GitOps 现在被全世界采用。正如 Kubernetes 被认为是实现云原生应用的最佳方式一样，GitOps 也越来越被认为是实现 Kubernetes 的最佳方式。然而，并不是所有的 GitOps 实现都是平等的。您对 GitOps 的承诺程度决定了您将享受其好处的程度。

这不仅仅是功能集不同的竞争厂商的问题；毕竟，大多数 GitOps 组件都是开源的。不同的是你准备采用最佳实践的水平。这是一个光谱。您的承诺越大，[您的组织将获得越多的利益](https://www.weave.works/blog/gitops-for-cost-efficiency-compliance-velocity-security-and-resilience)。

那么，你如何知道自己在光谱中的位置呢？正如技术世界中的许多事情一样，有一种模式。作为 GitOps 供应商，我们在 Weaveworks 开发了 [GitOps 成熟度模型](https://go.weave.works/2021_GitOps_Maturity_Model.html?LeadSource=Web%20Content&LSD=Website&CampaignID=7014M000001zDhf)。它确定了采用 GitOps 的四个级别，从实现先决组件到大规模、全组织的采用。

## **GitOps 成熟度模型**

成熟度模型的想法并不新鲜。Thoughtworks 的作者[马丁·福勒](https://martinfowler.com/bliki/MaturityModel.html)将成熟度模型描述为“一种工具，它帮助人们评估一个人或一个团队当前的效率，并帮助他们计算出为了提高他们的绩效，他们下一步需要获得什么能力。”简而言之，它告诉你现在在哪里，更重要的是，告诉你下一步的目标。

基于多年的实际 GitOps 部署经验，GitOps 成熟度模型反映了从 GitOps 中获得最大收益的组织所经历的历程。

### **零级:先决条件**

这个旅程通常从零级(L0)开始。从技术上讲，这根本不是完整的 GitOps，因此是零。虽然它表明一个组织已经经历了某种程度的数字化转型(例如，迁移到云并使用容器化的基础架构)，但它应该被视为 GitOps 之旅的一个点。一个组织可能在 Git 中存储至少一个应用程序的配置信息，这意味着他们可以更快地部署，并受益于一定程度的可重复性。但关键是，他们还没有利用 GitOps 的持续协调功能。

### **第一级:核心 gitop**

在一级(L1)，这是一个不同的故事。正如 Git 中所描述的，系统会不断地检查生产环境中运行的应用程序与其期望状态之间的差异。如果检测到任何漂移，系统将向操作人员发出警报。这种自动化程度提高了部署频率以及运营的可见性和可审计性，这对于受监管行业和任何处理客户数据的企业都至关重要。它还有助于降低成本和平均恢复时间(MTTR)。

### **二级:企业 GitOps**

第二级(L2)则更进一步。现在，整个 GitOps 自动化功能已经在整个环境中生效。运营团队可以管理跨不同地区、区域甚至云的多个集群。这反过来又允许开发人员在从开发到生产的过程中，完全专注于创建增加业务价值的新功能，而没有破坏东西的风险。与此同时，运营团队可以专注于治理、风险和合规协议，轻松扩展集群基础架构，而无需雇用新员工。对于许多有企业需求的组织来说，这个级别构成了完整的 GitOps。

### **第三级:缩放 GitOps**

第三级(L3)是关于大规模的。在这里，集群的整个舰队通过 GitOps 进行管理，从而实现整个舰队的一致性、明确的政策执行和更高的开发速度。此级别的组织受益于跨多个云的应用程序可移植性，以及跨云和内部基础架构运行数千个集群的能力。显然，这种自动化水平并不适合所有人，但是车队管理对一些人来说是必不可少的。一个现实世界的例子是[德国电信的 Das Schiff](https://www.weave.works/blog/kubernetes-at-deutsche-telekom-gitops-at-the-edge) 项目，旨在持续向数千个边缘集群提供 5G 工作负载。

## **将模型付诸实践**

GitOps 的势头越来越大。云计算原生计算基金会的 GitOps 工作组现在正在指导它的开发，成员包括微软、亚马逊、GitHub、Codefresh 和 Weaveworks。

在某种程度上，它的成功是因为 GitOps 不仅仅是一项技术。它是一组伴随着一系列过程和最佳实践的技术。它还有一个至关重要的额外好处:所涉及的技术大部分是人们已经在使用的技术。开发者懂 Git。DevOps 和平台团队了解 Kubernetes。所以从某种意义上来说，GitOps 并不是一个新事物；这只是一种新的做事方式。它们恰好是几乎每个组织都需要做的事情。

GitOps 成熟度模型本质上是一组路标。如果你想充分利用 GitOps，他们会为你指出正确的方向。但它们并不是 GitOps 成功的主要驱动力。这归结为一组明确的、已被证实的商业利益，以及大多数团队已经拥有将它投入工作所需的大部分技能的事实。

*如需了解更多信息，请阅读白皮书《[GitOps 成熟度模型——持续交付的 4 个进化步骤](https://go.weave.works/2021_GitOps_Maturity_Model.html?LeadSource=Web%20Content&LSD=Website&CampaignID=7014M000001zDhf)》，或观看点播网络研讨会《[您的 GitOps 成熟度之路](https://go.weave.works/2021-07-29-Webinar-Your-Path-to-GitOps-Maturity_On-Demand_LP-Registration.html?LSD=Webinar&CampaignID=7014M000001zH9bQAE&Person%20Source=TNS)》*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>