# Swagger 3.0 发布在即

> 原文：<https://thenewstack.io/swagger-3-0-release-approaching/>

Swagger 3.0 团队目前的目标是在未来几个月内更新他们的工具，以支持 [OpenAPI 3.0](https://www.openapis.org/) 规范。该更新将扩展描述更复杂的 API 的能力和描述带外请求的能力。这也是除了 Swagger 工具链之外， [OpenAPI 规范](https://github.com/OAI/OpenAPI-Specification)作为其自身实体的第一个主要版本。

如何扬眉吐气:2010 年，[托尼·谭](https://www.linkedin.com/in/tonytam)试图解决一些真正可怕的技术难题。作为一家四人创业公司的 API 开发人员，他试图让自己的文档与实现保持同步，这让他抓狂。这项工作是持续不断的，最终，在一个不眠之夜，Tam 决定是时候创建一个解决方案来满足保持 API 良好文档记录的持续需求，同时快速添加特性。

到年底，Tam 和他的团队已经构建出了后来的 Swagger 1.0。Swagger 不仅是一个以易于理解的方式编写 API 的规范，它还是一系列有助于简化这一过程的工具。使用 Swagger，开发人员可以自动为他们的 API 生成文档甚至客户端，并且他们可以通过权限控制对这些 API 的访问。

“团队中的一个人说，‘让我们用一个漂亮的 HTML 界面来呈现它吧’，而团队中的另一个人说，‘让它生成样本客户端和 SDK 吧’，所以我们把它建了出来。这完全是一个完成我们工作的附带项目。Tam 说:“我们在 2010 年将它作为开发者门户向公众发布，很多人伸出援手，说你应该开源它。

那发生在 2011 年。从那时起，项目、规范和工具都以它们自己特殊的方式发展。Swagger 最初被命名为 Web 应用描述语言[的替代语言](https://www.w3.org/Submission/wadl/):当你可以 Swagger 的时候，为什么要用 WADL？2015 年，Tam 将规范、开源项目和他自己卖给了 [SmartBear Software](https://smartbear.com/) ，他现在是 Swagger products 的副总裁。

然而，从那以后，真正的 Swagger 规范已经有了新的发展。它于 2015 年末捐赠给了 Linux 基金会，并在 [OpenAPI Initiative](https://www.openapis.org/specification/repo) 下更名为 OpenAPI 项目。

“当时，一些已经开始对 Swagger 进行标准化的大型公司与我们进行了接洽，这些公司分别是[微软](https://docs.microsoft.com/en-us/aspnet/core/tutorials/web-api-help-pages-using-swagger)、 [IBM](https://www.ibm.com/support/knowledgecenter/en/SSMKHH_10.0.0/com.ibm.etools.mft.doc/bi12018_.htm) 、 [Intuit](https://developer.intuit.com/apis) 、PayPal、[Capital One](http://api.reimaginebanking.com/)——涉及行业的不同领域。现在，这个项目不是由托尼管理的，而是由智能熊管理的。Tam 说:“我们同意将该规范放入一个 Linux Foundation 项目中，这样它就可以永远免费，以促进该规范的开放使用，这样人们就可以围绕它构建工具和公司，而不用担心 SmartBear 会用它来做什么。

尽管如此，他补充说，SmartBear 是他作为大摇大摆的开源项目的指导者的理想选择，他说他们不打算直接货币化或把这些工具分成产品线。相反，Tam 说，我们的目标是通过 Swagger 的传播，帮助每个人的工具和软件变得更好。

Tam 说，当 2014 年 [Swagger 2.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/2.0.md) 发布时，该团队每月有 120，000 次下载。到 2015 年底，每月下载量高达 37 万次。今天，Swagger 每天的下载量超过了 10 万次。

今天，Swagger 规范 3.0 版本的候选版本正在准备最终发布。这一版本规范的工作完全发生在 OpenAPI 计划中，这是第一次这样的工作发生在那里，而不是在 Tam 自己的工作组中。

Tam 没有领导这项工作，而是专注于 Swagger 工具系列中规范的实际实现。这包括 Java 中的[核心 Swagger 库](https://github.com/swagger-api/swagger-core)、 [Swagger UI](https://swagger.io/swagger-ui/) 、 [SwaggerHub](https://swaggerhub.com/) 和 [Swagger 编辑器](https://swagger.io/swagger-editor/)。Smart Bear 和 Tam 仍然负责这些项目，并继续以开源方式开发这些项目。

Tam 说，对于 3.0 版本，这些工具被从头开始重写。它们现在已经被完全重写，并加入了 3.0 规范。这些工具和规范本身应该在 5 月底准备好，尽管 Tam 说这不是一个硬性的截止日期。

Tam 将 Swagger 工具和 OpenAPI 3.0 规范之间的区别比作 HTML 和 web 浏览器之间的区别。Tam 说:“当浏览器出现时，并没有规范的概念。

对于 3.0 规范，Tam 说这个项目有很多重大的变化。“我们早期做的事情之一是使用 [JSON 模式](http://json-schema.org/)作为一种表示有效载荷和定义规范本身的方式。JSON 模式是一种验证结构。我们并不完全支持它。有些用例你根本不能做。如果你有一个 API 返回水果作为响应，还有椅子，那就不行了。我们有一个要求，即响应是确定性的，这意味着你必须事先说你要返回什么。我们在模式中添加了一些东西，允许您返回多种类型。这很难，但社区要求它如饥似渴，”谭说。

“人们在 Swagger 规范中批评的一件事是我们不支持超媒体。虽然我们不支持超媒体本身，但我们添加了一个称为链接的特性，这是一种在设计时表示 API 调用之间关系的方式。你不需要改变你的 API 来支持 OpenAPI 链接。这是一个描述。您描述了您的 API 如何支持它们，并且该工具在此基础上添加了功能。这是一件大事，因为对于 Atlassian 这样的公司，他们必须在 API 调用中支持链接。目前，他们发送这个巨大的有效载荷，每次你提出请求，每一个可能的链接。这是一笔巨大的成本，”Tam 说。

最后，OpenAPI 3.0 规范增加了一种:“描述带外或异步请求的方式。对于 [WebHooks](http://www.webhooks.org/) ，或者长时间运行的请求，或者订阅类型的机制，有必要提供一些方法，不仅描述如何处理异常或者请求何时可能返回，以及带外响应，更重要的是，作为消费者，你需要如何处理它。你可以去阅读 GitHub 的 WebHooks 是如何工作的:阅读一个关于如何实现服务器通信的巨大文档，它不同于 BitBucket、Google 和 IBM 的。我们建立了一种机制，允许 API 设计人员或文档专家描述带外请求和响应是如何工作的，以及如何设计您的消费者来接收这些呼叫，”Tam 说。

至于 Swagger 和 OpenAPI 规范的未来，Tam 说这些项目有两个主要的哲学驱动力。“这是一种描述语言，不是查询语言，也不是框架或设计指南。我们说过你不需要使用 Tony 的服务器工具来实现它。你只需要能够描述你的 API 是兼容的。我们不能描述所有的东西，否则看起来就像 WADL，但是如果你能描述你的 API，你就能得到符合规范的东西。好的一面是，一旦发生这种情况，自动化工具可以开始生成客户端并为您工作，”Tam 说。

Capital One 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>