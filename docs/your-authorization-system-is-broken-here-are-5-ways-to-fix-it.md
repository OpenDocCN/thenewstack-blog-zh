# 修复受损授权系统的 5 种方法

> 原文：<https://thenewstack.io/your-authorization-system-is-broken-here-are-5-ways-to-fix-it/>

[](https://www.aserto.com/)

 [奥姆里·加齐特

奥姆里是授权创业公司 Aserto 的联合创始人/首席执行官，也是他的第三次创业。他 30 年职业生涯的大部分时间都在从事开发人员和基础设施技术方面的工作，最近的职位是 Puppet 的 CPO。此前，他是惠普云原生平台的副总裁兼总经理(负责 OpenStack、Cloud Foundry、CloudSystem 产品和服务的业务、产品和工程监督)，也是微软的总经理，负责 Azure、SQL Server、应用服务器和。NET 框架。](https://www.aserto.com/) [](https://www.aserto.com/)

你或你的团队(重新)建立了多少次授权系统？

在我担任 Puppet 首席采购官期间，我们在整个产品组合中至少建立(或重建)了三次授权系统。我们这样做并不是因为这是一个独特的差异化来源，而是因为我们的客户需要将我们的产品与他们已经拥有的身份和访问系统和流程相集成。

这是拥有企业级 SaaS 产品的“做生意的成本”。尽管我们很想避免重新发明这个轮子，但没有一个开发人员 API 可供我们使用，就像我们使用 Auth0 进行身份验证或 Stripe 进行支付一样。

的确，[授权断了](https://blog.aserto.com/blog/2021/01/authorization-is-broken/)。一个优秀的开发者解决方案应该是什么样的？我们认为对开发者的授权应该遵循五个原则:

*   **[策略与代码分离](https://blog.aserto.com/blog/2021/03/why-separate-policy-from-your-code/)。**授权策略应该从应用程序中提取出来，用独立于应用程序语言和框架的文本表示来表达。这种“作为代码的策略”应该存储在自己的 git 存储库中并进行版本控制，这由应用程序管理员控制。授权策略应该能够在不重新部署应用程序的情况下进行更改。
*   **默认安全。**策略决策应默认为“否”(一个封闭的系统)，并应进行实时评估，而不是依赖于可能在数小时前创建的身份认证令牌的生命周期。
*   **服务，不是图书馆。**以库而不是服务的形式交付开发人员解决方案，就像以服务器软件而不是 SaaS 的形式交付一样，也就是说，很快就会消失。开发者服务提供了一个中心控制点，并负责大规模运行的运营负担——这也是开发者信任 Stripe 支付服务或 Auth0 身份验证服务的重要原因。
*   **开放，基于标准。**就像我们有 JWT、OAuth2 和 OpenID 用于认证一样，我们需要开放的标准用于授权。一个好的开发者解决方案应该有一个多厂商的开源基础，并且是一个广阔生态系统的一部分。
*   **易于集成。**一个优秀的授权服务可以帮助你落入“成功之坑”,因为明智的约定优先于复杂的配置。它与您现有的身份和目录提供商集成，并提供多种托管模式。它有针对每种语言和框架的绑定和示例，所以你可以在五分钟内完成集成，否则下一个就是免费的。

我们将在[自己的博客文章](https://blog.aserto.com/)中详细阐述这些原则——在[我们的邮件列表](https://blog.aserto.com/)上注册，关注这个系列！

授权服务的必备属性是什么？通过[媒体](https://aserto.medium.com/)、 [LinkedIn](https://www.linkedin.com/company/aserto-com) 或 [Twitter](https://twitter.com/aserto_com) 让我们知道。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>