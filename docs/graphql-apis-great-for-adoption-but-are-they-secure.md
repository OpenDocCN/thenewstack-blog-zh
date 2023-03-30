# GraphQL APIs:非常适合采用，但是它们安全吗？

> 原文：<https://thenewstack.io/graphql-apis-great-for-adoption-but-are-they-secure/>

[](https://www.linkedin.com/in/anantjhingran)

 [阿南特·金兰

阿南特是 StepZen 的创始人兼首席执行官，这是一家初创公司，致力于简化开发人员获取数据的方式，以增强数字体验。Anant 的职业生涯跨越了 IBM Fellow、IBM 信息管理部门的 CTO、Apigee 的 CTO 和 Google Cloud 的产品负责人，他的职业生涯一直处于数据库、机器学习和 API 创新的前沿。在 StepZen，Anant 正在享受创建一家公司，将他对这些技术的热爱结合在一起，以简化、加速和扩展前端开发。](https://www.linkedin.com/in/anantjhingran) [](https://www.linkedin.com/in/anantjhingran)

在研究生院，我学习了系统的安全和进程属性。安全防止坏事发生。进步也确保了好事的发生。没有这种平衡，一个什么都不做的系统很可能是绝对安全的。在这个安全和进步的统一体上，有你我每天都在使用的最佳系统的设计。

因此，让我们考虑一下这个连续体上的应用程序编程接口(API)。没有 API 是最安全的选择。但这是错误的选择。鉴于 API 支持新的商业模式，支持现代数字产品并创造新的商业渠道，没有 API 会阻碍当今商业的发展。能够被广泛采用的 API 通常对企业来说是一件好事。但是那么安全性呢？什么是新的攻击媒介？钟摆来回摆动，直到公司在两者之间找到正确的平衡。

我在 API 行业已经工作了十多年，亲眼目睹了公司是如何开发 API 的，但最终却因为隐藏 API 文档、创建需要人工批准的注册流程以及设置其他障碍而使 API 难以被采用。他们的想法是，如果他们使 API 的使用变得困难，他们会更安全。因此，许多企业最终在安全的祭坛上牺牲了进步。

与 Shopify 这样的公司形成对比。它提供了令人难以置信的完整 API，任何使用商店的开发人员都可以使用。人们的想法是，如果 API 易于采用，企业将从中受益。

但是 Shopify APIs 安全性更低吗？这很难说，但我没有听说过任何基于 API vector 对 Shopify 的攻击。

## 谁在采用 GraphQL？

根据 2020 年 [RapidAPI 开发者调查](https://www.devopsdigest.com/api-adoption-on-the-rise-across-all-industries)，2020 年对新 API 技术的兴趣加速增长，在生产中使用 GraphQL 的开发者数量从 2019 年的 6%增长到 2020 年的 12%，翻了一番。此外，调查发现，71.1%的开发者预计 2021 年将比 2020 年使用更多的 API，21.2%的开发者计划使用大约相同的数量。

Evans Data Corp .宣布了其[全球开发者人口和人口统计研究](https://evansdata.com/reports/viewRelease.php?reportID=9)的结果，表明 2021 年全球将有 2690 万开发者。 [SlashData](https://www.slashdata.co/) 预测，到 2030 年，全球开发者人数将增至[4500 万。](https://slashdata-website-cms.s3.amazonaws.com/sample_reports/EiWEyM5bfZe1Kug_.pdf)

因此，随着未来十年全球软件开发人员数量的 65%以上的增长，以及对 GraphQL 日益增长的兴趣，在未来几年，数百万开发人员将有可能在他们的项目中使用 GraphQL。太棒了。如果您构建了良好的 GraphQL APIs，它们很可能会被采用。瞧，进步了！

## GraphQL 带来了挑战和机遇

API 的新的、明确无误的形式是 GraphQL。GraphQL 有助于更快、更直观地采用 API，因为它使开发人员能够专注于他们的应用程序逻辑，并抽象出降低开发人员速度的后端复杂性。想象一个针对 GraphQL API 运行的查询:

```
{
  customer(email:  "john.doe@example.com")  {
    orders  {
      total
      delivery  {
        expectedDate
      }
    }
  }
}

```

在一个直观的查询中，开发人员获得所有数据来描绘她正在构建的任何 web 体验。她不关心后端；她只是得到了她需要的数据。

## GraphQL 安全吗？

让我们先听听大家的担忧，分为三类:

*   首先，开发人员可以访问她不应该访问的内容吗？
    *   使用 REST，可以将 API 分割成 API 产品，并限制对特定 API 的访问；但是在 GraphQL 中，一切都与其他一切相联系。能做些什么？
    *   GraphQL 支持查询参数。那么，有人可以访问他们不应该访问的数据吗？
    *   通过自省一个 GraphQL 端点，开发人员现在可以洞察她可能用我们的系统做的事情。它是否开辟了新的攻击途径？
*   开发人员是否可以有意或无意地提出一些最终会消耗大量资源的问题？
    *   她会不会要求太多的数据，比如“如果 numRecords 是可设置的参数，就给我数据库中的所有记录”？
    *   她能要求最终使用太多处理的复杂链吗？
*   由于 GraphQL 是许多系统的抽象，我如何管理对不同后端的访问？即使我解决了对 GraphQL 端点的访问，我仍然必须解决对后端的访问控制。我是否在云功能或 PaaS 层中引入了管理密钥的新问题？

从根本上说，这一切都归结为“休息是固定的，僵化的:你要求 X；我们给你 X”，而“GraphQL 是灵活的:你要求 X，Y，Z，你得到 X，Y，Z。”

以上三个木桶中的顾虑，没有一个是难以解决的。然而，这些问题必须得到解决，像 Apollo、Hasura 和 StepZen 这样的公司的开源和供应商软件正在这样做。一些企业认为 GraphQL APIs 将首先由他们的内部应用程序使用。一旦他们对安全配置文件感到满意，他们就会向第三方开发人员开放。这些企业正选择将刻度盘转向安全而不是进步，转向安全而不是采用。这完全没问题。但是 GraphQL 的采用曲线将会很陡，我相信长时间保持过于谨慎的企业将会遭受商业后果。

## **总结**

GraphQL APIs 对于前端开发人员来说非常优秀，为应用程序开发提供了加速，并改善了开发人员的体验。然而，它对这些 API 的安全性提出了一些新的挑战。在早期保持一点谨慎可能不是坏事，但从长远来看，保持谨慎会适得其反。所以在安全和进度属性之间，找到正确的平衡。

在 [StepZen](https://stepzen.com/?utm_content=inline-mention) ，我们不仅在构建一个抽象后端的 GraphQL 系统，而且还在关注安全问题，目标是继续帮助我们的客户驾驭采用浪潮，同时关注安全问题。

我们只是在这个旅程的第一局。快去。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>