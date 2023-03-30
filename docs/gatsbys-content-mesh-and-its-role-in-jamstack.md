# 盖茨比的内容网及其在 JAMstack 中的作用

> 原文：<https://thenewstack.io/gatsbys-content-mesh-and-its-role-in-jamstack/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是《新书库》的高级编辑，每周撰写一篇关于云原生互联网未来发展的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

像云时代的其他事物一样，内容管理系统(CMS)正在经历从单一架构到更加模块化的方法的转变。服务于网络开发的云服务公司 Gatsby 是试图以这种方式重新思考内容管理的众多创业公司之一。

在本周的专栏中，我采访了 Gatsby 首席技术官 Sam Bhagwat，讨论了其在云原生时代处理内容的方式。我还想揭开 JAMstack 生态系统的层层面纱，澄清盖茨比在其中的位置。

2018 年 10 月，巴格瓦特发表了[一系列博客文章](https://www.gatsbyjs.org/blog/2018-10-04-journey-to-the-content-mesh/)，描述了他所谓的“内容网格”。他将其定义为“分离网站的基础设施层”，并解释说它包括内容管理服务、开发框架(通常基于 JavaScript)和增强的性能(例如，通过使用内容交付网络(cdn)而不是 web 服务器的 JAMstack 模型)。

这些帖子是很好的读物，但是在这个系列的结尾，我觉得“内容网格”的概念仍然有点模糊——不完全清楚。当研究 JAMstack 时，我意识到这是一种熟悉的感觉。这些技术还没有完全开发出来，有时很难精确地计算出这个生态系统中的每个公司都做些什么。

盖茨比尤其如此。部分原因是因为 Gatsby 既是公司的名字*也是衍生它的开源 web 框架项目的名字*。[框架 GatsbyJS](https://www.gatsbyjs.org/) 创建于 2015 年，基于开源的 React JavaScript 库。几年后，在盖茨比成功的基础上成立了盖茨比公司。

但是公司是做什么的呢？如果你读了关于第页的[，没有关于盖茨比提供什么产品或服务的描述。相反，有一个简单的目标“帮助网站开发团队用现代工具构建 CMS 驱动的网站。”在其主页上，提到了一款名为](https://www.gatsbyjs.com/about/)[盖茨比云](https://www.gatsbyjs.com/)的产品——个人用户和企业都可以注册——但同样不清楚这款产品的用途。

为了确定盖茨比是什么，我请巴格瓦特描述一下该公司在 JAMstack 生态系统中扮演的角色。他的回答可以归结为:盖茨比是“内容网的编排层”盖茨比首席执行官[凯尔·马修斯](https://www.linkedin.com/in/kylemathews/)在最近的[资金公告](https://www.gatsbyjs.org/blog/2020-05-27-announcing-series-b-funding/)中也使用了这个短语，“编排层”。它表明 Gatsby 管理 JAMstack 网站或应用程序的所有不同组件。

至于这些组成部分是什么，巴格瓦特在 2018 年的一系列帖子围绕着《盖茨比》的几个主要特征:

1.  对于内容创建，Gatsby 集成了第三方 headless CMS 服务，如 Strapi 和 Contentful。它还可以连接到 Shopify 等专业服务，以及 WordPress 和 Drupal 等企业内容系统。
2.  它有一个开源的 GatsbyJS 形式的开发框架。
3.  它集成了构建和部署服务，如 Netlify。作为其中的一部分，Gatsby 充当“静态站点生成器”——这基本上意味着它构建静态 HTML 文件，为部署做准备。

所有这三样东西组成了一个“内容网”，正如巴格瓦特用这个文氏图所说明的:

如果你放大那张图片的“网站性能”部分，你会看到列出了 Netlify。据巴格瓦特说，Netlify 管理三件事:CI/CD、托管和 CDN(内容交付网络)。相比之下，Gatsby Cloud 只关注 CI/CD 部分——包括构建。所以盖茨比必须与 Netlify(或其他公司)在主机和 CDN 方面进行整合。

## 盖茨比和 WordPress

您可以在 Bhagwat 的 Venn 图的工具和性能部分看到 JAMstack 模型的好处——更好的开发框架和性能显然会吸引开发人员。但是卑微的内容创作者呢？正如我之前提到的那样，JAMstack 的一个潜在缺陷是，对于内容创作者来说，无头 CMS 服务比传统的 CMS 系统(如 WordPress 和 Drupal)更难使用。

巴格瓦特承认，内容编辑体验在 JAMstack 模型中还没有得到优化。

“现在，许多团队转向 JAMstack 范式的动机是更快的迭代速度、更好的开发和更好的性能，”他说。“在转向 JAMstack 的过程中,(对客户而言),内容已经不那么重要了。”

但他补充说，通过最近[推出的](https://www.gatsbyjs.org/blog/2020-07-07-wordpress-source-beta/) WordPress 插件，Gatsby 也可以和 WordPress 一起使用。本质上，它允许你使用 WordPress 输入内容，但是构建和部署是通过 Gatsby 进行的。这个所谓的“[无头 WordPress](https://www.gatsbyjs.org/docs/glossary/headless-wordpress) ”目前处于测试阶段，在撰写本文时，GitHub 中有 40 个已知问题[。因此，在这成为普通 WordPress 用户的可行插件之前，还有很多问题需要解决。](https://github.com/gatsbyjs/gatsby-source-wordpress-experimental/issues)

然而，巴格瓦特也引用了一个组织同时使用 WordPress 和 Gatsby 的业务用例。RealCedar 是加拿大一家名为西部红雪松木材协会的非营利组织的网站。其新的 JAMstack 网站是由总部位于温哥华的网络开发机构 Jambaree 创建的，该机构在 6 月份才推出。

Jambaree [声称](https://jambaree.com/blog/headless-wordpress)已经“开创了一种将熟悉的 WordPress 后端与基于 React 的 Gatsby 前端相结合的方法”——换句话说，就是一个无头的 WordPress。顺便说一下，这里的“后端”指的是 WordPress 软件，包括它的用户界面。

关于 Jambaree 如何为 ReadCedar 实现这个无头 CMS 解决方案，没有进一步的细节，但最终的网站看起来不错，速度也很快。

## JAMstack 还没有解决内容

在回顾了内容网格概念、与巴格瓦特交谈并研究了 Gatsby 的一些使用案例后，有一件事对我来说很清楚:JAMstack 在内容方面还没有完全成熟。

但是公平地说，JAMstack 方法(包括通过 Gatsby)确实为开发人员提供了真正的好处。作为开发者采用的指标，Bhagwat 指出 Gatsby 的插件生态系统正在稳步增长。在内容网格系列出版后的 21 个月里，他说，“我们已经从大约 600 或 700 个插件增加到大约 2000 个插件——所以(现在)有了更多的插件功能。”

不过，我更怀疑盖茨比吸引比开发者更广泛的观众的能力。内容创建者目前没有理由转向 JAMstack，我也不认为“无头 WordPress”的概念在这一点上有说服力。也就是说，在下周的专栏中，我将与一家领先的 headless CMS 供应商进一步探讨这个问题。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特(Twitter)或脸书(T2)与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[反馈@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>