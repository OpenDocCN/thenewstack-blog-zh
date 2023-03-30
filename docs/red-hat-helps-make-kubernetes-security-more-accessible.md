# Red Hat 有助于提高 Kubernetes 的安全性

> 原文：<https://thenewstack.io/red-hat-helps-make-kubernetes-security-more-accessible/>

向云原生的转变代表了一个组织的 DevOps 团队可以实施的一个重大(如果不是最雄心勃勃的)计划。挑战之一是管理安全性的复杂性，在高度分布式的 Kubernetes 环境中，风险和挑战甚至更大。为这些高度分散的容器化环境采用综合平台的必要性促使 Red Hat 提供了它所说的综合安全管理平台和用于云原生安全的相关工具。

在底特律的 KubeCon + CloudNativeCon 期间，Red Hat 代表与新的 Stack 讨论了该公司的最新努力，以帮助将 Kubernetes-native 安全功能与完全由 Red Hat 管理的产品的便利性和支持相结合。Red Hat 表示，其 Red Hat Advanced Cluster Security(ACS)云服务产品的预览版旨在让组织在构建、部署和维护云原生应用程序时提高安全性和安全性管理，而不管底层的 Kubernetes 平台如何。

在红帽[收购 StackRox](https://www.redhat.com/en/blog/red-hat-closes-acquisition-stackrox) 并选择[在 2021 年开源 StackRox 平台](https://www.redhat.com/en/blog/red-hat-releases-open-source-stackrox-community)之后，红帽为 ACS 增加的关键改进是 ACS 云服务如何为 Kubernetes 和 StackRox 提供更全面和直接的安全支持和管理。StackRox 被视为一种帮助 Kubernetes 特定工作负载更加安全、运行速度更快、效率更高的方法。

“以前您必须自己运行 StackRox 基础架构，但现在，我们将在您选择的云环境中为您运行 StackRox 基础架构，”[Red Hat ACS 高级首席产品经理 Doron Caspin](https://www.linkedin.com/in/dcaspin?miniProfileUrn=urn%3Ali%3Afs_miniProfile%3AACoAAAAvlOEBPp_qkzRiiZPO-bOpSE_rDWYxQ5s&lipi=urn%3Ali%3Apage%3Ad_flagship3_search_srp_all%3B1NVD7VSSRkKXe40qRe56dQ%3D%3D)告诉新的 Stack。

## 供应链安全

Kubernetes 的 red Hat Advanced Cluster Security(ACS)在其供应链安全模式中扮演着重要角色。通过与组织的 CI/CD 管道和映像注册表集成，ACS 提供了连续扫描，因此可以在同一个开发人员环境中修复易受攻击和配置错误的容器映像，并提供实时反馈和警报。红帽高级集群安全云服务支持红帽客户在亚马逊 Web 服务(AWS)上的红帽 OpenShift、Azure 红帽 OpenShift 和红帽 OpenShift 服务上运行容器化工作负载。红帽 ACS 托管服务也可用于主要云提供商(包括亚马逊 EKS、谷歌 GKE 和微软 AKS)提供的非红帽 Kubernetes 服务。

“我们努力帮助保持对 DevOps 的 Kubernetes 安全领域的高度关注。这意味着开发人员和运营团队成员的安全需求应该由 ACS 和现在的 ACS 云服务全面覆盖，”Caspin 说。“通过这种方式，开发人员可以有更多的时间来更快地开发代码和应用程序，并允许运营团队成员将更多的精力放在改善基础架构以实现业务目标上，而不是被安全管理所束缚。”

根据 Red Hat 的“2022 年全球技术展望”报告， [46%的受访者将 IT 安全作为他们的首要资金来源](https://www.redhat.com/en/global-tech-outlook-report/2022)。因此，安全性显然是 Red Hat 与其客户共同关心的一个大问题，这也有助于解释 Red Hat 如何积极地扩展它所能提供的安全工具的范围。在 ACS 云服务发布之前，还有许多其他更新的 Red Hat 安全项目。

## 内容签约

[红帽的 ansi ble Automation Platform 2.2](https://thenewstack.io/red-hat-embraces-devsecops/)提供了类似 Sigstore 的内容签名技术。它通过验证在管道中或运行时执行的代码已经过验证，因而是可信的，有助于自动化供应链安全最佳实践。Red Hat 的 OpenShift 提供了许多工具，并审查和推荐了来自第三方的用于供应链安全的选项。该公司已经创建了一个适用于混合云环境的[供应链安全模式](https://redhat-gitops-patterns.io/)—从内部到多云再到边缘，跨越整个技术生命周期和软件堆栈。

借助 Red Hat 的 OpenShift 容器平台，该模式以代码的形式交付完整的堆栈，并定义、构建和测试必要的软件配置。该模式通过 Red Hat OpenShift 管道和 Red Hat OpenShift GitOps 提供了一个 Kubernetes 集成管道，用于版本控制。通过 Tekton 链，该模式为代码的加密签名加入了 Sigstore。

此外，在[Red Hat Ansible Automation Platform 2.2 中，](https://www.redhat.com/en/about/press-releases/red-hat-delivers-managed-ansible-automation-microsoft-azure) Red Hat 正在提供其 ansi ble 内容签名技术的技术预览。这一新功能通过使自动化团队能够验证他们企业中正在执行的自动化内容，有助于软件供应链的安全性。

“我们的目标是通过帮助我们的客户提供安全解决方案来建立我们作为安全领导者的地位，无论他们的需求是什么，无论他们使用 OpenShift 还是他们的云提供商是谁，”Caspin 说。“对于云上 Kubernetes 的安全解决方案，我们预计 ACS 云服务将发挥重要作用，主要由 StackRox 的专业知识和经验提供支持，这些知识和经验目前正在扩展到整个云环境。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>