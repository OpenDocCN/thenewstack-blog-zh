# StepZen:一个连接所有数据的 API

> 原文：<https://thenewstack.io/stepzen-one-api-to-connect-all-the-data/>

在 2016 年将 API 管理平台 [Apigee 出售给 Google](https://techcrunch.com/2016/09/08/google-will-acquire-apigee-for-625-million/) 后，团队成员着手简化连接多个后端数据的 app 开发工作。

[阿南特·金格兰](https://www.linkedin.com/in/anantjhingran/)，前 Apigee 首席技术官，与[斯里达尔·拉贾戈帕兰](https://www.linkedin.com/in/sridhar-rajagopalan-9887321/)和[海伦·惠兰](https://www.linkedin.com/in/whelanhelen/)一起离开谷歌的 Apigee 团队，于去年创立了初创公司 [StepZen](https://www.stepzen.com/) 。

“我们生活在两个世界:我们生活在数据库世界，我们生活在 API 世界。我们意识到，这两个世界的交汇实际上可以带来变革。

在看到成百上千的客户如何实际实现 API 后，他说，“我们意识到一定有更好的方法。为了建立一种更好的方法，我们正在利用我们过去在数据库、机器学习和其他领域的经验，……来做一些今天非常费力和手工的事情。”

> StepZen 的想法是编写一个 API，从各种来源提取所需的数据，并管理提取过程。

他们在 Apigee 所做的事情之一是为数据科学家和软件开发人员创造一种方法，共同创建一种数据结构，作为连接数据的 [API 图](https://thenewstack.io/building-adaptive-apps-like-google-now-with-apis-and-analytics-with-apigee-insights/)。他们的最新努力再次连接了数据——动态应用程序用来从各种数据源(如数据库、内容管理系统和第三方 API)中提取信息。

例如，一个电子商务应用程序可能会从客户系统中提取数据；订单系统；递送系统，如 FedEx 或 UPS 以及其他可能的来源。

想法是编写一个 API，从各种来源提取所需的数据——*管理提取过程*。Jhingran 说，开发人员可以编写代码来处理所有这些，但是，特别是在 Jamstack 的世界里，开发人员不想管理任何东西，这只会减慢开发过程。

这就是 StepZen 介入的地方:它将数据检索为可用的格式，并负责错误处理、缓存、返回逻辑和路径优化等过程。

“我们希望成为所有 Jamstack 开发者访问所有 API 的地方，但从根本上来说，不运行任何基础设施对开发者来说是有吸引力的，(而且)很容易构建，”他说。

[https://www.youtube.com/embed/I6fgKVxr8eM?feature=oembed](https://www.youtube.com/embed/I6fgKVxr8eM?feature=oembed)

视频

## 只有一个 API

想法是用 [GraphQL](https://thenewstack.io/introduction-to-graphql/) 构建一个 API，用一个查询获取正确的数据。开发人员只需应用配置信息和凭证来连接必要的后端数据源。金格兰说， [SaaS 服务](https://www.stepzen.com/blog/why-stepzen-as-a-service)运行在谷歌云上，但它不关心后端在哪里。

StepZen 设想使用声明性技术来抽象后端，前端开发人员只要求他们想要的，而不是使用程序代码，即今天的 API 世界，它确切地指示 API 需要的位和可以请求它的精确方式。Jhingran 说，从谷歌搜索或谷歌地图中获得灵感，开发人员不必为查询可能采取的每一种形式编码，他们只需提出请求，系统就能解决它。

他称 GraphQL 对于前端开发人员来说是“了不起的”。例如，如果他们查询天气，但实际上只想要温度，它不会将找到的所有信息都返回给他们。他说，它允许后端和开发者使用它的方式分离。

“由于这种分离，你可以改变你的后端，或者你可以有多个后端，输入到同一个东西，等等。他说:“前端人员不关心事情是如何发生的，而 GraphQL 在这方面非常棒。

https://www.youtube.com/watch?v=3B00i18hYis

## **让开发者生活更简单**

这家总部位于加州圣何塞的公司在 11 月发布了它的 alpha 版本，并在接下来的六个月里与一批开发人员一起向 GA 迈进。

12 月下旬，它宣布获得 Neotribe Ventures 和 Wing Venture Capital 800 万美元的种子投资。

它不仅关注构建 API，还关注运行它们，总的来说，让开发人员的生活变得更加轻松。

“我们有一个由几十名开发人员组成的社区，他们与我们同行，他们基本上(告诉我们)他们处理的各种问题。虽然他们可以通过编程解决所有这些问题，但在某个时间点，所有这些都变得有点太多了。因此，我们和他们一起工作，并且说，‘好吧，看，对你来说有哪些事情是很难做到的？“我们怎样才能让它们变得简单，””金格兰说。

其中一位是费尔南多·安德拉德，他是 T2 工作公司的技术总监，该公司是一家开发网站、应用和数字体验的技术和设计机构。

“在过去的几年里，我们一直在关注 GraphQL 社区，并看到人们对托管的 GraphQL API 服务越来越感兴趣，这些服务旨在通过向前端开发人员隐藏服务器端的复杂性来缩短从想法到生产的周期。这正是 StepZen 所关注的领域，在这个领域我们看到了很多机会，”他说。

在活动中为招聘者和求职者牵线搭桥的初创公司 [Recorem](https://www.recorem.com/) 的创始人[普拉塔普·拉马纳坦](https://www.linkedin.com/in/pratap-ramanathan-78278023/)补充道:“在建立人才供应时，我们必须吸引第三方开发者，还必须整合许多后端。虽然还处于早期，但我们相信 StepZen 通过快速支持我们交付 GraphQL 端点，为我们提供了一种加快产品上市的方式。

特征图片:“ [Momento 禅！](https://www.flickr.com/photos/alablu/17334144562/in/photolist-spL2gq-zhGFK5-6gD7PY-4FE2hj-dzZmRU-6xtCgk-coCb3A-5nrVry-9anUiy-H4Qw-7ChHqy-yjC8fN-8bka6K-6gD6g9-fCWV3H-5givjC-bmaH1d-bmaH7E-795R5a-2jhyf1V-PFyJvK-4SU36C-2jv6npK-eaiXir-6wcuzF-5Gicvj-eaiXxX-2hRCePt-rAXni4-5CzTnV-7NeHAr-7UDn8Z-bJU58t-e3z1Rd-bjTg4a-5c4NEa-YjqXdL-dQkrr-bpNET9-a1sAYf-jEgYUf-9eNpRw-4Y7osy-8S4SFR-NKjD6-7aFA5q-dQktC-ETwnWA-5HoncU-4HjWvE)作者[费德里科·扎农](https://www.flickr.com/photos/alablu/)。根据 CC BY-SA 2.0 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>