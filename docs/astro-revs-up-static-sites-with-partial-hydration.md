# Astro 通过部分水合作用加速静态位点

> 原文：<https://thenewstack.io/astro-revs-up-static-sites-with-partial-hydration/>

在过去的十年中，增加网络交互性的愿望导致越来越多的客户端 JavaScript 使用 Angular、Vue 和 React 等框架。虽然这一趋势对寻求在网络上创建完整应用程序的开发人员来说是一个福音，但它意味着越来越多的 JavaScript 被运送到客户端，这可能会让使用较旧、功能较弱的设备的用户陷入困境。

作为回应，最近的一个趋势是试图转向服务器端的内容呈现和交付。Gatsby、Jekyll 和 Hugo 等工具采用的一种方法是将网站预构建为静态 HTML，并将其加载到遍布全球的内容交付网络上，这允许超快的加载时间，但减少了可能的交互性。虽然这些网站已经开始在边缘引入功能以增加更多的交互性，但它们仍然局限于此。

## 输入 Astro

Astro 首席执行官 [Fred Schott](https://www.linkedin.com/in/fredkschott/) 在接受 New Stack 采访时表示，Astro 自称是“现代网络的一种新型静态网站构建器”，大约一年前推出，是一种寻求用另一种方法解决这个问题的工具。

“这是我们试图解决我们在当前的现状开发工具中看到的一些问题，这些问题围绕着太多的 JavaScript 膨胀，对希望进入 web 开发的人来说门槛太高，他们几乎必须学习 React，或 Svelte 或任何 JSX 语言，才能开始建立一个' hello world '，”Schott 说。“我们真的想尝试建立一些东西，将 web 开发带回其根源，而不仅仅是‘什么是最好的 JavaScript 框架？’这是‘建立一个网站和创建 HTML、CSS 和 JavaScript 的最好方法是什么，在这个等式中所有的都是一样的？"

像许多对 JavaScript 框架的回应一样，Astro 试图将网络的基础模块放在前端和中心。Astro 通过使用 Markdown 来实现这一点，Markdown 也支持 JavaScript 表达式和 Astro 组件。Schott 解释说 Astro 是 HTML 的超集，所以任何在 HTML 中工作的东西在 Astro 中也能工作。

Schott 说:“对任何使用过 HTML 的人来说，这感觉都很熟悉，但你可以在需要时加入 JavaScript，并在需要时加入你最喜欢的 web 框架。”“如果你只知道 HTML，你应该对 Astro 感到很熟悉，但同时，你可以从你最喜欢的框架中引入组件，在你需要的时候在页面上进行必要的补充。”

### 部分水合

Schott 在这里提到了两个基本概念，他说[将](https://docs.astro.build/en/comparing-astro-vs-other-tools/)框架与其他框架区分开来:[部分水合](https://docs.astro.build/en/core-concepts/partial-hydration)和[与任何框架一起工作的能力](https://docs.astro.build/en/core-concepts/framework-components)。

对于许多框架来说，页面是作为一个单元加载的，这意味着在所有内容加载之前，用户不能与页面的任何部分进行交互。这也有带宽和计算方面的影响，因为这意味着充满图像传送带和其他功能的页面可能需要时间来加载并耗尽带宽。

有了 Astro，开发者可以用任何他们喜欢的前端 — [React](https://reactjs.org/) ， [Preact](https://preactjs.com/) ，[svelet](https://svelte.dev/)， [Vue](https://vuejs.org/) ， [SolidJS](https://www.solidjs.com/) ， [AlpineJS](https://alpinejs.dev/) 或 [Lit](https://lit.dev/) 来构建一个站点，例如 — ，所有的客户端 JavaScript 都被默认剥离然而，部分水合允许您通过在绝对需要的地方放回一些客户端 JavaScript 来创建交互性。同时，部分水合允许开发人员使用他们称之为“孤岛架构”的东西来决定加载哪些方面以及何时加载。

“岛状结构和部分水合作用的想法是，你是在孤立地、平行地、分别地水合组分。这意味着，你需要一些 JavaScript 的‘购买’按钮将会孤立地以更快的速度水合，而页面下方一个昂贵的图像转盘正在完全独立地渲染和加载，”Schott 解释道。“你甚至可以开始控制单个物品的装载。所以,“购买”按钮非常重要，可以立即补充水分，但是页面下方的图像传送带，我们并不关心这个，我们只在它变得可见时才给它补充水分的能力。如果你从来没有滚动到它，你永远不会支付它的成本。”

目前，Astro 提供了静态站点生成器的好处，并“加入”了 JavaScript，但随着服务器端渲染功能的引入和 1.0 测试版的发布，该工具正在超越 T1。Schott 说，在过去一年的开发中，他们一直在调整方向，并着眼于电子商务用例的服务器端渲染。他指着推特上分享的[互动图](https://twitter.com/t3dotgg/status/1499896450737573889)，指出“随着我们下周的宣布，我们也将进入图表中的‘电子商务网站’阶段，但除此之外，我们不会在我们的重点方面走得更远。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>