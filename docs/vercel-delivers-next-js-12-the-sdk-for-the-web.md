# Vercel 发布 Next.js 12:“面向网络的软件开发工具包”

> 原文：<https://thenewstack.io/vercel-delivers-next-js-12-the-sdk-for-the-web/>

本周，Vercel 举办了其 [Next.js Conf](https://nextjs.org/conf) 并发布了 [Next.js 12](https://nextjs.org/blog/next-12) ，该公司称之为网络 SDK。

Vercel 的创始人兼首席执行官 Guillermo Rauch 表示，Next.js 12 是 Vercel 迄今为止最大的技术发布，因为它能够以静态的速度开发和交付动态网站。他补充说，这项技术是 Vercel 和 1800 多名贡献者以及数千家公司和合作伙伴(如谷歌 Chrome 和脸书的 [React](https://reactjs.org/) 团队)合作的结果。

[Next.js](https://github.com/vercel/next.js/) ，Rauch 的创作，是一个面向前端 web 开发的 React 和 JavaScript 框架。最新版本引入了新的中间件功能，使开发人员能够快速个性化内容和交付。Next.js 12 还增加了 ES 模块和 URL 导入、即时热模块替换(HMR)和构建，以及其他工作流和协作创新。 [ES 模块](https://hacks.mozilla.org/2018/03/es-modules-a-cartoon-deep-dive/)是使用模块的 [ECMAScript](https://www.ecma-international.org/publications-and-standards/standards/ecma-262/) 标准。

ES Modules 使 Next.js 能够向用户发送更小的包。Rauch 说，新的 URL 导入支持允许与无代码和设计工具进行新的和各种各样的集成。

## 改进:开发、预览、发布

总的来说，Next.js 12 带来了三个方面的改进:“开发、预览和发布，”劳奇告诉新堆栈。他说:“我们已经对开发人员体验、工作流程和协作进行了改进，然后对我们的边缘网络进行了改进，以尽可能最快的速度提供网站和应用程序。”

新的中间件支持使开发人员能够在请求完成之前运行 Next.js 代码。劳奇说，根据用户的请求，开发者可以通过重写、重定向、添加标题，甚至流式传输 HTML 来修改响应。此外，他解释说，中间件可以用于共享一组页面逻辑的任何事情:身份验证，僵尸保护，重定向，处理不支持的浏览器，功能标志，a/b 测试，服务器端分析，日志记录等等，该公司说。

“我想这一切都归结于简化和加速基于网络的应用程序开发，”T2 奥本海默公司的高级股票研究分析师 Ittai Kidron 说。“网络现在是大多数数字企业的参与前沿，因此用户体验(UI)，即数据、功能和网站流量更新和调整的速度至关重要。Web 开发人员没有时间或知识来处理应用程序交付过程的“其他部分”——处理安全性、运营、建立基础设施等。Next.js 为他们提供了一个可控的环境，用于开发、预览和将应用交付到实际生产中。”

Ittai 说，基本上，Next.js 使开发人员能够将应用程序开发过程的前端和后端部分分开。

“开发者喜欢这一点，它的核心是开源的，它消除了层层复杂性和工作流程，使他们能够专注于他们需要做的事情，并更快地获得更好的结果，”他说。

## 接近边缘

Vercel 的[边缘功能](https://vercel.com/features/edge-functions)立即启动，并在全球部署中间件，支持流媒体。

根据 Vercel 的说法:Vercel 上的 Edge 功能消除了冗长的路由配置文件，并允许在边缘使用强大的应用程序，而不会给客户端带来负担。这为用户提供了动态代码的能力和静态代码的速度保证。

[Next.js 中间件](https://nextjs.org/docs/middleware)和 Vercel Edge 功能允许用户:

*   在处理请求之前，在边缘运行 JavaScript
*   通过重写、重定向、添加头等方式修改请求响应
*   通过在部署时添加几段代码来定义应用程序的整个全球基础结构

“最突出的是，我们正在改变网络的许多基础设施，”劳奇在采访中说。“在服务方面，我们正在从无服务器功能转向边缘功能。边缘功能，简单来说就是以静态的速度给你动态的力量。这是一个全局原语，开发人员在 Next.js 中编写代码，推送代码并部署全局功能，这些功能可以即时启动，对公司来说非常非常划算。”

## 新的 Rust 编译器

同时，在工具的基础设施方面，Vercel 引入了一个 [Rust](https://thenewstack.io/rust-by-the-numbers-the-rust-programming-language-in-2021/) 编译器。Rauch 说，新的 Next.js 12 Rust 编译器实现了三倍的快速刷新和五倍的生产构建，并且没有代码更改。

“我们正在为 JS 生态系统开发工具，通过进行过去十年中发生的大量实验，开发和构建速度非常快，”他说。“随着项目和团队的增长，在前端，它多少显示了语言和运行时的一些限制。因此，我们也在工具基础设施方面进行创新，用本地语言重写了它的核心部分。”

在 Next.js Conf 的演示中，Vercel 展示了其新的 [Rust](https://www.rust-lang.org/) 编译器，其构建 vercel.com 的速度比之前的版本快 1.87 倍，并提供了更快的开发时间刷新。

Forrester Research 的分析师, [Andrew Cornwall](https://www.linkedin.com/in/acornwall/) 告诉 The New Stack，“Vercel 已经表示，他们的路线图的一部分是让非开发人员，而不仅仅是专业开发人员建立网站。“他们的新 Rust 编译器对 URL 导入提供了实验性支持——这是朝着构建低代码平台迈出的一步。他们还没有达到非开发人员建立网站的地步，但他们正在为此增加基础。”

与此同时，在工作流协作方面，Vercel 正在通过 [Next.js Live](https://vercel.com/live) 降低进入 Next.js 的门槛。他说，Next.js Live 在网络浏览器中本地运行，立即启动，允许任何有链接的人进行协作。

“我们正在扩展该产品，我们开始模糊无代码、低代码和前端(空间)之间的界限——我们正在帮助更多的人为前端做出贡献，”劳奇说。

## 模糊的线条

他们将如何模糊这些界限？

“有了我们的新工具，我们可以通过使用[服务工作者](https://developers.google.com/web/fundamentals/primers/service-workers)【Service Workers . js】和 [WebAssembly](https://thenewstack.io/cncf-welcomes-webassembly-based-wasmcloud-as-a-sandbox-project/) 的组合，直接在浏览器中运行整个 next 开发体验，所以你不需要在你的本地机器上运行非常复杂的工具，”劳奇说。“或者，你不需要在云中部署虚拟机。这意味着我们可以将 Next.js 变成一种体验，公司中的任何人只需按下按钮，就可以立即对他们的前端进行更改，然后提交供审查。这可以追溯到经典的 GitHub 工作流程。但这对于公司，尤其是企业来说非常重要。所以，它给你带来了两个世界的最好的东西，就像我可以非常容易地、即时地编辑网络，就好像它是在网络浏览器中实时协作的谷歌文档一样。”

## 中间件是关键

然而，回到中间件创新，当开发人员将 Next.js 中间件定义为他们 Next.js 应用程序的一部分时，Vercel 默认情况下会在全球范围内部署每个 Edge 功能，该公司表示。并且，与无服务器功能不同，Edge 功能没有冷启动，无需任何配置就能在 Vercel 的 Edge 网络的每个区域自动运行。该公司表示，Vercel 会自动优化 Next.js 应用程序，以获得最佳性能。

[Forrester Research](https://www.forrester.com/bold) 的分析师 [Jeffrey Hammond](https://www.linkedin.com/in/jeffrey-hammond-770630/) 说:“他们的开发经验给我留下了深刻的印象，尤其是开发人员如何快速部署内容更新，并让利益相关者能够快速审查和批准变更。“他们本质上实施了 GitOps 原则来做到这一点。因此，他们真正构建的是一个以网络为中心的平台即服务，减少了开发人员的认知负荷，并提高了开发人员所构建内容的性能。”

## 解锁边缘

[边缘计算](https://thenewstack.io/the-challenge-of-scaling-the-intelligent-edge/)解决了跨国公司——不仅仅是大型跨国公司——需要处理的一类问题:他们的客户遍布全球，但他们的服务器却在弗吉尼亚州。安德鲁·康沃尔在接受《新堆栈》采访时说，但是他们如何确保澳大利亚的某个人获得与华盛顿的某个人相同的网络性能。

“Vercel 的答案是在边缘提供处理:换句话说，不是在你的网络服务器上运行代码，而是在你的客户附近的服务器上运行代码，”他说。“当客户在您的网站上请求某些东西时，澳大利亚客户将在悉尼的服务器上运行代码，而爱尔兰的某个人提出同样的请求将在都柏林运行代码——两人都可能得到适合当地的答案。”

这概括地描述了劳赫的策略。“我们认为未来就在边缘，我们希望每个开发人员都能享受到他们项目的最佳基础设施，”他说。

“Vercel 在其边缘服务器上公开了一个[V8 JavaScript](https://v8.dev/)/web assembly 引擎，”Cornwall 说。“他们在这方面并不孤单:我知道 [Cloudflare](https://www.cloudflare.com/) 已经做了类似的事情，Fastly 有他们的 [Lucet](https://www.fastly.com/blog/announcing-lucet-fastly-native-webassembly-compiler-runtime) 运行时，许多其他提供商也允许在边缘上计算。那些使用 JavaScript/WebAssembly 运行时的应用程序比容器和虚拟机有优势:代码开始运行的速度要快得多。Vercel 表示，它们可以在 5 毫秒内开始运行，而容器需要数百毫秒。边缘服务器只构建必要的内容并发送给客户端，而不是漂洋过海到 web 服务器寻求答案或将所有内容下载到客户端，然后让客户端决定显示什么。”

Cornwall 说，因此，Vercel 在 Next.js 12 中提供的是一种将你在边缘进行的计算集成到 Next.js 中的方法。“这使得 web 开发人员更容易编写在边缘运行的代码，就像他们目前在客户端为 React.js 编写代码一样，”他补充道。

例如，康沃尔描述了一个全球快餐连锁店的场景，该连锁店希望其澳大利亚客户看到基于澳大利亚价格和可用性的实时菜单，还希望其美国客户看到美国的菜单。

“当一个澳大利亚客户去 example.com/menu,时，我会在边缘服务器上建立一个澳大利亚菜单——而不必长途跋涉回到我在美国的服务器，”他说。“我的澳大利亚顾客看菜单的速度和我的美国顾客一样快。”

此外，这家快餐连锁店可能还在测试一种新的订购流程，它可以向那些表示愿意成为测试者的客户提供，但该公司还不想向所有人发布。

“Next.js 的集成使 web 开发人员更容易在 edge 上实现我的新订购流程，”Cornwall 解释道。“如果我检测到要求 example.com/menu 的用户在测试程序中，边缘服务器将建立一个包括新订购流程的菜单，这是由 Next.js 中编写的代码控制的。”

最后，Next.js 12 中的其他新特性包括:

*   [Checkly](https://www.checklyhq.com/) 集成了 [Vercel 检查](https://vercel.com/docs/concepts/deployments/checks):检查使用户能够在构建后立即确保正确性和 Web 重要性能，防止错误和不良性能进入生产
*   粒度缓存和带有[的](https://vercel.com/blog/everything-about-react-server-components)[增量静态再生(ISR)](https://vercel.com/docs/concepts/next.js/incremental-static-regeneration)React 服务器组件:用户现在可以在服务器端获取数据，并使用零客户端 JavaScript 将这些结果以增量方式传输到浏览器。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>