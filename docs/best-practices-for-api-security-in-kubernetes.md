# Kubernetes 中 API 安全性的最佳实践

> 原文：<https://thenewstack.io/best-practices-for-api-security-in-kubernetes/>

当使用 Kubernetes 部署容器化的应用程序时，考虑应用程序所依赖的基础设施是至关重要的。

 [朱迪思·卡勒

Judith 是一名产品营销工程师，对安全性和身份非常感兴趣。在加入 curity 团队之前，她最初是一名开发人员，后来成为了一名安全工程师和顾问。](https://www.linkedin.com/in/judith-k-3269a6a9) 

在 Kubernetes 中保护应用或 API 时，请确保考虑云原生安全性的[4c 标准](https://kubernetes.io/docs/concepts/security/overview/):

*   云
*   串
*   容器
*   密码

遵循这些方面的最佳实践可以确保应用程序在安全的环境中运行。这样的环境有控制和组件来监控和避免各种级别上的意外行为，包括 Kubernetes 生态系统及其管理。

本文主要关注应用程序安全性。特别是，它讨论了 Kubernetes 中作为实现保护 API 的[最佳实践的一部分的](https://curity.io/resources/learn/api-security-best-practices/)[入口控制器](https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/)的角色。

## 提供单一入口点

默认情况下，pod 的端口不会暴露在 Kubernetes 集群之外。可以通过服务对 pod 进行分组，这些服务可以配置为在互联网上公开端口。然而，服务资源是一个简单的组件。即使与负载平衡器结合使用，这种设置也缺乏灵活性和适应性。另一方面，入口控制器提供了企业用例所需的许多功能，例如基于名称的虚拟服务托管、路径映射、代理、响应缓存，或者最重要的安全功能，如身份验证或 TLS 终止。

入口控制器为集群的单点入口(入口)实施规则。作为实现的一部分，入口控制器通常提供一系列安全功能。例如， [NGINX 入口控制器](https://docs.nginx.com/nginx-ingress-controller/configuration/ingress-resources/advanced-configuration-with-annotations/)支持 SSL 重定向、HTTP 严格传输安全(HSTS)或 HTTP 报头过滤。根据入口控制器的选择，它甚至可以提供 API 网关的功能，如速率限制、聚合、监控或开发人员门户。一些入口控制器，如[孔入口控制器](https://docs.konghq.com/kubernetes-ingress-controller/latest/)或 [Tyk 操作员](https://github.com/TykTechnologies/tyk-operator)，通过与 API 网关紧密集成来利用 Kubernetes 中的 API 网关功能。此外，三大云提供商提供云原生 Kubernetes 入口控制器，即 [AWS 负载平衡器控制器](https://aws.amazon.com/about-aws/whats-new/2020/10/introducing-aws-load-balancer-controller/)，Azure 中的[应用网关入口控制器](https://docs.microsoft.com/en-us/azure/application-gateway/ingress-controller-overview)和 [GKE 入口控制器](https://cloud.google.com/kubernetes-engine/docs/concepts/ingress)。

当在 Kubernetes 中公开 API 时，使用入口控制器作为看门人来保护集群中的所有服务。根据您的[需求](https://curity.io/resources/learn/integrating-plugins-with-kubernetes-ingress/#ingress-controller-requirements)和以下最佳实践选择特性。

## 限制访问

作为单一入口点，入口控制器是实施安全策略(如身份验证和授权)的最佳位置。这是一个常见的要求，入口控制器通常通过 OAuth 2.0 和 OpenID Connect 等开放标准提供认证支持。选择开放标准而不是专有解决方案是一个很好的实践，因为它支持互操作性和可移植性。当使用 OAuth 2.0 或 OpenID Connect 时，入口控制器可以[在边界验证令牌](https://curity.io/resources/learn/jwt-best-practices/)。它还可以基于令牌中的数据执行粗粒度的访问控制，如发布者、范围和受众参数，从而卸载 API。

在微服务架构中，一个服务可以调用另一个服务来完成请求。实际上，在返回响应之前，可能会有一个完整的调用链。但是，并不是链中的所有服务都需要相同的权限。因此，请确保令牌有足够的权限。考虑[令牌共享机制](https://curity.io/resources/learn/token-sharing/)以避免令牌过载，以包含下游服务调用中可能需要或不需要的所有可能的权限(范围和声明)。

例如，让 OAuth 2.0 或 OpenID Connect 服务器发布包含另一个可在下游服务调用中使用的嵌入令牌的令牌。然而，这意味着令牌服务器必须预先知道要生成和嵌入哪些令牌。为了能够做到这一点，它必须预先知道将调用哪些其他服务。在复杂的设置中，这个需求可能很难维持。另一种更灵活的方法是[令牌交换](https://datatracker.ietf.org/doc/html/rfc8693)，现有的令牌可以换成新的令牌。该协议类似于幻影令牌方法，但它不是改变格式，而是改变部分内容。

无论采用哪种方法，转发定制的令牌都是实现最小特权原则的一部分。最小特权原则减少了整体攻击面，因为利用特权和获得不应授予的服务和数据的访问权限变得更加困难。

在成熟的设置中，入口控制器或 API 网关用于协调不同的微服务，它还将负责执行令牌交换。

## 不要相信任何人

最佳实践是不要止步于边界，而是实现一个[零信任架构](https://curity.io/resources/learn/zero-trust-overview/)。确保集群中的所有服务请求都经过身份验证。服务网格在基础设施级别提供了这样一种方法。此外，OAuth 2.0 和 OpenID Connect 还提供了应用程序级安全性的工具。[设计访问令牌](https://curity.io/resources/learn/scope-best-practices/)用于 API 中的细粒度授权。

JSON Web 令牌(jwt)是一种流行的访问令牌格式。它们非常有用，因为它们支持零信任架构和[独立令牌](https://curity.io/resources/learn/self-contained-jwts/)。但是，此类令牌可能包含敏感数据，如果未加密，恶意参与者可以轻松解析这些数据。因此，jwt 应该只在集群内部使用。这被称为[幻影令牌方法](https://curity.io/resources/learn/phantom-token-pattern/)。

选择一个可扩展的入口控制器，以允许定制和实施规则，如幻影令牌方法或令牌交换所隐含的规则。它应该支持脚本功能或插件。后者更容易，因为您可以简单地添加和配置插件，而无需编写代码。特别是，对于安全相关的插件，您可以依赖安全专家的工作。例如，使用为 NGINX 或 Kong 提供的插件来增加对幻影令牌方法的支持。但是，即使是脚本和配置也可以共享，并用于分发零信任架构的安全最佳实践。

## 最佳实践一览

简而言之，在 Kubernetes 中保护一个 API 时，要考虑以下几点:

*   使用入口控制器(或 API 网关)来保护 Kubernetes 中 API 的所有服务。
*   在外围执行粗粒度授权，并将细粒度决策留给 API。
*   仔细设计令牌，并在需要时交换它们，以满足最小特权原则。
*   依靠标准协议并使用可扩展性功能来实现零信任体系结构。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>