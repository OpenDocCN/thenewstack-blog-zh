# 向上堆叠:无服务器、Jamstack 和 JavaScript 年终回顾

> 原文：<https://thenewstack.io/up-the-stack-a-year-end-review-of-serverless-jamstack-and-javascript/>

在原生云王国，库伯内特人的统治持续到 2020 年。但是，尽管王位没有挑战者——国王有时被宣布为“[无聊](https://thenewstack.io/kubecon-pancake-breakfast-why-your-k8s-stack-should-be-boring/)”——王室高层还是有一些有趣的发展。

宣布基础设施将被摧毁的新贵骑士“无服务器”今年势头强劲。一个叫 Jamstack 的迄今不知名的平民粗鲁地戳了内容管理系统的贵族(强烈地激怒了 WordPress 先生)。与此同时，古老的 JavaScript 领地继续扩张，前端和后端开发人员联合起来形成了一支新的精英力量:全栈开发人员军团。

在这一点上，我将放弃中世纪的隐喻！现在让我们回顾一下 2020 年的三个主要发展趋势——无服务器、Jamstack 和 JavaScript——以及它们对 2021 年的预示。

## 无服务器增加功能

无服务器是云服务的一种形式，旨在通过抽象后端基础设施，让开发者的生活变得更加轻松。我们的目标是让开发人员能够专注于前端(它有自己的复杂层次，但我稍后会谈到)。

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇专栏文章，探讨云计算原生互联网的未来。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) 

