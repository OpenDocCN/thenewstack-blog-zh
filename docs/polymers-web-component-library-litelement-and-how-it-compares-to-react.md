# Polymer 的 Web 组件库 LitElement 及其对比反应

> 原文：<https://thenewstack.io/polymers-web-component-library-litelement-and-how-it-compares-to-react/>

[React](https://reactjs.org/) 之于 JavaScript 用户界面组件， [LitElement](https://lit-element.polymer-project.org/) 和 [lit-html](https://lit-html.polymer-project.org/) 之于 web 组件。从某种意义上说，它们都是帮助开发人员为网站和 web 应用程序构建和部署组件的库。但是这两套技术之间有一些关键的区别；以及关于互操作性的问题。

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇关于 web 和应用程序开发趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) 

LitElement 和 lit-html 是谷歌在 2015 年推出的开源 JavaScript 库[聚合物项目](https://www.polymer-project.org/)的一部分。该项目的目标是让使用 [web 组件](https://thenewstack.io/how-web-components-are-used-at-github-and-salesforce/)构建 Web 应用程序变得更加容易。LitElement 和 lit-html 是 Polymer 中的两项核心技术，前者是定义 web 组件的方法，后者是 JavaScript 的 html 模板库。

LitElement 和 lit-html 的下一个主要发布日期即将到来，所以我联系了谷歌的聚合物团队负责人 Justin Fagnani，以了解这将如何改变 web 开发——特别是在构建组件方面。我一开始问 LitElement 如何比较 React？

“嗯，LitElement 并不真正像框架，因为 LitElement 没有定义组件模型，而是由 HTML 规范定义的。LitElement 帮助您构建一个 web 组件——Lit 只是内部——但结果是一个[HTML]元素。这对互操作和解耦很重要，LitElement 旨在与其他构建组件的方式混合使用，包括框架。”

React 网站[声称](https://reactjs.org/docs/web-components.html)开发者“可以自由地在你的 Web 组件中使用 React，或者在 React 中使用 Web 组件，或者两者兼而有之。”但实际上，这两套技术之间几乎没有重叠。正如我在上周的专栏中提到的，GitHub(举个例子)选择使用 web 组件，而不是依赖 React 这样的前端框架。这似乎是采用 web 组件时的一种常见模式。

那么，为什么这两种技术——React 和 web 组件——不经常混合使用呢？

“React 使用 web 组件的困难源于它试图对开发人员隐藏 DOM，”Fagnani 说，“特别是像属性、特性和事件之间的差异这样的事情。这在 DOM 中只是三个独立的东西，但在 React 中，开发人员没有直接使用它们的表达能力。”

## 框架互操作

上周，Fagnani 做了一个由 Java 框架公司 [Vaadin](https://vaadin.com/) 主办的网络研讨会，主题是 LitElement 和 lit-html 的发展前景。讨论中最有趣的一点是 Fagnani 所说的“框架互操作”你大概能猜到他特别提到了哪个流行的框架。

“web 组件的主要好处是，”Fagnani 说，“它们可以在 HTML 工作的任何地方工作。因此，如果你在像[这样的网站上到处寻找](https://custom-elements-everywhere.com/)，你会发现大多数框架都有非常非常好的网络组件互操作能力。最突出的是**而不是**具有很好的互操作性，也是使用最多的，那就是 React。所以我们真的希望，你知道，对组件作者和潜在的组件用户都有很多同理心。”

他解释说，组件作者希望他们的组件“在尽可能多的地方可用”，而用户(指其他开发人员)不希望“为了使用它们而不得不经历重重困难。”

原来，Custom Elements Everywhere 网站在支持定制元素(Web 组件的基石，正如我在上一篇专栏文章中所讨论的那样)方面给 React 的评分最低，该网站是由 Google 开发者倡导者 [Rob Dodson](https://twitter.com/rob_dodson) 运营的。

为了让 React 更受欢迎，至少有一个流行的基于 React 的框架——[next . js](https://nextjs.org/)——表示它对使用 web 组件持开放态度。事实上，Next.js 的创建者 Guillermo Rauch 告诉我“Next.js 最初是以一种可以合并 web 组件的方式设计的。”然而，有一个问题。

“矛盾的是，当时的规范并没有包括在 HTML 中以有利于服务器渲染的方式声明性地定义它们，”劳赫说，“但我仍然对在某些场景中使用它们的可能性感到兴奋。”

Fagnani 在网上研讨会上说，他的团队正在“为框架互操作做一些实验”，包括一种“将 web 组件转换为 React 组件”的方法。

因此，双方都希望将 web 组件添加到 React 环境中。

## 框架锁定

采用一种新的方式来构建组件的一个常见问题是，它可能会使您在将来采用这种方法；至少如果你想减少工作量的话。在决定是使用原生浏览器 API 来创建 web 组件，还是使用 LitElement(一种抽象)之类的库时，这甚至可能是一个问题。[其他 WC 库](https://levelup.gitconnected.com/web-component-solutions-a-comparison-e2fa25c34730)包括 [Svelte](https://svelte.dev/) 、 [Stencil](https://stenciljs.com/) 、 [FAST](https://www.fast.design/) 和 sales force solution[Lightning Web Components](https://developer.salesforce.com/docs/component-library/documentation/lwc)(LWC，我上周写过的)。

但是等等，还有更多。LitElement 和它之前的库 Polymer 也有区别。令人困惑的是，LitElement 是 Polymer 项目的一部分，但是 LitElement 与 Polymer the library 完全不同。“LitElement 是聚合物项目当前的 web 组件库，”Fagnani 是这样说的。无论如何，旧聚合物库提供了一个他称之为“组件间耦合过多”的例子

“双向数据绑定系统是主机和子组件之间的契约，其他库没有实现，”他说。“因此，要从聚合物中迁移出来，你必须从双向绑定中迁移出来，或者重新执行协议。在 LitElement 中，我们已经消除了所有像这样的跨组件耦合，特别是为了更容易互操作和迁移。”

“文学元素给你三个主要的东西，”他进一步解释道。"反应性属性，一个可挂钩的更新/呈现周期，它增加了自定义元素的生命周期，以及声明性模板."

其他 WC 库也有类似的功能。

“Stencil、LWC、FAST 和许多其他助手都提供了这三种反应属性、额外的生命周期和模板，”Fagnani 说，“因此，在维护一个工作应用程序的同时，一个元素一个元素地移植不会太困难。”

我不得不再次提起我们的老朋友的反应。我问法格纳尼，随着时间的推移，LitElement(以及一般的 web 组件)是否能够吸引成千上万的 React 前端开发人员？

“我们的目标不是‘击败’框架，”他回答说，“而是解决真正的问题——尤其是围绕互操作性的问题——并帮助 web 开发变得更加健壮和可伸缩。”

他指出了一些“在 web 组件上的大赌注”，如 Salesforce LWC“以及其他我们很快会听到更多的大项目。”

他设想 web 组件最终会被广泛应用于不同的框架中。

“我们已经看到框架进化到更好地与 web 组件互操作，”他说，“不同的框架做得越好，比如 Vue 和 Svelte，就越需要可互操作的 web 组件。”

这个词，互操作性，是 web 组件和 Web 应用程序未来的关键。曾经有一段时间(20 世纪 90 年代中后期)，主要的网络浏览器互不兼容。谢天谢地，这已经是过去的事了，如今四大浏览器厂商(谷歌、Mozilla、苹果和微软)都在定义网络标准方面紧密合作，都是 WHATWG(T1)小组的成员。

也就是说，我们仍然会看到流行的 JavaScript 库和 web 组件之间的互操作性问题——很大程度上是因为后者仍然相对较新。因此，观察组件架构中的这种动态在未来几年如何发展将是一件有趣的事情。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>