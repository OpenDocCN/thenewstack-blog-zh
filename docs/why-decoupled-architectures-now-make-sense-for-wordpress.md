# 为什么去耦架构现在对 WordPress 有意义

> 原文：<https://thenewstack.io/why-decoupled-architectures-now-make-sense-for-wordpress/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是 New Stack 的高级编辑，每周撰写一篇关于网络和应用程序发展趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

解耦架构已经成为这个 web 开发时代的一个决定性趋势。随着 Jamstack 架构的兴起，我们最明显地看到了这一点，例如 Netlify 和 Gatsby 这样的公司。但这也是使用开源 WordPress 内容管理系统(CMS)构建的大型网站生态系统中的一个关键主题。事实上，如果你仔细观察，Jamstack 公司和现代的 WordPress 托管公司如 [WP Engine](https://wpengine.com/) 没有太大的区别。

WP Engine 是运营 wordpress.com 的 Automattic 公司的主要竞争对手之一，该公司最近一直在进行收购(最近，收购了一家创建了名为 Frontity 的 React 框架的小型初创公司)。然而，尽管 Automattic 只是不情愿地接受解耦架构，WP Engine 却相反。它将无头 CMS 方法视为“企业 WordPress 的未来”

为了找出 WP Engine 的 headless CMS 战略与 Automattic 的不同之处，我采访了 WP Engine 的联合创始人兼首席技术官[杰森·科恩](https://twitter.com/asmartbear)。

## WP 引擎与 Automattic

在我们开始交谈后不久，我意识到科恩对分离 WordPress 趋势的观点与 Automattic CEO(和 WordPress 联合创始人)[马特·莫楞威格](https://twitter.com/photomatt)大相径庭。虽然 Mullenweg 对 jam stack(T21)甚至“无头”这个词持批评态度，但 Cohen 认为去耦合架构是 WordPress 生态系统的一个积极趋势。

“这种去耦合、无头、Jamstack 或任何你喜欢的词的趋势……很容易被视为对 WordPress 的威胁，”他告诉我。“但对我来说，这只是技术的进化。WordPress 已经存在[将近] 20 年了，所以有进化是很自然的——事实上，有一种进化仍然包括 WordPress，并且*需要* WordPress，这有点令人惊讶。一个脱钩的网站需要一个 CMS，这一点没有改变，也不会改变。”

WP Engine 和 Automattic 都至少将部分业务转向了“无头 CMS”策略，即在 WordPress 系统之外管理展示和发布方面(前端，或“头”)，通常使用 JavaScript、Node.js 和类似的技术。使用 headless 方法，WordPress 被严格地用作内容作者和编辑的接口。换句话说，它已经从表示(设计)和发布(构建和部署)中分离出来。

但据 Cohen 称，Automattic 对 headless WordPress 的支持有限。他说 [WordPress VIP](https://wpvip.com/) ，一家在高端 WordPress 托管市场上与 WP Engine 直接竞争的自动化公司，除了增加一个 Node.js 组件之外没做什么。“换句话说，你添加了 JavaScript 基础设施，然后你说我们完成了，我们添加了那个基础设施，”他在谈到他的竞争对手的无头产品时说。

科恩说，WP Engine 的无头产品 Atlas 提供了更多功能。他提到了 WP Engine 的定制 JavaScript 框架 [Faust.js](https://developers.wpengine.com/docs/faustjs/next/getting-started) ，以及一款名为 [Atlas Content Engine](https://developers.wpengine.com/docs/content-engine/introduction) 的新发布产品——他说这款产品提高了性能。

## 开发商可以自行出击

不管 WP 引擎和 WordPress VIP 在无头产品方面的相对优势如何，很明显，WordPress 的解耦时代在很大程度上是由开发者的需求驱动的。特别是，在创建网站时，React、Angular 和 Vue 等现代 JavaScript 框架为开发人员提供了许多选择。

“有所有这些优势，”科恩说，“就像，开发人员可以使用现代工具和语言，[和]开发人员可以-在某种意义上-重新开始。换句话说，他们可以从一个新的网站开始——他们不必使用旧的 Adobe Experience Manager 网站或 WordPress 网站，并以某种方式改变它。他们可以从 JavaScript 和 React 以及该生态系统的工具开始。”

分离架构的好处之一是开发者可以通过 API 从 WordPress CMS 中检索数据，并将其移植到他们的 JavaScript 应用程序中。这很重要，因为从内容创建者的角度来看，WordPress 仍然是管理内容的首选方式。

科恩在谈到 WordPress 时说:“这就是营销人员所拥有、了解和喜欢的东西。他认为能够将数据从 WordPress 移植到 web 应用程序中“是开发人员自己解决问题的一种方式，而不必去摆弄遗留系统。”他所说的遗产是指 WordPress 作为一个整体出版系统，很大程度上仍然运行在 PHP 上。

Cohen 还指出，采用 headless CMS 方法允许开发人员潜在地实现更好的网站速度、更高的安全性和可伸缩性。虽然不能保证选择一个去耦合的架构而不是传统的 WordPress 架构会实现这些事情，但是开发者至少可以*尝试*使用他们也很熟悉的现代工具来实现——JavaScript 框架、内容交付网络(cdn)、Node.js、云计算等等。

## 去 Jamstack 还是不去 JAMstack，这是个问题

在过去的一两年里，对解耦 web 架构的大肆宣传主要来自所谓的 Jamstack 公司，如 Netlify、Gatsby 和 Vercel。我问科恩，相对于这些公司，WP Engine 如何定位自己？他回答说，WP Engine 以不同的方式与每家公司竞争，但 Jamstack 的口号令人困惑。

“Netlify 一开始只是一个 CDN。然后他们发明了“Jamstack”这个术语，并且他们仍然拥有它。然后，他们将产品添加到他们的产品线中。从静态 CDN 开始，他们添加了节点托管，然后创建了 CMS，等等。当他们这样做的时候，他们编辑了 Jamstack 的意思——他们甚至改变了拼写，对吗？”[从 JAMstack 到 Jamstack]

他补充说，盖茨比和 Vercel 不再把自己标榜为 Jamstack 公司。(果然，在检查了两家公司的主页后，我可以确认没有提到 Jamstack 除了盖茨比用这个词来帮助宣传一个即将到来的活动。)

也许 Jamstack 宇宙中最著名的 CMS 是 Contentful，Cohen 提到它是 WordPress 的一个可能的替代品。不过还是那句话，WP Engine 只是部分竞争 Contentful。“这很复杂，”他说，“因为每个人都在提供不同的产品。”

## WP 引擎与开发者的崛起

当审视 WordPress 生态系统多年来的演变时，WP Engine 是一家令人着迷的公司，从开发人员是小角色的单一方法(他们基本上负责插件)到开发人员是整个过程的中心的完全分离的开发平台。

WP 引擎一直处于这一演变的最激烈阶段。正如我的老科技博客读写网在 2010 年的文章中解释的那样，它在 2010 年开始时是一个小型的优质 WordPress 主机。但是在过去的十年里，它有了显著的增长，这在很大程度上是因为网络开发者市场的快速增长。

正如 Cohen 所说，2010 年 CMS 的一个部分是内容编辑界面，它在现代网络开发中仍然是绝对需要的。但是对于 CMS 的其他方面，我们看到前端——表示和发布——现在可以用其他方式完成。这就是无头 CMS 方法如此引人注目的原因。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>