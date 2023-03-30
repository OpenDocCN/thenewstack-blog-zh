# JavaScript 开发人员关注什么是重要的，下一步是什么

> 原文：<https://thenewstack.io/javascript-developers-on-what-matters-and-whats-next/>

根据 Geeks for Geeks 的调查，超过 72%的公司正在寻找 JavaScript 开发人员。随着语言的不断发展，这种情况似乎不会很快改变。

“JavaScript 在网络开发中越来越受欢迎，并且已经成为了 [Jamstack 生态系统](https://thenewstack.io/10-jamstack-startups-to-empower-frontend-developers/)的基石，”[开发平台 Netlify 的开发者体验副总裁 Jason Lengstorf](https://www.linkedin.com/in/jlengstorf/) 告诉 New Stack。“由于该语言对 web 构建者的广泛适用性，公司投资推动该语言向前发展，这解释了为什么许多组织都对 ES2022 版本的语言规范做出了贡献。”

JavaScript 的最新版本 [ECMAScript 2022](https://thenewstack.io/javascript-forecast-whats-ahead-for-ecmascript-2022/) ，在 6 月份做了 8 次更新。新的堆栈要求开发人员分享他们认为最重要的变化。

Lengstorf 说, [Netlify](https://www.netlify.com/) 特别关注这个版本如何帮助无服务器和 edge 功能做得更多。

Lengstorf 说:“有一些相当大的(和有些争议的)内含物，如顶级 await，这对许多开发者来说是一个受欢迎的补充，但一些专家认为它是一个 [footgun](https://en.wiktionary.org/wiki/footgun) 会绊倒那些不知道它在引擎盖下如何工作的开发人员。”

根据 [ECMA 2022 语言规范](https://262.ecma-international.org/)，顶级 await 特性将“延迟当前和父模块的执行，直到导入的模块被加载”。根据标准，它允许模块使用运行时值来确定依赖关系，并且可以用作依赖关系的后备。

Lengstorf 说，他很高兴看到的一件事是。at()方法，该方法现在受 Array、String 或 TypedArray 支持。这将支持 JS 数组的负索引，这是其他编程语言已经允许的。根据软件工程师 Brayan Arrieta 的博客，它提供了编写 arr[-1]而不是 arr [arr.length-1]的能力，其中负数从最后一个元素向后计数。

“这是对 JavaScript 语法的一个很大的人体工程学的提升，”Lengstorf 说。

## 错误原因特征

Lengstorf 还强调了抛出错误的“原因”的引入，称它给了“库作者更多的途径来创建优秀的[开发者体验](https://thenewstack.io/developer-experience-is-essential-so-why-is-it-so-bad/)”

[T4 Agoric](https://www.linkedin.com/in/kkowal/)的软件工程师克里斯·科瓦尔也指出 Error.cause 功能是一个关键的升级。Agoric 是一个 JavaScript 本地智能合约平台，也是区块链的利益证明。

在 error.cause 中，error 对象及其子类现在允许开发人员指定哪个错误导致了当前的异常，原因显示在堆栈跟踪中，并可通过 err.cause 访问，根据 [web 开发人员凯·文泽尔对标准变化的简介](https://community.codenewbie.org/kai_wenzel/whats-new-in-javascript-after-the-es2022-release-1lef)。

“一个突出的特征是 Error.cause，”Kowal 告诉新的堆栈。ES2022 增加了一个习语，用于表达和检查错误之间的串行因果相关性，补充了 AggregateError，后者表达了对并行错误的因果相关性

他说，这些特性一起“使得对错误因果关系的思考成为可能”，这最终会在开发人员工具中显现出来。再加上将开始利用表达错误因果关系能力的库，“开发人员将更有能力收集关于失败根本原因的有用信息。”科瓦尔补充道。

“Error.cause 代表了 JavaScript 进化的最佳方式之一:通过填补其他功能的存在所隐含的空白来变得更加完整，”他说。

## 支持用户界面创建

SEO 公司 [Rank Secure](https://www.ranksecure.ca/) 的首席执行官 [Baruch Labunski](https://www.linkedin.com/in/baruchlabunski/?originalSubdomain=ca) 说，部分更新有助于开发人员加快用户界面的创建，并包括新的、“非常受欢迎的”UI 小部件。

“一个变化是允许那些使用 AngularJS 的人迁移到 AngularJS，因为对 Angular js 的支持已经停止，”Labunski 说。其他受欢迎的程序也收到了更新。部分更新是因为微软支持在 JavaScript 中添加类型语法，帮助程序员在他们的 JS 代码中添加类型注释。”

同样重要的是:Labunski 说，更新解决了两个损坏的库，它们的原始创建中包含恶意包。

## 下一步是什么？

Agoric 通过其首席技术官兼首席科学家马克·米勒(Mark Miller)在 ECMAScript 会议上占有一席之地，自 20 世纪 90 年代中期作为谷歌代表加入以来，他一直是 ECMAScript 标准小组的成员。(请关注我们即将对米勒进行的关于 E 如何帮助塑造 JavaScript 的采访。)Agoric 在其区块链解决方案中使用了 JavaScript 的强化版本。

Kowal 说，在下一次迭代中，Agoric 希望看到区间支持

“随着一流的模块和模块资源进入该语言，我们将很高兴分享更多内容，以及允许我们安全地邀请访客程序在共享领域中运行的强化 JavaScript 的功能，”他说。

开发者[王自如](https://www.linkedin.com/in/shawnswyxwang/)，又名@ [swyx](https://www.swyx.io/) ，记录了 JavaScript 的[进化，并声称](https://www.swyx.io/js-third-age) [JavaScript 正处于其第三个时代](https://thenewstack.io/the-third-age-of-javascript-an-update-from-reactathon/)。他期待的一个变化是临时提案，它处于四阶段提案流程的第三阶段。

“这可能是最受期待的即将推出的功能，其中基本上所有的日期格式，如今天的日期减去一个月意味着什么？”王说。有各种复杂的日期逻辑，包括格式，但也包括像日期数学，…有时它有点模糊。"

尽管这种语言受到了批评，但在可预见的未来，JavaScript 似乎仍将存在。

“是的，它有问题，但它工作，”王告诉新堆栈。“它到处跑。这是一个需要克服的巨大优势。…是的，如果你有一种特定于领域的语言，可以在其他任何东西都无法运行的新平台和设备上使用，那么你当然可以创造自己的语言。但除此之外，JavaScript 可以运行任何东西。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>