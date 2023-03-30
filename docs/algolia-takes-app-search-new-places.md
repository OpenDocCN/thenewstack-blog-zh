# Algolia 将应用内搜索引入新领域

> 原文：<https://thenewstack.io/algolia-takes-app-search-new-places/>

Algolia 提供了一个托管的“随你输入搜索”API，通过提供搜索作为应用程序的可定制构建模块来赢得开发者的心，就像 [Stripe](https://stripe.com/) 提供支付和 [Twilio](https://www.twilio.com/) 提供语音和消息一样。

作为一种激励，它提供了一个免费的搜索服务组合: [Algolia Places](https://blog.algolia.com/introducing-algolia-places/) ，它提供了一种在你的网站上嵌入地址搜索自动完成 JavaScript 库的简单方法。基于 [OpenStreetMap](https://wiki.openstreetmap.org/wiki/Planet.osm) 的数据库，它使得通常用于注册和结帐的 HTML 表单的填写更加用户友好。在 [npm](https://www.npmjs.com/package/places.js) 和 [jsDelivr](https://www.jsdelivr.com/projects/places.js) 上都有。

据公司联合创始人兼首席执行官 [Nicolas Dessaigne](https://twitter.com/dessaigne) 称，Algolia Places 是该公司的社区项目之一，比类似的 Google 产品 [Google Places](https://developers.google.com/places/) 更具灵活性。

“谷歌在 Google Places 中提供了一个非常好的产品，但是你不能用它做你想做的事情。他说:“我们提供了更加开放的东西，你可以结合自己的数据，或者用新的东西来扩展——你可以更新地图上的东西，让它变得更好。”

Algolia 已着手改善个人网站和应用程序的搜索体验，以应对数据库全文搜索的缺点。它起源于一个离线软件开发工具包，在移动设备的能力和处理能力有限的情况下提供快速、可靠和相关的搜索。

Dessaigne 坦率地承认，免费提供位置是为了提高该公司的知名度，该公司最初总部设在巴黎，但现在总部设在旧金山。

Algolia 已经从包括 Accel Partners、Docker 的 Solomon Hykes、凯文·罗斯和 Splunk 的 Erik Swan 在内的投资者那里筹集了 2122 万美元。它的 1600 个客户包括 CrunchBase、Genius.com、Vevo、Digital Ocean、Periscope 和 Birchbox。

成立于 2012 年，创始人从 Stack Overflow 上寻求在自己的移动应用程序中嵌入 Apache Lucene **、**elastic search 中使用的库的开发人员数量中看到了机会，Dessaigne 说这不是为这个用例设计的。因此，该公司建立了自己的移动离线搜索 SDK。

[![demo](img/9c814446b0af3ebb2352445e97cb991f.png)](https://blog.algolia.com/introducing-algolia-places/)

“硬件限制迫使我们重新发明搜索，权衡利弊，使其在移动设备上运行。就技术而言，这是一个巨大的成功，但市场完全不是我们所希望的。这就是我们后来转向 SaaS 的原因，”Dessaigne 说。“如果我们从服务器开始，我们可能永远不会想到这些想法。”

在转向 SaaS 的过程中，C++ SDK 作为 Nginx 模块嵌入到高端服务器中。公司首席技术官[朱利安·莱莫因](https://twitter.com/jlemoine_algo)写了公司使用裸机而不是云基础设施的决定，以及其克服障碍提供高性能的工作[。它在全球 15 个地区使用 36 个数据中心，并在三个不同的数据中心复制客户数据。](https://medium.com/@algolia/algolia-s-fury-road-to-a-worldwide-api-c1536c46f3a5#.r4o4efnyk)

现在，在世界顶级市场，它可以在不到 50 毫秒的时间内返回结果——比面向大数据的弹性搜索快 200 倍。其他竞争对手包括[swift type](https://swiftype.com/)、 [Searchify](https://www.searchify.com/) 和[亚马逊云搜索](http://aws.amazon.com/cloudsearch/)。

Algolia 还构建了自己的[排名算法](https://blog.algolia.com/how-algolia-tackled-the-relevance-problem-of-search-engines/)来提高相关性。

“传统上，相关性是基于引用的数量，这对于今天的大多数用例来说确实不是一件好事，”Dessaigne 说。“如果你在寻找一个产品，你不会真的对一个词出现了多少次感兴趣，你更感兴趣的是这个词出现在哪里。如果你在一个电子商务网站上，你可能对一个产品有多少赞、多少粉丝更感兴趣。

“因此，我们开始构建一些将事件与业务数据相结合的东西。有了这个，客户可以利用他们对自己用户的了解，”他说。

“如果你在一个关于电视节目的社交网络上，如果你键入‘G’，你会得到‘权力的游戏’；你输入“B”，你就会得到“绝命毒师”即使这不是你要找的，在七个字母内，我们通常会找到你想要的。我们可以做到这一点，因为我们有关于用户行为的数据。"

Algolia 提供了一个基于 JSON 的 REST API 来索引数据。客户可以使用存储在与主索引同步的多个从索引中的业务数据，定制可搜索的属性(如流行度、地理位置数据、标签、日期)和属性排名相关性。更新可以随时进行。

为了消除网络和处理延迟，它建议消除后端的搜索逻辑和功能，而是专注于前端，以便所有来自用户浏览器或移动设备的查询都直接与 Algolia 处理。在 5 月的 Serverlessconf 上，开发者和 TNS 贡献者 Joe Emison 表示，他更愿意直接使用 Algolia 而不是 Elasticsearch，因为该公司已经完成了大量的配置工作，这使得 T2 更容易集成到他自己的应用程序中。

它集成了大多数流行的编程语言以及许多平台和工具，包括 WordPress、Heroku、Zendesk、Meteor、MongoDB 和 ColdFusion。

展望未来，它正在努力根据用户的行为个性化搜索，并允许用户在因任何原因断电时从在线搜索无缝切换到离线搜索。

[码头工人](https://www.mirantis.com/software/docker/kubernetes/)是新堆栈的赞助商。

专题图片:[我们乘船旅行的地图](https://www.flickr.com/photos/oliverquinlan/5627079126/in/photolist-9zffzC-napvpK-8pRm97-bNWdXa-bjPdqs-7dDyU7-rfZcWS-bxHYPg-ncu4Bo-9Af25g-766aPU-bkwnku-8BgxV2-4kTq7c-2fwSbX-bNWdNp-drJiNN-czJpfj-cadtbm-9FZirR-9gqV1K-chneuY-7dzERg-diBmFL-nBpFAT-8n49mA-diBphr-ohNqUL-nemJvV-nRcnnE-dNRofz-9B9MAu-ni2wEU-7oHPsN-drSom8-9e7r1W-4A959U-e1M5oQ-e1M6xC-e1M8nb-3z2GKF-fLi6yZ-44k73q-7m74Zr-gJYLs7-65GH7i-96ANsw-4mLvtP-z5ge1W-79aZCc)，作者[奥利弗·昆兰](https://www.flickr.com/photos/oliverquinlan/)，授权于 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>