随着无服务器时代的到来，2020 年出现了几大主题。首先，它现在已经不仅仅是“功能即服务”(FaaS)，这是从 2015 年左右开始定义该领域先锋的东西: [AWS Lambda](https://aws.amazon.com/lambda/) 。其次，现在有一些可行的项目旨在将无服务器超越无状态应用程序(Lambda 仅限于无状态应用程序)，进入*有状态*应用程序的世界。

由于无服务器已经和亚马逊网络服务(AWS)联系在一起，今年早些时候[我采访了](https://thenewstack.io/theres-a-service-for-that-amazon-web-services-and-serverless-computing/) AWS 高级开发者倡导者 [Nader Dabit](https://twitter.com/dabit3) 。与其陷入定义无服务器意味着什么的困境，Dabit 更愿意将其视为“一种开发哲学”

“云计算的准入门槛真的很高，”他向我解释道，“我认为，由于云计算提供的所有好处，前端开发人员或不喜欢云计算的开发人员都渴望开始使用它。”

他还指出，前端开发人员现在可以更容易地构建“全栈”应用程序，因为像 AWS Lambda 这样的无服务器平台会自动管理后端。

如果说 2020 年是前端开发人员的能力由于无服务器而得到扩展的一年，那么这一年也是无服务器应用程序的定义得到扩展的一年。特别是对国家的管理。

在 AWS Lambda 中，函数是无状态的——这意味着 Lambda 函数中没有以前交互的记录。但是有了云原生厂商 Lightbend 的分支 [Cloudstate](https://cloudstate.io/) ，有状态功能成为可能。Cloudstate 的目标是为它所谓的“无服务器 2.0”建立一个基础。Lightbend 创始人兼首席技术官 Jonas Bonér 解释说，它这样做是为了在无服务器环境中开发通用应用程序，包括在线银行、电子商务购物车和消息传递等有状态应用程序。

[Roper 告诉我](https://thenewstack.io/cloudstate-is-lightbends-attempt-to-define-serverless-2-0/)FaaS 是为开发人员消除后端摩擦的“第一次迭代”,但是“下一次迭代……]将着眼于状态管理，以及如何消除这种摩擦；这样一来，开发人员不仅可以在第一天就高效工作，还可以生产出可扩展的、有弹性的、有弹性的生产就绪代码，并根据他们的需求进行扩展。”

## Jamstack 挑战 WordPress(和世界)

2020 年的另一个趋势是 Jamstack，它实际上是一种无服务器的形式，但在这种情况下，它专门应用于网站和 web 应用程序。Jamstack 中的“jam”指的是 JavaScript、API 和标记；“栈”部分指的是云计算技术。

Jamstack 的目标是将 web 开发的前端与后端分离。在 2020 年期间，它作为网站管理现代化的一种方式得到了大力推广。新一波资金雄厚的创业公司——如 Netlify(创造了这个术语)、Gatsby、Strapi 和 Contentful——将自己定位为 WordPress 和 Drupal 等传统系统的替代品。

“基本上所有传统的单片 CMS 已经真正开始看到这种(前端和后端的)分离是一个现实，这对开发者来说是可取的，” [Netlify](https://www.netlify.com/) 首席执行官[马特·比尔曼](https://twitter.com/biilmann)在 7 月告诉我[。“今天直接使用 WordPress 作为整个堆栈的人，有很多不满的感觉，你会完全落后于你在前端实际可以做的事情。”](https://thenewstack.io/why-netlify-is-tech-agnostic-and-its-role-in-jamstack-development/)

虽然 Jamstack 对开发者很有吸引力，并且很可能提供 Biilmann 概述的好处，但对于内容创作者来说，目前的 JAMstack 服务[远远达不到 WordPress](https://thenewstack.io/gatsbys-content-mesh-and-its-role-in-jamstack/) 的水平……事实上，对于任何不是开发者的人来说也是如此。

8 月份，当我把比尔曼的评论告诉 WordPress 联合创始人[马特·莫楞威格](https://twitter.com/photomatt)时，他[对 Jamstack](https://thenewstack.io/wordpress-co-founder-matt-mullenweg-is-not-a-fan-of-jamstack/) 不屑一顾。他称之为“绝大多数采用它的人的倒退”，并声称“可用性和功能性实际上更低了。”Biilmann 和 Mullenweg [在 Netlify 十月份的虚拟会议 Jamstack Conf 上继续讨论 Jamstack 的优点(或缺点)。Mullenweg 在这场辩论中提出了一些观点，包括 WordPress 现在利用了许多与 Jamstack 相同的前端技术。](https://thenewstack.io/jamstack-vs-wordpress-round-2-the-two-matts-debate/)

“我们有一个漂亮的 REST API，我们有一个 GraphQL API，你可以解耦使用它，还有 Frontity 这样的东西，它允许你使用 React 构建 WordPress [with]无服务器预渲染。有太多的方法来整合它。”

这场辩论[将在 2021 年](https://thenewstack.io/jamstack-vs-wordpress-which-is-the-future-of-web-architecture/)激烈展开，但在 2020 年底有一件事是清楚的:挑战 WordPress 的 Jamstack 初创公司对网络开发者来说是个好消息，因为最终这将为他们提供更多可供选择的工具。

## JavaScript 变得越来越流行——无论是前端还是后端

对于 JavaScript 开发人员来说，2020 年又是忙碌的一年，无论是前端还是后端(或者实际上是整个堆栈)。也许今年最令人印象深刻的专注于 JavaScript 的公司是从开源 JavaScript 框架 [Next.js](https://nextjs.org/) 中分离出来的 [Vercel](https://vercel.com/) 。

事实上，Vercel 将我在这篇文章中讨论的所有“向上堆栈”趋势结合在一起:无服务器、Jamstack 和 JavaScript。联合创始人兼首席执行官 [Guillermo Rauch](https://twitter.com/rauchg) (他创建了 Next.js) [在 7 月份告诉我](https://thenewstack.io/vercels-frontend-and-the-rise-of-the-hybrid-developer/)他的公司给前端开发人员“一个完全托管的无服务器边缘基础设施，这样他们的应用程序或网站就不需要自己进行任何[基础设施]投资，他们可以专注于他们的核心应用程序。”

除了在前端迎合 Next.js 开发人员，Vercel 在后端有一个类似于 Netlify 的“构建和部署”设置；这意味着 Vercel 也可以说是一家 Jamstack 公司。

对于后端 JavaScript 开发人员来说，这也是活跃的一年，他们现在有两个相互竞争的开源 JavaScript 运行时可供选择。现任网站 [Node.js](https://nodejs.org/en/) 于 11 月发布了第 15 版。在 Node.js 一如既往地受欢迎的同时，今年 5 月份推出了一个新贵竞争对手: [Deno](https://deno.land/) ，由 Node.js 的原作者[瑞安·达尔](https://tinyclouds.org/)打造。

Deno 旨在修复 Dahl 认为的 Node.js 的关键弱点，包括安全问题、集中式存储系统(npm)的使用和“高压工具”。

不管 Deno 的技术优势如何，Node.js 仍然非常受欢迎和通用——它甚至与 Jamstack 有联系。正如 Red Hat 的高级软件工程师和 Node.js 技术指导委员会成员贝瑟尼·格里戈斯上个月告诉我的那样，“Node.js 仍然被大量用于构建支持静态页面的微服务，这些静态页面可以使用 Jamstack 之类的方法部署。Node.js 也继续在构成客户端 JavaScript 开发管道的工具中大量使用。

## 向我们发送您的反馈

正如你所看到的，这是这三个“向上堆叠”趋势的繁忙的一年！让我们在社交媒体上知道你今年在大规模开发的快节奏世界中注意到的其他趋势——我是 Twitter 上的 [@ricmac](https://twitter.com/ricmac) ，或者你可以 ping 整个团队 [@thenewstack](https://twitter.com/thenewstack) 。

至于在新的一年里我们可以期待什么，我会在 2021 年的第一篇专栏文章中做一些预测。

亚马逊网络服务、Lightbend 和 Red Hat 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>