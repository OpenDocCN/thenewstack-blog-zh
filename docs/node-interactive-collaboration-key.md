# Node.js Interactive 的 TNS 制作者:协作是关键

> 原文：<https://thenewstack.io/node-interactive-collaboration-key/>

随着 [Node.js](https://nodejs.org/en/) 服务器端 JavaScript 平台的使用持续增长，越来越多的组织开始注意如何将它应用到自己的运营中。无论是用来[一点一点地取代单体企业应用](https://thenewstack.io/microservices-node-js/)，还是用来运行[大型 web 应用](http://www.nearform.com/nodecrunch/how-node-js-has-revolutionized-the-mailonline/)，Node 正被用于越来越多种类的工作负载。

上周在波特兰举行的 Node.js 交互式会议上，新的 Stack 主编 Alex Williams 与一些 Node.js 思想领袖进行了交谈，不仅讨论了如何从内部统一 Node 社区，还讨论了 Node.js 的整体未来。

## IBM 开放技术副总裁 Todd Moore

IBM 多年来为 Google V8 JavaScript 引擎做出了贡献，并与 io.js 和 Node.js 社区合作。作为 io.js 和 Node [重新统一](https://thenewstack.io/node-js-long-term-support-ready-enterprise/)的结果，有了一个更强大的代码基础。开发人员不仅可以依赖长期稳定的分支，还可以依赖 36 个月的支持周期，一年发布几个版本。

“节点社区的重新统一是重新走到一起的最好例子，”摩尔说。

Node 已经在整个物联网和企业中得到采用，因为开发人员很快就接受了它的简单性、性能和易于理解。Node.js 是 [Bluemix 上最流行的语言。“我们对世界的看法是，一切都与 API 有关。如何发现和利用它们，无论是人类可读的还是机器可读的，”摩尔说。](http://www.ibm.com/cloud-computing/bluemix/)

与 API 类似，NPM 也有各种各样的软件包。帮助开发人员选择一个包使得将这些分析应用到 IBM 的 API 管理哲学的交叉点变得更加容易。Node 作为前端开发中心的崛起不仅带来了支持基础设施的应用程序，还带来了从整体上简化开发过程的解决方案。

这一点在容器上表现得最为明显。随着越来越多的开发人员和企业开始采用容器技术来大规模部署和管理应用程序，Moore 指出，“容器年”将持续到 2016 年。Node.js 和基于容器的平台有许多相似之处，包括快速启动、轻量级系统占用空间和简单性。随着越来越多的人参与创建和定义作为开发工具的容器标准，容器标准的发展也将继续。

对于开发人员来说，必须有一个平滑的集成路径，不管他们使用的是什么容器服务。云原生计算的采用将新旧技术结合在一起，平台提供了一种可靠的方法来将旧技术重新用作服务平台。这可以在旧的分析系统中看到，这些系统被绑定到 web 前端，以从 web 中挖掘数据，将其与数据库相结合，为客户提供针对其用例定制的解决方案。

“运行 RESTful 接口的传统平台被设置为服务，当提供给人们时，流量很大，使用它的人不知道它在运行什么，”Moore 指出。开发不仅是关于产品背后的底层技术，也是使创造过程稳定、简单和易于采用的工具。

[托德·摩尔，IBM:打造更强大的节点](https://thenewstack.simplecast.com/episodes/todd-moore-ibm-making-a-stronger-node)

## Gaurav Seth，微软首席项目经理主管

在大会上，微软宣布可用于 Node.js 的 JavaScript 引擎 Chakra 即将开源。微软的团队最初在 2008 年开始开发 Chakra，从头开始创建它。自 2010 年发布以来，Chakra 已经从仅在浏览器中使用发展到将 JavaScript 作为一个平台。

随着时间的推移，Chakra 的目标是专注于使引擎有益于开发人员看到的真实世界用例。如今，Chakra 为各种场景提供支持，从具有灵活资源的基于云的服务和应用，到更加受限的物联网环境。

通过将 Chakra 放入开源社区，微软希望将 JavaScript 生态系统推向新的高度。“我们希望人们查看资源，提交请求，将其嵌入到他们的应用程序中，并给我们反馈，”Seth 说。微软不仅希望为 Chakra，也希望为其他 JavaScript 引擎一起帮助推进 Node 生态系统。

Chakra 使用垫片层来解释节点理解的 [V8](https://developers.google.com/v8/?hl=en) 代码。垫片层本质上是 API 的调用重路由器。“起点是 IoT。Chakra 是对 Node 的支持，可以在任何地方使用，通过 API 帮助开发人员控制它必须在其中工作的源代码约束，”Seth 说。

[Gaurav Seth，微软:Chakra，开发 JavaScript 引擎](https://thenewstack.simplecast.com/episodes/gaurav-seth-microsoft-chakra-developing-a-javascript-engine)

## 钱璐·迈丁，nearForm 公司首席执行官

位于都柏林的咨询公司 nearForm 很早就采用了 Node。从 2012 年开始，nearForm 首席执行官钱璐·ómaidín 亲眼目睹了试图进入 Node.js 的艰难，“传统公司不感兴趣。[他们会说]“服务器端 JavaScript？不。这太荒谬了。我们不这样做，”ómaidín 指出。

当 nearForm 开始时，团队努力使用 Node 构建软件。最初使用 monolith JavaScript 应用程序令人望而生畏。微服务架构帮助了我们。微服务特别适合分布式团队，因为这种工作模式非常适合全天处理应用程序的小型团队。

2013 年，当 PayPal 和沃尔玛宣布他们正在采用这种语言来重组他们的业务，以便继续以世界上一些最大的公司所要求的速度创新时，Node 成为了焦点。Node 为公司提供了一种快速创新的方式，迅速获得了整个开发人员社区的关注，平息了异议，为 Node 今天的发展铺平了道路。NearForm 在他们自己的办公室看到了这一点，从 2 人的团队到分散在全球各地的 70 多名员工的分布式团队。

NearForm 为节点社区提供了他们所谓的“[节点日](http://www.nearform.com/node-events/)”，以帮助将企业和开发人员社区聚集在一起进行交互式讨论。2016 年，nearForm 将举办十场节点日活动，从 2016 年 2 月开始在伦敦举行，然后是纽约，然后是西雅图。

节点日是免费的，讨论根据举办活动的城市量身定制。Maidí说:“这是 Node 的开发者福音，不仅要与社区中的其他人讨论 Node 的当前状态，还要讨论该技术的未来。”NearForm 还提供了[微服务日](http://www.nearform.com/microservices-events/)，吸引了希望快速将其产品环境转变为更加数字化的地形的企业。2016 年有四个近形式微服务日，分别在伦敦、纽约、班加罗尔，第四个地点尚未公布。

在进行任何新的努力时，合作是至关重要的。在 Node Interactive，io.js 和 Node.js 团队联合起来进一步改善整个社区的未来。随着越来越多的企业将 Node 引入企业，JavaScript 程序员之间跨越鸿沟的持续贡献将推动该语言向前发展，并进入一个因其众多产品而接受它的世界。

[钱璐ó' maidín，near form:Node Interactive](https://thenewstack.simplecast.com/episodes/cian-omaidin-nearform-node-interactive)

要订阅新 Stack Makers 播客或查看其他剧集，请访问新 Stack 的播客部分[。](https://thenewstack.io/podcasts/)

IBM 是新堆栈的赞助商。

专题图片:波特兰[街头艺术](https://www.instagram.com/p/_HfbHVQ8_c/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>