# Weaveworks 将策略添加为代码，以保护 Kubernetes 应用程序

> 原文：<https://thenewstack.io/weaveworks-adds-policy-as-code-to-secure-kubernetes-apps/>

Weaveworks 通过提供新的策略代码功能来编织 GitOps，从而增加了 GitOps 平台的安全性。

随着[weaver works](https://www.weave.works/)继续努力实现 Kubernetes 应用和基础设施运营的自动化，额外的安全性将在整个软件开发和部署生命周期中为企业提供安全的 [GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 管道。

Weaveworks 通过收购西雅图的 [Magalix](https://www.magalix.com/) 将策略作为代码添加进来，Magalix 专门为开发人员和安全团队构建工具，以在他们的软件开发生命周期中编纂安全性和合规性。

## 将云和 Kubernetes 安全性转移到左边

RedMonk 的联合创始人 James Governor 在一份声明中表示:“策略即代码是一个重要的趋势，为采用基于 Kubernetes 的分布式系统的企业的安全性、合规性和 guardrails 工作提供了基础。”

Weaveworks 首席执行官 [Alexis Richardson](https://www.linkedin.com/in/richardsonalexis/?originalSubdomain=uk) 表示:“我们相信 GitOps 是解决客户和云原生应用运营问题的正确方式。

根据 IDC 2020 年的一项研究， [67%的云安全漏洞](https://www.idevnews.com/stories/7376/IDC-Study-Finds-Cloud-Data-Breaches-Impact-80-of-CISOs)是由错误配置的应用程序或基础架构造成的。

Gartner 分析师 Chris Saunderson 在去年的一份报告中表示:“基础设施自动化增强了应用交付，支持内部部署和云拓扑。“GitOps 和策略即代码方法和工具，辅以漏洞优先级技术平台，将推动安全和合规性要求的评估和执行。”

Magalix 的创始人兼首席执行官 Mohamed Ahmed 说:“政策即代码就是将你的安全标准和最佳实践编成法典。

## Magalix 的魔力

“Magalix 就是增加护栏，这样你就可以快速移动而不会弄坏东西，”他说。“Magalix 是基于开源的[开放策略代理(OPA)](https://www.openpolicyagent.org/) 。我们有一套全面的政策库。第二，我们集成了市场上现有的 DevOps 工具。我们带来的最后一件东西是我们为任何构建云原生应用的组织中的所有关键参与者提供的见解和全面报告。”

Richardson 指出，通过添加 Magalix，Weaveworks 为 GitOps 工作流提供了可定制的策略、合规性能力和全面的风险可见性，确保只部署授权的应用程序，并且没有恶意活动。

Magalix 成立于 2017 年，专注于为运行云原生应用的团队提供安全代码。此外，利用 Magalix 的安全功能，客户可以使用与 Kubernetes 相同的声明性方法来控制和执行策略，以扩展他们的应用程序，同时保持监管要求和安全最佳实践，Ahmed 说。

他在一份声明中说:“我们看到越来越多运行零信任安全模式的客户转向 GitOps，将 DevOps 引入云原生应用开发和 IT 运营。”

## 企业客户需求

理查森说，Weaveworks 已经收到了许多大型企业客户对额外安全性的要求。

“因为最大的客户在合规性要求方面非常先进，他们中的许多人都受到监管，”他告诉新的堆栈。“他们中的许多人都有需要照看的数据。但他们没有做的是采用 Kubernetes。在规模上，他们已经做到了 POC(概念验证)级别。阻止他们这么做的只是我如何让它变得安全？他们想要我描述的所有东西，你知道，安全，安全的管道，合规性，能够在坏事发生之前阻止它们发生，供应链验证等。这些都是客户不断提出的问题。”

一个大客户，德国电信，正在使用 Weaveworks 和 GitOps 推出针对云原生 5G 部署优化的 Kubernetes。

“一旦我们授权我们内部的 Kubernetes 平台团队在 Weaveworks 的支持下向前发展，他们就在几个月内将一个工作系统投入生产，并在 2021 年实现 5G，”德国电信 SVP 技术部门的 Abdu Mudesir 在一份声明中说所有这些都是通过 GitOps 模式实现的。"

## 可信交付

可信交付将策略作为代码添加到 GitOps 中，在 DevOps 工作流中加强安全性。GitOps 可信交付意味着:

*   策略即代码从源代码到产品实施安全性和合规性:Magalix 的策略引擎使 DevOps 团队能够在多个 Kubernetes 环境中应用一致的策略和最佳实践。客户现在可以通过引入开发人员防护栏，在开发人员、开发人员和安全团队之间架起一座桥梁。
*   运行时策略和漂移管理保护措施可保护生产部署:Magalix 的 KubeGuard 代理可确保检测到任何运行时漂移并自动修复。客户可以放心，策略会在所有部署中得到执行，并且会立即意识到任何违规行为。
*   在 GitOps 工作流中嵌入安全性:Magalix 通过直接集成到软件生命周期的源代码、构建和部署阶段，简化了 DevSecOps 并使云原生环境更加安全。

Weaveworks 正在将 Magalix 集成到 [Weave GitOps Enterprise](https://www.weave.works/product/gitops-enterprise/) 中，在混合云、多云和边缘环境中提供 Kubernetes 安全性、增强的可见性和跨云原生生命周期的弹性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>