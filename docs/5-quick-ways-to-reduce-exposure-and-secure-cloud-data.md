# 减少暴露和保护云数据的 5 种快速方法

> 原文：<https://thenewstack.io/5-quick-ways-to-reduce-exposure-and-secure-cloud-data/>

转向公共云服务现在是大多数组织长期发展计划的必要策略。但是，他们如何调整和扩展其网络安全能力，以保护其云环境中的资产、数据和客户呢？

传统的安全措施在云中不起作用，因为没有边界可以保护。手动流程无法以必要的规模或速度进行，并且缺乏集中化使可见性变得极其困难。

具有多云环境的组织具有更大的攻击面。他们的网络安全战略不仅仅围绕物理数据中心和本地服务器。相反，还有一个庞大、杂乱的终端网络，以及虚拟服务器、远程应用程序、云工作负载、[容器](https://thenewstack.io/containers/)和环境之间的网络通信。

这里有五种简单的方法，组织可以通过不断搜索和删除云中不必要的攻击面来[降低暴露风险](https://www.crowdstrike.com/resources/white-papers/how-to-find-and-eliminate-blind-spots-in-the-cloud/?utm_campaign=blog&utm_medium=syn&utm_source=cont)。

## 1.分割

分段是一种安全技术，它将您的云环境划分为[更小的区域](https://thenewstack.io/zero-trust-vs-microsegmentation-establish-a-winning-strategy/)，以保持对网络每个部分的单独访问。这些部分有助于遏制攻击，并在发生违规时限制损害。

细分可以基于设备类型或功能以及用户身份。它包括针对不同类型的工作负载使用不同的云帐户、虚拟专用云(VPC)、子网和角色。组织还应该致力于避免重叠的应用程序生产、开发和集成工作负载。

## 2.加密

云加密是将数据从原始纯文本格式转换为不可读格式(如密文)的过程，然后将数据传输并存储到云中。如果没有加密密钥，这个过程会使信息变得无法解读和无用。即使数据丢失、被盗或与未经授权的用户共享，这一点也适用。

每个著名的云服务提供商(CSP)——拥有和运营云的企业或实体——都提供基本的安全性，包括[加密](https://www.crowdstrike.com/cybersecurity-101/cloud-security/cloud-encryption/?utm_campaign=blog&utm_medium=syn&utm_source=cont)。然而，云用户应该实施额外的措施来确保数据安全。

对于使用基于云的模式或开始向云迁移的组织来说，开发和部署专门用于保护和捍卫基于云的资产的全面数据安全战略非常重要。组织应咨询其网络安全合作伙伴，选择最佳的第三方[加密](https://thenewstack.io/protect-and-index-sensitive-data-with-polymorphic-encryption/)工具，并将其集成到现有的安全技术体系中。

## 3.DevSecOps

DevSecOps 是在软件开发生命周期的早期加入安全性的实践。它具有提高质量和降低风险的双重目的。虽然许多 [DevOps 团队](https://www.crowdstrike.com/resources/reports/walking-the-line-gitops-and-shift-left-security/?utm_campaign=blog&utm_medium=syn&utm_source=cont)过去可能不愿意遵循这种方法，但今天的威胁形势几乎要求安全第一的心态。

此外，[左移](https://www.crowdstrike.com/cybersecurity-101/shift-left-security/?utm_campaign=blog&utm_medium=syn&utm_source=cont)有助于在开发过程的后期防止延迟，那时解决问题会更加复杂、昂贵和耗时。一个全面的安全策略可以通过实现工具、自动化和标准来帮助减轻开发过程中的问题，使工程师能够遵循所需的安全行为。这些工具减少了开发人员的摩擦，也减少了使用不安全或默认配置的可能性。

## 4.多因素身份验证(MFA)

多因素身份验证(MFA)是需要多项证据来验证用户身份的过程。这些证据可能包括安全问题、电子邮件/文本确认或基于逻辑的练习，以评估用户的可信度。MFA 是每个[云原生安全](https://www.crowdstrike.com/cybersecurity-101/cloud-security/?utm_campaign=blog&utm_medium=syn&utm_source=cont)策略中的必需品。组织还应考虑对高影响环境(如 GovCloud 部署)使用硬令牌。

## 5.云安全态势管理(CSPM)

在每天的过程中，云可能会连接和断开数百甚至数千个其他网络。这种动态特性使得安全性更难实现，因为可见性和可发现性可能会很有挑战性。鉴于云的动态特性，通过自动发现云工作负载足迹来主动维护良好的 it 环境非常重要。

[云安全态势管理(CSPM](https://www.crowdstrike.com/products/cloud-security/falcon-horizon-cspm/?utm_campaign=blog&utm_medium=syn&utm_source=cont) )自动识别和补救云基础设施中的风险，包括基础设施即服务(IaaS)、软件即服务(SaaS)和平台即服务(PaaS)。CSPM 用于风险可视化和评估、事件响应、合规性监控和 DevSecOps 集成，可以将云安全的最佳实践统一应用于混合、多云和容器环境。

全面的 CSPM 功能使组织能够:

*   建立跨多云环境和客户的单一事实来源，从而提高可见性和可发现性。
*   在部署时自动发现云资源和详细信息，包括错误配置、元数据、网络、安全性和变更活动。
*   [通过识别错误配置、开放 IP 端口、未经授权的修改和其他暴露云资源的问题，消除安全风险](https://www.crowdstrike.com/resources/white-papers/how-to-find-and-eliminate-blind-spots-in-the-cloud/?utm_campaign=blog&utm_medium=syn&utm_source=cont)。
*   通过有针对性的威胁识别和管理方法消除多云环境安全警报的噪音，在整个应用开发生命周期中主动[检测威胁](https://www.crowdstrike.com/resources/reports/threat-landscape-cloud-security/?utm_campaign=blog&utm_medium=syn&utm_source=cont)。
*   使用实时威胁检测持续监控环境中的恶意活动、未经授权的活动和对云资源的未经授权的访问。

在选择供应商来保护您的组织时，[选择端到端的统一网络安全解决方案，](https://www.crowdstrike.com/resources/white-papers/the-crowdstrike-security-cloud-ebook/?utm_campaign=blog&utm_medium=syn&utm_source=cont)最好在同一平台上。来自多个供应商，甚至来自同一个供应商的多种安全解决方案可能会留下安全漏洞，而这些漏洞[经常被对手](https://www.crowdstrike.com/resources/reports/threat-landscape-cloud-security/?utm_campaign=blog&utm_medium=syn&utm_source=cont)利用来进行攻击。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>