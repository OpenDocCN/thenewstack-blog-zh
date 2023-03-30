# JavaScript 的历史及其如何导致 ReactJS

> 原文：<https://thenewstack.io/javascripts-history-and-how-it-led-to-reactjs/>

脸书今天在 ReactJS 上做了一个精彩的演讲，“一个用于构建用户界面的 JavaScript 库”主讲人是来自脸书的 Christopher Chedeau，他简要介绍了 JavaScript 的历史以及脸书为什么要编写 ReactJS。如果您已经使用过 ReactJS，并且至少了解了“如何”编写 ReactJS 的基本知识，那么这个演讲将解释“为什么”

ReactJS 最初是 T2 XHP T3 的一个 JavaScript 端口，是脸书四年前发布的 PHP 版本。XHP 主要关心的是最小化跨站脚本(XSS)攻击。当恶意用户输入旨在对内容查看者造成伤害的内容时，XSS 攻击就变得容易了。典型的攻击媒介是输入嵌入和隐藏 JavaScript(在每个 web 浏览器中运行的语言)的内容，然后使用该嵌入的 JavaScript 窃取信息或以其他方式危害查看内容的用户。XHP 消除了用户提交信息的负担。

但是，XHP 有一个明显的问题:动态 web 应用程序需要多次往返服务器，而 XHP 没有解决这个问题。因此，一名脸书工程师与他的经理协商，让 XHP 使用 JavaScript 进入浏览器，并获得六个月的试用时间。结果是 ReactJS。

如果你多年来一直关注 JavaScript 开发，你会知道“DOM 操纵是昂贵的”已经成为一句口头禅。换句话说，获取 JavaScript 应用程序数据并将其“呈现”到浏览器中是一项成本高昂的操作。因此，令人惊讶的是，ReactJS 是第一个得出这一明显结论的框架:针对 DOM 操作的优化产生了一个快速的库，在这种情况下，这个库支持只需要很少代码的 web 应用程序。ReactJS 的工作方式是在内部存储应用程序的状态，并且只在状态改变时将内容重新呈现到浏览器中(DOM 操作)。当状态发生变化时，通过告诉 ReactJS 来与 ReactJS 进行交互，react js 为您处理应用程序的所有可视变化。这种抽象非常出色。实现类似于 AngularJS，它通过双向数据绑定为您处理 DOM 操作，但是 ReactJS 更进一步，因为它知道什么时候事情发生了变化，什么时候没有，这在大型应用程序中很重要。AngularJS 依赖于脏检查和一个摘要循环，我自己的经验是，AngularJS 接口没有能力智能地确定何时不需要对 DOM 进行更改并跳过 DOM 操作。对于大型应用程序，我相信这会有所不同。

如果你是一个计算机科学家，这个演讲将会很吸引人，因为它记录了构建一个有效的“区分”算法的步骤，这个算法可以理解状态树何时改变。Christopher 展示了初始方法如何具有 O(n^3 算法的复杂性。任何面试过计算机工程职位的人都知道，这是一种高成本的算法，除了微小的数据集之外，任何东西都应该避免使用。演讲者指出，对于一个有 10，000 个 DOM 节点的大型 web 应用程序，这意味着在 1 GHz CPU 上区分树需要 17 分钟。随着 Facebook 工程师对 ReactJS 的进一步研究，他们能够优化算法，首先实现 O(n^2 复杂度，这是一个巨大的改进，然后通过使用包含唯一键的 DOM 元素的哈希映射，能够实现 O(n)复杂度。演讲的这一部分是进入这个可爱的图书馆背后的真正 CS 基础的一个迷人的切入点。

了解用于实现这种算法复杂性的步骤有助于解释为什么该库具有它所具有的接口。ReactJS 依赖于“批处理”步骤和“修剪”步骤来确定要渲染的内容，应用程序可以向这些步骤提供提示，并且理解幕后的算法让我头脑中的灯泡熄灭，因为我最终明白了它为什么以这种方式工作。ReactJS 有一个学习曲线，因为你通常需要在脸书为你建立的视图和模型之间来回整理数据(AngularJS 彻底改变了这一步)。在 ReactJS 中做这件事的 API 更有意义，当你理解为什么它要求你在它做的时候提供提示时，这个谈话对我来说澄清了很多。

本质上，ReactJS 接口不同于其他更具命令性的 JS 库，这意味着您告诉他们直接更改 DOM。Jquery 就是这样。ReactJS 更像是:这里是我的状态，这里是你应该如何解读我的状态，以及它将如何变化。现在，我可以高枕无忧，让 ReactJS 处理昂贵而复杂的任务，让用户在浏览器中看到它。

Christopher 还提到了一个非常令人兴奋的框架，叫做“ [Om](https://github.com/swannodette/om) ”，来自[的 David Nolan](https://github.com/swannodette) 用 ClojureScript 编写，包装了 ReactJS 库。因为 Om 使用不可变的数据结构(Clojure 和 ClojureScript 等衍生工具的一个特性),所以 Om 可以优化 ReactJS 内部的“shouldComponentUpdate”方法，并自动向应用程序提供适当的提示，以便 ReactJS 算法最有效地重新呈现 DOM。在像 Om 这样的应用程序中实现撤销是很简单的，[David 指出](http://swannodette.github.io/2013/12/31/time-travel/)，并要求我们考虑如何在其他 JS 库中实现撤销。ReactJS 是编写有趣的库的坚实基础。

最后，Christopher 谈到了 ReactJS 免费提供的性能优化技术。如果您的应用程序使用 ReactJS，您可以使用 ReactJS 中的[集成性能监控](http://facebook.github.io/react/docs/perf.html)工具来分析应用程序的哪些部分不正确地对应用程序进行了重新呈现。只需在应用程序中调用“perf.printWasted()”，您将看到对应用程序浪费渲染周期的地方的分析，因为 ReactJS 可以判断是否调用了渲染，但没有进行状态更改。然后，您可以提示您的应用程序不应该这样做，从而提高响应速度。我不知道还有什么框架足够聪明，能告诉你代码写错了，该怎么办。

ReactJS 是一种用 JavaScript 构建 web 应用程序的绝妙方法。这个演讲教你“为什么”，这在你学会“如何做”之后很有帮助 OSCON 的视频上传后，非常值得一看。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>