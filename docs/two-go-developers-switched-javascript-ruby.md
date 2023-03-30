# 两个从 JavaScript 和 Ruby 转行的 Go 开发者

> 原文：<https://thenewstack.io/two-go-developers-switched-javascript-ruby/>

有了无数种可用的编程语言，开发人员在选择一种语言时经常面临艰难的决定，这种语言在许多因素之间达到最佳平衡，这些因素包括兼容性和易用性。在过去的几年中，许多开发人员正在从更成熟的语言转向相对较新的语言:Google 的 Go——一种使用类似于 c 语言语法的静态类型语言。正如我们之前听到的，这些程序员公开谈论他们为什么选择 Go:因为它更好的性能、简单性、同时执行多个计算的能力，以及其他原因。

## 为什么一个前端开发人员选择使用 JavaScript

在上周科罗拉多州丹佛市 GopherCon India 的一次演讲中，总部位于 T2 的前端开发人员 Julia Poladsky 阐述了为什么 Go 是比 JavaScript 更好的设计语言。

[朱莉娅·波拉斯基:去做前端开发者](https://thenewstack.simplecast.com/episodes/julia-poladsky-go-for-front-end-developers)

Poladsky 解释说，尽管开始使用 JavaScript 并为节点或前端应用程序编写服务端代码很容易，但在即将到来的版本 ES6 和 ES7 中，随着新语言特性的增加，JavaScript 将受到限制。

JavaScript 的一些显著特性是它可以轻松处理函数、对象文字和动态类型。另一方面，JavaScript 已经很容易地声明了全局，所有的东西都被转储到同一个全局空间中，这可能很难区分，所有这些都可能使新手开发人员出错。

Poladsky 认为 Go 是编程语言发展的下一步。Go 拥有并构建了 JavaScript 的所有主要优点，而且更加简单。比如和 JavaScript 一样，Go 的函数也是一等公民。Go 中有词法作用域，但它包括块。你也可以用 Go 做闭包，在不同的类型上实现 create 方法。但由于 Go 是静态类型的，所以有点不同:它支持类型参数、类型返回和多重返回。

[![0554f40](img/d25516f5fcdd55e66a9c88eaaf1c7e50.png)](https://thenewstack.io/wp-content/uploads/2015/02/0554f40.jpg)

其他值得注意的相似之处是 JavaScript 的异步功能与 Go 的并发性相比，这很容易理解。与其他静态类型语言不同，Go 是“垃圾收集”的——不太担心内存管理，而且根据 Poladsky 的说法，Go 具有“良好的错误处理能力”

另一个显著的区别是，Go 没有 JavaScript 的无限参数，而是有一个叫做“splats”的东西，它可能在 JavaScript ES6 中实现。此外，与 JavaScript 相比，Go 编译器的错误初看起来可能令人生畏，但它有助于开发人员更彻底地学习和理解这种语言。JavaScript 有原型继承，而 Go 有组合，可以用接口实现。Go 的构成是“安全、舒适和明确的”，因为它可以解决经典继承无法解决的复杂关系。Go 简单易懂的本质最终迫使开发人员编写清晰、客观、易于维护的显式代码，并让开发人员确切地知道代码在做什么。

## 一个 Rubyist 从 Ruby 到 Go 的旅程

在 GopherCon India 的第二次演讲中，Pivotal Labs 的 Mike Gehard 讲述了他从几乎只使用 Ruby 编程到转向 Go 的历程，以及他根据自己学习一门新语言的语法和习惯用法的经验，给出的关于这种转变的建议。

[迈克·格哈德，Pivotal:从 Ruby 到 Go 的旅程](https://thenewstack.simplecast.com/episodes/mike-gehard-pivotal-a-journey-from-ruby-to-go)

格哈特的建议是学习一门语言的词汇和句法——与学习一门语言的习语相比，这两者都相对容易。他指出，与 Go 的规范相比，Ruby 的规范文档要复杂得多，也难以理解，而 Go 的规范目前只有 50 页左右。

Gehard 解释说，了解习惯用法是在围棋中有效交流的关键。习语是一种特殊的语法，或者说是一种特性。Gehard 认为，编写习惯用法的代码会使语言的使用变得更容易:如果你知道习惯用法是什么样的，你就可以更有效地编写代码，并且让别人更容易理解你的代码。

[![2deb3d5](img/f48b07727422dfc7b05a2b44e4e11c8d.png)](https://thenewstack.io/wp-content/uploads/2015/02/2deb3d5.jpg)

来自 Ruby 的 Gehard 建议从头开始，不要对一门新语言应该如何编写有先入之见，因为 Go 不同于 Ruby、Java 和 JavaScript 等面向对象的编程语言。围棋没有传承；它使用复合，而 Go 有一个轻量级的类型层次结构，不像 Ruby。格哈德指的是[内森·杨曼的](http://nathany.com/)篇围棋文章:[这里](http://nathany.com/why-go/)和[这里](http://nathany.com/good/)。

在 Ruby 中，从不定义或传递接口，但在 Go 中，一切都有接口。Go 有两个接口:阅读器和关闭器。如果您希望两者都使用，那么您可以组合和重用接口。另一个有趣的 Go 实验:不写对象，而是写结构和操作结构的函数。不要把方法附加到你的结构上，看看会发生什么——实验是学习语言和获得乐趣的关键。

Gehard 建议研究并发模型，但在 Go 中也要谨慎使用并发。最后，Gehard 给出了一些其他花絮:性能不是成本收益分析的唯一因素，但 Go 的性能领先 Ruby 好几光年；Go 对 web apps 不好，对 API 好；而且 Go 的类型系统比 JavaScript 的要轻很多。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>