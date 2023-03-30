# 云原生技术时代的 PCI 合规性

> 原文：<https://thenewstack.io/pci-compliance-in-the-age-of-cloud-native-tech/>

[](https://www.linkedin.com/in/corinimai)

 [科林今井

科林是 Styra 公司的安全与合规策略师兼产品营销总监。Corin 的职业生涯始于信息技术，从事桌面虚拟化、网络和云计算技术方面的工作。后来，她投身于安全领域，专注于应用程序开发、敏感数据、DNS 研究和连接设备。](https://www.linkedin.com/in/corinimai) [](https://www.linkedin.com/in/corinimai)

随着支付欺诈的兴起，支付卡行业数据安全标准( [PCI DSS](https://www.pcisecuritystandards.org/pci_security/maintaining_payment_security) )早在 2004 年就出现了。PCI DSS 由信用卡行业的领导者创建，旨在提供旨在保护持卡人支付数据的技术和操作要求基线，并为传统安全领域的人员所普遍理解。

参与支付卡处理的所有实体，包括商户、加工商、收单机构、发行商、服务提供商以及存储、处理或传输持卡人和敏感数据的其他组织，都必须遵守这些法规。

2006 年，PCI 安全标准委员会(SSC)成立，定期更新标准以反映当前的最佳实践。多年来，PCI DSS 经历了无数个版本，每个版本都强化了功能测试程序，以帮助组织实施正确的策略来处理敏感数据。

如今，PCI DSS 由 [12 个高级需求](https://www.pcisecuritystandards.org/pci_security/maintaining_payment_security)组成，但是即使有了这些规定，您如何在云原生技术时代确保 PCI 合规性呢？

## 在云原生环境中实施 PCI

PCI DSS 要求现在已经有将近 20 年的历史了，从通过身份和访问管理(IAM)控制访问，到在您的特权身份管理(PIM)工具中实施该策略，我们已经走过了一段漫长的道路，并满怀希望。

然而，向云原生的转变彻底改变了组织开展业务的方式，并重新定义了网络和存储参数。虽然您很难在 PCI DSS 标准中找到有关云原生技术的具体细节，但这并不意味着您的公司可以在 PCI 合规性方面有任何回旋余地，因为它正在运行一个容器化的环境。

在基于微服务的环境中，控制点是新的和高度多样化的，因为应用程序存在于云和/或混合环境中，并以各种能力交付，使它们更容易被最终用户访问。

更复杂的是，通常有无数冗余选项用于控制存储、网络和计算资源，如 API 网关、服务代理/网格、命名空间、L7、微分段、云 SDN 等。因此，满足 PCI 合规性会带来巨大的挑战。

在云原生环境中迁移到合规状态需要一个新的非常耗时的步骤:确定策略在哪里最有效，以及它们如何映射到现有法规。它还需要一个新的安全模型，包括以下内容:

*   **从可靠来源构建** —确保您的容器映像是从可靠来源的当前最小基础映像构建的。
*   **应用精简的安全检查站** —使用精简的安全检查站。
*   **左移用于声明性遵从** —通过在过程中尽可能早地编纂您的安全需求，保留策略驱动的发布实践。确保控制到位，以便所有许可的图像都经过必要的验证。

如果处理遗留参数，您可能会跳过这一步，因为工作已经完成了；这将是审查最佳做法的最佳时机。

对于那些没有运行遗留系统的人来说，最容易的起点是 Kubernetes (K8s)。Kubernetes 允许控制存储、网络和计算资源，但仍然要求您将相关控制映射到 PCI 标准本身。

**举例:**

要求 7.1.2:将对特权用户 id 的访问限制为履行工作职责所需的最低特权。

然而，在 cloud native 中，由于容器的动态特性，身份验证和 IAM 并不总是有效。解决方案必须实时活跃，并能够自动响应快速变化的攻击。答案是什么？Kubernetes 准入控制。

除了确保用户和服务帐户遵守最小特权原则，容器也应该这样做。运行容器的最佳实践是使用非 root 用户运行流程。 [Pod 安全策略(PSP)](https://blog.styra.com/blog/prepare-your-kubernetes-cluster-for-pod-security-policy-deprecation?utm_campaign=MKT%202020-12-16%20The%20New%20Stack%20sponsorship&utm_source=PR&utm_medium=byline) 是一种准入控制器/集群级资源，控制在集群上创建和更新 Pod 的请求。它还定义了一组条件，除了相关字段的默认值之外，pod 必须满足这些条件才能被集群接受。

以前，当创建或更新 pod 的请求不符合 Pod 安全策略中的条件时，该请求会被立即拒绝，并向用户返回一个错误。自从 PSP 贬值以来， [Styra](https://www.styra.com/?utm_campaign=MKT%202020-12-16%20The%20New%20Stack%20sponsorship&utm_source=PR&utm_medium=byline) 已经实施了替代 PSP 的政策包。

如您所见，快速开发意味着解决云原生环境中的需求并非易事，但您可以通过正确的步骤实施 PCI:

*   如果您正处于数字化转型的初期，请了解传统系统如何处理持卡人数据，并将其映射到云原生架构。这个过程确保在移动应用程序时，可以将适当的框架放在适当的位置，无论是控制流程编排、服务到服务的通信还是网关的策略。
*   在开始时，使用开源解决方案来查看差距所在，并了解管理这些解决方案和证明法规遵从性(内部或外部)所需的手动工作。像[开放策略代理(OPA)](https://blog.styra.com/blog/what-is-open-policy-agent?utm_campaign=MKT%202020-12-16%20The%20New%20Stack%20sponsorship&utm_source=PR&utm_medium=blyine) 这样的解决方案可以用来手动创建映射到 PCI 的策略。或者，根据您在旅程中所处的位置，有已经映射的带有预构建 PCI 策略包的交钥匙控制面板。
*   寻找不仅能够支持您的团队，而且还能支持负责任何法规遵从性部分的团队的解决方案。对于一些组织来说，是法律、安全、it 和 GRC 团队，有时只是 IT。但是要认识到，随着组织的成长，解决方案需要能够适应。
*   虽然实施 PCI 政策至关重要，但证明该政策有效更为重要。对该政策将正确处理持卡人数据的信心使安全、IT 和 GRC 团队能够获得政策代码，并为审计人员提供证据。

当涉及到 PCI 时，确定使用云原生技术的合规性对于审计员和用户来说都是一个挑战，特别是因为需求不是特定于容器的。然而，有了详细的文档、干净的自动化和合适的解决方案，PCI 合规性是可以实现的。

*要深入了解 Styra 如何帮助您实现 PCI 合规性，请阅读白皮书“[Styra 如何映射到 PCI 数据安全标准 v3.2](https://registration.styra.com/pci_dss_v3.2?utm_campaign=MKT%202020-12-16%20The%20New%20Stack%20sponsorship&utm_source=PR&utm_medium=byline) ”*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>