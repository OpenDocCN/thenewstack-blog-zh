# Solo.io 为 Istio 推出开发者门户

> 原文：<https://thenewstack.io/solo-io-launches-a-developer-portal-for-istio/>

服务网格软件提供商 [Solo.io](http://solo.io/) 利用其创建 [Gloo API 网关](https://www.solo.io/products/gloo/)的经验，推出了 [Istio 开发者门户](https://www.solo.io/products/istio-developer-portal/)，它位于 [Istio 服务网格](https://istio.io/)之上，帮助记录、公开和组合 Istio APIs。

Solo.io 首席执行官 [Idit Levine](https://www.linkedin.com/in/iditlevine/) 表示，客户正在接触并说“即使你的 API 网关是最先进的，我们也想转向 Apigee 或 Kong——他们有一个开发者门户。”

因此，Solo 团队着手为 Istio 构建一个开发人员门户，Levine 解释说“最终，无论我们在开发人员门户中做什么，我们都将翻译它并为 Gloo 驱动配置。所以我们现在所做的是，我们基本上看到了 Istio 社区的巨大需求，我们决定支持 Istio。所以，当你真正翻译的时候，你可以把它翻译成 Gloo 资源或者 Istio 资源。”

Levine 所说的翻译是 [OpenAPI 规范](https://en.wikipedia.org/wiki/OpenAPI_Specification)的翻译，它可以用于声明性地定义 REST API，或者 [gRPC](https://grpc.io/docs/) ，它允许客户端应用程序直接调用不同机器上的服务器应用程序上的方法，就像它是一个本地对象一样。Istio 的开发者门户获取这些规范，并使用它们来构建前端和后端功能。

[https://www.youtube.com/embed/fnmKTOYjNoA?list=PLBOtlFtGznBiO0B06Px-KCXb-mGzj7uUB](https://www.youtube.com/embed/fnmKTOYjNoA?list=PLBOtlFtGznBiO0B06Px-KCXb-mGzj7uUB)

视频

在前端，Solo 的 Istio 开发者门户为用户提供了搜索 API、注册访问和获取安全密钥的能力，甚至可以直接在门户上测试 API。在后端，门户获取 API 规范并使用它来自动创建文档，添加必要的单点登录身份验证，并创建定制品牌的 web UI。开发人员门户还提供了添加速率限制策略的能力，甚至可以使用简单的复选框式界面将不同的 API 缝合到单一 API“产品”中，作为无缝的单一 API 呈现给最终用户。莱文说，否则这将是非常困难的事情。

“如果你没有和我们一起做，那几乎是不可能做到的。不止一个 API 的拼接，简直是噩梦。为 Istio 创建配置是一场巨大的噩梦。我可以告诉你，特别是因为我们增强它来做事情，我们有点绕过 Istio，直接去找 Envoy，因为我们真的了解 Envoy。这可不是小事，”莱文说。

Istio 的开发人员门户允许您在不管理 Istio 入口配置的情况下公开 API，自动驱动 Istio 路由并生成自定义资源定义，从而创建“转换为低级 Istio 配置的每消费者策略”目前，它支持 OpenAPI 和 gRPC 模式，但还不支持 GraphQL。

“我们将用 GraphQL 做一些更大的事情，但这将是一个重大的宣布，”Levine 说。“所以，敬请关注。”

来自 Pixabay 的 David Mark 的特写图片。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>