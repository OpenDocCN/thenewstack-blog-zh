# 基于 React 的开源静态站点生成器 Gatsby 获得了商业支持

> 原文：<https://thenewstack.io/gatsbyjs-the-open-source-react-based-ssg-creates-company-to-evolve-cloud-native-website-builds/>

套用托尔斯泰的话，“所有快的网站都是一样的，但所有慢的网站都以不同的方式慢。”——Gatbsy 创作者凯尔·马修斯。

静态站点发电机疲劳综合征。这是一个东西，人们。随着[五百多个 SSG](https://staticsitegenerators.net/)在这些天漫游——从用 [Ruby](https://www.ruby-lang.org/en/) 编写的 [Ace](https://github.com/botanicus/ace) ,到用 [awk](https://www.gnu.org/software/gawk/manual/gawk.html) 和 [sh](https://en.wikipedia.org/wiki/Shell_script) 编写的[zodiac](https://github.com/nuex/zodiac)——SSG 相关的公告很可能在开发者中产生一个集体\_(ツ)_/。

但是并不是所有的静态站点生成器都是一样的。虽然所有 SSG 都有相同的目标——将数据与模板结合起来，以创建通过内容交付网络静态提供的资产——但它们都面临着相同的现实挑战。例如在模板和服务之间创建一个“粘合层”,扩展到非常大/复杂的站点，以及如何实现快速的增量构建。

一个解决所有这些挑战的平台，解决幕后的一切，以便开发人员可以，你知道，制作东西，这听起来像是前端 web 开发人员将云原生架构应用于网站构建的快乐白日梦。酪如果呢？如果我们可以像许多乐高积木一样，用同样的模式将组件、数据结构和设计系统整合在一起，来建立网站，会怎么样？有点像网站的 CI/CD…

事实证明，这个白日梦正在变成现实。

## 见见盖茨比一家

GatsbyJS 是一款基于 React 的 SSG，于 2015 年首次亮相。Gatsby 由 Kyle Mathews 创建，完全开源，通过一组丰富的插件(WordPress、Drupal、Contentful、MongoDB 等)将最佳实践前端开发技术(基于路径的代码分割、PRPL、服务工人和离线支持)与动态数据集成结合起来，颠覆了 SSG 的生态系统。)，在编译时查询。最棒的是 Gatsby v1.0 附带了像 Drupal 和 WordPress 这样的 PHP 主力 CMS 的连接器。这意味着非技术人员仍然可以轻松地以熟悉的方式推送内容，而开发人员可以利用 React 的组件模型。开发者们像蛋糕上的生日小孩一样扑向盖茨比:盖茨比已经被成千上万的开发者使用，每个月下载近 50 万次。

今天，第二个盖茨比加入了这个聚会。Mathews 与他的老朋友(也是 Gatsby 的核心贡献者)Sam Bhagwat 合作成立了 Gatsby Inc .围绕开源的 Gatsby 创建公司的动力来自于，Mathews 说，他意识到为了充分发挥“实时流处理系统，仅适用于网站建设”的潜力，Gatsby 将需要定制的云支持。实现这一点的方法是建立他们自己的以盖茨比为中心的创业公司。

## 溪流中的岛屿

Gatsby 采用了一种新颖的方法，即采用流处理的核心原则(Mathews 解释说:“预先计算出所有需要的状态，这样读起来——或者在这种情况下，网页加载——非常快”),并发明了一种实用的方法来模拟静态网站。这是一个革命性的概念:将现代软件工程实践和工具应用于网站建设。然而，即便如此，通过使用 Gatsby 加速项目的开发人员在使用 Gatsby 方面仍有大量工作要做。

React 强大的工具集无疑是有帮助的，Gatsby 致力于创建和维护插件和库以优化 SSG 的超能力的开源社区也是如此。然而，不可避免的是，构建阶段是每个静态站点生成器中的一个障碍——这个列表目前包括 Gatsby——因为无论何时，只要有一个更改，您都必须重新计算整个站点。不出所料，这使得扩展本身就很困难。

Bhagwat 和 Mathews 意识到他们想要的是 web 开发人员能够简单地推送代码并让一切正常工作——就像在无服务器和托管数据库中一样。本质上，通过快速无缝地将服务粘合在一起，给予前端开发人员构建网站的能力——这是软件开发人员，我们的技术表亲，这些天来几乎被视为理所当然的能力。接下来是第二个认识:即使考虑到 Gatsby 1.0 就是为了利用这种模式而构建的，如果没有专门构建的云软件，这也是不可能实现的。

![](img/addd8c9623846d5e63f21b2673e7043b.png)

为了交付这个特别构建的软件，Gatsby 需要一个特别构建的公司，致力于将其创新的、将云本地原则应用到网络开发的可能性带到现实世界中。

“通过 Gatsby Inc，我们正在构建专门的云基础架构来进行增量、并行构建，利用当前的 Gatsby 流处理/云原生架构并将其推向更远的地方，”Bhagwat 解释道，他现在是新公司的企业主管(也是联合创始人)。目标是“实际上完全消除构建步骤:您只需做出一个更改，任何更改——代码更改或内容更改——它将立即生效。”

