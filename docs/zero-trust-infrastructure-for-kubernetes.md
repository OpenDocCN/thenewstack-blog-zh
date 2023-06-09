# 面向 Kubernetes 的零信任基础设施|新堆栈

> 原文：<https://thenewstack.io/zero-trust-infrastructure-for-kubernetes/>

零信任安全是今天每个人都在谈论的时髦词——这是有充分理由的。

虽然安全模式近年来越来越受欢迎，但在新冠肺炎疫情期间，在家订单刺激了向新的远程和混合工作模式的突然(对一些人来说，是永久性的)转移，这一模式很快成为所有人关注的焦点。

[https://www.youtube.com/embed/x3Uk22OZ-I0](https://www.youtube.com/embed/x3Uk22OZ-I0)

视频

但不仅仅是[那些正在向远程或混合工作过渡的公司需要考虑零信任安全](https://thenewstack.io/the-future-of-zero-trust-in-a-hybrid-world/)；相反，所有机构、平台和基础设施都应该将注意力转向这些安全原则。特别是，对于部署了 Kubernetes 的组织来说，采用[零信任架构](https://thenewstack.io/what-is-zero-trust-architecture/)将被证明对于确保所有环境的安全性至关重要。

## Kubernetes 安全挑战

在各行各业中，无处不在的压力使得软件能够更快、更高效、更大规模地运行。为了寻求强大的可移植性和灵活性，许多 IT 组织已经转向 [Kubernetes](https://thenewstack.io/why-cloud-native-systems-demand-a-zero-trust-approach/) (K8s)来帮助他们有效地满足这些市场需求。

虽然 K8s 是 IT 组织高效、大规模交付软件的强大解决方案，但它也有自己的安全挑战和漏洞。

首先，仅仅因为 Kubernetes 是一个相对较新的系统，它对网络攻击者来说是一个有吸引力的猎物。如果不采取适当的安全措施，其运作模式的动态性质很容易为不良行为者的渗透留下空间。

来自 Shadowserver Foundation 的研究人员发现，仅今年一年就有 380，000 个开放的 Kubernetes API 服务器暴露在互联网上。虽然这些服务器只是被确定为暴露的，而不是被攻击的，但这仍然是一个有力的数字，表明了 API 服务器的脆弱性和潜在的危险。

事实上，Salt Security 的 [2022 年 API 安全状况](https://salt.security/api-security-trends?)显示，34%的受调查企业没有 API 安全策略——尽管其中 95%的企业在过去 12 个月中其 API 安全受到威胁。

## 零信任:Kubernetes 的安全救星？

面对这种可怕的局面，很明显，该行业需要一种新的解决方案来加强 Kubernetes 的部署。

因此，问题依然存在:组织如何继续利用 K8s 的诸多优势，同时保持强大的安全态势？

对许多人来说，答案显然是零信任安全。

### 什么是零信任安全？

零信任安全模型由 Forrester 于 2009 年首次开发。当时，这是一个开创性的概念，颠覆了网络安全的标准视角。

对于传统的安全模式，现状一直是“信任，但要验证”

零信任安全翻转脚本，改为证明“从不信任；始终验证。”这意味着所有用户和设备都必须不间断地进行无差别检查和验证。

过去，一切都是为了保护边界。一旦用户通过验证，他们就被授予了访问网络的权限，并且一旦进入网络，他们通常会受到信任。

零信任意味着永远不要建立信任。

相反，用户和设备总是被认为受到了威胁，因此必须不断地被授权、认证和证实，以便保持与网络的连接或采取任何行动。这样，zero trust security 的预防措施可以帮助组织始终保持警惕，永不放松警惕，从而领先坏人一步。

## Kubernetes 的零信任架构

[零信任安全的原则为 Kubernetes 的安全挑战提供了真正的解决方案](https://thenewstack.io/securing-access-to-kubernetes-environments-with-zero-trust/)——但实现合规性也带来了新的挑战。

重要的是要记住，零信任安全只是一组目标，而不是一个确切的工具；因此，有许多不同的方法来实现零信任架构。

那么，零信任原则如何适用于 Kubernetes 呢？

它从保护 Kubernetes API 服务器开始。

服务器是每个 Kubernetes 集群的控制平面的核心。因为这个 API 服务器用于控制所有的 Kubernetes 对象，所以确保安全的 API 访问是确保受控 Kubernetes 访问安全的基础，从而实现零信任 Kubernetes。

为了控制和保护 API 服务器，第一步是调节所有传入和传出的流量；这可以通过传输层安全性(TLS)来实现。一旦所有的 API 服务器流量都得到保护，Kubernetes 就会提供所有必要的钩子来实现零信任 Kubernetes。

钩子主要有四种类型，它们对于成功实现 Kubernetes 的零信任架构都至关重要:身份验证；授权；准入控制；审计和日志记录。

### 证明

为了维护 Kubernetes 的零信任安全原则，第一步是确保所有用户和服务帐户定期进行身份验证。这意味着在执行任何 API 调用之前需要进行身份验证。

为了实现这种身份验证，组织可以求助于几种可用的安全模型和插件，例如客户端证书、HTTP 基本身份验证和不记名令牌。

零信任模型还建议要求多因素身份验证(MFA ),以进一步降低安全性。

### 批准

除了身份验证，所有用户和服务帐户还必须具有授权。

这是零信任的一个关键原则。

为了保持强大的安全性，所有用户的操作都应该受到限制，即使在身份验证之后也是如此。换句话说，不是所有的用户都应该被允许做每一项任务；相反，他们应该被授予足够的权限去做他们需要的事情。

说到零信任 Kubernetes，那么，所有访问 Kubernetes 集群的用户和服务帐户都不应该被允许执行任何操作；相反，Kubernetes 中的请求应该只在用户(一旦通过身份验证)有执行该请求任务的明确权限时才被批准。为此，每个请求都应该指定请求者的用户名、所请求的动作以及该动作的效果。

### 准入控制

保持对所有用户和操作的可见性是零信任模型的另一个重要支柱。这就是为什么准入控制器是 Kubernetes 零信任架构的关键组件。

使用准入控制器，组织可以管理所有请求，这些请求试图创建、修改、删除或连接到任何 Kubernetes 对象。内置的准入控制器可以帮助组织实施行动和执行他们的政策，而动态准入控制器可以允许他们实时修改请求。

对于更精细的安全方法，在一个系统中使用多个准入控制器是一个好主意；有许多与 Kubernetes 部署兼容，比如 ResourceQuota 和 LimitRanger。

### 审核和日志记录

在任何类型的安全态势中，审计都是弹性的基本组成部分。

当谈到 Kubernetes 的零信任时，审计允许组织监控在 Kubernetes 集群中执行的所有操作——由用户、应用程序甚至控制平面执行的操作。然后，团队可以决定在哪里记录这些审计事件，例如，在本地文件系统中还是在外部日志记录系统中。

适当的审计和日志记录实践在确保 Kubernetes 基础设施符合现有政府政策方面也发挥着关键作用。

在各种各样的组织、机构和平台中，零信任安全正在成为网络安全健康的关键因素，Kubernetes 当然也不例外。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>