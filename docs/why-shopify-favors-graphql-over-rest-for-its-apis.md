# 为什么 Shopify 的 API 更喜欢 GraphQL 而不是 REST

> 原文：<https://thenewstack.io/why-shopify-favors-graphql-over-rest-for-its-apis/>

GraphQL ，一种 API 的查询语言和执行这些查询的服务器端运行时，已经成为 web 应用程序获取数据最流行的方式之一。它越来越成为[单页面应用](https://thenewstack.io/djangos-place-in-a-web-development-world-ruled-by-react/)(SPAs)[无服务器产品](https://thenewstack.io/fauna-and-its-client-serverless-application-model/)、 [Jamstack 框架](https://thenewstack.io/gatsby-wants-to-be-orchestration-layer-for-building-websites/)和其他现代应用的首选解决方案。最重要的是，它已经成为一些互联网公司构建 API 的首选技术——在许多情况下，取代了传统的获取数据的方法。

“QL”部分导致了与 SQL 的直接比较(在一篇针对新堆栈的 GraphQL 的精彩[介绍中，](https://thenewstack.io/introduction-to-graphql/) [Fikayo Adepoju](https://twitter.com/coderonfleek) 写道，它“类似于 SQL，但用于前端”)。它肯定是一种查询语言，所以 SQL 比较是有效的。但我在这里将重点讨论与休息的比较。在不久前，GraphQL 还需要 REST APIs，现在它是如何使用的呢？相对于 REST，有哪些优点和缺点？另外，在本专栏的后面，我将把 Shopify 对 GraphQL 的采用作为一个例子，说明它是如何在行业中使用的。

## GraphQL 与 REST

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇关于 web 和应用程序开发趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) 

促使脸书的一个团队在 2012 年创建 GraphQL 并在 2015 年公开发布的基本观点是，现代 web 应用程序的数据越来越需要图形结构来进行优化，特别是在移动应用程序中。GraphQL 给脸书带来的灵感是其移动应用从 HTML5 过渡到 iOS 和 Android 上的原生应用(背景:在智能手机的早期，脸书试图绕过应用商店，创建移动网络应用而不是原生应用；它在 2012 年放弃了这项政策。

为了转向原生应用，脸书发现它需要“一个 API 数据版本的新闻订阅——在那之前，它只是以 HTML 的形式提供。”这导致了一个关键的见解，正如 GraphQL 的联合创始人[李·拜伦](https://twitter.com/leeb)在 2015 年对[的解释(重点是我的):](https://engineering.fb.com/2015/09/14/core-data/graphql-a-data-query-language/)

*“我们不以资源 URL、二级键或连接表的形式考虑数据；我们从* ***的角度来考虑，这是一个对象图*** *以及我们最终在应用程序中使用的模型，如 NSObjects 或 JSON。”*

与 REST 最大的不同是，GraphQL 只需要一次到服务器的访问，这使得数据读取速度更快。对 GraphQL 查询的响应作为 JSON 发送回来。在获取数据的 REST 模型中，通常需要多次往返服务器才能获得应用程序所需的所有数据，因此速度会很慢，尤其是在移动设备上。

GraphQL 的另一个主要好处是，客户端可以精确地指定它需要哪些数据。例如，如果是电子商务应用程序上的产品页面，客户端可以指定只接收产品的名称、价格、客户评级和可用性。除非特别要求，否则不会下载关于该产品的所有其他数据(例如，如果是电子产品，则为其技术规格)。而在同一个用例中的 REST API 请求，服务器可能会发回一大堆关于特定产品的不必要的细节。

GraphQL 中的这种特殊性是可能的，因为模式是服务器和客户机之间定义数据类型的一种契约。所以 GraphQL 确实需要更多的前期工作，使用模式定义语言(SDL)。但是一旦这项工作完成，GraphQL 比 REST 有更多的灵活性。

## Shopify 对 GraphQL 的采用

坚持将电子商务作为一个用例，现在 GraphQL 的最大支持者之一是 Shopify。2018 年 5 月[2018 年](https://www.shopify.com/partners/blog/graphql-admin-api)Shopify 在 GraphQL 中提供了其最常用的 REST API——Admin API。从那时起，GraphQL 已经“成为 Shopify 构建 API 的首选技术”，据其开发者网站[称。](https://shopify.dev/concepts/graphql)

在今年早些时候的工程博客上，Shopify 的高级开发人员 Maryam Fekri 解释说，Shopify 与 REST 的一个“痛点”是将数据从服务器映射到客户端(反之亦然):

*“当使用 REST 端点时，这些映射基本上将静态类型的代码与非结构化的 JSON 响应相匹配。换句话说，移动开发人员被要求对字段的类型进行硬编码，并将 JSON 值转换为假定的类型。”*

这意味着当 Shopify 必须对其 REST APIs 之一进行更改时，外部开发人员需要相应地更新他们的代码。但是对于 GraphQL，因为数据是强类型的(意味着每种类型都在模式中预定义)，所以在映射数据时，客户端总是与服务器保持同步。正如 Fekri 所说，“移动应用程序中不再有静态类型，代码库中不再有与静态数据类型的 JSON 映射。”

虽然 Shopify 现在全力以赴在 GraphQL 上构建 API，但 Fekri 警告说，“在客户端，我们必须考虑我们构建查询的成本。”换句话说，你不能让你的查询太复杂。出于这个原因，Shopify 对它所称的“[计算查询成本](https://shopify.dev/concepts/about-apis/rate-limits?shpxid=af78c715-1A10-4449-915B-D34EB46BE48B#rate-limiting-methods)”有一个限制费克里是这样解释的:

*“模式中的每个字段都有一个整数成本值，所有这些成本的总和就是我们在客户端构建查询的成本。”*

Shopify 有一个基于积分的公式来定义“计算查询成本”——例如，你可能只允许在 60 秒内累积 1000 分。

## 结论

这并不是说 Shopify 已经完全放弃了 REST API——它仍然有用于管理、计费和库存等基本功能的 [REST 版本](https://shopify.dev/docs/admin-api/rest/reference)。但是有一些 Shopify APIs 现在只有 GraphQL 中的**可用，比如[合作伙伴 API](https://shopify.dev/docs/partner-api) 和[店面 API](https://shopify.dev/docs/storefront-api) 。至于核心管理 API，GraphQL 版本是最受青睐的版本，正如其 [API 概述页面](https://shopify.dev/concepts/about-apis)上的以下注释所表明的:**

*“可以使用 GraphQL(推荐)或 REST 访问管理 API。”*

我应该补充一下，REST 仍然是许多其他公司最常用的 API 格式，包括著名的 API 上市公司 [Stripe](https://stripe.com/docs/api) 和 [Twilio](https://www.twilio.com/docs/api) 。所以这不是一篇“安息之死”类型的文章；安息活得好好的。但是 GraphQL 发展很快——至少在 Shopify，已经证明它是 REST 的一个有价值的替代品。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>