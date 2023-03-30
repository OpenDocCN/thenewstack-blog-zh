# WinterCG 将为 JS 服务器端运行时标准化浏览器 API

> 原文：<https://thenewstack.io/wintercg-to-standardize-browser-apis-for-js-server-side-runtimes/>

一个新的 W3C 工作组正在着手标准化 web 浏览器和 JavaScript 服务器端运行时环境(如 Node.js、Deno 和 Cloudflare Workers)之间的 API 实现。

web 互操作运行时社区组，简称为 WinterCG，有来自 Cloudfare、Vercel、Shopify 和其他几个 web 巨头的核心贡献者。他们想标准化服务器端的 API，就像浏览器 API 为了开发人员的健康而变得统一一样。

## 服务器端标准化

标准化实践并不新鲜。在[万维网联盟](https://www.w3.org/) (W3C)的保护下，[网络超文本应用技术工作组](https://whatwg.org/) (WHATWG)成立于 2004 年，创建了网络浏览器的 API 标准。他们的一些工作包括 HTTP 请求、Web 套接字、URL 标准化和流。

当涉及到在服务器端环境中实现这些相同的标准时，速度有点慢。

服务器端环境和 web 浏览器之间的代码实践有所不同。目前有哪些解决方案？Polyfill？“让它工作”的黑客代码？创建新的 API？新的中间件使 API 适应后端环境？WinterGC 的目标是开始改变这种情况。

### 为什么这对开发者很重要？

灵活性。模块化，可移植的代码。

作为一个不打算迁移到新环境的人，我也不会拒绝在熟悉的环境中尝试新事物的想法。

我的大部分工作都是用 Node.js 编码的，但对于我最近的开源产品，我第一次冒险进入未知领域，在 [Deno 环境](https://deno.land/)中开发。有起有落，但肯定有功能重叠。职能重叠的一致性是我非常期待的。

API 实现中这种脱节的一个很好的例子是 Node.js 中的 Streams 实现。Node.js 的实现非常接近 WHATWG 的标准化，并且产生了比其他非浏览器环境更快的数据流。

## WinterCG 是什么，WinterCG 不是什么

对 WinterCG 来说，“网络互操作性”意味着以一种与那些功能在网络浏览器中工作的方式相同或至少尽可能一致的方式来实现这些功能，这对于该小组来说非常重要。以至于它成了他们名字的前半部分。

实际上，这意味着 URL()构造函数将在 web 浏览器中执行与在 Node.js、Deno 和 Cloudflare Workers 中相同的功能。URL()将在整个堆栈中保持一致和标准化。

跨堆栈调整标准化的一个重要目的是消除每个新环境为公共功能创建自己的 API 的需要。声明 WinterCG 不会创建新的 API 或他们自己的一套与 WHATWG 制定的现有标准相竞争的标准是至关重要的。

该小组不会专注于将功能从一个环境调整到另一个环境。WinterCG 的工作范围将继续集中在调整基于 web 的环境和 Node.js、Deno 和 Cloudfare Workers 中存在的功能之间的连续性，或者是没有 web 浏览器的三个服务器端环境。

如果 WinterCG 提出了新的规范想法，该小组会将该想法提交给 WC3 和 WHATWG 进行审查。如果 WHATWG 无意推进，只要不与现有网络标准冲突，WinterCG 有权推进。

## 让我们开始吧！

值得一提的一个重要领域是[网络加密流](https://github.com/wintercg/proposal-webcrypto-streams)。该小组目前正在起草一个新的网络加密流规范，供 W3C 考虑，作为更新[网络加密规范](https://www.w3.org/TR/WebCryptoAPI/)的更大努力的一部分。

由于 Web Cryptography API 为常见的操作提供了一个最小的 API 集，所以加密是开发人员社区的一个痛处。除了作为内置模块提供的 Node.js 之外，不支持对称加密算法的流式输入和输出。因此，性能和可伸缩性受到限制。希望 WinterGC 的工作在这种情况下会有影响。

Fetch 是不一致的另一个痛点。Web 浏览器和服务器端运行时实现 Fetch。由于 fetch 前端和后端用例之间的差距，WinterCG 正在编写 fetch 标准的子集，以考虑每个实现的更窄范围。

还有一个最小 API 列表[可以在这里找到](https://github.com/wintercg/proposal-common-minimum-api)。

每个人都可以参加！这些目标是雄心勃勃的，而这个团队才刚刚开始。鼓励 W3C、WHATWG 和大型 JavaScript 社区的成员参与协作。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>