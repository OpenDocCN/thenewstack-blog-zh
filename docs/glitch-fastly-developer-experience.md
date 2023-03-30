# Fastly Matrix 中的故障:这与开发人员的体验有关

> 原文：<https://thenewstack.io/glitch-fastly-developer-experience/>

云计算公司 Fastly 上周宣布[收购 Glitch](https://www.fastly.com/blog/fastly-announces-acquisition-of-glitch-a-future-of-yes-code-at-the-edge) ，这是一款流行的基于浏览器的应用创建工具。Fastly 在 21 世纪初以内容交付网络(CDN)起家，但如今它将自己定位为“边缘云平台”。因此，Glitch 将非常适合 Fastly 不断增长的云工具套件。Glitch 用户将(大概)获得更快的网络，而 Fastly 的客户将获得新的开发工具。

但是，Glitch 会不会不仅仅是法斯特丽工具箱中的一个补充品呢？为了找到答案，我采访了 Fastly 的联合创始人兼战略计划副总裁[西蒙·威斯特夫](https://www.linkedin.com/in/simonwistow/)。

## 欢迎来到边缘

在 LinkedIn 上对 Glitch 收购的评论中， [Wistow 写道](https://www.linkedin.com/feed/update/urn:li:activity:6933047850381574146/)“我们将改变人们建立网站和应用的方式。”我问他那是什么意思？

他回答说，这“可以追溯到 Fastly 的起源故事”，他和他的联合创始人在 2011 年开始创建一家基于边缘计算的 CDN 公司。根据 Wistow 的说法，像 Akamai 这样的传统 cdn“植根于 90 年代末关于网站是什么的想法。”对于 Fastly，[他们的目标是](https://www.fastly.com/blog/fastly-looks-back-10-years-of-fond-memories)“将更多的代码和逻辑移到边缘。”

> “如果我们给人们一种通用编程语言，那么他们可以在边缘做更多的事情。”

西蒙·威斯特，法斯特丽的联合创始人

“如果你要能够缓存动态内容，”他继续说，“你需要能够将一些逻辑从原点移开，去做一些事情，比如负载平衡，或者付费墙，或者出售 cookies，或者各种不同的事情。如果你要把一些逻辑从原点移开，你还不如给人们一种通用编程语言。当你开始这样想时，如果我们给人们一种通用编程语言，那么他们可以在边缘做更多的事情。”

这一理念促使 Fastly 在 2019 年 11 月推出了一项名为 [Compute@Edge](https://www.fastly.com/products/edge-compute) 的服务，CTO Tyler McMullen [当时将其描述为“在网络边缘构建无服务器应用的强大、灵活和可扩展的方式。”它以 WebAssembly 运行时为特色，并支持 Rust 和 JavaScript 等现代语言。](https://www.fastly.com/blog/join-the-beta-new-serverless-compute-environment-at-the-edge)

## Glitch 增加了开发体验

据 Wistow 称，Glitch 为 Fastly 增值的地方在于开发人员的体验。“仅仅是能够将 JavaScript 运行到边缘就将成为赌注，”他说，指的是 Fastly、Cloudflare 和 Netlify 等 CDN 公司。

“这将成为开发者的体验，”他说，“以及人们如何容易地启动并运行”一个新项目。“我认为 Glitch 无疑是网络上最容易起步的地方。”

在我去年对 Glitch 的评论中，我注意到它的部分吸引力在于它给今天的网络带来了 20 世纪 90 年代的“查看源代码”精神。它让用户看到代码中真正发生了什么，但也通过抽象掉其他复杂性来保持事情的简单。出于这个原因，Glitch 是广大开发人员最喜欢的游戏工具——从业余程序员到专业人员。我知道许多有经验的开发人员使用 Glitch 来运行他们的爱好项目，而对于新手来说，这项服务是学习编码的一个极好的方法。

“我们在 Fastly 内部使用它，用于很多东西，”Wistow 谈到 Glitch 时说。“我们用它来做内部工具，我们用它来做销售——工程师用它来为我们的客户演示东西。我们的客户使用它。”

## Fastly vs. Cloudflare、Vercel 和 Netlify

从市场的角度来看，Glitch 的收购迅速向直接针对前端开发人员的公司靠拢，如 Vercel 和 Netlify，这两家公司都提供以开发人员为中心的平台，也利用了边缘网络。

随着时间的推移，CDN 公司变得更加关注开发者已经成为一种趋势。见证 Fastly 的直接竞争对手 Cloudflare 的最新举措，它最近推出了用于平台(使开发者能够“编程事件如何工作”)和 [Web3 网关](https://blog.cloudflare.com/next-gen-web3-network/)的[工人。这两项举措都旨在吸引新开发人员加入 Cloudflare 平台。虽然 Fastly 在构建其开发者平台方面没有 Cloudflare 那么忙，但收购 Glitch 将会给它带来提振。](https://blog.cloudflare.com/workers-for-platforms/)

> “能够将代码从原始位置转移到这些边缘计算环境中有很多优势。”

但是开发者使用 Fastly 这样的 CDN 公司作为他们的开发环境有什么好处呢？

“在中央云中运行有一些缺点，”Wistow 说，“不管人们怎么说，在多个数据中心运行东西并不容易。[……]因此，能够将代码从原点转移到这些边缘计算环境中有很多优势，在这些环境中，您 a)更接近您的用户，b)地理上分散，非常非常可扩展。”

## 未来平台

最后，我问了 Wistow 他对新兴开发者平台的看法，比如元宇宙和 Web3，以及 Fastly 在这些领域可能会看到哪些机会？

他回答说，Glitch 是一个领先的“运行 WebVR 东西”的平台，“有一些插件，你可以从 Unity 导出到 Glitch。”因此，他对 Glitch 如何服务于下一代开发人员感到兴奋。

“有一代人学会了如何编码，以便定制他们的 LiveJournals(一个早期的博客平台)，然后是他们的 MySpaces，之后的下一代人用 Roblox 之类的东西做了同样的事情。因此，如果元宇宙真的成功了——我不认为这是有保证的，但你知道，这背后有很大的营销力量——(那么)给人们一个平台，让他们可以去建立自己的元宇宙东西是非常重要的。你可以看到下一代学习如何在 Glitch 这样的平台上编码，去驱动元宇宙。”

> “我们希望成为网络的未来，但我们也希望成为一个平台，人们可以在这个平台上构建网络的未来。”

他对 Web3 持怀疑态度，但不管怎样，他希望构建网络未来的人们能够快速使用它。

“这是试图让人们更容易发布复杂数据应用程序的想法，”他说。“我们一直将 Fastly 视为其他人构建的平台。我们希望成为网络的未来，但我们也希望成为一个平台，人们可以在这个平台上构建网络的未来。”

很容易将 Glitch 视为开发者构建未来原型的应用。这些原型是否会成为网络的未来还有待确定。无论如何，收购 Glitch 是 Fastly 的一个明智之举，并使其成为对开发者更具吸引力的平台。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>