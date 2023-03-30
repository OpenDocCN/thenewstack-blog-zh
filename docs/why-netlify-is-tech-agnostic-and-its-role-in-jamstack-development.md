# 为什么 Netlify 是技术不可知的以及它在 JAMstack 开发中的作用

> 原文：<https://thenewstack.io/why-netlify-is-tech-agnostic-and-its-role-in-jamstack-development/>

在云原生时代，应用程序开发发生了根本性的变化；不仅仅是随着容器和 Kubernetes 的兴起，大规模部署也是如此。Web 开发也正在经历一场巨变，JAMstack 的出现是一个显著的趋势。

正如 Docker 是容器革命最初的变革推动者一样，JAMstack 运动的背后也有一家公司: [Netlify](https://www.netlify.com/) 。因此，我联系了 Netlify 的联合创始人兼首席执行官[马特·比尔曼](https://twitter.com/biilmann)，谈论 Netlify 迄今为止的历程及其在开发者生态系统中的地位。

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇专栏文章，探讨云计算原生互联网的未来。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) 

JAMstack 中的“jam”指的是 JavaScript、API 和标记；“栈”部分指的是云计算技术。但并不是 JAMstack 的组件让它变得有趣。这种方法将 web 开发的前端和后端分离开来。最终，这使得开发人员的生活变得不那么复杂(尽管对内容创建者来说没那么复杂，这个问题我将在本文后面讨论)。

但是对于开发者来说，JAMstack 有很多潜在的好处。正如 Biilmann 所解释的，“我们承担了构建部署管道、运行基础设施、管理无服务器功能等所有这些工作的复杂性，[并且]我们只是将这些从您身上抽象出来。”

请注意，JAMstack 对最终用户来说也很棒，因为它将所有的动态编程从服务器转移到了用户的浏览器上。这意味着更快、更容易扩展、更安全的网站和应用。

## 网络生活是技术不可知的

