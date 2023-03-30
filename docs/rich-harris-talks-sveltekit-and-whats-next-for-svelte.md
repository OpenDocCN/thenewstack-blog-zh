# 里奇·哈里斯谈论苗条身材和苗条身材的下一步

> 原文：<https://thenewstack.io/rich-harris-talks-sveltekit-and-whats-next-for-svelte/>

据前端框架的创建者 Rich Harris 称，Svelte 的第一次重大修改工作正在进行中。这是紧随该团队发布 SvelteKit 之后的，SvelteKit 是一个用于构建 web 应用程序的全栈框架。

“既然 SvelteKit 已经出来了，在这一点上已经相当广泛和稳定，我们的注意力将转回到[svelite](https://svelte.dev/)本身，”Harris 告诉 New Stack。"现在我们正在开发 Svelte 4，它将使代码库现代化."

该团队正在将底层代码从[类型脚本](https://thenewstack.io/key-concepts/typescript/)切换到 [JavaScript](https://thenewstack.io/jamstack-panel-multiple-javascript-frameworks-are-a-good-thing/) 。他补充说，这一更新将允许团队在今年晚些时候为 Svelte 5 引入“大创意”。

哈里斯说，Svelte 是一个框架，但它也是一种描述用户界面的语言。它被编译成 [JavaScript](https://thenewstack.io/javascript-developers-on-what-matters-and-whats-next/) ，这样它可以在任何地方运行。他说，这样做的好处是，当应用程序建立时，Svelte 知道应用程序的哪些部分可以改变，哪些部分不能改变。

“尽管(第一个)框架必须做大量的工作来找出页面上需要改变的内容，但 Svelte 是第一个真正表明这是不必要的，并且通过提前做尽可能多的工作而不是在浏览器中做，你可以在性能和软件包大小方面获得显著收益的框架，”哈里斯说。

## SvelteKit 为前端开发者提供了什么

关注苗条意味着短期内对苗条的关注会减少。 [SvelteKit](https://github.com/sveltejs/kit) 在 12 月发布为 1.0 版本，现在是 1.11 版本。哈里斯说它很稳定。它与 [Next.js](https://thenewstack.io/what-developers-told-us-about-vercels-next-js-update/) 、[盖茨比](https://thenewstack.io/netlify-acquires-gatsby-its-struggling-jamstack-competitor/)和 [Nuxt](https://nuxtjs.org/) 竞争。

“有时人们会说，‘我应该从苗条还是苗条开始’，好像它们是相互排斥的。我的框架是，如果你熟悉像 [React](https://thenewstack.io/angular-vs-react-how-to-choose-the-right-framework-for-you/) 和 [Meta](https://thenewstack.io/jest-metas-javascript-testing-framework-joins-openjs/) 框架、 [Next](https://thenewstack.io/next-js-13-debuts-a-faster-rust-based-bundler/) 或 [Remix](https://remix.run/) 这样的框架，那么 Svelte 和 SvelteKit 也有类似的关系，”Harris 说。

他说，SvelteKit 是一个用于创建自包含组件的用户界面框架，它将一些标记、行为和风格结合到一个可重用的组件中，开发者可以在他们的应用程序中使用。他补充说，这可能是一个导航条、一个博客帖子或聊天工具，甚至是另一个组件中的一个组件。它可以是开发者想要的任何东西。

“在过去的几年里，我们越来越多地看到框架团队意识到，我们有责任为人们提供工具，用这些组件框架实际构建应用程序，”Harris 说。“Next 可能是这方面第一次真正认真的尝试。它让 React 不再是你必须拼凑到自己的应用程序框架中的东西。”

简而言之，如果开发者正在用 Svelte 进行构建，SvelteKit 支持并提供了最好的方法，他解释道。Svelte 可以在两种不同的环境中运行——在服务器上或在浏览器中，在浏览器中它将操纵 [DOM](https://thenewstack.io/google-docs-switches-to-canvas-rendering-sidelining-the-dom/) 。哈里斯说，SvelteKit 是用 JavaScript 构建的，具有服务器/客户端分离的思想。

“一个是一次性的，生成 HTML，你就完成了，”他说。“另一个是你正在创建这个长寿命、潜在交互式的东西，它可能会接收新数据，你可以点击按钮，创建事件，改变状态和所有这些事情，所以它必须有这么长的生命周期。”

他补充说，即使你只编写一次组件，你也是在针对两种截然不同的环境。

“SvelteKit 给你一个非常简单的方法来弥补这个差距，”他说。它将协调服务器上的初始渲染，然后将无缝切换到浏览器

## SvelteKit 方法的好处

这种方法的好处是更好地感知性能，因为页面的一部分甚至在 JavaScript 加载时运行，或者即使它不加载，Harris 说这种情况比开发人员想象的要多。例如，每当他在地铁上时都会遇到这个问题——在 JavaScript 加载之前，连接就断开了。无论如何，服务器端呈现都可以让用户看到内容。

“这对搜索引擎优化更好，对存档更好，对可访问性更好，所有这些都更好，”他说。“这就是我们采用服务器/客户端思维模式的原因，在这种思维模式下，两者在应用程序中是平等的合作伙伴。”

不过，它不仅仅是服务器端渲染。SvelteKit 也有一个从服务器获取数据的过程。他说，如果一个页面需要更新而不需要重新加载，它也可以从服务器获取数据，使开发人员能够创建 API 端点，以便数据甚至可以用于同一应用程序中的第三方。

## 边缘渲染和苗条

边缘渲染是另一种类型的服务器端渲染。在[边缘使用苗条已经引起了一些讨论](https://morioh.com/p/3772a1098574)，并且是两年前苗条峰会上[的一个话题。哈里斯说，这种能力是前端框架的一个功能，并不是苗条身材所独有的。](https://www.youtube.com/watch?v=CgfF1Otav_o&list=PL8bMgX1kyZThM1sbYCoWdTcpiYysJsSeu&index=17)

“Edge 功能的重大创新是不再运行[节点](https://thenewstack.io/linux-manage-multiple-versions-of-node-js-with-the-nvm-manager/)；他们正在运行一个轻量级的 JavaScript 运行时，可以在世界各地的许多不同的数据中心运行，”哈里斯说。“我们看到的发展是从集中的、手动管理的服务器到这些可以在世界任何地方运行的非常小的计算单元。那可以是任何一台电脑，但在我们的例子中，它恰好在呈现 HTML。”

## 苗条企业准备好了吗？

哈里斯欣然承认，以前，苗条可能不是大公司的最佳选择。

“如果你在一家大公司负责工程决策，那么你应该考虑的事情是:这个框架有大公司的支持吗？是不是有很多开发者在用？很长一段时间，答案都是否定的。

在 Vercel 的支持下，这种情况发生了变化，它的一些客户现在正在使用 Svelte。[施耐德电气](https://www.se.com/ww/en/)、[布丁](https://pudding.cool/)和 [GitBook](https://www.gitbook.com/) 都是使用 Svelte 的公司。

“我们越来越多地看到大公司的开发人员使用它，”哈里斯说。“一旦你有了一个你所知道的公司成功实现苗条身材的例子，其他公司通常会效仿。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>