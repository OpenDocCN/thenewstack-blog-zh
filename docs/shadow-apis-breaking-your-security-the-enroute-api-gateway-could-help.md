# 影子 API 破坏你的安全？途中 API 网关可能会有所帮助

> 原文：<https://thenewstack.io/shadow-apis-breaking-your-security-the-enroute-api-gateway-could-help/>

[](http://linkedin.com/in/chintant)

 [钦坦·塔卡尔

钦坦·塔卡尔是一名初创公司黑客和产品构建者。可以在 Twitter @SaarasInc 上找到他。](http://linkedin.com/in/chintant) [](http://linkedin.com/in/chintant)

虽然当今的组织正在进行数字化转型，但他们越来越多地采用 API 优先的方法来设计和执行这些计划。这与开发运维实践相结合，是这些转型目标不可或缺的一部分。API 为实现这些实践提供了一个清晰的界限，它们也是驱动 DevOps 实践的一部分，devo PS 实践为软件发布提供了敏捷性。

然而，这种 DevOps 敏捷性需要确保 API 得到批准，并且执行不会滞后。敏捷带来了保持所有涉众同步的挑战，尤其是确保这些 API 交付的 SecOps 团队。为了保持这种 DevOps 敏捷性，需要以同样的速度动态地检查和加强安全防护。

如果不注意，DevOps 敏捷性可能会导致影子 API 超出企业 IT 的权限。这为滥用 API 提供了机会。据 Gartner 称，到 2022 年，API 滥用将成为最常见的攻击媒介。

## OpenAPI 规范 APIs 的蓝图。

当利益相关者合作设计、构建和交付 API 时， [OpenAPI spec](https://swagger.io/specification/) 被采用作为一个系统来同意和开发这些 API。例如，在面向服务的架构(SOA)中，它形成了一种在服务提供者、服务代理和服务消费者之间共享信息的机制。

## 使用 OpenAPI 规范作为 API 的声明性防护

虽然 API 的设计是使用 OpenAPI 驱动的，但是客户端和服务器实现可以使用该规范以选择的语言生成。这些 API 的交付通常涉及一个中间 API 网关来提供访问、监控、认证、授权和转换。

然而，API 网关通常是独立于 OpenAPI 规范配置和运行的。这导致 API 网关上的配置偏离了规范中指定的内容。这可能会创建不在 API 网关范围内的影子 API，因此不会在 API 上实施任何安全(或其他)策略。

## 在 API 网关上接收 OpenAPI 规范并检测漂移

虽然有工具可以从 OpenAPI 规范中生成客户机/服务器(用一种选择的语言),但中间 API 网关最终还是要手动编程。

如果您的 OpenAPI 规范可以被您的 API 网关接受会怎么样？如果这个网关可以作为独立的、sidecar 的或 kubernetes ingress API 网关运行会怎么样呢？

有了这样的自动化，从 OpenAPI 检测 API 网关配置中的偏差就变得容易了。它还简化了作为 CI/CD 流程的一部分以及客户机/服务器/规范的 API 网关的更新。

[途中通用 API 网关](https://getenroute.io)建立在特使代理上，可以使用 OpenAPI 规范对[进行编程。它可以在 Kubernetes 入口作为一个独立的网关运行，也可以作为一个边车运行，以执行特定于提供该 API 的微服务的规范。](https://getenroute.io/cookbook/openapi-swagger-spec-autoprogram-api-gateway-30-seconds-no-code/)

## 消除影子 API，满怀信心地实现开发运维敏捷性

使用 [enroutectl](https://getenroute.io/cookbook/openapi-swagger-spec-autoprogram-api-gateway-30-seconds-no-code/) 工具(与映像打包在一起)对 [Enroute(特使路由器)API 网关](https://getenroute.io/)进行编程不到一分钟。该工具可用于保持 API 网关与 OpenAPI 规范同步。

这种实施机制为 API 提供了必要的防护，确保不受 IT 部门管理或监控的 API 一旦创建就可以被纳入 IT 体系。

或者，可以通过打开默认路径并监控流量命中来发现影子 API。这是一种机制，它解除了开发人员的障碍，并允许开发速度，同时它可以保持在新开发的顶部。

此外， [enroutectl](https://getenroute.io/cookbook/openapi-swagger-spec-autoprogram-api-gateway-30-seconds-no-code/) 还可以提供漂移检测。随着 OpenAPI 规范的更新，可以运行该工具来检查 API 网关是否是用最新的规范编程的。

## 您的 API 的 L7 ACLs

Enroute 提供了一种为 API 流量创建第 7 层 ACL 的机制。网络 ACL 是一种流行的访问控制机制。Enroute 提供了自动创建和实施 API ACLs 或框架以监控影子 API 的能力。

## 使用高级速率限制保护您的 API

途中社区版船舶与先进的速率限制。保护 API 资源对于内部和外部使用都至关重要。途中还可以对经过身份验证或未经身份验证的用户实施不同的速率限制。关于在通用网关上的高级速率限制的更多信息可以在文章中找到— [为什么每个 API 都需要一个时钟。](https://getenroute.io/blog/why-every-api-needs-a-clock/)

## 结论

[途中通用 API 网关](https://getenroute.io/)提供运行时 API 一致性评估和影子 API 发现。

Enroute 的灵活性允许在任何环境中运行它，无论是公共云还是私有云。它还为运行在 Kubernetes 内部的微服务提供了实施开放 API 规范的能力。

Enroute 通用 API 网关社区版允许组织免费防止 API 滥用。如果 API 被允许或有影子，它会在回答关键问题时强制执行最佳实践。

强制执行 OpenAPI 规范和消除影子 API 是一个不足的需求，并且随着 DevOps 的采用而加剧。它需要一个左移的方法来执行规范。

Enroute Universal API Gateway 是一个 [OSS 项目](https://github.com/saarasio/enroute/)，也有一个社区版，包括高级功能，如认证/未认证用户的不同速率限制、金丝雀部署、OpenAPI 规范支持，可以独立工作或作为 Kubernetes 入口。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>