作为开发人员的基线，Netlify 自动完成构建和部署过程。不再摆弄网络服务器；您需要的只是一个前端工具和一个 git 存储库。以我自己的[实验性 JAMstack 博客](https://generatestatic.com/)为例:当我创建一个新帖子时(在我的例子中，使用一个名为 [Hugo](https://gohugo.io/) 的静态站点生成器)，我在本地文件系统上构建它，将更改“提交”到 GitHub，然后 Netlify 自动将更新的站点部署到它的定制内容交付网络(CDN)。

当我第一次建立我的网站时，我所要做的就是将 Netlify 连接到 GitHub，并调整设置，以便 Netlify 知道我使用 Hugo 框架。

这让我想到了 Netlify 的另一个有趣之处:它是框架不可知的。Hugo 基于 go 编程语言，但是我可以使用基于 Javascript 的 Gatsby 作为我的静态站点生成器——或者任何其他前端工具。

比尔曼告诉我，这种技术不可知论是有意为之的。

“核心思想是，一切都从前端开发人员使用他们采用和使用的框架开始，只要他们坚持这种 JAMstack 架构，我们就可以完成整个工作流——从编写代码开始，直到用户看到它为止。”

“我们总是从 web 架构的角度来考虑这个问题，”他继续说道，“我们总是看到特定框架和技术的领域，这是一个变化非常快的领域——工具来来去去。”

Netlify 可以与许多前端框架合作，包括 Hugo、Gatsby、Vue.js、Next.js、Angular、Ember.js 和 Nuxt。其中大部分都是 JavaScript 框架——比如 Gatsby 就是基于流行的开源 JavaScript 库 React。

“我们希望接受所有这些框架，”比尔曼说。

选择一个框架并以这种方式推广其 JAMstack 方法可能会更容易，但正如 Biilmann 解释的那样，Netlify 选择关注“我们如何看待未来 web 的整个架构，并构建正确的原语和正确的组件，然后框架作者可以采用和构建它们，并用来推动 web 向前发展。”

## API 和无服务器功能

我自己的 JAMstack 设置仅仅触及了这种方法的皮毛。除了自动化站点或应用程序的构建和部署，Netlify 还可以帮助开发人员利用 web 蓬勃发展的 API 生态系统，以及相对较新且闪亮的无服务器功能世界。

比尔曼告诉我，他们通常看到人们以三种不同的方式使用 API。

首先，在构建时使用 API 与一个无头 CMS、一个电子商务系统或其他服务进行对话。Netlify [最近推出了](https://thenewstack.io/netlify-launches-plugin-infrastructure-to-extend-automated-build-capabilities/)一个[构建插件](https://docs.netlify.com/configure-builds/build-plugins/#install-a-plugin)平台来使这变得更容易(一个类似于 WordPress 插件的概念，尽管在 Netlify 的例子中更侧重于开发者)。比尔曼将 Netlify 的角色描述为“通用调度程序”

“无论你是在 GitHub 中修改代码，”他说，“还是内容编辑在 Contentful[一个无头 CMS]中编辑，或者如果有人在 Shopify 中修改了产品定义，或者其他什么，我们都会发现这一变化，我们会运行构建，我们会进行协调并与 API 对话，然后部署到 edge [Netlify 的 CDN]。”

第二个用例是在前端的中使用 API *，例如与 Stripe 对话以管理支付。这是在 web 上使用 API 的一种相当常见的方式，Netlify 在这里并没有扮演积极的角色。但在第三种用例中，它确实帮助了开发人员，扩展或补充了前端 API 功能。比尔曼再次用条纹的例子来说明。*

“一旦用户进行支付，你需要一些服务器端代码，这些代码具有秘密的 Stripe API 令牌，并且可以从那里与 Stripe 的 API 进行对话。这正是我们通过管理环境变量和网络功能使之变得非常容易解决的事情。”

## WordPress 应该感到威胁吗？

所以 JAMstack 方法对开发人员来说是一种强大的方法。然而，如果 JAMstack 目前有一个关键问题，那就是它让内容创作者的网络发布变得更加复杂。

虽然我很喜欢尝试我的 Hugo 博客，但不可否认的是，它需要做更多的工作。有一个技术学习曲线(我不得不再次了解命令行)，在发布内容时需要采取更多的步骤(这不仅仅是点击一个“发布”按钮的问题)，并且你通常会处理不止一个系统(Hugo、GitHub 和 Netlify，就我而言)。

但是正如我在[我之前的专栏](https://thenewstack.io/gatsby-wants-to-be-orchestration-layer-for-building-websites/)中提到的，Gatsby 希望让 JAMstack“对每个人都有用”——这意味着超越开发者，并试图吸引内容创作者。因此，随着时间的推移，就像 2000 年代早期到中期的博客一样，JAMstack 可能会变得更容易使用。

我问马特·比尔曼，主导网络内容管理系统 WordPress 的幕后公司 Automattic 是否应该担心……或者它会适应吗？

“基本上所有传统的单片 CMS 已经真正开始看到这种(前端和后端的)分离是一个现实，它对开发者来说是可取的，”他回答说。“今天直接使用 WordPress 作为整个堆栈的人，有很多不满的感觉，你会完全落后于你在前端实际可以做的事情。”

也就是说，比尔曼认为不仅来自 WordPress 社区的人，而且来自其他大型 CMS 如 Drupal 和 Sitecore 的人，都想要两个世界最好的东西。他说，他们意识到，他们“可以保留整个内容编辑体验和管理用户界面，然后将它作为一个无头 CMS 公开。”

Biilmann 说，WordPress 可能感到威胁的地方是“专门为这个模型(JAMstack)从头开始构建的无头 CMS。”他没有提到任何人的名字，但主要的玩家包括 Contentful，Ghost 和 Strapi。尽管他也指出，目前还没有一个占主导地位的开源无头 CMS，所以 Automattic 可能认为这是一个机会。

无论如何，对我来说很明显，Netlify 将继续在新兴的 JAMstack 生态系统中占据中心位置。至少，这是一家每个 web 开发人员都应该去看看的公司——尤其是在你可以使用你最喜欢的框架的情况下。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>