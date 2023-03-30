# Salt Security 发现严重的 GraphQL API 安全漏洞

> 原文：<https://thenewstack.io/salt-security-finds-serious-graphql-api-security-hole/>

[GraphQL](https://graphql.org/) ，应用编程接口(API)的开源查询语言，非常强大。正如蜘蛛侠提醒我们的那样，强大的能力带来巨大的责任，有时开发者会犯严重的错误。据领先的 API 安全公司 [Salt Security](https://salt.security/) 称，这正是所发生的事情，当时他们的研究人员在一个 B2B 金融技术(FinTech)平台中发现了一个 [GraphQL API 授权漏洞](https://salt.security/blog/api-threat-research-graphql-authorization-flaws-in-financial-technology-platform)。

哎呦。

Salt Security 的研究部门 Salt Labs 在调查这家金融科技公司的移动应用和软件即服务(SaaS)平台时发现了这些安全漏洞。问题的根源在于授权级别的缺陷。这种错误是 GraphQL 嵌套查询的通病，Salt Labs 发现，未能正确实施授权检查意味着研究人员可以针对任何客户帐户提交未经授权的交易，并获取任何客户的敏感数据。

“与 REST APIs 相比，GraphQL 在查询选项方面提供了一些优势。然而，这种灵活性也带来了风险，因为一个 API 调用可以包含多个独立的查询，”Salt Security 的联合创始人兼首席执行官 Roey Eliyahu[说。“随着 GraphQL 的发展，我们的目标是为用户提供智能、功能和支持，以开发更安全的 API 环境。”](https://www.linkedin.com/in/roey-eliyahu-78391b85/)

### 太容易了

使用 GraphQL，很容易在 GraphQL 代码中留下这样的安全漏洞。这是因为,[GraphQL 开发公司](https://www.linkedin.com/in/khalilstemmler/) [Apollo](https://www.apollographql.com/) 的开发者支持者 Khalil stem ler指出，“graph QL 让客户能够以各种不同的方式要求数据。因为有各种入口点可以用来请求数据，所以可以编写[非常大的嵌套查询。](https://www.apollographql.com/blog/graphql/security/9-ways-to-secure-your-graphql-api-security-checklist/)

他没开玩笑。很有可能编写的 GraphQL 查询虽然完全合法，但可能会导致服务器崩溃，或者消耗远远超出预算的云资源。

### 设置 API 安全策略

此外，根据 2021 年第三季度 API 安全报告的 [Salt 安全状态，62%的组织没有或只有基本的 API 安全策略。这是没有借口的。正如](https://salt.security/api-security-trends) [OWASP GraphQL 备忘单](https://cheatsheetseries.owasp.org/cheatsheets/GraphQL_Cheat_Sheet.html#general-practices)所指出的，如果你不保护你的 API 免受像不验证或净化你的 API 查询这样简单的攻击，你可能会在一个伤害的世界中结束。能不能说一下，比如 [SQL 注入](https://owasp.org/www-community/attacks/SQL_Injection)？我知道你可以。

正如 Fortinet 的应用安全产品总监 Brian Schwarz 最近观察到的，组织“可能有多个开发团队，他们有自己的方法和审查级别。这种分散的方法使得[很难在整个 API 攻击面保持一致的安全态势。](https://thenewstack.io/dont-leave-your-apis-undefended-against-security-risks/)

的确如此，这一保护弱点尤其令人担忧，因为针对 API 的网络攻击正在增加，同时采用了相对较新的技术，如 GraphQL，从 2020 年到 2021 年翻了一番。

在这种特殊情况下，Salt Labs 发现了一个 GraphQL 授权缺陷，该缺陷可能被用来操纵 API 调用，以泄漏敏感的用户数据并启动未经授权的交易。这不是你想从你的金融科技应用中得到的。

雪上加霜的是，该平台还有 API 调用，它访问一个不需要认证的 API 端点。换句话说，任何人都可以输入交易标识符并查找过去的金融交易。将这两个缺陷放在一起，攻击者可以窃取重要的用户信息，并且，哦，是的，在用户不知情的情况下，从他们的账户中转移资金。如果曾经有过失败的话，这是一个致命的失败。

“如果没有专用的 API 安全工具，拥有基于 API 的应用程序和平台的组织将面临严重的风险。行业内围绕 GraphQL 的普遍假设是，这些 API 是不常见的、隐蔽的攻击目标，因此更安全。

### 事后才想到安全性

真的，今天还有人会那么蠢吗？哦，是的，对许多程序员来说，安全性是事后才想到的。

Isbitsku 继续说道,“通过模糊来实现安全性一直是一个糟糕的策略，而 GraphQL APIs 的复杂性使得保护它们更具挑战性。Salt Labs 的研究表明，GraphQL APIs 中的失误会导致漏洞和新的攻击媒介，使组织面临风险。”

如果有 API 网关和 web 应用防火墙(WAFs)就好了。他们不是。正如 [Armis Security](https://www.armis.com/) 的 CISO Curtis Simpson 所说，“像 WAFs 和 API gateways 这样的工具不知道 API 之间发生了什么，因此，不能有效地检测或防止利用。Salt 汇集了所有用户的所有活动，因此它可以发现并阻止攻击者。”

### 专门构建的安全工具

因此，Salt Labs 建议其最新更新的 [Salt Security API 保护平台是](https://salt.security/platform)您所需要的。这是一个专门构建的 API 安全工具，用于在整个生命周期中保护 GraphQL APIs。有了它，您可以发现 API，减少数据泄露，阻止攻击，并从源头消除漏洞。

这通过应用其 [API 上下文引擎(ACE)](https://salt.security/why-salt) 架构来实现。它使用基于 AI/ ML 的大数据引擎来解析每个 GraphQL 查询，以识别唯一的对象实体，提供完整的 GraphQL APIs 清单，以及识别和阻止攻击的基线。它还集成了流行的 API DevOps 工具，如 [Apigee](https://cloud.google.com/apigee/docs/api-platform/get-started/what-apigee) 、 [Mulesoft](https://www.mulesoft.com/platform/enterprise-integration) 和 [Kong](https://konghq.com/) 以简化修复。

你可以去看看盐安公司的产品是否能满足你的需求。考虑到如果 GraphQL APIs 出错会给你带来多大的麻烦，我强烈建议你看看这些。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>