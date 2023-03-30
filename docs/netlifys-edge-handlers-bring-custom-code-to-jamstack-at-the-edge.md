# Netlify 的边缘处理程序在边缘将定制代码引入 JAMStack

> 原文：<https://thenewstack.io/netlifys-edge-handlers-bring-custom-code-to-jamstack-at-the-edge/>

使用 [JAMstack](https://jamstack.org/) 构建 web 应用程序意味着通过消除开发者对后端 web 服务器的担忧来简化开发过程。相反，应用程序是使用 Javascript、外部托管服务的 API 和内容标记构建的。这些片段使用静态站点生成器构建，然后内容通过内容分发网络(CDN)发布，为全球用户提供快速体验。

虽然使用 JAMstack 制作的网站和网络应用程序并不完全是静态的，但它们的功能有一些限制，几年前创建 JAMstack 的主要公司 [Netlify](https://www.netlify.com/) 正致力于通过引入边缘处理程序来解决这些限制。Netlify 已经提供了无服务器功能，作为添加一些后端处理和功能的方式，现在该公司正在添加边缘处理器，作为通过在网络边缘执行定制代码，在网站和网络应用中实现快速个性化内容的方式。

“在请求响应周期中，您通常会在应用服务器中做一些事情，如个性化会话或复杂的身份验证模式，如果没有请求响应周期，您将如何做这些事情？”Netlify 首席执行官兼联合创始人[马特·比尔曼](https://twitter.com/biilmann)在接受采访时说。“我们总是有一套非常强大的声明性规则，您可以在重写、重定向等方面使用，但仍然有一些东西会成为障碍，除非您有办法在请求-响应周期中定制程序。这就是我们用边缘处理器真正解决的问题。边缘处理程序允许开发人员用 JavaScript 编写完全定制的代码，这些代码作为请求周期的一部分直接在我们的边缘节点上执行。”

本周在 Netlify 的 [Jamstack Conf Virtual](https://jamstackconf.com/) 上推出，Edge Handlers】可用于预览版中的精选客户，旨在更轻松地交付本地化内容，简化 A/B 测试，并提供自定义身份验证，以及其他可能难以使用 Jamstack 的功能。Netlify 将在 Netlify UI 中为边缘处理器提供详细的日志，允许用户使用他们现有的工具，并很快计划在交付生产之前提供位置测试和验证。Biilmann 说，边缘处理器在速度上不同于无服务器功能。

“在边缘处理器中，你需要路由决策、认证决策、个性化、响应转换，一般来说，你需要编写能够做出非常快速的决策并在几毫秒内运行的代码，”Biilmann 说。

根据 Biilimann 的说法，此次发布将伴随着本周大会上后台功能的发布，加入该公司现有的无服务器产品，提供三种方式来扩展 JAMstack 功能，具有三种不同的用例。

“我们将引入第三种功能，即后台功能，它适用于真正长时间运行的任务。假设您有一个允许某人订阅您的服务的功能，它调用 Stripe 并将您创建为订阅者。这样做之后，您可能需要该电子邮件地址并运行一些后台进程。Biilmann 说:“这些都是你可能想在一个运行几分钟的后台函数中做的事情。“我倾向于从这三个层面来看待它:边缘处理程序，用于可以在几毫秒内完成的事情，通常涉及快速路由决策、身份验证决策或响应转换；无服务器功能，用于更像微服务、API 端点等类似的事情；以及后台功能，用于长期运行的任务，您只需启动任务，然后用户就可以按照自己的方式运行。”

一份公司声明将 Edge Handlers 描述为“Netlify Edge network 基础重写的结果”，Biilmann 解释说，该公司用 Rust 而不是 C++重写了其边缘层，因为该语言具有强大的内存保证。Rust 被选中也是因为它的性能，他说这是边缘速度的关键。边缘处理程序本身是使用 Deno 编写的，Deno 是基于 V8 Javascript 引擎的 Javascript 和 Typescript 的运行时，他说这“让我们有机会使用隔离来确保我们可以控制任何给定的边缘处理程序允许使用多少资源。”

感兴趣的用户可以[请求提前获得边缘处理程序，](https://www.netlify.com/products/edge/edge-handlers/)尽管 Biilmann 拒绝透露该功能何时会普遍可用。

Pixabay 的 skeeze 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>