“这在 SSG 中是独一无二的，这是一项技术进步，将极大地改善 DX/UX！”巴格瓦特补充道。

事实证明，硅谷同意了。盖茨比公司很快找到了总部位于旧金山的三一投资公司的支持。专注于支持云原生创业公司的 Trinity 认识到，高度交互、带宽密集型企业网站是当前的行业最佳实践。(这些应用中有许多也是单页应用，这并没有什么帮助)。当然，最好看的网站通常也是加载最慢的。而且每个电子商务公司的底线都直接关系到他们网站的加载时间。

三一集团合伙人丹·朔尔尼克说:“盖茨比颠覆了这个顾客难题，创建了最先进的网站，速度也快得像闪电一样。”。“这解决了一个真正的需求，所以我对他们在整个操作系统世界看到如此非凡的采用并不感到惊讶。自从[码头工人](https://www.docker.com/)早期以来，我还没有见过这种程度的热情。”

## 进步是渐进的

Scholnick 的话对每一个曾经努力让 JavaScript 支持的单页面应用程序出现在搜索结果中的前端 web 开发人员(使用 escaped_fragment“功能”)来说都是真实的——也就是我们大多数人。我们对 Gatsby 的“渐进式”体验特别着迷的原因之一是，当您运行 Gatsby 构建时，输出文件以 HTML 呈现。这意味着，对于搜索引擎来说，所有的内容都在那里，从最初的获取开始就准备好了索引。在客户端，一旦页面完成加载，React 应用程序就会装载到根 div 中。因此，用户可以享受同样丰富的 SPA 浏览体验，只是不需要花费大量时间观看 beachball spinner 浏览 5MB 的 JavaScript 文件。

欢迎来到渐进式网络应用程序(PWAs)的美丽新世界。这是 Gatsby 架构的基础:Mathews 说，Gatsby 被有意设计成 PWA 网站框架。

“谷歌做了很多关于如何制作快速网站的研究，PWA 是这些模式的总称，”他解释道。“所以对于盖茨比，我们只是问自己，为什么不把这些模式，所有这些让网站快速发展的东西，烘焙成一个网站框架？”

基本上， [PWA 是通过 web](https://developers.google.com/web/progressive-web-apps/) 交付的本地应用。像一个本地移动应用程序一样，它有一个外壳，允许应用程序风格的交互和导航——但不需要从应用程序商店下载。完全独立，PWAs 直接在浏览器中运行。他们可以即时加载，即使在覆盖/连接不好的地区，这要感谢[服务人员](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers)——基于 JavaScript 的客户端代理——允许他们即时加载，因为已经驻留在设备上。然后，由于预先缓存，该应用程序可以随时更新，在启动时显示最新版本，并提供即时可靠的用户体验。马修斯解释道，

*这里有一个与[即时制造](https://en.wikipedia.org/wiki/Just-in-time_manufacturing)非常相似的想法。公司发现，最能响应客户需求的方法是避免提前做工作。当他们提前做工作时，这会矛盾地减慢他们的速度，因为推测性的工作会妨碍完成实际上必要的工作(资源争用)。对于制造业和 web 应用程序来说，都有很高的库存成本(未使用的代码会占用内存)和响应速度。汽车客户昨天想要他们的新车，而 web 应用程序消费者想要他们的应用程序立即运行。因为“他们可能需要”而提前做的任何工作都会妨碍应用程序对用户的响应。*

*对于这两种方式，你都希望等到用户提出要求，然后尽可能快地为他们提供服务。*

最终，Mathews 总结道，“基本目标只是让浏览器做他们必须做的工作，以达到你的网站目标。”

那么盖茨比实际上是如何把这种 PWA 性能放进开发者的工具箱的呢？

这是盖茨比应该知道的，而 devs 永远不必担心。“你不应该考虑性能，你的网站应该很快。你的框架应该让你的网站运行得更快，”马修斯说。

这并不像盖茨比团队试图隐藏一切是如何运作的。毕竟是一个开源项目。他们真的只是想让开发人员专注于需要为网站定制的东西——设计和 UI/UX——同时代表我们处理其余的事情。大多数开发者都乐于接受这种安排。

## 透明度

在这一点上，盖茨比公司是非常新的。甚至是正在进行的工作。大多数创业公司不会在其存在的早期阶段做出正式宣布，但盖茨比再次改变了游戏规则。

作为《盖茨比》的原创者，Kyle Mathews 希望让所有人都知道，Gatsby Inc .不会以任何方式背离开源。Gatsby 公司正在为 SSG Gatsby 构建云服务——该服务本身将保持完全开源。Mathews 和他的团队希望在原始平台之外构建的大部分内容也是如此。尽管这个“是什么”在这一点上很大程度上是抽象的，但 Mathews 希望以一种本质上开源的方式启动一家私人公司。

也许，部分原因是因为创业公司获得了资金支持，使得 Gatsby 实际上带来了几个核心开源贡献者。

“创建这家公司意味着我们可以投入更多的精力来改善 Gatsby core 及其周围的生态系统，”Mathews 说。“能够与开放的上游合作，进行有针对性的改进，不仅有利于 Gatsby 本身，也有利于整个前端生态系统。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>