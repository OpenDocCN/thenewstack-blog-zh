# 边缘安全性:API 的认证和授权

> 原文：<https://thenewstack.io/security-at-the-edge-authentication-and-authorization-for-apis/>

我最近看到一个开发人员做了一个演示，其中一部分包括查看一个接收请求和响应代码的仪表板。我问开发人员她是如何产生请求流量的。“哦，我不是，”她回答说。“我刚刚开通了一个公共 IP up 多分钟，人们正在点击它寻找漏洞。”

我习惯于保护一个活跃的网站，但不是一个随机的 IP 地址。这就是当今 web 开发环境的现实。如果你有一个在网络上运行的 API，你必须保护它，因为肯定有人会攻击它。

理想情况下，你可以立即制定一个[零信任模型](https://www.vmware.com/topics/glossary/content/zero-trust-security.html)，在这个模型中，即使是你网络内部的流量也会在所有阶段被[检查。但是实现系统，无论是安全、部署、持续集成还是其他，通常都是分步骤完成的。从网络安全开始的一个很好的地方是在您的网络边缘，在那里它与用户和攻击者进行交互。](https://thenewstack.io/what-do-authentication-and-authorization-mean-in-zero-trust/)

通常一个 [API 网关](https://www.getambassador.io/products/edge-stack/api-gateway)将会是你系统中第一个接收请求的部分，使它成为你的第一道防线的好工具。一般来说，在云原生架构中，我们试图通过提取 sidecar 服务的可观察性等功能来尽可能多地减轻应用程序开发人员的负担。

授权也是如此，在 API 网关中处理授权就像为更大的系统提供一个 sidecar。有两个主要的安全领域, API 网关应该能够自己处理或集成:

*   认证(Authn)
*   授权

我们将在这里集中讨论这些与 API 网关相关的主题，但是如果您需要这两个主题的入门知识， [Auth0](https://auth0.com/intro-to-iam/authentication-vs-authorization) 提供了关于[认证](https://auth0.com/intro-to-iam/what-is-authentication)和[授权](https://auth0.com/intro-to-iam/what-is-authorization)的很好的指南。

## 认证和授权

简而言之，系统使用[认证](https://www.getambassador.io/docs/edge-stack/latest/topics/running/services/auth-service)和授权过程来回答给定请求的两个问题:

*   谁提的这个要求？(认证)
*   他们被允许做他们正在努力做的事情吗？(授权)

无论请求来自系统外部还是内部，都是如此，例如来自另一个服务的请求或者来自[身份和访问管理](https://www.techtarget.com/searchsecurity/definition/identity-access-management-IAM-system) (IAM)系统的请求。一些工具同时具有这两种功能。例如，JSON Web 令牌(JWT)可用于标识用户，并在其有效负载中包含授权权限列表。

## API 的验证

身份验证的核心是对照已知实体检查用户的凭证，并发回某种凭证供用户在后续请求中发送，无论是 JWT、会话 cookie 等。您在 API 网关中寻找的是与尽可能多的标准认证方法的内置兼容性和可扩展性*、*，以便您可以使用网关没有内置的其他方法。

在 API 网关中寻找的一些常见的[认证](https://www.veriff.com/blog/types-of-authentication-methods)方法有:

*   基本身份验证—也称为“用户名和密码”
*   OpenID Connect ( [OIDC](https://openid.net/connect/) ) —这是大多数主要提供商用于单点登录(SSO)的工具，如 Azure Active Directory、Google、Github、Okta 等。
*   JWT —要接收 JWT，用户需要以其他方式进行身份验证，但只要令牌有效，就会发送 JWT 以备将来请求。在入境点快速验证 JWT 非常方便。

### 展开性

对于大型业务系统来说，通常会为较旧的或高度定制的服务提供定制的或不常见的身份验证系统。当您第一次开始使用 API 网关的身份验证系统时，您可能不需要扩展它，但是知道您可以这样做总是很好的。通常，这看起来像是一个特性，允许您配置 API 网关向您创建的外部服务发送请求，并接收批准或拒绝请求的响应。

## API 的授权

授权是一个更棘手的问题，因为它通常是特定于业务和领域的。即使有常见的*类型*的授权系统，如基于角色的访问控制(RBAC)，角色和每个角色能做什么也是特定于您的系统的。也就是说，在 API 网关中有一些功能可以被认为是授权，您可以寻找将其与您的系统集成的能力，就像身份验证一样。

### API 网关的授权功能

如果授权试图回答这个问题，“你被允许做什么？，“那么您的网关应该能够验证网络边缘的一些权限:

*   你被允许提这个要求吗？如果用户试图发出不应该发出的请求，您的 API 网关应该能够立即返回 403 或等效的“未授权”响应。
*   允许你以多快的速度提出请求？速率限制是一种许可形式，属于 API 网关的权限范围。理想情况下，您应该能够通过 IP 地址和用户 ID 将网关配置为全局速率限制。
*   你应该被允许向哪里提出请求？应该处理您的请求的系统可以是授权的一部分。例如，在多区域架构中，您可能要求欧盟客户只能向欧盟服务器[发出请求，就像 Monday.com 的](https://engineering.monday.com/monday-coms-multi-regional-architecture-a-deep-dive/)一样。您的 API 网关应该能够支持动态路由。
*   与 [OAuth2](https://oauth.net/2/) 一起工作，这在你使用 OIDC 的地方经常可以找到。OIDC 验证您的身份，OAuth2 协议提供相同系统的访问授权。

### 综合

多地区架构的例子是一个更大模式的开始。您的 API 网关应该能够向您的授权服务发送请求，并接收关于如何处理它们的返回指令。应该转发吗？重定向？掉线？因为授权往往是定制的，但是您希望在边缘保护您的网络，所以您的边缘需要能够与您的定制系统集成。

## 从边缘开始

当攻击者总是探查您的网络，寻找进入的方法时，API 安全性是一项要求。如果没有它，您就离违规和非常不满意的客户只差一天了。

就像你可以从在网络边缘用 API 网关实现[TLS](https://www.getambassador.io/docs/edge-stack/latest/topics/running/tls)开始，然后使用服务网格在内部服务之间添加 [mutual-TLS，你可以在边缘实现安全措施，同时努力实现一个完全的零信任系统。](https://linkerd.io/2.12/features/automatic-mtls/)

如果您想了解更多信息，3 月 22 日至 23 日举行的最新一期在线 [KubeCrash](https://www.kubecrash.io/) 活动将深入探讨[零信任](https://thenewstack.io/what-is-zero-trust-security/)的主题，涵盖从入口到服务网格到认证生成和策略实施的主题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>