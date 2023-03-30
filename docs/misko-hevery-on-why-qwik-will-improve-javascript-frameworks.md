# Misko Hevery 解释为什么 Qwik 会改进 JavaScript 框架

> 原文：<https://thenewstack.io/misko-hevery-on-why-qwik-will-improve-javascript-frameworks/>

一种新的 JavaScript 技术或库似乎每周都会在开发人员社区中出现。其中大多数的必要性是有争议的，但是[builder . io](https://www.builder.io/)CTO[Misko he very](https://www.linkedin.com/in/misko-hevery-3883b1/)说他的最新项目解决了一个长期存在的问题。 [Qwik](https://qwik.builder.io/) 是一个以 DOM 为中心的 JavaScript 框架，通过[专注于](https://www.builder.io/blog/introducing-qwik-framework)“HTML 的服务器端渲染的可恢复性和代码的细粒度延迟加载”，使“即时应用”成为可能

Hevery 最为人所知的是他是 Google 在 2010 年发布的有影响力的 JavaScript 框架 [Angular](https://angular.io/) (当时被称为 AngularJS)的创造者。因此，如果你要列出一个能够修复 JavaScript 框架的人的名单，Hevery 将会排在名单的前列。

他最初在 2019 Angular Ng-Conf 上谈到了[可恢复的应用。在那次演讲中，他给出了创建即时启动应用程序的框架应该遵循的两条规则:只下载和执行处理用户交互绝对必要的代码，不重复服务器已经完成的工作。](https://youtu.be/-kYtw3CSe6s?t=799)

正是基于这些理想，Qwik 应运而生。“框架设定了游戏规则，开发者必须遵守它们，”Hevery 在接受 New Stack 采访时说。“因为当前的框架规则是水合作用以使站点交互，所以所有复杂的站点启动都很慢。要走出这个陷阱，你需要一个具有可持续性而不是水合作用的框架。

## **服务器端渲染的优势**

2021 年 1 月，Qwik 开始开发，作为一个项目，Hevery“主要是在考虑我能在多大程度上延迟客户端代码的执行。”他说最初的语法没有工具，因此还有很多需要改进的地方。尽管如此，在工作中学习还是很有收获的。

“当我在 2022 年 6 月加入 Builder.io 时，”他说，“它变成了一项全职工作，我和 [Adam Bradly](https://www.linkedin.com/in/adamdbradley) 和 [Manu Martinez-Almeida](https://twitter.com/manucorporat?lang=en) 一起全职工作。事实证明，在我们三个人之间，我们有很多构建框架的经验，所以我们对 Qwik 有一个清晰的想法。”

为了更好地理解 Qwik 的吸引力，Hevery 描述了它如何对抗其他框架。“当前的框架只关心客户端渲染。SSR[服务器端渲染]实际上是后来才想到的。因此，客户端水合是使应用工作的唯一方式，水合是昂贵的，并且导致应用启动缓慢。”

他继续说，“通过端到端地解决整个问题，SSR 不是事后的想法，而是 Qwik 的中心目标。结果是网站的启动性能大大提高。Qwik 可以用零 JavaScript 提供大多数网站，然后只下载处理特定用户交互所需的代码。”

例如，当你在亚马逊上导航到一个产品页面时，你会遇到该网站的许多部分。购物车、评分、产品详情、菜单等。都要装。但是，正如 Hevery 指出的，“作为一个用户，你不需要所有这些部分一次。”

“将第一次交互延迟到所有代码都下载并执行后，代价会很高，但这正是水合作用所做的，”他继续说道。相反，Qwik 向客户端发送纯 HTML 和一个大约 1kb 的小 polyfill。如果用户单击 add to cart，则只下载和执行将商品添加到购物车并更新购物车组件的代码。这使得浏览器上的 JavaScript 数量很少，不管整个应用程序有多复杂。”

## **精懒加载**

Qwik 拥有“细粒度”的延迟加载，这是指 Qwik 将应用程序分成更小的部分，并授权服务器自由决定哪些大部分代码应该发送给客户端以及何时发送。

Hevery 说:“对于当前的框架，延迟加载是开发人员的责任。“在 Qwik 中，延迟加载落在了框架上。每个回调(效果、监听器、渲染函数)都是可延迟加载的。这种细粒度的特性，以及独立呈现组件的能力，使 Qwik 能够在不需要代码的情况下不下载代码。”

Hevery 继续解释说，与 Qwik 最接近的技术实际上是谷歌的主要产品(他从 2005 年到 2021 年在谷歌工作)。“在内部，谷歌有一个名为 [Wiz](https://www.wiz.io/partners/google?utm_source=google&utm_medium=search-ad-nonbrand&utm_device=c&utm_campaign=amer-lead-gen-rtg&utm_term=&campaignid=17499291051&adgroupid=143519118891&adid=604451970447&gclid=CjwKCAjwrNmWBhA4EiwAHbjEQJDO25D3kjFFHqZyeJmz3PpR1ccyg31PDOkC5PmEvRPpKXCwq6x69hoCU5MQAvD_BwE) 的框架，支持谷歌搜索、照片和 Gmail 等功能。Wiz 为应用程序提供了即时启动的属性，根据您对它的看法，您可以说它是可恢复的。严格地说，在 Wiz 中没有 JavaScript 的服务器执行被暂停，所以没有‘恢复’发生，但是效果是一样的。Wiz 有一个名为 [jsaction](https://github.com/google/jsaction) 的开源部分，据我所知，它开创了将监听器序列化为 HTML 的想法。Qwik 的监听器序列化与 jsaction 非常相似。”

Hevery 说，Qwik 在核心、实现和语法上与 Wiz 有很大不同，但目标是相同的——即时启动的应用程序。

## Qwik 的下一步是什么？

Qwik 目前可以在 Builder.io 的 [GitHub](https://github.com/BuilderIO/qwik) 上下载。Hevery 补充说，该项目正在接近全面可用。“我们对 Qwik 非常有信心，但希望在宣布之前有一个完整的解决方案。出于这个原因，我们也在研究 Qwik City，这是 Qwik 的一个元框架，允许我们用基于文件的路由来建立网站。此外，我们正在开发 Qwikify React，它允许从 Qwik 网站迁移，并允许 Qwik 使用 React 生态系统库，如材料组件。”

Hevery 说 Qwik 为开发者提供了一种构建网络应用的新方法。“细粒度的延迟加载和可重用性从一开始就导致即时启动的应用程序和 SEO 解决方案，”他承诺道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>