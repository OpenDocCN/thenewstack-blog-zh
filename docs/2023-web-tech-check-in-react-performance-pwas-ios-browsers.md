# 2023 年网络技术签到:反应性能、PWAs、iOS 浏览器

> 原文：<https://thenewstack.io/2023-web-tech-check-in-react-performance-pwas-ios-browsers/>

当 Figma 去年把自己卖给 Adobe 时，从某种意义上说，这是网络标准的胜利。Figma 建立在 WebGL、JavaScript 和(后来的)WebAssembly 之上。这是网络技术持续强大的另一个标志，在许多情况下，网络技术现在就像本地应用一样强大。

然而，当我们进入新的一年时，仍然有几个问题是 web 标准观察者所关心的。在这篇文章中，我们检查了三个最重要的问题:过度依赖 React 导致的 JavaScript 性能问题，渐进式网络应用的进展(或不进展)，以及苹果是否有任何迹象向外部浏览器引擎开放其 iOS 平台。

## React 及其对 JavaScript 生态系统的影响

React 在 JavaScript 社区中越来越受欢迎，然而，人们对它给浏览器带来的巨大负载越来越不满——这对许多用户来说意味着性能问题。

[据微软 Edge 团队的亚历克斯·罗素](https://infrequently.org/2022/12/performance-baseline-2023/)称，“网站继续发送超过世界 80%以上用户合理水平的脚本，扩大了富人和穷人之间的差距。”

Russell 称这是“前端的道德危机”,并把责任完全归咎于 React 和利用它的框架。他引用了加利福尼亚州政府网站 CA.gov 的例子，该网站运行缓慢是因为“一个官方的 Twitter 插件，出于某种该死的原因，是使用 React、Next.js 和完整的现代恐怖游行构建的。”

我联系了 Russell，问他对开发者、React 粉丝或其他人有什么建议，因为他们正在考虑 2023 年初的工艺。

“我对开发人员和项目经理的建议是，在开发过程中首先要有代表性的设备进行测试，”他回答道。“没有什么能代替真正的感受。人们可以通过在 CI 中运行类似 webpagetest.org 的东西和/或采用绩效预算来取得进步。”

至于哪些前端框架将在 2023 年使用，React 和它的兄弟们似乎不太可能很快离开。但是至少在输出较少代码的新框架中[鼓励了增长](https://2022.stateofjs.com/en-US/libraries/front-end-frameworks/)——像[苗条](https://thenewstack.io/svelte-and-the-future-of-front-end-development/)和[轻盈](https://thenewstack.io/polymers-web-component-library-litelement-and-how-it-compares-to-react/)。

## PWAs:良好的浏览器支持，但移动平台不感兴趣

渐进式网络应用程序(pwa)基本上是网站，但它们具有类似于原生 iOS 或 Android 应用程序的功能。我在 2021 年报道了 PWAs 的先进能力。从那以后，pwa 的力量继续增长，这主要归功于谷歌及其[项目 Fugu](https://www.chromium.org/teams/web-capabilities-fugu/) (但也归功于谷歌 Chrome 团队在这一功能方面的灵活性)。

[Thomas Steiner](https://blog.tomayac.com/) ，府谷项目的开发者支持者，向我介绍了该项目最近的进展。他对许多 API 越来越多的跨浏览器支持特别满意。

他说:“跨浏览器的巨大成功绝对是起源私有文件系统(OPFS)协议。”。“这开启了全新的用例，比如编译成 Wasm 并由 OPFS 支持的 [SQLite。现在有更多的 API——像 Web 编解码器、屏幕唤醒锁和异步剪贴板等——支持跨浏览器。在 Fugu 团队，2023 年的大主题是](https://developer.chrome.com/blog/sqlite-wasm-in-the-browser-backed-by-the-origin-private-file-system/)[完善现有的 API](https://developer.chrome.com/blog/is-project-fugu-done/)。

因此，浏览器厂商似乎在很大程度上支持 PWAs。然而，移动开发平台仍然对整合网络技术不感兴趣——包括谷歌自己的 Android 团队，正如 Chris Coyier 本月早些时候指出的。科伊尔提到了 Android 开发者文档，其中列出了 Kotlin、Java 和 C++作为其支持的语言，并俏皮地评论道:“你不是在建立一个网站。这里没有列出任何网络技术。”

对于终端用户来说， [Appscope](https://appsco.pe/) 是 PWAs 的目录，包括 Instagram、Twitter、Telegram。**更新:**一位读者指出 [Project Fugu 的 API showcase](https://developer.chrome.com/blog/fugu-showcase/) 更新更快。

## 苹果浏览器禁令:迫于压力，但仍无行动

PWAs 的另一个令人沮丧的地方是苹果用户最不可能使用它们。这是因为苹果公司长期以来决定禁止其 iOS 平台上的竞争浏览器引擎。通过迫使谷歌、微软和 Mozilla 等浏览器供应商使用 WebKit 浏览器引擎，苹果故意限制 iOS 上网络应用的功能——这尤其影响了 PWAs。

到目前为止，苹果还没有对外开放浏览器引擎。然而，英国垄断监管机构竞争和市场管理局(CMA)施加了一些压力，该机构于 2021 年启动了一项移动生态系统市场研究。2022 年 6 月，CMA 在[公布了它的报告结果，称](https://www.gov.uk/government/news/cma-plans-market-investigation-into-mobile-browsers-and-cloud-gaming)它正在“就启动对苹果和谷歌在移动浏览器市场势力的市场调查进行咨询”然而，尚未采取任何强制行动。

然而，去年年底，当一份[报告](https://www.bloomberg.com/news/articles/2022-12-13/will-apple-allow-users-to-install-third-party-app-stores-sideload-in-europe#xj4y7vzkg)浮出水面，称苹果正在[考虑](https://www.macrumors.com/2022/12/14/apple-considering-non-webkit-iphone-browsers/)取消 iPhone 和 iPad 网络浏览器使用 WebKit 的要求时，还是有一些新的希望。苹果引用欧盟的数字市场法案作为动机。然而，没有给出时间框架。

据一直站在向苹果公司施压的前沿的[开放网络倡导](https://open-web-advocacy.org/)组织的马修·托马斯称，世界各地的政府机构将继续受到压力。

“我们一直在与世界各地的许多监管机构沟通，包括英国资本市场管理局、澳大利亚 ACCC、日本 HDMC、美国 NTIA 和欧盟的一些监管机构，”他告诉我。“我们的主要目标是取消苹果的 2.5.6 规则(在苹果的应用商店审查指南中)，禁止竞争对手的浏览器引擎，但更广泛地说，我们专注于增加浏览器竞争，增加本地应用和网络应用之间的竞争。”

托马斯说，“世界各地的许多监管机构正在认真调查这些问题。”

他引用欧盟的数字市场法案作为 OWA 的一个成功故事。“我们设法让浏览器、浏览器引擎和网络应用程序成为法案的最终文本，”他指出。

## 结论

上述三个问题表明，试图解决这三个突出问题的势头很大，特别是来自谷歌、微软和 Mozilla 的浏览器团队，以及像 OWA 这样的独立团体。

然而，上述更新也表明，大平台——苹果 iOS、谷歌的 Android 部门和 Meta——不会自愿放弃各自领域的权力。即使使用 React，从平台能力的角度来看，这是三个问题中问题最少的，也没有什么迹象表明 Meta 关心与该方法相关的性能问题。

但我想以一个充满希望的音符结束，所以也许 2023 年是网络最终在 iOS 上突破的一年，前端开发人员开始更多地关注最终用户的性能。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>