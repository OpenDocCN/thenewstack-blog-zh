# 查看 Kubernetes 部署|新堆栈

> 原文：<https://thenewstack.io/kubernetes/a-look-at-kubernetes-deployment/>

据[云本地解决方案](https://thenewstack.io/category/cloud-native/)高级总监 Sitaram Iyer 称，Kubernetes 已经成为整个行业的事实标准，以确保容器工作负载按照规范运行并且可以扩展。 [Kubernetes](https://thenewstack.io/primer-how-kubernetes-came-to-be-what-it-is-and-why-you-should-care/) 现在被描述为世界上最大的集装箱化工作负载编排平台——83%的[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)成员已经在生产中使用它。

“通过自动化集装箱化的环境，Kubernetes 实现了一个动态的、多声音的、多开源的环境，这个环境也是可扩展的、经济高效的和富有成效的——一个开发者的天堂，”Iyer 说。

但是，为了让开发者真正到达并享受这个天堂，他们必须正确地部署 Kubernetes。

## 库本尼斯部署:基本步骤

伊耶说:一个特定的团队通常会对一家公司的 Kubernetes 初始部署进行工作。该团队通常会创建用于实验和“踢胎”的小集群。Kubernetes 的初始介绍还提供了一个机会，以了解使用云提供商管理的服务提供的 Docker 图像和容器的基础知识，例如谷歌 Kubernetes Engine (GKE)或[亚马逊 Web 服务](https://aws.amazon.com/?utm_content=inline-mention)'弹性 Kubernetes 服务(EKS)。然而，许多人经常开始使用现有的虚拟环境在内部部署 Kubernetes。

**探索阶段**:在这一步，团队对 Kubernetes 的使用超越了实验，集群应该承载“真实的”工作负载，Iyer 解释道。这些工作负载可能是应用程序的非关键组件，也可能是[连续集成](https://thenewstack.io/category/ci-cd/) (CI)服务使用的临时工作人员。

**基础阶段**:根据 Iyer 的说法，一旦团队对自己运营和管理 Kubernetes 集群的能力有了足够的信心，他们就应该能够轻松托管分布式云本地应用程序。

**可重复阶段**:随着团队获得在生产 Kubernetes 集群中托管关键应用程序的信心和经验，他们将会很好地将遗留应用程序迁移到 Kubernetes，Iyer 说。应该很好地理解迁移遗留应用程序的挑战，并且一些迁移应该已经到位。

优化阶段:根据 Iyer 的说法，在这个阶段，团队现在应该使用定制的操作符超集，如 Knative 服务和 Argo 工作流，而不是直接使用 Kubernetes 原语。应该开发利用这些操作符的应用程序，并使用适合 Kubernetes 控制器-协调器范例的设计模式。

## Kubernetes 部署的最佳实践

Saad Malik， [Spectro Cloud](https://www.spectrocloud.com/?utm_content=inline-mention) 的联合创始人说，当组织将开发团队的技能与 [Kubernetes](https://thenewstack.io/kubernetes/) 的用户(平台工程/IT 运营团队)的技能组合、工作流/流程和工具结合起来，不断地重新评估进展时，他们在 [Kubernetes 部署](https://thenewstack.io/a-step-by-step-guide-to-continuous-deployment-on-kubernetes/)中取得了最大的成功。“将 Kubernetes 平台视为一种产品，不断从您的内部客户(开发团队)和运营商(平台工程/IT 运营团队)那里获得反馈。”

Malik 补充说，虽然整个组织可能会对最初的 Kubernetes 部署感到满意，但需求可能会迅速变化，因此公司应该事先考虑他们需要的一整套工具，以及公司将如何支持它，包括扩展、备份和恢复、更新和升级、修补等。

“从升级过程中会出现问题的前提出发，制定明确的业务连续性和灾难恢复计划，并经常测试这些计划，”Malik 说。

公司还需要确保 Kubernetes 的部署不会危及数据安全。

Malik 说:“每个添加到集群中的新集成都会带来一系列挑战，如安全漏洞、兼容性问题，它们实际上是需要管理的平台的附加层。

“尽管 Kubernetes 集群和容器本质上是安全的，但部署中最佳实践的关键是确保安全和管理是重中之重，”Iyer 补充道。“随着 Kubernetes 的成熟，这变得更加重要，因为现在更需要更大的控制和治理。”

Malik 补充说，安全和治理不能是事后的想法，尤其是如果你在生产中使用 Kubernetes。“一个真正的[零信任模型](https://thenewstack.io/what-is-zero-trust-security/)应该是一个先决条件，以及一套监控和审计功能，以提供成本(Kubecost)、策略执行(OPA、Kyverno)、RBAC (Fairwinds RBAC 经理)等所需的可见性。”

Iyer 说，未能充分解决安全问题是 Kubernetes 部署中可能犯的最大错误。“许多组织部署 Kubernetes 的方式大大增加了风险。开发团队正在从部署大型集群发展到多个较小的集群，每个集群都与一个应用、团队单元或业务区域相关。”

Iyer 解释说，这种更灵活的方法的问题是，它带来了更多的复杂性，因此需要管理更多的机器身份，因为这些集群需要安全地相互通信。“在每个 Kubernetes 集群中，每一行代码和微服务都需要一个机器身份来实现安全通信。通过部署复杂的多集群策略，创建了大量无法手动管理的身份。

Iyer 表示，许多公司正在转向 Istio 等解决方案来帮助管理这种机器身份的涌入，但这实际上增加了风险，因为 Istio 只支持自签名的机器身份，这使组织容易受到攻击。这些证书不是由公共信任的组织管理的证书颁发机构(CA)签署的，并且不能被吊销和永不过期。

## Kubernetes 部署的未来

Kubecost 等成本管理工具形式的自动化将越来越多地集成到 Kubernetes 平台中，以提供跨不同环境的实时、粒度成本监控和分析。此外，D2iQ 首席执行官鸢·克纳普预测，集中管理将使团队和基础设施平台之间的资源共享更加高效。

根据 Iyer 的说法，许多组织都在关注持续交付的下一次演变——“渐进交付”，涉及到潜在用户子集的应用程序的逐步推出，并使用学习成果向每个人交付。“渐进式交付的想法也是为了给业务领导提供更大的控制权，这样他们就可以使用功能标志之类的东西来管理交付。这在实施多租户时非常有益，因为它允许组织只为相关租户管理部署和扩展。”

Iyer 警告说，渐进式交付存在挑战，因为它可能会使系统变得复杂，并需要维护多种版本的服务和管理流量。

Malik 认为，大规模简化所有管理点并能够实现自动化将是未来成功部署 Kubernetes 的关键。能够以“即服务”的方式快速适应开发团队的不同需求，并快速集成新工具(例如多个 Kubernetes 分发服务网格等)。)将至关重要。

Malik 表示，以超额订阅“虚拟化 Kubernetes 集群”或更好的集中化管理功能为形式的效率将是另一个发展方向。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>