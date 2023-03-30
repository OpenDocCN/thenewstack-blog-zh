# WordPress 联合创始人马特·莫楞威格不是 JAMstack 的粉丝

> 原文：<https://thenewstack.io/wordpress-co-founder-matt-mullenweg-is-not-a-fan-of-jamstack/>

WordPress 的创始人兼 Automattic 的首席执行官马特·莫楞威格认为，目前流行的 [JAMstack 网站管理方法](https://thenewstack.io/why-netlify-is-tech-agnostic-and-its-role-in-jamstack-development/)——将前端和后端分离，不需要网络服务器——是网络的倒退。

“对于大多数采用 JAMstack 的人来说，这是一种倒退，”Mullenweg 在电子邮件中告诉我。“可用性和功能性实际上更低。即使是在 JAMstack 重建网站也要追溯到活字时代，那时网站越大，重建或更新模板的速度就越慢。

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇专栏文章，探讨云计算原生互联网的未来。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) 

他所指的重建过程是静态 HTML 页面的生成，这在 JAMstack 模型中通常由“静态站点生成器”来完成——这类产品的常见例子包括 Gatsby、Jekyll、Next.js 和 Hugo。在呈现为 HTML 之后，页面被分发到内容交付网络(cdn)——就像 Netlify 提供的那样。这使得 JAMstack 网站比依赖网络服务器的网站速度更快，因为它们是从本地网络而不是从大洋彼岸的某个服务器传送给最终用户的。

但是，虽然在 JAMstack 模型中，用户的页面下载通常非常快，但在某些情况下，发布者的构建时间可能需要 30 分钟或更长。事实上，盖茨比是上周新闻中的[，因为(除了其他原因)太慢。愤愤不平的前盖茨比承包商纳特·艾莉森](https://thenewstack.io/gatsby-faces-community-upheaval-over-commercialization-plans-diversity-challenges/)[在一条长长的 Twitter 帖子中声称](https://twitter.com/tesseralis/status/1293679185169244160)盖茨比“建造缓慢”。

Gatsby 和其他静态站点生成器正在研究如何进行增量构建来解决这个问题，但是 Gatsby 的首席执行官 Kyle Mathews 向新的堆栈承认“构建时间与站点大小和所使用的特定功能成比例”，并且“一些非常大或图像繁重的站点可能需要那么长时间。”

对于 Mullenweg 的观点，是否大多数网站或博客需要在每次发布新页面时通过 CDN 预渲染和交付整个网站是有争议的。作为一个长期的博客作者，它确实让我想起了可移动字体——我最终放弃了可移动字体(转而使用 WordPress ),部分原因是构建速度慢。

也就是说，2005 年的老式活字网站和现在的 JAMstack 网站有很大的不同。尽管“静态”这个词在 JAMstack 中被频繁使用，但这些网站可以是非常动态的。事实上，JAMstack 的优势之一是开发人员可以更容易地将 API 和无服务器功能集成到他们的站点中。

## 脆弱的链条？

这让我们想到了 Mullenweg 对 JAMstack 的下一个抱怨:它依赖于太多不同的服务。

他说，“你可以把十几个服务拼凑在一起，每个服务都有自己的账户和账单，每月花费数百美元，就能得到类似的结果，就像你在共享主机上使用 WordPress 每月花费几美元一样。”“而且它会更脆弱，因为链条的强度取决于它最薄弱的一环。你将不同的工具集、登录、计费、托管连接在一起……任何一个环节出现问题都会破坏整个流程。”

对于网站的基本功能——内容管理、构建、虚拟主机和设计——Mullenweg 认为 JAMstack 是一套解决方案，而不是像 WordPress 那样的单一系统。

我自己的实验性 JAMstack 博客没有花费我任何运营成本，但是它依赖于几种不同的服务。我在开源 Hugo 框架上运行它，通过 GitHub 在 Netlify 上部署它，我现在使用一个名为 Forestry 的“headless CMS”服务。这是我所依赖的四个独立系统，而我只用 WordPress.com 的(Automattic 的托管解决方案)就可以运行完全相同的博客。

正如我在关于 [Gatsby 的“内容网格”](https://thenewstack.io/gatsbys-content-mesh-and-its-role-in-jamstack/)和 [headless CMS 供应商 Strapi](https://thenewstack.io/strapi-headless-cms-and-lessons-learned-from-docker/) 的专栏中指出的，内容管理者的 JAMstack 体验并不是最佳的。然而，JAMstack 的好处在于开发方面。开发人员有理由对像 Vercel 这样的前端开发平台和像 Netlify Functions 这样的创新感到兴奋。

例如，如果考虑电子商务，JAMstack 站点可以使用 Stripe API 来集成购物车系统。最近的一篇 [Netlify 博客文章](https://www.netlify.com/blog/2020/04/13/learn-how-to-accept-money-on-jamstack-sites-in-38-minutes/)展示了如何“在 Jamstack 网站上销售产品，使用 Stripe Checkout 处理支付，使用 Netlify 函数安全地创建结帐会话。”

当然，你也可以将 Stripe 集成到 WordPress 站点中。通常这是通过 WordPress 插件系统完成的(Stripe 有[多个插件选项](https://wordpress.org/plugins/search/stripe))。

Stripe API 是否有可能暂时失败或出现故障，从而给使用该 API 的网站带来问题？是的，是的——对于 JAMstack *和* WordPress 来说，这是一个风险。事实上，如果你有任何使用 WordPress 插件的经验，你会知道它们会给你的网站带来奇怪的技术问题。

## 结论

虽然我认为马特·莫楞威格对 JAMstack 提出了两点有效的批评——缓慢的构建时间和“脆弱的”服务链——但应该注意的是，WordPress 在 2020 年也有批评者。一个 WordPress 站点有时会非常慢，可能是由于一个遥远的网络服务器或者一个麻烦的插件。2018 年 12 月在 WordPress 5.0 中引入的古腾堡基于块的编辑器招致了大量批评(它目前在[wordpress.org](http://wordpress.org/)上的[平均评级为五星二星](https://wordpress.org/support/plugin/gutenberg/reviews/))。

就我个人而言，我喜欢 Gutenberg 编辑器，因为它使内容创作成为一种更加模块化的体验——这几乎是现代网络的必需品。但是当它第一次发布的时候确实有一些问题，我花了几个月的时间来适应它。这与我目前使用 JAMstack 的体验没有什么不同。改变的代价是开始时经常会迷失方向。

那么我会把我的个人网站从 WordPress 迁移到 JAMstack 吗？尽管我的 WordPress 站点运行速度太慢，不符合我的喜好，但我不会马上把它转移到 JAMstack。这是因为 WordPress 有更好的内容管理功能，并且需要更少的维护工作。但我会继续关注 JAMstack，并继续尝试这些技术。最终用户的速度优势是无可争议的，此外，我对开发人员的机会也很感兴趣。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>