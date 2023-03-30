# 并非所有的原料药都生而平等——易贝如何扩大其收购原料药的规模

> 原文：<https://thenewstack.io/how-ebays-buy-apis-hit-5-billion-in-gross-merchandise-bought/>

[](https://www.linkedin.com/in/tvlahovic/)

 [坦尼娅·弗拉霍维奇

Tanya 领导着易贝的开发者生态系统。在领导这个团队之前，她是公共 API 的首席架构师。她是改造易贝公共 API 项目的主要贡献者之一。](https://www.linkedin.com/in/tvlahovic/) [](https://www.linkedin.com/in/tvlahovic/)

在易贝，我们有一个庞大、强大且充满活力的第三方应用生态系统。对我们来说，API 是企业对开发者模式的基础，有助于实现业务目标和整体成功。我们将我们的 API 视为一流的产品，使市场平台的访问民主化，并与我们的合作伙伴分享成功。

我们于 2000 年 11 月在[启动了](https://tech.ebayinc.com/engineering/celebrating-20-years-ebays-new-apis-enable-developers-to-create-modern-buying-and-selling-experiences/)[开发者计划](https://developer.ebay.com/)，最初的一组 API 为我们的平台带来了很多价值。其中一些仍然被大量使用，并且对我们的客户非常重要，但电子商务领域的变化表明，现在是时候重新审视我们的产品组合，以加快该领域的增长。这就是为什么我们在 2016 年决定彻底改造我们的开发者计划，并推出新的现代 RESTful APIs。

除了就标准和模式达成一致之外，关键的一步是定义 API 分类法。我们将我们的能力分为四种情况:

*   [Sell](https://developer.ebay.com/products/sell) —包括供卖家大规模管理其易贝业务的 API。
*   [购买](https://developer.ebay.com/products/buy) —包括允许在第三方购物网站上展示易贝商品以及从任何地方在线下订单的功能。
*   [商务](https://developer.ebay.com/products/commerce) —包含有利于购买和销售整合的功能。
*   [开发者](https://developer.ebay.com/products/developer) —为开发者提供关于他们与我们的 API 集成的见解。

到 2020 年底，我们的 Buy APIs 达到了一个重要的里程碑，从 2017 年 1 月到 2020 年 12 月计算，累计 GMB(购买的商品总额)超过 50 亿美元。这是我们如何实现的。

## 购买原料药

[易贝](https://tech.ebayinc.com/?utm_content=inline-mention)汇集了超过 10 亿份房源，向我们的合作伙伴展示最棒的房源选择。这包括新的，日常用品以及罕见的，独特的发现。如果世界上有什么东西存在，你很可能在易贝找到它。我们的重点是实现简单的数据驱动的购物体验，让买家能够找到、比较和购买他们需要和想要的商品。对高容量和低延迟购买的需求从根本上影响了我们的 API 功能。

四个购买 API 对整个 GMB 里程碑贡献最大。

*   [**浏览 API**](https://developer.ebay.com/api-docs/buy/browse/static/overview.html) 让合作伙伴可以使用易贝强大的内部搜索功能。该 API 还支持通过按关键方面(例如，品牌、颜色、大小)进一步过滤响应来创建搜索细化体验。
*   [**Feed API**](https://developer.ebay.com/api-docs/buy/feed/static/overview.html) 允许授权开发者大规模管理、镜像和展示易贝库存。
*   [**订单 API**](https://developer.ebay.com/api-docs/buy/order/static/overview.html) 支持客人和会员从任何地方在线安全结账，无需访问易贝网站或使用易贝本地应用。此外，它还提供订单状态、货件跟踪详情和预计交货日期的更新。
*   [**报价 API**](https://developer.ebay.com/api-docs/buy/offer/static/overview.html) 允许买方进行代理投标并检索投标详情。

除了上述四个 API，合作伙伴还利用我们产品组合中的其他 API 来集成其业务的各个部分，例如用于检索交易和销售事件的[交易 API](https://developer.ebay.com/api-docs/buy/deal/static/overview.html) ，以及我们的[商务](https://developer.ebay.com/products/commerce)API 系列的功能。[分类法 API](https://developer.ebay.com/api-docs/commerce/taxonomy/static/overview.html) 允许开发者理解易贝分类法，并为他们的终端用户选择最好的类别。[翻译 API](https://developer.ebay.com/api-docs/commerce/translation/static/overview.html) 基于内部模型和最先进的算法，针对翻译商品标题和描述的电子商务进行了优化，有助于跨越语言障碍。最后，[慈善 API](https://developer.ebay.com/api-docs/commerce/charity/static/overview.html) 使合作伙伴能够发现易贝支持的 101，000 个慈善组织，并为[易贝慈善](https://www.ebayinc.com/impact/ebay-for-charity/)自 2003 年以来筹集的超过 10 亿美元的资金做出贡献。

## 我们如何在 4 年内达到 50 亿美元

给 API 带来价值的是成功的集成。API 是开发人员用来为用户创造良好体验的构建块。并非所有的 API 集成都是平等的，第三方通过以独特的方式将这些构建块放在一起进行创新。

### **倾听、学习和发展**

在交付 API 时，与值得信赖的开发人员合作并征求直接反馈以帮助制定战略和路线图至关重要。设计优先的方法允许 API 提供者在与消费者迭代的同时不断发展接口。最初，我们发布了所有的 Buy APIs 测试版。我们专注于与值得信赖的合作伙伴建立关系，走遍全球与他们会面，并尽可能经常和尽早地收集反馈。

间接反馈同样重要。API 使用分析指出了变通办法和 API 组合中缺失的功能。因此，准确的洞察——包括运营和业务指标——是增强 API 功能的主要驱动力。

### **简化开发者体验**

交付一个 API 只是工作的一半。重要的是要考虑整体开发人员的体验，通过启用提高开发人员生产力和简化集成的工具来促进采用。我们在 2017 年加入了 [OpenAPI Initiative](https://www.ebayinc.com/stories/news/ebay-joins-the-openapi-initiative/) ，让开发者更容易、更快速地与我们的 API 集成。 [OpenAPI](https://www.openapis.org/) 规范是描述 API 的行业标准。对于所有[我们的 RESTful API](https://developer.ebay.com/docs)，我们已经发布了 [OpenAPI](https://www.openapis.org/) 文档——这使得开发者能够[立即调用我们的 API](https://www.youtube.com/watch?v=E-Ucnf1LBlo)。

软件开发工具包(SDK)是另一套提高开发人员生产力的工具。在我们的例子中，他们抽象了一些概念——比如与我们的授权服务的集成。Feed SDK 就是一个例子。由于我们的数据馈送很大，并且包括易贝库存的最大选择，馈送 SDK 抽象了文件操作并简化了库存管理。我们的 SDK 是开源的，让开发人员完全透明地集成我们的 API(我们感谢开发人员社区的贡献)。

### **通信和连接**

让您的开发合作伙伴了解信息并保持联系是成功合作的关键。自 2017 年以来，我们一直在举办易贝连接大会，在那里我们向我们的开发者生态系统展示了我们的新 API 和易贝的顶级举措。我们在世界各地举办了许多开发者活动，包括在日本、中国、英国、德国、澳大利亚和以色列。全球疫情并没有阻止我们与顶级开发人员的联系。今年夏天，我们举办了第四届虚拟连接开发者大会。尽管面临诸多挑战，但我们期待 2021 年又是一个重大事件和合作年。

### **创新文化**

只有当团队有能力创新时，为我们的开发人员交付成功的 API 才成为可能。在开发者生态系统组织中，我们培育了一种不仅仅是 DevOps 的无可指责的文化。我们鼓励团队成员每天代表客户大胆创新。灵活性和快乐是人们感到安全去冒险和尝试新事物的关键。

作为我们创新文化的一个例子，去年我们利用我们的 API 产品组合做了一件好事，与英国国家医疗服务系统(NHS)合作，推出了向全国医疗保健提供者分发个人防护设备(PPE)的门户网站。与易贝的集成是通过[购买 API](https://developer.ebay.com/products/buy)实现的，我们的团队努力工作，在几天内交付了这个解决方案。这种整合最近获得了现代零售奖的认可，被授予[最负责任零售商](https://www.modernretail.co/awards/modern-retail-awards/#sponsor_attendee)类别。但最重要的是，自 2020 年 4 月推出以来，我们都非常自豪地交付了超过 10 亿件个人防护设备，并有机会帮助拯救生命。

## 连续顶端化

2020 年是整合年。全球疫情将生活的许多方面数字化，持续的蜜蜂化使像易贝这样的组织能够更高效、更频繁地与客户互动。精通数字技术可以实现敏捷的业务，并增加很多灵活性。API 在易贝发挥着关键作用，因此我们将继续为开发人员提供工具来推动他们的业务，并为他们的用户创造出色的体验——他们最终是我们的客户。我们的目标始终是与我们的合作伙伴分享成功。要了解更多信息，请访问易贝的[开发者门户](https://developer.ebay.com/)。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>