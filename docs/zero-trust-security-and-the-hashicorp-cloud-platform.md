# 零信任安全和哈希公司云平台

> 原文：<https://thenewstack.io/zero-trust-security-and-the-hashicorp-cloud-platform/>

几乎默认情况下，组织现在正在成为多云运营。没有一种云服务能提供企业可能需要的全部内容，而且企业自己也发现自己经常在无意中使用多种服务。

[https://www.youtube.com/embed/vm2j32WLYfU](https://www.youtube.com/embed/vm2j32WLYfU)

视频

HashiCorp 是一家通过使用一套一致的软件工具来帮助企业应对管理多个云的挑战的公司。为了了解更多信息，在 HashiConf 用户大会上，我们采访了[梅根·拉弗雷姆](https://www.linkedin.com/in/megan-laflamme-b6362315/)、 [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) 产品营销总监，这是最新一集的新 Stack Makers 播客。我们讨论了零信任计算、身份的重要性以及 HashiCorp Boundary 单点登录工具的普遍可用性。

[零信安全与哈希公司云平台](https://thenewstack.simplecast.com/episodes/zero-trust-security-and-the-hashicorp-cloud-platform)

她解释说:“在云运营模式中，[安全]边界不再是静态的，你将移动到一个更加动态的基础设施环境中。

## **什么是 HashiCorp 云平台？**

[HashiCorp 云平台](https://cloud.hashicorp.com/products/boundary) (HCP)是一个完全托管的平台，提供 HashiCorp 软件，包括 Consul、Vault 和其他服务，所有这些都通过 HashiCorp 虚拟网络(HVN)连接。通过门户网站或平台，HCP 可以管理多个云资产的登录、访问控制和计费。

HashiCorp 云平台[现在为](https://thenewstack.io/hashicorp-cloud-can-now-spin-up-a-single-sign-on-zero-trust-network/)提供了单点登录的能力，减少了登录多个应用和服务的麻烦。

## 什么是哈希公司边界？

Boundary 是实现这种“安全远程访问”的客户端，现在平台用户一般都可以使用它。它是一个远程访问客户端，通过可信身份管理细粒度授权。它[为](https://thenewstack.io/hashicorp-cloud-can-now-spin-up-a-single-sign-on-zero-trust-network/)提供会话连接、建立、证书颁发和撤销。

“有了 Boundary，我们可以实现更加简化的工作流程，允许访问我们与云提供商或服务注册中心集成的关键基础设施，”Laflamme 说。

[HCP 边界](https://cloud.hashicorp.com/products/boundary)是运行在哈希公司云上的[哈希公司边界](https://www.boundaryproject.io/)的完全管理版本。有了 Boundary，用户[只需登录一次](https://www.hashicorp.com/solutions/zero-trust-security)，可以说其他一切都在地板下处理。应用程序、网络和人员的身份通过 HashiCorp Vault 和 HashiCorp Consul 处理。每项行动都经过授权并记录在案。

Boundary 通过利用 Okta、Azure Active Directory 和 GitHub 等现有的身份提供者(IDP)来认证和授权用户。Consul 认证和授权应用程序和服务之间的访问。这样，网络就不会暴露，也不需要颁发和分发凭证。[用户会话的动态凭据注入](https://developer.hashicorp.com/boundary/tutorials/hcp-administration/hcp-ssh-cred-injection?in=boundary%2Fhcp-administration)是通过 HashiCorp Vault 完成的，它将一次性凭据注入远程主机进行无密码身份验证。

## 什么是零信任安全？

使用[零信任安全](https://thenewstack.io/beyondcorp-google-ditched-virtual-private-networking-internal-applications/)，用户在服务级别进行认证，而不是通过集中式防火墙，这在多云设计中越来越不可行。

在行业中，有一种转变，“从更静态的数据中心和基础设施中基于 IP 的高信任授权，到云，再到低信任模型，在这种模型中，一切都基于[身份](https://thenewstack.io/what-do-authentication-and-authorization-mean-in-zero-trust/)，”Laflamme 解释道。

这种方法确实需要用户以某种形式登录每个单独的服务，这对于那些在日常工作中登录许多应用程序的人(即开发人员和系统工程师)来说是一个头疼的问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>