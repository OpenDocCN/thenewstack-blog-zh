# GraphQL 作为新的 API 网关？

> 原文：<https://thenewstack.io/graphql-as-the-new-api-gateway/>

GraphQL 已经证明了自己是一种定位于改变我们构建现代 API 的方式的技术。许多公司一直在使用 GraphQL 来改变他们与 API 的交互方式。

很少讨论它添加到 API 架构中的可组合性，因为 GraphQL 不仅仅增加了灵活性和性能。您还可以使用它来管理您的 API，例如，通过将其实现为 API 网关。

## **API 网关的优势**

 [罗伊·德克斯

Roy 是一名来自荷兰的开发人员、作家和公共演说家。他的使命是通过培训和激励世界各地的开发者，用技术让世界变得更美好。目前，他正与 StepZen 合作，致力于使 GraphQL 的采用变得容易和可扩展。](https://www.linkedin.com/in/royderks1/) 

在 API 架构中的所有 API 前面使用 API 网关并不是一个新概念。多年来，公司一直使用 API 网关来管理由他们的服务或微服务公开的内部 API，通常是 SOAP 或 REST APIs。

API 网关在为这些 API 的消费者提供统一的体验方面起着至关重要的作用。例如，API 网关允许您进行速率限制、处理访问控制或管理 API 的版本。一些 API 网关甚至提供负载平衡、监控和安全工具。

API 网关通常是一个反向代理层，它提供了所有 API 的单一入口点。您可以创建 API 公开的所有不同端点的映射，而不必单独跟踪所有服务。

这意味着您不再需要向每个 API 发送带有不同参数的单独请求，而是可以发送一个请求，返回您的应用程序需要的所有信息。

## **将 API 与 GraphQL 结合起来**

GraphQL 是一项伟大的技术，[将不同的微服务结合起来，](https://thenewstack.io/why-graphql-for-microservices/)就像一个 API 网关，可以提供一个进入公司 API 的单一入口。然而，在您的 API 架构中使用 GraphQL 作为 API 网关还不常见。这很奇怪，因为 GraphQL 为您提供了从 API 网关获得的许多好处，而没有额外的成本。

GraphQL 允许您将对不同服务的请求合并成一个请求，同时为您提供一个无版本 API。GraphQL 允许您控制请求响应的形式和结果，而 API 网关只允许您控制请求本身。

GraphQL API 的一个用户可能只需要响应的一部分，而另一个用户需要完整的响应。如果没有 GraphQL，就无法在不为该响应创建新端点的情况下限制将返回的数据。

根据您为 GraphQL API 使用的框架或服务，您可以处理现成的访问控制或速率限制，就像处理 API 网关一样。在 StepZen，我们允许您仅使用声明性代码来配置 GraphQL APIs，这意味着您可以使用代码而不是管理界面来管理您的微服务 API。

## **GraphQL 与 API 网关**

通过使用 GraphQL 作为 API 网关，您可以获得与使用常规 API 网关相同的好处，这取决于您用来创建 GraphQL API 的框架或服务等等。例如，使用 StepZen 创建 GraphQL API 的开发人员在使用 StepZen 的托管服务时，可以获得负载平衡、监控/分析和安全性的额外好处。

此外，您还可以深入了解 API 的结构，因为 GraphQL 公开了一个包含 GraphQL API 支持的所有响应类型和操作的模式。即使您的底层 API 没有规范，GraphQL API 也会包含这些 API 的规范。这既改善了开发人员的体验，又提高了 API 的可发现性，而无需投资于额外的文档。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>