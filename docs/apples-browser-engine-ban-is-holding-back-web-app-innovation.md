# 苹果的浏览器引擎禁令阻碍了网络应用的创新

> 原文：<https://thenewstack.io/apples-browser-engine-ban-is-holding-back-web-app-innovation/>

著名的苹果博主约翰·格鲁伯最近在推特上引起了一场轩然大波，因为他[建议](https://twitter.com/gruber/status/1438356519951683584)网络开发者“不应该试图在网络浏览器中创建一个‘类似本地的应用程序’。”格鲁伯说，这与越来越多的批评苹果不允许在其 iOS 平台上竞争浏览器引擎有关。通过强制谷歌、微软和 Mozilla 等浏览器厂商使用 WebKit 浏览器引擎，苹果在有意限制 iOS 上的网络应用功能。这就是为什么[渐进式网络应用](https://thenewstack.io/was-parler-really-a-progressive-web-app/) (PWAs)的许多功能无法在 iPhone 或 iPad 上运行。

尽管格鲁伯对苹果专有的 iOS 平台有明显的偏见，但他确实提出了一个有趣的哲学问题:在试图模仿本地应用的高级功能方面，网络应用应该走多远？要回答这个问题，我们首先需要了解 web 应用已经走了多远。

## 网络应用的简史

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇关于 web 和应用程序开发趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。在 Twitter @ricmac 上关注他。](https://twitter.com/ricmac) 

在其历史的大部分时间里，web 一直是应用程序和网页的平台。尽管它在 1991 年开始时是一个以文档为中心的平台，但早在 1993 年，随着 CGI 脚本的出现，网络开始演变成一个应用平台。网景公司和微软公司都在 90 年代中后期将他们的网络浏览器转变为网络应用平台，到了 2000 年代早期，我们有了 Ajax 应用——所谓的 Web 2.0 时代的主要驱动力。

格鲁伯反对将网络作为应用平台的论点是在 2000 年代末苹果 iOS 和谷歌 Android 的到来时发挥作用的。这使得互联网变成了一个主要由智能手机驱动的应用平台。众所周知，Instagram 在 2010 年推出时是一款仅支持 iOS 的应用，完全忽略了网络(它在 2012 年增加了一款 Android 应用)。即使到今天，Instagram 的网络浏览器功能仍然有限。因此，在 2010 年代初，随着 iOS 和 Android 开始主导互联网格局，网络在某种程度上被抛在了后面。

然而，在过去的几年里，我们已经看到网络作为一个应用开发平台再次出现。这不仅归功于像 React 这样的 JavaScript 驱动的前端框架，也归功于最近 web 标准的进步。后者在很大程度上要归功于由苹果、谷歌、Mozilla 和微软运营的 [WHATWG](https://whatwg.org/) (网络超文本应用技术工作组)。WHATWG 运营着它所谓的 HTML“生活标准”,该标准随后被[万维网联盟](https://www.w3.org/) (W3C)采纳为官方网络标准。

问题是，尽管谷歌、微软和 Mozilla 都全力推进网络平台，但苹果不想削弱其 iOS 平台的受欢迎程度。它希望下一个 Instagram 建立在 iOS 上，而不是作为 PWA 推出！这就把我们带到了苹果将 iOS 上的网络浏览器引擎限制为自己的 WebKit 引擎的争议立场。

![](img/b329aab5337ab7b3c54a796e0f16f726.png)

Instagram 仅在 2010-11 年作为 iOS 应用提供。它在 2011 年的网站是 brochureware。

## WebKit 和 Blink 的区别

苹果的决定很大程度上是为了在 iOS 上阻挡谷歌的技术。谷歌牵头开发的 Blink 浏览器引擎，作为开源 Chromium 项目的一部分，是 Chrome 在桌面、安卓以及除 iOS 之外的所有其他操作系统上绝对至关重要的一部分。相比之下，iOS 用户可以下载的 Chrome 版本就相形见绌了，该版本使用的是 WebKit 而不是 Blink。

Blink[项目的既定任务再清楚不过了，它的应用功能目标是什么。它的使命是“让网络成为体验世界信息的首要平台，并提供世界上最好的网络平台实施方案。”这意味着 Blink 希望其引擎直接与本地应用竞争，成为消费者互联网的“首要平台”。](https://www.chromium.org/blink)

虽然 WebKit 也是开源的，但它宣称的目标并不是以应用程序为中心。WebKit 被定位为“内容引擎”——这是一种微妙的方式，告诉我们网络浏览器应该留在自己的车道上，坚持内容，而不是全功能的应用程序。相比之下，Blink 自称为“渲染引擎”，这是一个更开放的定义(应用程序和网页都被渲染)。此外，WebKit 项目声明，如果 WebKit 要在应用程序中使用，那么它应该是一个配角，而不是主角:“……我们还希望能够将 WebKit 嵌入到其他应用程序中，并将其用作通用的显示和交互引擎。”

“其他应用”显然指的是 iOS 应用，这是苹果的主要开发平台。

## 那么为什么 Web 应用要和原生应用竞争呢？

上述问题的答案很简单:应该允许 web 应用程序与本地应用程序竞争，因为 web 是一个开放的平台，允许开发者“编写一次，在任何地方运行”*反对*网络应用的理由往往更加复杂和脆弱。

约翰·格鲁伯(John Gruber)等苹果粉丝认为，在 iOS 设备上，最好使用原生 iOS 开发平台来创建复杂的应用程序。在他与网络应用粉丝的推特之战中，[他引用了](https://twitter.com/gruber/status/1438319377200394248)“电池寿命、安全性、隐私和反对 Chrome 统治整个网络的立场”作为他支持苹果禁止第三方浏览器引擎的一些原因。他后来在帖子中补充说，“原生应用提供了更好的用户体验。”

他们当然知道。格鲁伯故意没有提到的是，苹果在 iOS 上禁止第三方浏览器引擎，这抑制了网络应用的创新。运行在 Android 上的现代 pwa 越来越多地提供与 Android 上的原生应用一样好的用户体验。然而在 iPhone 上，本地应用程序比 pwa 更好是毋庸置疑的——但这仅仅是因为苹果不允许第三方浏览器使用所有的网络应用技术。

不仅仅是 iOS 上的浏览器引擎缺乏选择，而是 WebKit 本身作为浏览器引擎有所欠缺。亚历克斯·罗素，现在是微软 Edge 的合作伙伴项目经理，但在此之前，他在谷歌 Chrome 担任了多年的高级工程师，他写了大量关于[苹果的网络策略](https://infrequently.org/2021/08/webkit-ios-deep-dive/)。当他还在谷歌的时候，他发表了一篇[对 WebKit](https://infrequently.org/2021/04/progress-delayed/) 的长篇评论，结论是“苹果的网络引擎在兼容性和功能上一直落后于其他公司，导致了与苹果原生平台的巨大和持续的差距。”

## 构建更好的应用程序

在这里总结一下，原生应用程序只比 iOS 上的 web 应用程序好，因为 a)苹果阻止其他浏览器供应商使用他们首选的浏览器引擎，b)苹果的 WebKit 在应用程序功能方面没有跟上 Chromium 之类的应用程序。因此，网络应用无法与 iOS 应用完全竞争的事实是苹果的问题，而不是网络的问题。

web 应用应该渴望等同于原生应用吗？他们当然应该这样做，因为在 web 上运行应用程序有着悠久而丰富的历史——可以追溯到 1993 年。由于智能手机应用程序，网络应用程序在 2010 年代初脱离了轨道。但是现在，由于 web 标准和围绕开源 web 引擎的创新，web 再次成为一个令人兴奋的开发平台。见鬼，也许下一个 Instagram 终究会建立在网络上！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>