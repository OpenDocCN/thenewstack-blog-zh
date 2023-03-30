# Box 打开 T3，这是一个适用于大规模应用的 JavaScript 规则系统

> 原文：<https://thenewstack.io/box-opens-t3-a-system-of-rules-applied-to-javascript-for-large-scale-apps/>

“现在 JavaScript 的热门词汇是 MVC，”Nicholas Zakas 说，他是文件共享服务 Box 的前端工程师，在 2012 年由他的公司赞助的一次演讲中。“‘哦，你知道 JavaScript 架构吗？’嗯，我是做 MVC 的，所以很明显我必须了解 JavaScript 架构，”Zakas 继续说道，模仿着一段人们很容易无意中听到的对话。

“这一切都很好，除了没有告诉你整个故事，”他继续说道。

这是一个 JavaScript 应用框架的想法的发布——不是一个库，而是他希望能为模块化 JavaScript 编程提供一些基础结构和可扩展性的东西。这个想法在上周取得了更大的成果，Box 宣布开源发布 [T3](http://t3js.org/) ，这是一个旨在提供网页组件划分的框架，使它们每个都可以由后端应用程序寻址。

(不要将 Box 的 T3 框架与用于构建 Joomla CMS 扩展的 [T3 Joomla 框架](http://www.t3-framework.org/whats-new)混淆。)

## 可伸缩性的另一面

当我们在这些页面中谈论可伸缩性时，通常是在云中部署容器化的应用程序，并围绕微服务重新构建整体应用程序。后端 JavaScript，如 Node.js 及其曾经的竞争对手 io.js，已经结合这些目标进行了讨论，因为 JavaScript 已经努力采用更正式的结构。

但这不是后端故事。

可伸缩性的另一方面是后端服务器如何与浏览器内应用程序的文档对象模型中维护的无数图形组件进行通信的故事，无论它可以扩展到什么程度。

适用于后端可伸缩性的原则同样适用于前端的 T3 框架。想想微服务架构如何促进功能之间的无状态。有了 T3，新的抽象支持松散耦合组件的建立，这些组件可以更容易地被重写和替换。

这就是近年来 Box 如何成为一个更加渐进的系统，稳步渐进地实现变化，包括它在浏览器和 Web 应用程序中的行为。

“许多其他的 JavaScript 框架，”上周发布的开源 T3 文档这样写道，“假设你想在客户端处理所有的 HTML 渲染。T3 假设 HTML 内容已经存在，只允许组件与该内容交互。我们相信渐进式增强对于大规模应用程序来说是一种更强大的方法。”

这是我 20 年前写关于 Visual Basic 的书时宣称的理想之一(是的，你会注意到我当时是如何把自己的名字弄得一团糟):如果你构建可以响应任何事情的模块，那么你就不需要复杂的数据结构来让这些模块相互交流每个“任何事情”可能是什么。

## 行为作为一个单独的东西

T3 本身不是一种语言，而是一个应用于 JavaScript 的规则系统，由 T3 客户端组件执行。一个模块成为一个独立的功能单元。而且，正如最初的 Visual Basic 在恐龙漫游地球时所尝试的那样，每个 T3 模块都是一个可插拔、可重用、易于复制的单元。

但是这里是 Zakas 的想法将 T3 带入一些新方向的地方。在 20 世纪 90 年代和 21 世纪初的大多数面向对象编程中，模块是由其行为定义的。在 T3 中，模块和行为是两个独立的功能类别。网页上的某个东西是什么，以及网页上未命名的某个东西可以做的离散动作，都是单独定义的，然后再相互关联。

我想把一个行为称为一种模块，但是 Zakas 会纠正我。行为和模块的区别在于，前者描述的是一个动作或一组动作，而后者描述的是一个事物。动作一旦被定义，就可能被事件触发。在 JavaScript 中，使用方法来响应事件，例如 **onClick** 。在 T3 中，同样的格式 **onEvent** 响应行为的子句中定义的事件。

一个标准模块有一个 **init** 方法，可以自我启动。行为子句不使用(Zakas 不使用“子句”这个词，但我会使用，因为对象需要是某物)。这一点非常重要，因为执行永远不会在模块之间传递，也不会在模块和行为之间传递。这就是 Zakas 的松耦合规则是如何实施的:模块之间的通信仅限于显式消息，这些消息通过每个人都听的 **messages** 数组相互广播。

T3 文档中写道:“消息不是关于应该发生什么的命令。”。例如， **makerequest** 不是合适的消息名称。消息旨在共享关于已经发生的事情的信息，而不是将要发生的事情。这使得其他模块能够做出适当的反应。”

所以页面的 **init** 方法是一切开始的地方。纯粹的可重用代码是为 T3 调用的服务保留的，因此模块可以调用属于它们相关联的服务的可重用功能。但是模块和服务之间的关系是严格的数学关系——或者，正如我在一次会议上看到的一位开发人员所描述的，“柏拉图式的”

## 是正确的焦点吗？

关于 T3，没有任何东西会将 JavaScript 弯曲或扭曲成它不应该成为的东西，并且可以想象它应该同样适用于 JS 的未来版本，比如 ES6。

在上周发给黑客新闻的一条消息中，独立的[软件顾问伊万·布拉诺夫](http://ivanbulanov.com/)写道，“对于一个变化来说，看到一个纯架构的 JS 框架是很好的。它解决了我称之为 GUI 开发的一个相当重要的问题:把什么放在哪里。它还强加了访问规则:谁打电话给谁。不像 Ember 或 Angular 这样包罗万象的解决方案，它只专注于此，允许开发人员自己选择其他部分。”

并非所有黑客新闻的反应都是积极的。“我很感激 Box 免费发布了 T3，如果人们想使用它，那太好了。“没有人被迫使用它，”用户 DigitalSea 写道，“但正是在这种情况下，我忍不住想知道是否应该花更多的精力为现有的开源项目做贡献？”

尼古拉斯·扎卡斯(Nicholas Zakas)上周写道:“我们发现，我们构建的几乎所有东西都适合这三个组成部分(服务、模块和行为)中的一个，混合和匹配它们的能力足以创建许多不同类型的用户体验。此外，如果我们愿意，除了 T3 之外，没有什么可以阻止我们使用主干网、反应网或其他框架。T3 确实有助于更好地组织单个代码，同时允许我们的工程师用他们想要的任何东西拼凑出一个完整的客户端堆栈。”

几年前，我曾说过，当 JavaScript 无法无天、缺乏结构、无法大规模管理时，它就会毁灭。事实证明，与关注一种全新的客户端语言相比，更关注给 JS 赋予结构，它最明显的缺失很快成为它最大的优势。

通过 Flickr Creative Commons 发布特色图片[。](https://www.flickr.com/photos/jdub1980/8671736602/in/photolist-edhVb3-71vhoa-2UWhVJ-2PifAz-2Wx1sb-3KaK3-fdF838-2DtSz-iQ8pKS-93HDxZ-83Hxvk-dvhQgt-r6YMmE-q9b1sm-ppMfaa-8rdvNF-87oAqq-ed6kDh-d4iPrh-e5kcT2-oZc761-7zPoxb-rsN7Ft-syMTB-9ezxAi-cPedsh-keLDPc-aKsPbp-q79BLu-pTE1qh-qPK7GJ-6Vinhb-8RwZpQ-2WsKd2-88YfEt-e5kbrh-7BhG9Q-oGRPp-r4s28o-qQdY8A-rgXZF8-nHXfBY-2Wx687-99YSxV-pVmp3Q-81Tpo6-rHQsed-pFYfWF-qn2VBU-r77JQk)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>