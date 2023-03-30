# 2022 年是 JavaScript 走向边缘的黄金年

> 原文：<https://thenewstack.io/2022-a-golden-year-as-javascript-moves-to-the-edge/>

2022 年 1 月，新栈提出了一个问题:“[2022 年将是全栈 JavaScript](https://thenewstack.io/will-2022-be-a-golden-age-for-full-stack-javascript/) 的黄金时代吗？这篇文章借鉴了开发人员和 JS 最佳创造者 [Michael Rambeau](https://www.michaelrambeau.com/) 的工作，他跟踪 JavaScript 生态系统中的[趋势项目，并将它们汇编成他的年度 JavaScript 新星，根据 GitHub 上给出的星星对项目进行排名。](https://bestofjs.org/)

这是一个令人信服的想法，JavaScript 可能会进入黄金时代。尽管早期经常有传言说 [WebAssembly](https://thenewstack.io/key-concepts/wasm/) 或 [htmx framework](https://thenewstack.io/htmx-html-approach-to-interactivity-in-a-javascript-world/) 可能会动摇 JavaScript 的地位，但这些预测仍然是……预测。

与此同时，JavaScript 迎来了又一个黄金年，它向边缘发展，框架激增。

## Javascript 走到了边缘

2023 年一个可能只会加速的大趋势是 JavaScript 向边缘的转移。越来越多的公司——包括 [Cloudflare](https://thenewstack.io/cloudflare-raises-1-25-billion-for-startups-using-its-workers-platform/) 、 [Netlify](https://thenewstack.io/10-jamstack-startups-to-empower-frontend-developers/) 、 [Deno](https://thenewstack.io/with-additional-funding-deno-sets-out-to-challenge-node-js/) 和[Vercel](https://thenewstack.io/what-developers-told-us-about-vercels-next-js-update/)——采用了这种模式，使得开发人员比以往任何时候都更容易在边缘部署。

今年早些时候， [Shawn "@swyx" Wang](https://www.swyx.io/) 告诉 New Stack 说:“另一个非常非常有趣的[趋势]是边缘计算的兴起，这主要是由 CloudFlare 和 Deno 引领的。

传统上，边缘意味着物联网技术，但当开发人员使用该术语时，他们往往指的是[内容交付网络](https://thenewstack.io/cdn-outages-exploring-ways-to-increase-resilience/) (CDN)，这是一组地理上分布的服务器，从离用户最近的位置交付内容。它甚至被用作无服务器的同义词。

“他们试图在用户附近缓存内容，”王解释说。“因此，当我坐在旧金山，从美国东部一台请求内容时，我实际上并没有为美国东部一台付费，我实际上是在 ping 我当地的 CDN 数据中心。”他补充说，这些 CDN 服务可以小到足以坐在手机信号塔上。王认为，有一个很大的推动重写代码，以利用优势。

“因为你将你的代码部署到更多的服务器上，本质上，它们只是更小的服务器。他说:“新的中心——新一代的边缘计算公司——他们已经找到了一种部署它的方式，类似于[V8 隔离](https://news.ycombinator.com/item?id=31740885),它们实际上是从[Chrome](https://thenewstack.io/google-aurora-a-collab-between-chrome-and-web-frameworks/)获取 JavaScript 引擎，并将其作为服务器运行。“与整个操作系统相比，Chrome 是超轻的，[所以]你只是把它当作服务器来运行；当你把它缩小那么多，你可以让它便宜很多。”

他补充说，因此，边缘服务器往往比从中央位置提供页面服务更便宜。

王并不是唯一一个吹捧这种优势价值的人。在今年的 Jamstack 大会上，[成为了焦点，在会上，](https://thenewstack.io/jamstack-panel-how-the-edge-will-change-development/) [Cloudflare](https://thenewstack.io/cloudflares-kiwi-farms-support-may-soon-hurt-its-bottom-line/) 的前高级系统工程师 [Sunil Pai](https://twitter.com/threepointone?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) 建议开发者在 2022 年最后一个季度将他们网站的一部分放到边缘。

“我们目前正在研究剩下的部分。有很多工作要做，但你今天应该用很多，”Pai 说。Pai 现在是酷派电脑俱乐部(Cool Computer Club)的创始人，该俱乐部为 edge 应用开发开发工具。

Netlify 的联合创始人兼首席执行官马特·比尔曼(Matt Biilmann)表示，他的基于云的开发公司最近在边缘用例方面的月环比增长约为三倍。根据 Netlify 对 Jamstack 社区的近 7000 名开发者进行的一项[调查](https://thenewstack.io/survey-finds-majority-of-jamstack-community-testing-edge/)，超过一半的人正在通过构建边缘动态网站来测试边缘。调查将边缘动态网站定义为“完全动态的网站，并在边缘呈现所有内容(即使用无服务器功能或边缘功能)。”

## 静态页面结束的开始

走向边缘的一个原因是，它承诺了某种程度的个性化，这是静态的服务器端站点所不能实现的。

王在今年的 Reactathon 的一次谈话中，一口咬定静边代()已经【基本死亡】。他还提到了一种向增量渲染和边缘路由的发展趋势。他指出“Next.js 赢得如此艰难”是支持这些趋势的框架。

王在会上概述了 JavaScript 的“时代”，声称我们现在正处于第三个时代。他预测，到 21 世纪 20 年代末，JavaScript 将会“再技能化”。虽然他没有具体说明什么可能取代 JavaScript，但他确实提到 WebAssembly 目前正处于“第一个时代”。

## 你得到一个框架！你就有了一个框架！

不完全是。同一个 Jamstack 社区调查发现使用最多的框架是 [React](https://thenewstack.io/how-to-use-google-sheets-as-a-database-with-react-and-ssr/) ，在榜单上 29 个框架的排名中，一些或大多数项目的使用率超过 71%。虽然 React 在技术上是一个 JavaScript 库，但它构成了许多 JS 框架的基础。

“我们的框架数据中最明显的故事是 React 的持续增长，”调查称。“虽然构建反应式 web 应用程序有许多选择，但 React 周围的巨大生态系统继续使它成为许多人的轻松选择。”

这并没有阻止替代框架进入这个拥挤的领域，包括 Fresh。

[Fresh 是 Deno 软件工程师 Luca Casonato 创建的全栈 JavaScript 框架](https://thenewstack.io/denos-fresh-uses-server-side-rendering-for-faster-apps/)。它基于 Preact，这是一个 JavaScript 库，宣传自己是 Meta 的 react 的替代品。它还使用 Deno，而不是更常见的 NodeJS。

Casonato 告诉新的堆栈，继续向边缘移动的趋势，Fresh 针对边缘计算进行了优化，大部分渲染都在服务器上完成。卡索纳托声称，即使在慢速设备上，这也意味着在全世界范围内的出色表现。他说，相比之下，其他向客户端发送更多代码的 JavaScript 框架在慢速设备上往往表现不佳。

他将它与 [Node.js](https://thenewstack.io/with-additional-funding-deno-sets-out-to-challenge-node-js/) 或 [Vercel](https://thenewstack.io/vercel-delivers-next-js-12-the-sdk-for-the-web/) 进行了比较，他说这两个软件可能具有在单个地区的[亚马逊网络服务](https://thenewstack.io/kubernetes-and-amazon-web-services/)上运行的无服务器功能。但是，为什么要创建另一个框架呢？Casonato 说速度和开发者体验是他认为其他框架所缺少的两个方面。他认为，这个组合是一个比现有框架更好的框架，缺点更少。

“这个框架实际上是为服务器端渲染而构建的，所以它向客户端发送很少的 JavaScript 和很少的代码，并尽可能多地保留在服务器上，为用户提供非常快捷的体验，”他说。

[Redwood 今年也发布了](https://thenewstack.io/redwood-a-javascript-framework-designed-for-startups/)。这是另一个使用 React 的基于 JavaScript 的全栈框架，但它的目标是希望获得基于流行工具的完整栈的初创公司和企业。 [Tom Preston-Warner](https://www.linkedin.com/in/mojombo/) ，Github 的[创始人和前 CEO，是开源 web 开发框架的四位创始人之一和 300 名贡献者。](https://en.wikipedia.org/wiki/Tom_Preston-Werner)

“我想做的是收集一套已经普遍使用的工具，但做真正漂亮地集成它们的艰苦工作，以便人们可以开始构建他们的应用程序的特殊之处，”普雷斯顿-华纳告诉 New Stack。

谷歌杰出的工程师和经常在会议上发言的人 Kelsey Hightower 认为，我们不太可能看到新 JavaScript 框架的终结。Hightower 告诉新的堆栈，永远不会只有一个 JavaScript 框架。

“永远不会有，因为经验在不断变化，”海塔尔说。“作为人类，我们喜欢这样，因为我们想听到一些新的东西。…它永远不会停止。但是我们希望这样吗？我不认为我们真的希望如此。”

## ECMAScript 进度

开放标准 JavaScript 今年也经历了八次更新，发布了 [ECMAScript 2022](https://thenewstack.io/javascript-developers-on-what-matters-and-whats-next/) 。一些开发人员指出 error.cause 特性是一个关键的升级。

王昌娥在 2023 年期待的是[临时提案](https://tc39.es/proposal-temporal/docs/)，该提案处于四阶段提案流程的第三阶段。他告诉新的堆栈，这将解决数据格式问题，这些问题可能会变得复杂，有时甚至是不明确的。

总而言之，JavaScript 仍然是网络应用创新的驱动力。只是现在，它在边缘上更加突出，甚至有更多的框架可供选择。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>