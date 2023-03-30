# htmx:JavaScript 世界中实现交互性的 HTML 方法

> 原文：<https://thenewstack.io/htmx-html-approach-to-interactivity-in-a-javascript-world/>

围绕多页面应用程序(MPAs)或传统网站与单页面应用程序(spa)或使用 React 等前端 JavaScript 框架构建的 web 应用程序的争论已经持续了好几年。一个名为 [htmx](https://htmx.org/) 的新 HTML 扩展框架，被描述为“一个允许你直接从 HTML 访问现代浏览器特性的库，而不是使用 javascript”，希望将 web 开发从 SPA 方法中转移出来。

最近，[Rich Harris](https://www.nytimes.com/by/rich-harris),[苗条框架](https://svelte.dev/)的创建者发布了一个视频，询问[单页应用是否已经毁了网络](https://www.youtube.com/watch?v=860d8usGC0o)？在视频中，哈里斯研究了双方的利弊，最终确定前进的道路是两种方法都用一点——通过他所谓的“过渡应用程序”，这是 SPA 和 MPA 技术的混合。

[https://www.youtube.com/embed/860d8usGC0o?feature=oembed](https://www.youtube.com/embed/860d8usGC0o?feature=oembed)

视频

在对这个视频的回应中，htmx 的创建者 Carson Gross 认为，Harris 提出的大多数对 MPAs 有问题的例子实际上都可以用 htmx 解决。然而，除了提供 htmx 作为解决方案之外，Gross 还认为 Harris 在研究 spa 的缺点时忽略了一个大问题:复杂性。

“不幸的是，有一个话题哈里斯先生没有讨论，我们认为这可能是因为他没有看到，”格罗斯在他的回应中写道。“他是一名 JavaScript 开发人员，对这种语言充满热情，并且在前端框架的工程文化中游刃有余，所以当前 JavaScript 前端开发的复杂性对他来说似乎很自然。然而，对于我们中的许多人来说，JavaScript 生态系统简直是过于复杂了。事实上，考虑到大多数 web 应用程序的需求，这很可笑。”

## htmx 是什么，为什么有用？

近十年来，Gross 一直试图解决前端 web 开发中的复杂性问题，早在 2013 年就首次创建了 [intercooler.js](https://intercoolerjs.org/) 替代前端库，其口号是“带属性的 AJAX:没有必要变得复杂”。最近，intercooler.js 打出了 2.0 版本，变成了 htmx，GithHub 的描述是“允许你直接在 HTML 中访问 [AJAX](https://htmx.org/docs#ajax) 、 [CSS Transitions](https://htmx.org/docs#css_transitions) 、 [WebSockets](https://htmx.org/docs#websockets) 和[服务器发送事件](https://htmx.org/docs#sse)，使用[属性](https://htmx.org/reference#attributes)，这样你就可以用超文本的[简单性](https://en.wikipedia.org/wiki/HATEOAS)和[威力](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)构建[现代用户界面](https://htmx.org/examples)。

> “这个概念是，让我们使用原始的网络模型来构建网络应用程序，但让 HTML 变得更强大。”

–卡森·格罗斯，htmx 的创造者

更简单地说，Gross 将 htmx 描述为试图“停留在 web 的原始模型中，使用 HTML 和超媒体概念，而不是要求开发人员编写大量的 JavaScript。”对于这个讨论来说，有点有趣的是，htmx 是一个 JavaScript 库——但是为了与这种简单的方法保持一致，它是无依赖性的，使用 htmx 的前端开发人员不需要编写 JavaScript 来实现类似的功能。相反，它们使用 HTML 标签中的附加属性来实现动态内容和更新。在该项目的描述中，Gross 写道，他创建 htmx 是为了解决传统 HTML 的四个基本问题:

*   为什么只有 [< a >](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) 和 [<表单>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) 能够发出 HTTP 请求？
*   为什么只有[点击](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event) & [提交](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit_event)事件才会触发它们？
*   为什么只有[获得](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) & [发布](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)的方法是[可用](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)？
*   为什么只能更换整个屏幕？

“通过去除这些任意的约束，htmx 使 HTML 成为一种超文本，”他总结道。Htmx 通过直接从 HTML 发出 AJAX(异步 JavaScript 和 XML)请求来实现这一点，使用类似于 JavaScript 的事件——比如鼠标悬停或滚动行为。使用 htmx，开发人员可以创建 UI 特性，如[无限滚动](https://htmx.org/examples/infinite-scroll)、[进度条](https://htmx.org/examples/progress-bar)、[确认对话框](https://htmx.org/examples/dialogs)、[内联编辑](https://htmx.org/examples/click-to-edit/)，以及其他“用最少的 HTML 和样式在 htmx 中实现的 UX 模式”的[变种](https://htmx.org/examples/)。

相比之下，React 和 Vue.js 等 JavaScript 框架通过使用 JavaScript 向服务器发出请求来创建 spa，然后服务器使用 JSON (JavaScript 对象表示法)数据格式发送数据，并再次使用 JavaScript 来处理数据和更新用户界面。

## 让 HTML 更强大

“我认为现在的很多 JavaScript 框架，你几乎是在浏览器中构建一个胖客户端，”Gross 在接受 New Stack 采访时说。“你只是把浏览器当作虚拟机来使用。显然，在那个世界里，你可以做更多的事情，但也有更多的复杂性。”

Gross 认为 htmx 可以解决很多网站的这种复杂性——甚至像脸书或 Twitter 这样的网站,“大部分是文本和图片”。

“这个概念是，让我们使用原始的网络模型来构建网络应用程序，但是让 HTML 变得更加强大，”Gross 继续说道。“如果我们让 HTML 变得更强大，也许我们就不必忍受这些 JavaScript 前端框架带来的所有复杂性，因为当你用 JavaScript 编写用户界面时，你会编写大量代码。管理起来非常复杂。Htmx 实际上是一种倒退，试图说，“好吧，与其沿着 JavaScript 这条路走下去，用 JavaScript 在浏览器中构建大型应用程序，不如让 HTML 更强大，看看我们可以通过让 HTML 作为超文本、超媒体、交换 HTML 的东西变得更强大来获得多少交互性。”"

虽然他预计 htmx 不会很快从 React 的统治地位上分一杯羹，但 Gross 说，鉴于最近对一切都采用 JavaScript 的犹豫，他希望它能找到更多的立足点。

“这可以归结为超媒体和以 JavaScript 为中心的方法，”他说。“这两种方法都是构建 web 应用程序的合理方法——目前，业界非常倾向于后者。我希望至少改变一点点，并证明事实上超媒体应用程序可以实现许多相当复杂的 UI 模式，而不需要复杂的 JavaScript 框架。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>