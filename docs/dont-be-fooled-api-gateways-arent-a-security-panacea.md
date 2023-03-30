# 不要被愚弄了:API 网关不是安全的灵丹妙药

> 原文：<https://thenewstack.io/dont-be-fooled-api-gateways-arent-a-security-panacea/>

这一次，开发人员和安全领导者在某些事情上达成了一致:API 对于数字创新的未来是必不可少的。事实上，在 Forrester 进行的一项全球调查中， [78%](https://www.imperva.com/resources/resource-library/white-papers/improve-api-performance-with-a-sound-api-security-strategy/) 表示，采用 API 对于他们的公司保持市场竞争力非常重要。

 [程乐斌

Lebin 是一名技术专家和开发人员，在网络安全领域拥有 20 多年的经验。他共同创立了 Netskope，后来又共同创立了 CloudVector，后者被 Imperva 收购。他在网络安全、应用基础设施和 API 检测等领域获得了 15 项专利。他拥有加州大学伯克利分校哈斯商学院的 MBA 学位和普渡大学的计算机科学硕士学位。](https://www.linkedin.com/in/lebin/) 

随着对 API 需求的增长，保护它们的需求也在增长。同一项调查显示，56%的应用程序开发人员认为 [API 安全性](https://www.imperva.com/blog/api-security-explained/)是他们组织在未来 12 个月的一个关键优先事项。是为了你和你的团队吗？

作为一种常见的安全最佳实践，开发人员和安全团队将在前端部署一个带有 web 应用防火墙( [WAF](https://www.imperva.com/learn/application-security/what-is-web-application-firewall-waf/) )的 API 网关，以阻止针对 API 和应用的恶意流量或网络攻击。

不幸的是，这种传统方法无法抵御组织如今面临的复杂威胁。此外，云原生环境更加复杂，连接应用程序所有部分的 API 数量也在成倍增加。这些端点位于 WAF 之外的情况并不少见，这使得它们容易受到攻击。

如果您的组织认真对待[安全性](https://www.imperva.com/blog/apis-are-here-to-stay-so-get-in-front-of-securing-them/)，那么您现在使用的 API 网关或 API 管理解决方案无法阻止所有可能导致严重数据泄露的攻击。

## **不要混淆 API 网关和 API 安全**

API 网关通常作为 API 管理解决方案的一部分提供。任何与 API 网关相关的安全特性通常都与访问认证或端点级授权有关。

事实上，访问控制只是 API 安全性的一个组成部分。利用有效 API 令牌的复杂攻击可以成功地瞄准应用程序业务逻辑和数据层中的漏洞。只有专门构建的 API 安全解决方案才能检测到此类攻击。

API 网关监控端点；他们不能发现每个 API 的完整模式。更关键的是，API 网关不能识别或分类流经每个 API 的数据。如果没有这种级别的可见性，组织就看不到潜在的数据泄露风险。

虽然一些云服务提供商提供 API 网关产品，但他们仍然建议在前端部署 WAF 来保护应用程序。组织必须采取新的方法来保护他们的前端和后端 API。

## **只看南北交通？你已经了解了故事的一半**

为了真正保护支持和连接您的业务所依赖的应用程序和数字服务的 API，需要对 API 行为的可见性。

传统上，组织只能看到通过 API 网关和 WAF 的南北 API 流量。然而，他们对东西向流量模式视而不见——这构成了服务器、容器和服务之间的通信，并且在 WAF 的可见性之外。在现代面向服务的架构(SOA)中，数据中心内的东西向流量是通过 API 进行的，并且在所有流量中占很大比例。在某些情况下，东西向 API 流量是南北向流量的延伸，这使得它对于安全监控至关重要。例如，后端对前端(BFF)应用程序可能会向任何信任的后端泄漏南北呼叫，导致在没有东西监视的情况下几乎不可能检测到违规。

如果没有正确的可见性层，组织将对 API 滥用或潜在的数据泄漏视而不见。在这些漏洞中，组织可能面临中间人( [MITM](https://www.imperva.com/learn/application-security/man-in-the-middle-attack-mitm/) )攻击、API 代码注入( [XSS](https://www.imperva.com/learn/application-security/cross-site-scripting-xss-attacks/) 和 [SQLi](https://www.imperva.com/learn/application-security/sql-injection-sqli/) )或横向移动攻击。

API 网关的存在是为了提供访问控制等重要功能，但为了防御 OWASP API 安全 10 强，组织需要投资于具有发现和数据分类功能的 API 安全。

## **如果您关心您的应用程序和 API，请有效地保护它们**

管理由 API 生态系统连接的复杂软件开发环境的组织需要保护面向公众的 API 和后端 API。该解决方案必须能够跨传统、混合和云原生环境工作，包括 Kubernetes、传统单片应用、独立微服务和 web 代理。最重要的是，当开发团队推进组织的创新路线图时，这个解决方案不应该减慢他们的速度。

当今市场上的许多产品都标榜以安全为中心，但只为 API 提供高级别的访问控制。这不足以阻止使用复杂攻击方法的有动机的攻击者。开发人员和安全团队都需要能够超越端点看到 API 的底层负载，同时在生产中对 API 进行修改时自动更新 API 清单。

如果您还不了解完整的 API 模式或对模式所做的更改，您就不会知道 API 是否受到了损害，或者 API 访问了哪些数据。这些类型的漏洞将继续被网络犯罪分子利用，并将成为未来数据泄露的温床。不要被愚弄了:API 网关不是最终的安全解决方案。专注于寻找能够提供专门构建的 API 安全性的合作伙伴。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>