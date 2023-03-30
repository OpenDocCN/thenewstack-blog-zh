# 不总是需要 JavaScript 框架的 5 个理由

> 原文：<https://thenewstack.io/5-reasons-you-dont-always-need-a-javascript-framework/>

框架是很好的工具，可以帮助开发人员不必不断地重新发明轮子和重写代码。当一个项目需要高效和有效地部署时，一个框架将大大有助于你的开发团队实现它。

但是并不是每个项目都需要框架。对于你的软件工程师所依赖的许多语言来说都是如此。JavaScript 也是如此吗？你打赌。

JavaScript 框架通常被认为是现代前端 web 开发的基本工具。通过使用众多框架中的任何一个，您的开发人员可以构建可伸缩的、动态的基于 web 的应用程序，这些应用程序可以在您的公司内部使用，甚至可以由消费者、客户或客户使用。有相当多的框架可供选择，比如 [Vue.js](https://vuejs.org/) 、 [Angular](https://angular.io/) 、[svelite](https://svelte.dev/)、 [Express.js](https://expressjs.com/) 、 [Bootstrap](https://getbootstrap.com/) 、 [Django](https://www.djangoproject.com/) 。

所以，当你需要一个框架时，它们就在那里(而且大多数是开源的，所以可以免费使用)。但是什么时候你可能*而不是*需要 JavaScript 框架呢？我们来看看五个原因。

## 1.如果你正在做的事情很简单

说实话，JavaScript 框架最适合大规模应用的复杂项目。如果你正在做一些简单而小的东西，那么框架将会是多余的。事实上，如果你正在做一个更小的项目，框架只会让事情变得复杂，所以你最好不要这样做。

请记住，使用框架的目的是通过实现普通 JavaScript 中您需要的一切来简化您的工作并节省时间。如果你正在做的项目比较小，你节省的时间将会被你花在加快框架速度或者把它添加到组合中的时间所掩盖。

如果项目的目标是保持简单，就不要为框架费心。

## 2.当 HTML 和 CSS 单独完成任务时

您将使用 JavaScript 框架做的大部分事情是构建 web 应用程序。是的，JavaScript 有助于使这些应用程序变得更具交互性、更具动态性和更令人兴奋，但有时 JavaScript 会矫枉过正，降低网站的性能。

退一步想想:HTML 和 CSS 足以构建网站或 web 应用程序吗？如果是这样，那就坚持做基本的。当然，您可能需要添加一些 JavaScript，但是在这个过程中添加一个框架可能会很快使由更基础的语言创建的清澈的水变得浑浊。记住这一点:HTML 是为了结构，CSS 是为了外观，JavaScript 是为了行为。HTML 和 CSS 通常是至关重要的成分，而 JavaScript 是蛋糕上的糖衣。JavaScript 框架是一种工具，它可以帮助您将所有这些成分混合在一起，烤出一个值得竞争的蛋糕，但它增加了一层您可能不需要的复杂性……尤其是当您只想要一个基本的蛋糕时。

## 3.如果您使用的是 JavaScript ES6

随着 [JavaScript ES6](http://es6-features.org/#Constants) 的发布，对框架的需求不像以前那么大了。随着 ES6 包含了模块和类，大多数流行的框架可以被认为是过时的。

记住，框架是用来抽象开发的一些更复杂的方面的。随着 ES6 的发布，许多新特性(如默认参数、模板文字、多行字符串、析构赋值、增强的对象文字和箭头函数——以及模块和类)减少了许多用例对框架的需求。

在 ES6 之前，处理像类这样的东西是一个主要的挑战，即使以前的迭代是专门为支持类而设计的。

JavaScript 的这些新特性大大有助于让框架成为过去，因为它们为这种语言带来了某些以前没有的功能。不用使用那些第三方工具，几乎所有的东西都将被预先打包在语言本身中。

## 4.如果创作自由是你的难题

让我们面对现实吧，当你使用一个 JavaScript 框架时，你通常只能使用一个，并且你会受到该框架的限制。当你不使用框架时，你可以完全按照你想要的方式来设计你的 web 开发。鉴于你可以通过 HTML、CSS 和 JavaScript 的组合做任何你想做的事情，除非你是在大规模建设，并且不在乎创作自由，你已经拥有了你需要的一切，你的创造力没有极限。

## 5.HTMX

HTMX 是 intercooler.js(使用熟悉的声明性 HTML 属性将 AJAX 添加到应用程序中)的继任者。这个新的库允许您直接从 HTML 访问许多现代浏览器特性(如 AJAX、CSS 转换、WebSockets 和服务器发送的事件),而不是使用 JavaScript。这意味着开发人员将能够构建现代化的界面，而不必求助于 JavaScript——以及 JavaScript 框架。

从官方 [HTMX 网站](https://htmx.org/)，我们看到这个例子:

```
 <button hx-post="/clicked"
       hx-trigger="click"
       hx-target="#parent-div"
       hx-swap="outerHTML">
    Click Me!
  </button>

```

在这个例子中，当用户点击一个按钮时，一个 HTTP POST 请求被发出/点击，然后响应被用来替换 DOM 中使用 *parent-div* 的元素。

## 结论

使用框架的两个主要原因是速度和外部数据源的集成。如果这两个都不是你项目的问题，那么框架只会妨碍你，扼杀你的创造力。

JavaScript 框架当然有它们的目的，不应该被自动忽略。但是如果你有时间和兴趣，直接用 HTML、CSS 和 JavaScript 代码构建会非常有价值。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>