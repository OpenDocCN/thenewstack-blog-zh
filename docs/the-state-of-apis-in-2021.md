# 2021 年的 API 状态:无处不在、多样化、偶尔开放

> 原文：<https://thenewstack.io/the-state-of-apis-in-2021/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是 New Stack 的高级编辑，每周撰写一篇关于网络和应用程序发展趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

我第一次[遇到](https://web.archive.org/web/20060315002018/http://www.readwriteweb.com/archives/programmableweb.php)应用编程接口(API)目录 [ProgrammableWeb](https://www.programmableweb.com/) 是在 2005 年 9 月，在由 [John Musser](https://www.linkedin.com/in/jmusser/) 发布之后不久。当时，目录上只有 54 个条目。时代变了，因为近 16 年后，ProgrammableWeb [列出了超过 24，000 个 API。](https://www.programmableweb.com/apis/directory)

这表明 API 在今天的互联网上已经变得多么普遍。甚至还有价值数百亿美元的 API 提供商，比如 Twilio 和 Stripe。这是一个巨大的市场，主要是因为 API 使开发者能够插入他们的应用程序所需的几乎任何专业服务。例如，您不需要构建自己的通信服务，只需使用 Twilio。同样，成千上万的应用程序使用 Stripe 的 API 来管理支付。

为了更好地了解 2021 年的 API 生态系统是什么样子，我想还有谁比 ProgrammableWeb 的创始人约翰·穆瑟(John Musser)本人更合适呢？如今，Musser 是福特自动驾驶汽车部门的数据和分析总监。他还是 API Science 的创始人，这是他在 2013 年将 ProgrammableWeb 出售给阿尔卡特朗讯几年后创办的一家 API 监测公司。(ProgrammableWeb 随后于 2013 年被出售给 MuleSoft，后者于 2018 年被 Salesforce.com 收购)。

我一开始问 Musser，他是否对 API 和 API 提供者现在如此广泛和重要感到惊讶，或者他是否一直认为会发生这种情况？

“这非常令人惊讶，”他回答道，“尤其是当你回想起 2009 年至 2010 年的那个时代——就在那个时候——当第一批 API 作为产品的公司出现的时候。Twilio 是典型的用例，不久之后 Stripe 也是如此。这两者，我从来没有想到会有数百亿美元的市值，还有许多其他数十亿美元的公司都是 API 第一的公司。”

然而，Musser 认为 API 变得无处不在并不奇怪。这只是过去十年向软件即服务(SaaS)和云计算转变的副产品。

“如果你认为一切都将转移到云上，”Musser 说，“你需要将一切都集成到云上，那么云中的一切都将有一个 API 就不是什么问题了，因为 API 是连接云服务的粘合剂。”

## API 格式的多样性

除了现在是一个更大的市场之外，在形式上也有更多的多样性。虽然 REST(表述性状态转移)仍然是目前提供 API 的主要格式，但 GraphQL 等其他格式也越来越受欢迎。事实上，正如我几周前所写的，许多像 Shopify now [这样的公司在他们的 API 中更喜欢 GraphQL 而不是 REST](https://thenewstack.io/why-shopify-favors-graphql-over-rest-for-its-apis/) 。

按照 Musser 的说法，开发人员现在在选择 API 格式时可以采取一种马马虎虎的方法。

“我认为过去五年左右真正发生的是其他合适的非 REST APIs 的激增。GraphQL 是一个大的，还有 gRPC。GraphQL 是你需要灵活性的时候；gRPC 是你需要性能的时候。还有针对基于事件的模型优化的 WebSocket，以及针对回调模型优化的 webhooks。所以你有一套选择。”

在他自己在福特的工作中，Musser 已经看到了上面所有的 API 方法。

“当然，我们有 REST APIs。我们有许多 gRPC APIs，因为对于互联车辆 API，您需要谈论高容量、高吞吐量、高性能。我们有一些基于事件的 web socket API——特别是针对移动通信，在移动中来回传递。我们有一些 SOAP APIs 仍然存在于一些遗留系统中。这里有相当多的多样性…我们有几个 GraphQL 试点项目，围绕着一些用于账户管理的内部系统。”

当 Musser 在 2005 年开始 ProgrammableWeb 的时候，人们谈论的都是 REST 是如何侵占 SOAP(简单对象访问协议)的。现在，这不是其他格式篡夺 REST 的问题，而是出现了替代格式来更好地支持不同的用例。

就 REST 而言，最大的转变是从作为数据格式的 XML 转向 JSON。但是 REST 本身还是一如既往的受欢迎。许多 API 提供商，包括 [Twilio](https://www.twilio.com/docs/api) 和 [Stripe](https://stripe.com/docs/api) ，都非常依赖它。

## 开放 API 还是一个东西吗？

Web 2.0 API 领域的另一个特点是开放 API 的流行——你可以免费使用 Web 服务，而不必向 Twilio 或 Stripe 这样的公司付费。前 Twilio 时代(2005-2008 年)令人兴奋的部分是一些领先的 Web 2.0 产品提供了表面上开放的 API。例如，数百个第三方应用程序是使用 Twitter 的 API 开发的。但是当公司开始限制他们的 API 或者对访问收费时，这种田园诗般的情形很快就被打破了。众所周知，Twitter 在 2012 年排挤了许多第三方开发者[，当时它对其 API 进行了限制。](https://www.theverge.com/2012/8/23/3263481/twitter-api-third-party-developers)

但在 2021 年，围绕开放 API 有一种谨慎乐观的感觉，特别是随着[开放 API 规范](https://swagger.io/specification/) (OAS)，以前被称为 Swagger，目前在[Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)的保护伞下。Musser 认为 OAS 对于 API 工具来说是一个福音。

Musser 说:“(在规范中)有一个共同的、现代的、一致同意的描述是 API 未来的一个基本要素。“我认为 OpenAPI 规范，特别是它的采用以及它如何驱动和支持 API 工具—无论是在 CI/CD 和发布 API 的开发过程中，还是在 API 设计、API 监控、API 安全中的支持—许多 API 经济都可以从 OpenAPI 规范中受益。”

事实上，Musser 最近创建了另一个目录，这个目录主要关注开放 API。他和另一位 API 专家 Mark Boyd(T1)为 CGAP(T3)建立了一个“开放的金融包容性 API”[仪表板，这是一个位于世界银行的组织。该项目有助于培养一个围绕数字金融服务 API 的开发者和公司生态系统，为世界上 17 亿“无银行账户”的人——那些无法获得金融服务的人——构建解决方案，而金融服务是摆脱贫困的关键因素。由于世界上这部分人口中的许多人确实有手机，开发应用程序来满足他们的金融需求是一个可行的解决方案。仪表板中列出了近 800 个 API，从像印度 HDFC 银行这样的大公司到像肯尼亚 iPay 这样的小初创公司。](https://cgap.apidashboard.io/)

## 结论

API 的普遍存在、API 格式的多样性和开放 API 的发展只是 Musser 目前在 API 生态系统中看到的一些趋势。API 安全解决方案和 API 聚合器的增长是他注意到的另外两个趋势。[金融科技平台 Plaid](https://plaid.com/) 是后者的一个例子，它允许人们将自己的金融账户与应用程序连接起来。

如果软件正在吞噬世界，就像马克·安德森[在近十年前写的著名文章](https://a16z.com/2011/08/20/why-software-is-eating-the-world/)一样，那么很高兴知道它正越来越多地通过 API 提供。ProgrammableWeb 中超过 24，000 个 API 为开发人员打开了无限可能。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>