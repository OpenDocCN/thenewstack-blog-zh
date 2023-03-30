# Stitch 为 MongoDB 缝合第三方后端服务

> 原文：<https://thenewstack.io/stitch-sews-together-third-party-backend-services-mongodb/>

周二，MongoDB World 2017 在芝加哥拉开帷幕，这是一个为流行的开源 [MongoDB](https://www.mongodb.com/) 文档数据库开发的新服务集成软件包 Stitch。

[Stitch](https://www.mongodb.com/cloud/stitch) 旨在处理日常任务，如设置访问控制和安全规则，也可用于无缝集成第三方服务，如支付、消息传递和用户认证。

MongoDB 首席技术官和联合创始人埃利奥特·霍洛维茨(Eliot Horowitz)自豪地说，该软件旨在“在如何公开数据以及如何在应用程序中直接处理数据方面提供无与伦比的灵活性”。它与市场上的任何东西都不一样，不同之处在于你如何把东西放在一起，如何配置东西，以及如何为它提供担保。"

Stitch 推出了与谷歌、脸书、AWS、Twilio、Slack、MailGun 和 PubNow 的预建集成，尽管 Stitch 可以与任何其他提供 REST API 的服务集成。

Horowitz 在他的主题演讲中告诉观众，今天的软件开发主要是将各种服务缝合在一起。

“如果您将后端作为服务使用，并决定使用不同的工具直接访问数据，该怎么办？如果[后端服务的]API 不支持该工具怎么办？你运气不好。如果你想使用他们不支持的服务怎么办？竞争对手的服务？你也被困在那里了。如果我不想再使用这种后端即服务，该怎么办？我有其他选择吗？通常情况下，答案是否定的。通常情况下，你会被锁在里面，”霍洛维茨说。

Stitch 是一个用于 MongoDB 的 REST API，允许您直接从 web 应用程序、电话或物联网设备连接，以基于配置的方式进行身份验证、隐私和安全。您可以使用编写规则使它变得简单或复杂，而无需编写任何代码。

“你可以验证，你可以审计，你可以建立这些非常简单的规则，这样你就可以向任何人公开任何你想要的数据，”他说。你可以使用任何你想要的服务——任何与 HTTP 相关的服务你都可以直接嵌入其中。Stitch [可以在任何环境](http://video.mongodb.com/watch/jTMyduFFTfLmnvTmH6pkpU?)中使用，无论是云、内部部署还是 MongoDB 的数据库即服务 [Atlas](https://www.mongodb.com/cloud/atlas) 。

Stitch 可以将现有数据库中某些字段暴露给新的应用程序，并提供一种简单的方法来写入数据库。简单的 JSON 规则定义了用户可以读写哪些字段。还有针对 JavaScript、Android 和 iOS 的软件开发工具包(SDK ),以实现跨平台支持。

这个 Stitch 是从一个名为 Stitch 的公司提供的同名 MongoDB 软件包中分离出来的，用于数据仓库提取、转换和加载工作(ETL)数据管道。那针是基于[歌手 ETL 标准](https://www.singer.io/)。

## 一针及时

Horowitz 在另一次采访中说，Stitch 在 T4 的最大优势之一是没有锁定。

“我不认为任何后端即服务能够百分之百满足您的需求。总有一天会有东西坏掉。有了 Stitch，你可以绕过它，直接进入数据库，不用 Stitch 层就能拥有 Mongo 的全部功能，”他说。

Stitch 最初是作为 Atlas 数据库即服务的公共测试版提供的。

这家 NoSQL 供应商还宣布将 Atlas 扩展到亚马逊网络服务之外，以包括对 Azure 和谷歌云的支持。

Atlas 在去年的会议上推出，拥有 3000 多名客户，包括约会网站 eHarmony 和生物技术公司 Thermo Fisher Scientific。已经有超过 20000 名开发者注册了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>