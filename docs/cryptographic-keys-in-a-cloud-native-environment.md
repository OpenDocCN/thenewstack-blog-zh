# 云本地环境中的加密密钥

> 原文：<https://thenewstack.io/cryptographic-keys-in-a-cloud-native-environment/>

[KubeCon + CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 赞助了这篇文章，期待于 8 月 13 日至 16 日在阿姆斯特丹举办 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 。

 [列昂尼德·桑德勒

Leonid 是 CyberArmor 的首席技术官和联合创始人。他是一名安全专家，在软件安全方面有 20 年的经验。作为 NDS(被思科收购)的安全 CTO，他的解决方案被部署在 DirectTV 和 Sky 等全球最大的服务提供商。](https://www.linkedin.com/in/leonidsandler/) 

为了保证业务和客户数据的安全，云工作负载使用身份验证和加密等安全功能。这些功能需要必须保密的密钥和密码。安全软件开发最佳实践建议避免将此类材料保存在软件分发和部署映像中，如容器、虚拟机、配置文件等。然而，[2019 年 NDSS 的一项研究](https://www.ndss-symposium.org/wp-content/uploads/2019/02/ndss2019_04B-3_Meli_paper.pdf) (PDF)显示，人们并不总是遵循哪怕是最基本的准则。

虽然正在开发许多工具以及验证和遵从过程来帮助组织解决微不足道的人为错误，但是软件架构师和开发人员必须实现他们的产品，以便不可能出现微不足道的部署错误。他们的解决方案必须通过设计来确保安全。

然而，这说起来容易做起来难。一方面，我们必须应对数量不断增长的软件漏洞(其中一些并不为公众所知，也就是 0 天),另一方面，攻击技术和方法变得越来越复杂，也越来越有组织性。对于大多数旨在获取有价值信息的网络攻击来说，追踪加密秘密和密码是一个最佳时机。

本文研究了云原生环境中密钥和秘密材料分发的安全方面，在云原生环境中，软件被分成数百甚至数千个微服务和工作负载，零星地运行在巨大的计算集群中，如 Cloud VPCs、Kubernetes 和 Spark。为了提高基础设施利用效率，将这些集群分布在多个基础设施上变得越来越普遍，例如多个云供应商以及公共和私有数据中心。当代架构不能依赖于特定的基础设施能力；但是，即使他们这样做了，当涉及到加密秘密的分发和最重要的保护时，这样的能力也不总是提供最佳答案。

假设遵循了最佳实践，并且在一个先前未知的计算节点上启动了工作负载，那么它现在需要提供一个或多个密钥来执行其任务。在不“使用”时，密钥保存在某种类型的密钥管理系统(KMS)中，通常由云供应商或独立的第三方提供。工作负载通过 IP 接口与 KMS 通信，可能使用标准 KMIP 或专有接口。在本文中，我不会质疑 KMS 实现的安全性，而是将重点放在密钥分发过程的安全性方面。

## 谁在要钥匙？

工作负载必须向 KMS 发出请求才能获得密钥。但是，可能会有许多工作负载一直与 KMS 通信。KMS 必须能够识别工作负载，以决定向其提供什么键。有几种技术可以做到这一点；例如密钥令牌、密钥 id 或 IAM 令牌。

这些技术有些是特定于基础设施的，有些是中性的，但它们都有一个共同的概念问题。KMS 使用请求令牌来标识密钥，而不是对请求者进行身份验证。这些代币可以被视为保险箱的钥匙，实际的钥匙就放在那里。最佳实践要求我们避免将密钥保存在软件中，因为我们知道窃取这些密钥是多么容易。

那么,“钥匙对钥匙”怎么会更好呢？嗯，它比真正的钥匙要好——但也差不了多少。当没有对 KMS 的外部访问时，攻击者需要额外往返一次 KMS，甚至可能利用一些软件漏洞从群集内部进行攻击。但这并没有阻止攻击者。这里的概念性问题是 KMS 不能认证请求工作负载的密钥。

## 不要混淆识别和认证

密钥标识符或令牌完全足以识别所请求的密钥。但是，由于它们可以被复制，KMS 无法确保请求来自合法的工作负载。正常情况下，这样的问题应该已经通过认证解决了；但是认证必须基于不能被窃取或复制的东西。这又把我们带回了秘密材料。由于工作负载在没有任何机密材料的情况下启动，因此无法执行可靠的身份验证，这使得潜在攻击者能够伪装成合法的工作负载，并直接从 KMS 获取密钥。

因为几乎所有的 KMS 产品都是众所周知的，攻击者确切地知道代币的样子和存放地点；以及因此如何操作。我们将此称为密钥分发的“鸡和蛋”问题，因为当工作负载需要从 KMS 获得秘密材料以便运行时，一个“完美的”KMS 应该安全地认证请求的工作负载。这要求该工作负载首先拥有一个身份验证秘密。

## 如何解决这个僵局？

由于秘密材料不能用于认证请求的工作负载，我们应该找到另一种认证方法，允许 KMS 确保它与合法的请求者通信。人类生物统计学认证方法提出了另一种认证请求工作负载的方法——软件“DNA”向 KMS 请求密钥的工作负载软件的加密签名提供了缺失的认证因子，从而确保 KMS 与合法的客户端进行通信。作为密钥分发协议的一部分，如果 KMS 能够在运行时远程验证这种加密签名，它将防止恶意软件获取属于其他工作负载的加密密钥。

这种方法仍然需要采取额外的措施来避免合法的软件克隆。此外，一旦交付，密钥在“使用中”时必须受到保护

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>