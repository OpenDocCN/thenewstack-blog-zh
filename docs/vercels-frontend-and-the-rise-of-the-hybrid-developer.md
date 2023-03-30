# Vercel 如何将前端开发者从后端负担中解放出来

> 原文：<https://thenewstack.io/vercels-frontend-and-the-rise-of-the-hybrid-developer/>

前端开发是 2020 年互联网技术令人兴奋的地方。为什么？因为后端在这一点上已经基本完成了。正如 [Vercel](https://vercel.com/) 联合创始人兼首席执行官 [Guillermo Rauch](https://twitter.com/rauchg) 最近[所言](https://rauchg.com/2020/vercel)，“后端已经被云基础设施、Kubernetes 和现成的 API 商品化了。”

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇专栏文章，探讨云计算原生互联网的未来。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) 

劳赫认为前端提供了“最有趣的现代化新机遇。”在一次采访中，我与 Rauch 讨论了这些机会是什么，以及 Vercel 如何融入新兴的前端生态系统。

Vercel(以前称为 ZEIT)是多家资金雄厚的初创公司之一，它们采用 JAMstack 方法进行 web 开发，这种方法将后端与前端分离，消除了管理 web 服务器的需要。

然而，这并不意味着后端从开发人员的生活中完全消失——他们的应用程序或网站仍然需要构建和部署。尽管基础架构现在可能已基本商品化，但其配置和管理比以往任何时候都更加复杂。所以我问 Rauch Vercel 如何帮助开发人员处理这种复杂性？

“当涉及到选择基础设施时，”他回答说，Vercel 为前端开发人员提供了“一个完全托管的无服务器边缘基础设施，这样他们的应用程序或网站就不需要自己进行任何[基础设施]投资，他们只需专注于核心应用程序。”

与我在上周的[专栏](https://thenewstack.io/why-netlify-is-tech-agnostic-and-its-role-in-jamstack-development/)中描述的 [Netlify](https://www.netlify.com/) 类似，Vercel 专注于 JAMstack 方法的构建和部署方面。

“我们建立了一个工作流程，前端开发人员只需推送代码、构建代码、优化代码以供发布，然后将代码放在客户身边，”Rauch 解释道。

## 偏爱的框架:Next.js

虽然 Vercel 和 Netlify 有相似的构建工作流和边缘网络，但两家公司之间有一个关键的区别:框架。

正如我在上一篇专栏文章中所解释的，Netlify 是技术不可知的，可以与一系列框架一起工作——从 Hugo 到 Gatsby，到 Next.js，等等。虽然 Vercel 也为开发人员提供了在其平台上工作的框架选择，但它特别针对一个框架进行了优化:开源 JavaScript 框架， [Next.js](https://nextjs.org/) 。

原因很简单:劳赫是 Next.js 的创造者。

Next.js 基于 [React](https://reactjs.org/) ，这是一个用于构建用户界面的 JavaScript 库，于 2010 年代初出自脸书(正如[上一篇专栏文章](https://thenewstack.io/gatsby-wants-to-be-orchestration-layer-for-building-websites/)中提到的，JAMstack 公司的伙伴 Gatsby 也基于 React)。

根据 Rauch 的说法，Next.js 是“当今人们在网络上构建生产级网站或应用程序的最简单的方式。”他列举了 Hulu.com、Staples.com 和 Nike.com 等几个由 Next.js 支持的大型网站

## 低位代码

Next.js 还展示了云原生互联网的另一个趋势:低代码。Rauch 告诉我，Next.js 框架的吸引力很大一部分在于“让一个前端网站或应用程序正常工作只需要很少的代码。”

换句话说，Next.js 不仅仅是面向 web 开发者的；网页设计师也可以使用它。

“React 上只有这么薄的一层，”劳奇解释道，“你实际上只是在操纵概念。您操作的主要概念是组件。所以它对设计者和开发者都非常非常有吸引力。我的看法是，我们正在这里看到一个混合产品工程师的崛起，[他]拥有这种设计敏感性。”

这种低代码、“设计满足开发”的前端方法在很大程度上是可能的，因为 Vercel 负责后端工作。

“一旦你不再考虑基础设施，”劳赫说，“你就不会考虑缓存，不会考虑负载平衡，不会考虑 CDNs[内容交付网络]，不会考虑 CI/CD…然后你所有的时间都花在优化设计和产品体验上。”

## 为什么 Vercel 建立了一个专有的边缘网络

像 Netlify 一样，Vercel 已经建立了自己的边缘网络——基本上是一种 CDN。Rauch 将其描述为“我们建立的专有边缘网络，它直接插入前端开发人员今天使用的框架和工具，如 Next.js、Gatsby 等。”

CDN 是地理上分布的服务器网络，通常用于托管图像、视频和音频。这个想法是，文件由地理上最靠近最终用户的服务器交付给最终用户。但正如劳赫指出的，cdn 传统上是“非常专业的工具，你必须配置它来加速你的应用程序或网站的一部分。”

Vercel 和 Netlify 都意识到 CDNs 可以成为主要的分发模式，而不仅仅是专注于特定的文件。不仅如此，通过使用 CDNs，开发者可以避免 web 服务器所需的复杂的配置工作。

Rauch 说，通过 Vercel 专注于这种 CDN 组件，“我们获得了这个广泛网络的所有可靠性和性能优势，并将其提供给开发人员。几乎没有办法在这些工具的基础上进行构建，这样会很慢，或者它们可能会离线。所以它基本上是建立在分布式系统之上的，开箱即用。”

## 前端

所有这些联系在一起的方式是，Vercel 为开发人员提供了一系列服务。目标有两个:第一，尽可能多地去掉后端配置；第二，让开发者使用 JavaScript 框架构建他们的网站或应用变得容易。

“现代开发商正在寻找垂直整合的解决方案，”劳赫说。他将 Vercel 描述为“一家工具链和工作流公司，为[开发者]提供这种端到端的体验。”

在 4 月份宣布 Vercel 重新命名的博客文章中，Rauch 引用了该公司一位投资者的话说，Vercel 就像是“面向前端开发者的 AWS(亚马逊网络服务)”这是一句很棒的台词，但它到底是什么意思呢？

“Vercel 正在解决 AWS 的一个关键问题，”Rauch 说，“那就是它从来没有真正的开发者体验。”

他继续说，AWS 的体验是“一种*选择你自己的冒险*类型的考验，我真的不认为这是现代产品开发人员今天想要的。”

总之，我们现在看到的 JAMstack 和 Vercel、Netlify 等公司的情况，与[无服务器](https://thenewstack.io/serverless-has-unlocked-a-new-world-of-cloud-mashups/)和托管服务趋势类似。这一切都是为了抽象出后端，并帮助开发人员在(目前已经成熟的)云平台上构建东西。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>