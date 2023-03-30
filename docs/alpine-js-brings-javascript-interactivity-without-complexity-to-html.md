# Alpine.js 为 HTML 带来了不复杂的 JavaScript 交互性

> 原文：<https://thenewstack.io/alpine-js-brings-javascript-interactivity-without-complexity-to-html/>

在去年的[阿尔卑斯日会议](https://alpineday.com/)上，当[凯莱布·波尔齐奥](https://calebporzio.com/) [讲述](https://www.youtube.com/watch?v=BaQJCyKgMjA)他是如何建立 [Alpine.js](https://alpinejs.dev/) 的时候，他用攀登和下降一座“JavaScript 山”来描述它

他说，在他开发生涯的早期，他从 jQuery 开始攀登 JavaScript 的高峰，当他开始用 Laravel 和 Vue.js 构建单页面应用程序时，他达到了顶峰。然而，JavaScript 的顶峰并不全是软糖和彩虹，他在创建看似简单的功能时遇到了问题。

“这促使我走下 JavaScript 山，我开始真正质疑，比如，在前端创建一个完整的应用程序，在后端创建一个完整的应用程序，我做了多少工作，”波尔齐奥说，他解释说，他后来决定挑战自己，完全不用 JavaScript 来创建应用程序。很快就流产了。

## 零 JavaScript？

“你能用零 JavaScript 做这件事吗？”他问。“答案是否定的，不负责任，因为你最终会因为简单的，比如下拉菜单，而做出疯狂的事情。”

正是在这一点上，他想到了 Alpine.js 的想法，这是一个将 JavaScript 行为直接放在您的标记中的极简框架，它将提供 Vue.js 的一些交互性，而没有任何复杂性。

“Alpine 是现代的 jQuery，这是我的愿景，”Porzio 在一次采访中解释道。“当我开始从事 web 开发时，jQuery 就是你在前端添加的东西。你的整个前端不是由前端框架驱动的，而是由类似 Rails 的东西驱动的。我仍然喜欢用这种方式编写 web 应用程序。我兜了一圈，完成了整个 SPA 项目，本身没有任何问题，但对于许多使用案例来说，它实在太复杂了。”

虽然像 jQuery 这样的技术对于增加交互性来说非常好，但对于 Porzio 的口味来说，它太强制性和手工化了。他说他喜欢 React、Vue 和 Angular 等框架的声明性和反应性，所以他在头脑中创造了 Alpine。同时，这些框架将功能和设计分离到许多不同的文件中，这使得很难找到在哪里发生了什么。

“我希望它就在模板中，而不是维护所有这些不同的文件，不得不组织我的前端逻辑，并真正思考这些东西，”Porzio 说。“有时候简单的说，‘当这个按钮被点击时，在按钮本身上，设置 open 为 true，然后在你想要打开的 div 上，显示 open 是否为 true。’"

## 对复杂性的抵制

Alpine 用尽可能少的代码完成了所有这些工作——只有 15 个属性、6 个特性和两个方法——并且开始使用起来就像在 HTML 文件的标题中插入一个单独的

“他们都依赖于这种概念，伪造一个活的网站，伪造一个 SPA，而不是实际上所有都生活在前端，所有都生活在后端，前端只是调用后端获得新的 HTML 并将其交换到页面中，”波尔齐奥说。“Alpine 的出发点是，‘我们需要一些用于模态、标签和下拉菜单的东西，因为你不应该为这些东西去访问服务器。’"

通过这种方式，Alpine 发现自己处于许多大型 JavaScript 前端框架和它们的后端、有线对等物之间的中间地带。Alpine 完全以 JavaScript 框架的形式存在于前端，但完全专注于简单性和轻量级。为了进一步保持这些理想，Porzio 去年增加了创建插件的能力。

“像 React 或 Vue 这样的东西，它们可以给核心添加更多的功能，因为有这些复杂的构建步骤，所以你的浏览器只装载你使用的东西，”Porzio 说。

## 保持苗条

对于 Alpine，许多用户使用

“我想添加一些东西，我认为 Alpine 应该处理的东西，但这将是太多的千字节，所以我使用插件，”他补充道。

展望未来，Porzio 表示，他希望看到 Alpine 成为“所有后端框架的工具”，他的部分努力将集中在教育上。为此，他为 Alpine 推出了一个[组件](https://alpinejs.dev/components)方面，由教育视频和图像传送带或单选按钮等预建组件组成，所有这些都是用 Alpine 创建的。组件可在单一付款的基础上，目前提供 17 个不同的组件，包括所有未来创建的组件。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>