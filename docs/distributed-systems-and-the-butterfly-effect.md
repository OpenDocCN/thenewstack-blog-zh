# 分布式系统和蝴蝶效应

> 原文：<https://thenewstack.io/distributed-systems-and-the-butterfly-effect/>

已故科幻作家雷·布雷德伯里的经典短篇小说《雷霆之声》讲述了一群猎人穿越时空，希望杀死霸王龙恐龙的故事。早在《T2》、《侏罗纪公园》(Jurassic Park)和《T3》系列电影问世几十年前，允许人类与恐龙互动的愚蠢的技术创新就不出所料地出现了问题。然而，《雷霆之声》的主题与其说是关于满足人类对可怕野兽的典型好奇心的风险，不如说是关于我们的行为是如何相互联系的。例如，布拉德伯里描绘了时光倒流和踩到一只蝴蝶这样的偶然事件如何引发连锁反应，最终导致未来的灾难性事件。

[吉列尔莫·劳赫——如何杀死一只蝴蝶就能搞垮一个网络](https://thenewstack.simplecast.com/episodes/guillermo-rauch-how-killing-a-butterfly-can-bring-down-a-network)

在当今由 Kubernetes 和容器编排技术构建的分布式系统构成的 IT 世界中，应用程序的深度以及它们的分布式程度已经开始显现。Leslie Lamport 的名言[反映了这种非常分布式和互联的基础设施的影响之一:](https://www.microsoft.com/en-us/research/publication/distribution/)“在分布式系统中，您甚至不知道存在的一台计算机的故障会导致您自己的计算机无法使用。”换句话说，杀死一只蝴蝶可能不会导致网络崩溃，但话说回来，谁知道任何不幸或错误会产生什么影响，无论是服务受阻还是咖啡溅到云网络提供商的数据服务器上。

在这个最新的[新堆栈制造商](https://thenewstack.io/podcasts/makers)播客中， [Guillermo Rauch](https://www.linkedin.com/in/guillermo-rauch-b834b917b) ，托管服务 [Zeit](https://zeit.co/) 的创始人，React 框架 [Next.js](https://nextjs.org/) 的共同创建者，说他今天的大部分工作都涉及网络同步。更具体地说，他描述了他在状态方面的工作，以及它如何在网络上同步，以及这如何影响他为应用程序创建策略结构。他还描述了他的雄心，即帮助改进数据一致性模型的连贯和一致系统的基础。

Rauch 说，互连性的主题也是“我们如何从服务架构的角度以及前端应用程序的背景下更深入地思考如何构建弹性系统的一个很好的开端”。

具体到 Next.js 的发展，JavaScript 库仍然是一个有趣的工具，“但我们真正看到的是，随着编写前端应用程序的架构 [JAMstack](https://thenewstack.io/the-sweetness-of-jamstack-javascript-apis-and-markup/) 的兴起。劳奇说:“js 由一个全球网络分发，该网络服务于设备，然后在设备上运行，查询一个 API。

至于微服务，它们是“健谈的”，劳赫说。微服务“实际上对可用性非常不利。”这是因为即使微服务之间非常微小的连接丢失事件也会导致网络性能低于标准。“因此，我们着手做的事情之一就是说‘好吧，让我们打破这种信息技术聊天链，转向网络，因为这就是 Leslie Lamport 所说的分布式系统的复杂性之一。它们是介于两者之间的所有这些计算机，以及介于两者之间的所有这些会损害您的可用性的网络人工制品。"

TNS 出版商亚历克斯·威廉姆斯主持了这个播客。

照片由 Kristel Hayes 在 Unsplash 上拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>