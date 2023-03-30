# Glitch 带来了“查看源代码”的理念

> 原文：<https://thenewstack.io/glitch-brings-view-source-philosophy-to-react-node-js/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是 New Stack 的高级编辑，每周撰写一篇关于网络和应用程序发展趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

2021 年做开发者意味着什么？如果你使用一个无代码的工具，完全通过拖拽来构建一个应用，那你是一个开发者吗？如果你在 [Glitch](https://glitch.com/) 上“重新混合”(即复制)了一个现有的网络应用，并在其中修改了一些代码——这是否意味着你可以称自己为开发者？

那些生活在 C++中的开发人员，或者那些整天用 JavaScript 操纵 DOM 的开发人员，可能会看不起无编码人员和故障混血儿。的确，成为一名开发人员并不一定意味着你就是一名软件程序员。但是不可否认的是，在开发 web 应用程序时，无代码工具和 Glitch 的力量都在不断增强。

Glitch 是一个基于浏览器的应用创建工具，最近[宣布](https://blog.glitch.com/post/remix-a-whole-new-glitch)它现在可以让用户“在一分钟内”创建一个全栈网络应用正如 Glitch CEO [Anil Dash](https://twitter.com/anildash) 告诉我的那样，这“比你使用无代码工具或网站构建器构建它要快。”

这种速度是由于 React 应用程序、基于节点服务器的应用程序或 Eleventy 网站(更受欢迎的静态站点生成器工具之一)的新的现成模板。当然，这些模板都是非常基本的——例如，Node 应用程序模板是用于一个简单的颜色选择应用程序的。但它们是专业或业余开发人员使用我们每天听到的流行 web 开发框架创建网站或应用程序的起点:React、Node.js、Eleventy。

“Glitch 多年来一直有能力在浏览器中构建应用程序，”Dash 说，“但新的是性能的巨大飞跃，能够在一分钟内构建这些网站，独特的是他们使用完全标准的框架，能够定制构建过程，甚至创建全栈应用程序。”

## 降低编码的障碍

Glitch 是传统的[网站构建工具](https://thenewstack.io/gatsby-wants-to-be-orchestration-layer-for-building-websites/)(如 Squarespace 或 Wix)和低代码或无代码工具(如 OutSystems，我在去年 9 月对其进行了简介[)的混合体。它与两者的主要区别在于，对于 Glitch，我们鼓励您动手编写代码。“编码、协作，几秒钟内发货”是 Glitch 的营销口号。然而，对于网站构建者和低代码/无代码工具，重点是通过用户友好的界面(大多隐藏代码)来轻松构建网站或应用程序。](https://thenewstack.io/outsystems-pushes-low-code-beyond-its-visual-basic-legacy/)

去年 5 月，Dash 想出了一个聪明的术语来描述 Glitch 相对于低代码/无代码工具所做的事情:他声称，这是一个[是的代码](https://www.linkedin.com/pulse/code-great-heres-why-we-need-yes-anil-dash/)工具。他提出的观点之一是“能够编码是一种超能力，我们应该通过降低门槛，让更多的人能够利用这种能力。”实现这一点的关键是 Glitch 的重新混合功能，用户可以在平台上复制现有的应用程序，并根据自己的目的调整代码。

如果你年纪够大，还记得 20 世纪 90 年代的网络，你会意识到这是创建网站的“查看源”哲学的更新。当时，查看您欣赏的网站的源代码并将其复制粘贴到 Dreamweaver 或 Microsoft Frontpage 等工具中是很常见的。您甚至可以浏览 CGI 脚本或 JavaScript 目录，并从那里复制和粘贴一些代码(例如，创建一个表单，或添加一些滚动文本)。即使你不是程序员，我们中的许多人从 20 世纪 90 年代的网络开始熟悉 HTML 代码、CSS、JavaScript 甚至 Perl 或 Python 之类的东西——仅仅是因为我们定期查看源代码。

这基本上是 Glitch 现在试图实现的，只是在 2021 年有更复杂的开发框架可以使用。例如，React 是一个非常受欢迎的 JavaScript 库，用于创建我们在今天的 web 上看到的许多单页应用程序(spa)。

Glitch 试图降低编码壁垒的另一种方式是自动化大部分后端工作。这类似于 [Vercel](https://thenewstack.io/vercels-frontend-and-the-rise-of-the-hybrid-developer/) 或 [Netlify](https://thenewstack.io/why-netlify-is-tech-agnostic-and-its-role-in-jamstack-development/) 等公司的[无服务器](https://thenewstack.io/serverless-has-unlocked-a-new-world-of-cloud-mashups/)方法。

Dash 说:“以前独立的手动步骤，如配置构建脚本、安装安全证书，甚至在修改代码时提交 git，都可以在 Glitch 上自动处理。”

同样值得强调的是，Glitch 正在利用的技术——如 React、Node.js 和 Eleventy——都是开放框架。Dash 说这尤其是 Glitch 和站点构建工具之间的一个不同点。

“在 Glitch 上，”Dash 说，“用这些新的启动器构建的应用程序使用完全标准、流行的开放框架，如 React 或 Eleventy，所以没有对平台的锁定，因为它只是常规代码(不像模板化的网站构建器)，网站在一个安全的 URL 上运行，可以立即共享。开发者甚至可以点击几下就添加他们自己的域名。”

## 浏览“矩阵”代码

Glitch 的部分吸引力在于它将 20 世纪 90 年代的“查看源代码”精神带到了今天的网络中。它让您看到代码中真正发生了什么，同时也通过抽象掉其他复杂性来保持事情的简单。这在当今是非常罕见的事情。你最近看过一个 SPA 的源代码吗？它的大部分是令人费解的，非常违背“查看源”的精神。

以 Gmail 为例——如果你在浏览器中查看它的源代码，就像在看“黑客帝国”的代码。这是因为，正如一位名为 [Jim Nielsen 的开发人员解释的那样](https://blog.jim-nielsen.com/2020/the-spirit-of-view-source/)，你能够看到的源代码“很可能是一些工具通过一系列模板将内容和标记缝合在一起，然后将其放大/缩小以通过网络交付的结果。”

另一方面，当我在 Glitch 上使用 React 和 Node.js 模板时，所有代码都显示得很好，很容易导航。事实上，我非常想“重新组合”Node.js 模板，修改几行代码，并在 Twitter 上宣布我现在是一名全栈开发人员。我没有走那么远，但是能够再次查看(并理解)源代码是很好的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>