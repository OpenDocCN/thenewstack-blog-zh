# JavaScript 框架 Unpoly 和 HTML 在线趋势

> 原文：<https://thenewstack.io/javascript-framework-unpoly-and-the-html-over-the-wire-trend/>

HTML over-the-wire 已经成为创建 web 应用程序的一种更直接的方式，不需要使用太多的 JavaScript。它的工作原理是通过网络发送 HTML，而不是 JSON。

现在，一个名为 [Unpoly](https://unpoly.com/) 的新“不引人注目的 JavaScript 框架”成为了 [Basecamp 的 HTML over-the-wire 框架](https://thenewstack.io/ruby-on-rails-creator-takes-on-javascript-frameworks-with-hotwire/)、 [Hotwire](https://hotwire.dev/) 的竞争者。Unpoly 承诺“为服务器呈现的 HTML 视图提供快速灵活的前端”Unpoly 的创始人 Henning Koch 向新的 Stack 讲述了为什么像 Unpoly 这样的框架越来越受欢迎。

“代码总是一种负担，探索减少代码的方法总是值得的，”他说。“根据我们的经验，与同类 SPA 相比，Unpoly 让我们用更少的代码构建应用，同时保留了前端的大部分速度和灵活性。对我们来说，这是一个更好的甜蜜点。”

## **un poly 的目的是什么，为什么要开发？**

Koch 将 Unpoly 描述为“一个[不显眼的 JavaScript](https://blog.teamtreehouse.com/unobtrusive-javascript-important) 框架，为服务器呈现的 HTML 视图提供快速灵活的前端。它通过网络发送 HTML，不需要 JSON API。它不依赖于任何后端语言或框架。”

Unpoly 七年前出道，2015 年。这是 Koch 的最新成果，他已经开发网络应用超过 25 年了。“我职业生涯的一半时间是在一家网络开发公司, [Makandra](https://makandra.com/) 担任开发主管，”他解释道。“有了 Unpoly，我可以从我的团队交付的数百个 web 应用程序中汲取经验。当你每年从事几个新项目时，你可以看到模式有机地出现，并从中提取出来。”

使用 Unpoly，您的视图可以做通常在 HTML 中不可能做的事情，例如:

Unpoly 是由 Koch 开发的，因为他注意到用于创建 web 应用程序的代码越来越复杂，而且大多数时候是不必要的。“基本上，当 SPA 框架在 2010 年代初开始流行时，我的团队在一段时间内全力投入 AngularJS。他说:“我们一直在努力克服服务器端渲染的局限性，我们希望 SPA 风格的应用程序能够让我们用更少的复杂代码提供更具雄心的用户界面。”

“当 Angular 在版本 1 和版本 2 之间进行了一次重大的兼容性突破时，我们借此机会回顾了我们过去几年的 SPA 工作，并带着复杂的感情走出来，”Koch 继续说道。“虽然一些应用受益于大量的 JavaScript 方法，但我们对大多数其他应用并不满意，特别是 SPA 方法所需的大量代码和重复。”

Koch 指出，他的团队决定更深入地研究他们的新假设——必须有一种方法来改进他们的 JavaScript 编码，同时简化已经很复杂的语言。

“这促使我们重新审视服务器端渲染和渐进式增强，但这一次我们投入了更多的工作，用结构化的方法来推动极限，而不是堆积如山的不显眼的 JavaScript 片段，”Koch 说。“主要的愿景是:如果有一个 HTML6 规范，并且它都是关于服务器端应用程序的，那么这个规范中会有什么？Unpoly 是一个虚构 HTML6 规范的聚合填充

## 【Unpoly 比 React 如何？

JavaScript 是世界上最流行的编程语言，React 是其领先的库之一。React 最初于 2013 年发布，旨在成为一个帮助开发人员制作用户界面(ui)的库。

根据亨宁·科赫的说法，反应和不礼貌并不完全相反。他们有一些相似之处，但也有一些重要的区别。“这两个框架的共同点是，当用户导航时，它们呈现一个完整的页面，但只有新页面的片段被插入到 DOM 中，其余的被丢弃，”他解释道。“然而，尽管 React 应用程序通常会通过网络调用 JSON API 并在浏览器中呈现 HTML，但 Unpoly 会在服务器上呈现 HTML，我们可以同步访问数据并自由选择编程语言。”

不过，科赫承认，在某些情况下，React 和 SPA 是合适的选择。他接着说，“仍然有一些案例中 SPA 方法大放异彩。例如，我们最近构建了一个实时聊天，其中的消息需要进行端到端的加密。对于一个主要是服务器端的解决方案来说，这可能很难做到，实际上我们最终用 React 构建了聊天组件。我只是不认为这是大多数 web 应用程序的最佳默认设置。”

## **为什么 HTML Over-the-Wire 越来越受欢迎**

几乎总是，[你用的代码越少越好](https://www.freecodecamp.org/news/long-code-vs-short-code/#:~:text=Arguably%2C%20using%20shorter%20lines%20of,than%20many%20lines%20of%20code.)。分散在多行中的较长代码给了 bug 更多的藏身之处。HTML over-the-wire 简化并增加了安全性，而 web 开发人员不必用 JavaScript 编写创建 HTML 的每一行代码，从而节省了时间。

开发人员发现 JavaScript 有时会变得不必要的复杂——有更简单的方法来创建网页和应用程序。正如 Ruby on Rails 和 Hotwire 创建者 David Heinemeier Hansson 所写的那样，“是的，我们需要一点 JavaScript 来使它足够好地与传统单页应用程序提供的保真度相竞争，但是其中的大部分可以由几个小库抽象出来，而不会泄漏到我们编写的应用程序代码中。”

Henning Koch 希望这一新的框架浪潮继续下去，并且更多的人会很快适应它们。他告诉我们:“我想鼓励开发者学习如何在没有大量客户端 JavaScript 的情况下构建网络应用，并检查它是否有助于减少你正在构建的应用中的 JavaScript。”“像 [Unpoly、htmx、Hotwire 或 LiveView](https://htmldriven.dev/html-over-the-wire) 这样的全新一代工具正在尝试构建网络应用的新方法，值得你关注。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>