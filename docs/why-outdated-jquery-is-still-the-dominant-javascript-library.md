# 为什么过时的 jQuery 仍然是占主导地位的 JavaScript 库

> 原文：<https://thenewstack.io/why-outdated-jquery-is-still-the-dominant-javascript-library/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是 New Stack 的高级编辑，每周撰写一篇关于网络和应用程序发展趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。在 Twitter @ricmac 上关注他。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

jQuery 是 web 上运行时间最长、最有影响力的 JavaScript 库之一。根据 BuiltWith 的数据，在排名前 100 万的网站中，惊人的 78%以某种方式使用 jQuery。至于今天谈论最多的 JavaScript 库 React，它的使用率相对来说只有 14%。

jQuery 早在 2006 年推出，当时“Ajax”一词正处于顶峰。Ajax(异步 JavaScript 和 XML)和早期 Web 2.0 时代的其他 JavaScript 技术已经远离了开发人员的日常用语。但是 jQuery 经受住了时间的考验。事实上，直到最近，它还在逐年增长。为了了解这项持久技术的最新进展，我采访了一位继续维护 jQuery 的开发人员。

go biowski-Owczarek 是本月早些时候在 OpenJS 基金会的博客上发表的两篇文章的合著者，这两篇文章讨论了 jQuery 项目中正在进行的“现代化工作”。[第一篇文章](https://openjsf.org/blog/2021/10/07/jquery-maintainers-update-and-transition-jquery-ui/)宣布了 jQuery UI 的新版本——一个建立在核心 jQuery 库之上的用户界面库。这将是“项目的最终计划发布”，意味着 jQuery UI 现在“处于仅维护模式”[第二个帖子](https://openjsf.org/blog/2021/10/07/deprecation-of-jquery-mobile/)宣布弃用 jQuery Mobile，这是 jQuery 的另一个子项目，为移动浏览器提供“基于 HTML5 的用户界面系统”。

这两个项目自 2018 年成为 OpenJS 基金会的“荣誉项目”以来，一直在逐步减少。然而，这两个声明都没有影响到所谓的 jQuery 核心项目，该项目仍然是 OpenJS 基金会的“影响项目”。换句话说，主要的 jQuery 项目不会很快消失。

## WordPress 因素

尽管 jQuery 的使用非常广泛，但是今天的开发人员可能甚至没有意识到他们正在使用 jQuery。这是因为它被嵌入到许多大型项目中——最显著的是 WordPress 平台。许多 WordPress 主题和插件依赖于 jQuery。jQuery 库也是一些当今最流行的 JavaScript 框架和工具包的基础层，如 AngularJS 和 Bootstrap(4.0 及以下版本)。

“关于 jQuery 使用统计的许多惊奇来自于生活在泡沫中，”Go . biowski-Owczarek 告诉我。“大多数网站都不是需要复杂框架的复杂网络应用程序，它们大多是静态网站，带有一些动态行为——通常使用 WordPress 编写。jQuery 在那里还是很受欢迎的；它很有效，也很简单，所以人们不会觉得有必要停止使用它。”

jQuery 在未来一段时间内仍将是 WordPress 的一部分，如果没有其他原因，在不破坏向后兼容性的情况下移除它是很困难的。但我问 Go biowski-Owczarek，WordPress 是否有可能最终摆脱对 jQuery 的依赖？

“我认为这已经部分发生了，”他回答道。“WordPress 创建的古腾堡编辑器并不依赖于 jQuery。因此，至少在管理方面，他们有不依赖于它的变化。”

他预计，随着时间的推移，WordPress 将转向更新的技术，但这将是一个渐进的过程。

在 WordPress 开发者社区中，“在 WordPress 主题中使用 jQuery 的性能影响”是一个热门话题。甚至有一个名为“[你可能不需要 jQuery](https://youmightnotneedjquery.com/) 的参考网站，提供了如何在你的 WordPress 应用程序中替换 jQuery 的技巧。它的推理包括这样一个事实:对于现代浏览器，“除了浏览器自带的东西，你可能不需要任何东西。”

然而，[的另一个文档](https://docs.google.com/document/d/1LPaPA30bLUB_publLIMF0RlhdnPx_ePXm7oW02iiT6o/edit)警告说“开发人员应该意识到抛弃像 jQuery 这样的库很容易需要大量的研究来避免错误(即使是在现代浏览器中)。”所以尽管事实上"[jQuery 已经死了吗？文章已经流传了好几年了，至少在 WordPress 的生态系统中它仍然很活跃。开发商被鼓励替换它，但风险自负。](https://blog.logrocket.com/using-jquery-in-2019/)

## jQuery 的角色是…

那么 jQuery 是如何嵌入到今天的 web 中的呢？回答这个问题需要一点历史。

2006 年 1 月在 BarCampNYC，jQuery 创始人约翰·瑞西格在 T2 发布 jQuery 时写道“这段代码彻底改变了 Javascript 与 HTML 交互的方式”他主要指的是 jQuery 让开发人员更容易使用 DOM(文档对象模型)这一事实。请记住，这是在谷歌浏览器出现之前，所以这是一个浏览器创新很少的时代。微软的 Internet Explorer 拥有 85-90%的浏览器市场，IE6 是主要版本。即使在那个时候，IE6 也因历史上糟糕的浏览器而闻名于[。](https://www.pcworld.com/article/535838/worst_products_ever.html)

西蒙·威廉森在 2006 年 6 月的一篇文章中提到了 JavaScript 开发者在浏览器上遇到的一些问题:

*“JavaScript 中有许多问题(大部分源于浏览器的不兼容性)，任何中等复杂的应用程序都需要处理——比如规范化事件处理、DOM 节点选择、sane 动画或拖放。”*

这是 Resig 着手解决的问题，尽管 jQuery 本身并没有在 Willison 的帖子中提到。当时“四大”领先的 JavaScript 库是 Dojo、MochiKit、Prototype/Scriptaculous 和 Yahoo UI 库。大约一年后，在一篇博客文章[中，威廉森承认他最初认为 jQuery 是“一个可爱的黑客”，但现在认为它是“一个非常聪明的工程”](https://simonwillison.net/2007/Aug/15/jquery/)

所以基本上，jQuery 是为了帮助开发者解决当时浏览器的不足而发明的。

## …jQuery 现在的角色

当主流浏览器(甚至是 Safari！)更符合 web 标准？此外，JavaScript 标准本身在过去十年中也得到了显著改善，尤其是在 2015 年 ECMAScript 6 发布之后。

如上所述，React 已经成为当今谈论最多的 JavaScript 库。现代框架，尤其是 Next.js，都是建立在 React 之上的。其他流行的框架，比如 Angular(Angular js 的继任者)有自己的库生态系统。今天的 JavaScript 框架也允许你将 UI [分解成组件](https://blog.logrocket.com/the-history-and-legacy-of-jquery/)，使得应用程序更容易升级。

“这些框架提供了数据和视图之间更容易同步的抽象，”Go biowski-Owczarek 在谈到 Next.js 和 Angular 等公司时说。因此他们的用户不再需要如此频繁地直接修改/访问 DOM，并且通常不鼓励这样做。在这样的环境下，使用 jQuery 没有太大意义。但这只是整个网络生态系统的一小部分。”

然而，Go biowski-Owczarek 承认，对于大规模应用程序，jQuery 可能存在性能问题。

“这些年来，我们已经提高了 jQuery 的性能，”他说，“但是还有一些很难处理的障碍。其中之一是为了不与浏览器冲突，jQuery 不像其他一些库那样修改本机原型(后来常常会导致冲突 API 的标准化问题)，而是用 jQuery 包装器对象包装 DOM 节点。对这种包装器的每个操作都会创建一个新的。在大多数情况下，这并不重要，但是对于需要大量 DOM 操作的非常复杂的应用程序，这有时会成为一个问题。”

## 结论

很明显，对于开发人员来说，jQuery 不再是向他们的网站或应用程序添加 JavaScript 功能的最佳方式，尤其是当它需要扩展时。事实上 [GitHub 对 jQuery 的贡献](https://github.com/jquery/jquery/graphs/contributors)已经远远低于其巅峰时期(2006 年到 2013 年左右),这也意味着已经没有太多的事情可以让 jQuery 与我们当前的网络更加兼容了。

但是没关系。鉴于 jQuery 是在 Web 2.0 的早期出现的，它比大多数开发人员预期的时间要长得多。毕竟，它仍然完成了它设定的任务，它仍然是一个方便开发人员使用的 JavaScript 库。

无论如何，在未来几年，jQuery 将会嵌入到数千万的 WordPress 网站中。它甚至可能比反应更持久。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>