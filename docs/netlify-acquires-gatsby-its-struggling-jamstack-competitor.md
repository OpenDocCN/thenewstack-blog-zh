# Netlify 收购了苦苦挣扎的 Jamstack 竞争对手 Gatsby

> 原文：<https://thenewstack.io/netlify-acquires-gatsby-its-struggling-jamstack-competitor/>

Netlify 正在收购其主要竞争对手之一，Jamstack 框架和平台公司 Gatsby。我与 Netlify 的联合创始人兼首席执行官马特·比尔曼(Matt Biilmann)就这笔交易进行了交谈，他为什么对苦苦挣扎的盖茨比感兴趣，以及这对 Jamstack 的未来意味着什么——这是他自己的公司开创的网络发展趋势，盖茨比已经抓住了这一趋势。

“web 的未来是可组合的架构，”Biilmann 在新闻稿中说道，其中引用了 Gatsby 为企业开发人员提供的 Valhalla Content Hub 平台作为例子。Netlify 还证实，Gatsby web 框架将“保持开放源代码，供所有开发者使用。”

## 盖茨比击败韦尔塞尔和奈特丽菲的失败尝试

我告诉比尔曼，Gatsby 基于 React 的 JavaScript 渲染框架[在受欢迎程度上已经远远落后于像 Next.js 和 Nuxt 这样的竞争框架。我还说，我一直不太理解 Gatsby 公司的价值主张，该公司一度自称为“](https://2022.stateofjs.com/en-US/libraries/rendering-frameworks/#gatsby)[内容网](https://thenewstack.io/gatsbys-content-mesh-and-its-role-in-jamstack/)”，但似乎缺乏 Netlify 拥有的[基础设施](https://thenewstack.io/why-netlify-is-tech-agnostic-and-its-role-in-jamstack-development/)——特别是在 [CDN 技术](https://thenewstack.io/slow-jamstack-builds-netlifys-solution-is-distributed-persistent-rendering/)和托管内容的能力方面。那么为什么现在要买盖茨比呢？

比尔曼回答说，Gatsby 框架在“中端市场到企业公司中取得了成功，这些公司通常会建立内容非常丰富的网站——通常有数千个页面，有时甚至有数十万个页面。”他补充说，使用 Gatsby 框架的网站“通常是内容不完全来自一个 API，而是来自几个不同内容来源的网站。”

他指出，Gatsby 试图做与 Vercel 类似的事情，围绕其开源框架创建一家商业公司。我要补充的是，盖茨比也试图与 Netlify 竞争，最近声称“当涉及到构建时间和页面速度等关键指标时，盖茨比云优于 Netlify 等一刀切的平台。”

“很明显，过了一段时间，作为一个通用框架，他们没有赢得与 Vercel 的框架之战，”Biilmann 说。“在构建云平台方面，他们可能会受到我们的限制。”

但是比尔曼指出，去年年底发布的盖茨比的 Valhalla 平台是进步的标志。他说，它“是为了帮助客户从他们的无头内容管理系统、无头内容源和遗留系统中获取数据，并通过 GraphQL API 使[数据]在前端可以查询。”他补充道，“这是我们已经关注了一段时间的可组合架构领域。”

## 新口号:可组合架构

我问，这个术语“可组合架构”对网络生活到底意味着什么？

比尔曼将其描述为“远离单一解决方案的改变”，并举了几个例子:Adobe Experience Manager“是你所有网络作品的 DXP[数字体验平台]系统”，Drupal“是驱动你的网站后端和前端、业务逻辑和 UI 层等的核心引擎。”他认为，这些类型的“铁板一块”的解决方案会“开始让人觉得非常过时”

我应该指出的是，WordPress caretaker automatic 和 [Drupal caretaker Acquia](https://thenewstack.io/how-drupal-fits-into-an-increasingly-headless-cms-world/) 现在都已经采用了无头解决方案，所以他们可能会反对 Biilmann 构建他们的平台。

“许多针对 web 的解决方案，”Biilmann 继续说道，“我们正通过 Gatsby 和 Next.js 等框架看到现代前端技术的发展——一般来说，React、Svelte 和 Solid 等库使前端开发人员很难使用老派的模板系统和管道。”

他说在内容([无头 CMS](https://thenewstack.io/strapi-headless-cms-and-lessons-learned-from-docker/) )和“无头商务”API 中也有类似的前端进化。他认为，有了可组合架构，企业可以在所有这些领域选择“最佳”的解决方案。他说，Netlify 的作用在于它“帮助公司协调”所有这些部分。他提到了“web UI 层，将构建系统、来自不同内容源的 webhooks、部署、edge 运行时间结合在一起”等等。(值得注意的是，在 2020 年， [Gatsby 还打算](https://thenewstack.io/gatsby-wants-to-be-orchestration-layer-for-building-websites/)成为网站建设的“编排层”——但这显然没有成功。)

## 那 Jamstack 还是个东西吗？

Netlify 目前将自己标榜为“现代 web 开发的领先平台”,并表示其平台上有超过 300 万开发人员。与盖茨比不同，Netlify 在让开发者理解其平台方面做得很好——尽管它创造了一个有点模糊的时髦词“Jamstack”

值得研究一下 Jamstack 术语的来源，以及它是如何融入 Netlify 现在的工作的。Netlify 于 2015 年推出，不久后创造了 Jamstack。2015 年期间，我在 Netlify 的网站上找不到任何关于它的提及，但在 2016 年[推出了一个独立网站](https://web.archive.org/web/20160527203229/https://jamstack.org/)，它谈到了“JAM stack”，JAM 代表 JavaScript、API 和标记。[在](https://web.archive.org/web/20160606174927/https://www.netlify.com/)的时候，Netlify 宣传自己是一个静态网站的部署平台，但在其主页上没有提到 Jamstack(后来，[的一篇定义该术语的博客文章](https://web.archive.org/web/20170622093349/https://www.netlify.com/blog/2015/11/16/what-is-the-jamstack/)似乎追溯到 2015 年 11 月，因为我在 Netlify 的博客上直到 2017 年才找到它的记录)。

***更新:**Netlify 的投资者 Heavybit 的一名代表告诉我们，Matt Biilmann 在 2016 年 4 月的一次演讲中也谈到了“the JAM stack”。*

我提到所有这些历史，因为我认为可以公平地说，Netlify 偶然发现了一种新趋势——它创造了一个意义模糊的短语，但它开始引起人们的注意。一个社区形成了，新的创业公司(如盖茨比)开始利用这一优势。这与术语“Web 2.0”或“Web3”没有太大的不同，这是另外两个流行词汇，在人们不知道它们确切含义的情况下起飞并吸引了大型社区。

在 2022 年 7 月更新的最新定义中，Netlify 将 Jamstack 称为“一种将 web 体验层与数据和业务逻辑分离的架构方法。”但是 Brian Rinaldi 经营着一份名为 *Jamstacked* 的时事通讯，并与人合著了一本关于这个主题的书[，他认为](https://remotesynthesis.com/blog/jamstack-in-2023/) Jamstack 现在已经变得更像一个“社区”而不是一套架构规则。

比尔曼证实，Jamstack 是“一个社区驱动的术语。”他承认，“它一直在发展和变化，”但补充说，“它所描述的核心特征实际上从一开始就非常清楚——从 web UI 层与所有后端业务逻辑的分离的意义上来说。”

无论如何，现在盖茨比已经被吞并了，很明显 Netlify 是这个生态系统中最强的玩家之一——不管它是 Jamstack 公司还是专注于“可组合架构”的公司 Vercel 现在可能是其最接近的竞争对手，尽管像 [Fastly](https://thenewstack.io/anil-dash-on-mastodon-joining-fastlys-open-source-program/) 和 Cloudflare 这样的 CDN 公司也在成功地挖掘这一领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>