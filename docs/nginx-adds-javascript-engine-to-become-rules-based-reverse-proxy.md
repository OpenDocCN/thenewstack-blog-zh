# NGINX 增加 JavaScript 引擎成为基于规则的反向代理

> 原文：<https://thenewstack.io/nginx-adds-javascript-engine-to-become-rules-based-reverse-proxy/>

在 2014 年 10 月接受 InfoWorld 采访时，NGINX Inc .创始人伊戈尔·塞索耶夫抛出了一颗炸弹，如果当时有人知道如何引爆它的话:NGINX——本质上是一个代理服务器，但作为一个高级负载平衡器，它很快成为微服务应用程序的关键组件——将利用 JavaScript 做一些大事情。当 11 月，它生产了可以与 Node.js 一起使用的配置[时，人们认为这一定是塞索耶夫所说的。](https://www.nginx.com/blog/nginx-nodejs-websockets-socketio/)

不完全是。炸弹在周三正式爆炸，因为该公司透露，它正在开发自己的 JavaScript 引擎(而不是借用别人的引擎，这是一个选项)，使基础设施开发商能够部署复杂的后端逻辑，将请求路由到他们的服务器。这个引擎将被部署在 NGINX，本周在旧金山梅森堡中心举行的[会议上，NGINX 将其描述为一种新的逻辑驱动服务器的“工作原型”。](https://www.nginx.com/nginxconf/)

## 短暂的解释者

NGINX Inc .的营销主管欧文加勒特(Owen Garrett)在接受 New Stack 采访时表示:“它基于我们创造的全新 JavaScript 引擎，而且我们是开源的。”。

“我们研究了目前可用的 JavaScript 引擎——比如谷歌 V8、[Mozilla] SpiderMonkey 和苹果的 JavaScriptCore，”Garrett 继续说道。

> “但它们都是为在网络浏览器中工作而设计的。这种设计不太适合 NGINX，因为我们要处理成千上万的连接。我们想要一个 JavaScript 虚拟机，我们可以非常快速地启动和停止，以网页浏览器虚拟机无法设计的方式抢先和控制。”

很容易想象这样一个场景:一个单一的、集中式的 JavaScript 引擎扮演着一个庞大的并行连接帝国的监督者角色。因为这很容易，这就是你需要抛弃的模式。

想象一个模型，其中每个连接都由自己的紧密耦合的 JavaScript VM 进行编组，每个 NGINX JS VM 专注于自己的小任务。Garrett 说，这样可以将每个虚拟机精简到极小的规模。这与基于 web 浏览器的 JavaScript 引擎不同，后者的任务是处理多个连接，同时为本地客户端处理垃圾收集(内存清理)作业。

“我们的要求不是要有一个单一的、整体的 JavaScript 虚拟机来处理大量的连接和连接之间的切换，”Garrett 解释说，“而是要有一个非常小的、轻量级的 JavaScript 虚拟机，我们可以在需要时为连接启动，我们可以先发制人——这意味着我们可以把它放在一边，去处理其他操作——我们可以重新唤醒，然后当这个短暂的操作完成并且连接完成时，我们就可以扔掉 JavaScript 虚拟机。”

它是一个短暂的解释器，它的生命周期正好是它所监控的连接的生命周期。

虽然从技术上讲，NGINX 语言(称为 nginScript)是基于 JavaScript 的，但它实际上是 ECMAScript 6 的子集，目的是在未来的修订中扩展该子集。由于每个虚拟机都有自己有限的范围，理论上，连接本身是无限可扩展的。

目前，VM“监听”事件的方式与 web 浏览器的 VM 类似，但是使用了更小的内存模型。但 NGINX Inc .的营销负责人说，这些活动的深度不必过分。

> “我们对开发者隐瞒了很多内部的复杂性，”他说。

“开发者不需要知道由数据包触发的网络事件。我们的 JavaScript 调度将对开发人员隐藏这一点，因此他或她将能够使用 JavaScript 语法编写非常简单的线性脚本，并且他们不必担心调度事件和不同连接之间的交互。我们希望从开发者那里抽象出所有这些。”

## 简单的逻辑

NGINX 到目前为止的工作是终止传入的 IP 流量(充当目的地点)，检查数据包，在必要的地方重写它们，并应用认证规则和内容过滤器。“在我们的预览版中，”Garrett 继续说道，“你可以在每个阶段添加 JavaScript 逻辑，这样你就可以用 JavaScript 决策增强 NGINX 的内置功能。”

他举了一个例子，NGINX 在处理流量时有机会重写请求。首先，重定向被发送到不同的位置。然后，请求在被代理之前被修改。(对于 Apache，有一种方法可以使用它的。HTAccess 配置文件，NGINX 不支持。但是从历史上看，[基础设施开发人员一直避免使用 Apache 的规则处理程序](http://www.nginxtips.com/why-doesnt-nginx-support-htaccess-files/),因为它的性能很差。)

Garrett 说，有了 nginScript，开发人员将能够编写复杂的重写规则，每个规则都可以扫描大型数据库表。登录的用户可能有一个与其相关联的 cookie。如果 cookie 存在，脚本可能希望将重写请求定向到一个不同的 URL，而不是在这样的 cookie 尚不存在时保留的 URL。也许登录的用户应该被重定向到主页。

“所有这些功能都可以用 nginScript 以非常简单的方式实现，”他承诺道。

> “这是一种非常富于表现力的语言。如果你能清楚地表达你想对流量做什么，那么用 JavaScript 实现它应该是可能的，因为它是这类规则的一个非常灵活的基础。”

目前，NGINX 的 JavaScript 版本还不能与专业 JS 开发人员选择的 ide 集成。Owen Garrett 在我们的讨论中多次重申，NGINX Inc .对构建“JavaScript 服务器”不感兴趣，NGINX 也不应该被描绘成一个拥有自己的 JS 引擎的服务器。更确切地说，nginScript 是为单点解决方案和非常简单的脚本逻辑而设计的。

“但是开发者仍然需要像以前一样，使用一套独立的工具来构建他们的大部分应用程序，”他继续说道。NGINX 是交付应用程序的底层平台，nginScript 允许您以比现在更灵活、更具表现力的方式定制和配置该平台。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>