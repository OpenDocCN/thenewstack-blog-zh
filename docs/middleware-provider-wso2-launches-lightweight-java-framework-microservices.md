# WSO2 推出了用于构建微服务的轻量级 Java 框架

> 原文：<https://thenewstack.io/middleware-provider-wso2-launches-lightweight-java-framework-microservices/>

“大约一年前开始，从零到几乎每一个客户都问我们:你们在微服务上的战略是什么，你们在基于容器的服务上的战略是什么？”WSO2 产品管理副总裁 Isabelle Mauny 指出。

实际上，客户是在告诉中间件公司，“这就是我们想要部署的，”Mauny 说。

从它的客户那里，WSo2 看到了一种更敏捷的、语言无关的持续部署和持续集成环境的推动力，[一种基于容器和微服务的环境](https://thenewstack.io/containers-microservices-work-together-enable-agility/)。

“我们 80%到 90%的客户计划在未来 12 到 18 个月内迁移到基于容器的部署。这项技术正变得越来越稳定，”马尼说。

周一，WSO2 推出了面向 Java 的微服务框架( [MSF4J](http://wso2.com/products/microservices-framework-for-java/) )，该框架基于该公司的开源中间件平台 [Carbon](http://wso2.com/products/carbon/) 。MSF4J 正在与 Spring Boot 等竞争对手展开竞争。是什么让它脱颖而出？除了开源之外，MSF4J 还致力于为快速容器部署提供真正轻量级的微服务。

Mauny 说:“[MSF4J]在设计时就考虑到了容器，所以你可以在容器环境中运行微服务，这是一个非常小的环境。”。她接着说，MSF4J 使微服务能够在 400 毫秒内在 Docker 容器中启动，并“轻松”添加到 Docker 映像定义中。

“所有东西都需要非常轻便。您将运行所有这些微服务，并且您希望能够以即时方式创建该服务的新实例，[并且]您需要创建这些微服务的更多实例，以便能够在后台处理该负载。”

WSO2 MSF4J 功能还包括:

*   支持基于容器的部署。
*   免费使用注释，如 JAX-RS，来编写和监控微服务。
*   基于 WSO2 数据分析服务器功能的内置指标，用于监控微服务的行为。
*   通过与 WSO2 Identity Server 的预集成进行安全令牌验证，并支持包括 OAuth 在内的第三方认证服务器。
*   基于 WSO2 Developer Studio 的工具，用于从 Swagger API 定义开始生成微服务项目。

Mauny 说，几乎任何使用 MSF4J 构建的应用或服务都将享受 Carbon 提供的许多相同功能，包括集群、日志记录和安全性。

“从部署的角度来看，当你部署一个微服务时，你通常会希望它成为 Docker 映像的一部分，以保持部署的连续性，”她说。“这个想法是，在不到一秒钟的时间内，您就可以让您的新容器在您的核心框架中运行。”

MSF4J 的下一步发展是利用市场上巨大的 Spring 社区，使框架非常 Spring 友好。感兴趣的人应该访问 [MSF4J Github](https://github.com/wso2/msf4j) 并开始使用和贡献这个框架。

Docker 是新堆栈的赞助商。

特征图像[通过](https://images.unsplash.com/photo-1442411210769-b95c4632195e?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&s=7712b87007dacb7660344eb37364d365) Unsplash。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>