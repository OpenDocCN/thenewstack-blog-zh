# 为什么云 ide 正在转向平台即服务模式

> 原文：<https://thenewstack.io/why-cloud-ides-are-shifting-to-a-platform-as-a-service-model/>

上周，我在克罗地亚美丽的海滨城市扎达尔参加了 info bip Shift T1 开发者大会。演讲者名单是顶级的，热门话题包括云集成开发环境(ide)，生成式人工智能，模块化区块链，以及使用 CSS 创作书籍。

Shift Conference 于 2012 年由 [Ivan Burazin](https://www.linkedin.com/in/ivanburazin/) 创办，2021 年 1 月被克罗地亚 API 公司 Infobip 收购。布拉津现在是 [Infobip](https://www.infobip.com/) 的首席开发者体验官。他还是领先的云 IDE 产品之一 [Codeanywhere](https://codeanywhere.com/) 的联合创始人和前 CEO。我在会议上与 Burazin 坐在一起，讨论了它的背景故事，以及云开发的最新趋势。

## Codeanywhere 的发展

Codeanywhere 最初于 2009 年发布，名为 PHPanywhere，是一个基于 web 的 FTP 客户端和 PHP 文本编辑器。这大约是谷歌文档从测试版出来的时候，所以布拉津和他的联合创始人维德兰·朱基奇认为这是一个创造基于网络的代码编辑器的好时机。

“我们以为所有的东西都会被云覆盖到 SaaS，”布拉津说。“是的，没错——除了编码。”

![Ivan Burazin](img/0a742897a0f8c8db0c52146309a6ea8f.png)

Codeanywhere 的 Ivan Burazin 在他创建的开发者大会 Infobip Shift 上。

云 ide 现在是一个流行的产品类别，但在 21 世纪初，它并不是许多开发人员感兴趣的东西。尽管如此，PHPanywhere 还是扩展到了其他编程语言，并最终被重命名为 Codeanywhere。克罗地亚的创始人在美国的各种会议上推销它。他们没有赢得任何奖项，但这一经历激发了布拉津创办自己的科技大会，他将其命名为 Shift。几年后，他决定将其转变为一个开发者大会，作为帮助推广 Codeanywhere 的一种方式。令他惊讶的是，是会议发展迅速，而不是代码无处不在。

“过去几年，我们有点搁置它，”他谈到 Codeanywhere 时说。“它可以自我维持，但并不是一家年同比增长 100%的热门初创公司。但基本都是小生意。”

## 云 ide 现在必须是开发平台

本月早些时候，基于浏览器的流行设计工具 Figma 以 200 亿美元的价格卖给了 Adobe。甚至 Photoshop——由于其复杂性，可能是最终的桌面软件应用程序——[现在也有了浏览器版本](https://thenewstack.io/top-5-internet-technology-stories-of-2021/)。这是否意味着构建应用程序所涉及的一切都将转移到 web 上？

好吧，在线编码还没有定论。我问 Burazin 云 ide 如何适应应用开发的网络化。

“我认为云 IDE 本身已经商品化了，”他说。“每个人都会有一个——甚至 Codeanywhere 使用的那个也是开源版本。”

Burazin 认为，几乎所有外部开发人员都将使用云 IDE，内部开发人员也将越来越多地拥有这种选择——但后者将只是微软 Visual Studio 等企业工具的一个功能。去年 10 月，[微软在](https://code.visualstudio.com/blogs/2021/10/20/vscode-dev) [vscode.dev](https://vscode.dev/) 发布了Visual Studio 的浏览器版本，因此基于网络的代码编辑器已经是大多数开发人员熟悉的工具。

> “云 IDE 本身已经商品化。每个人都会有一个。”

Codeanywhere 联合创始人伊万·布拉津

Burazin 说，云 ide 的价值将转移到计算或基础设施层。他指出，Heroku 最初是一个云 IDE，但后来发现它的真正价值在于通过容器提供计算层。Heroku 现在是一个所谓的“平台即服务”(PaaS)，Burazin 认为云 IDE 公司也需要类似的转型。他说，Codeanywhere 已经做到了这一点，因为其产品的下一个版本(即将发布)将提供他所谓的“远程开发者环境即服务”

Codeanywhere 开发者 Toma Puljak [在 7 月柏林的 WeAreDeveloper 大会上预览了](https://www.youtube.com/watch?v=Blxq1-rmmYo)Codeanywhere 的新版本。他展示了“如何建立一个环境，一旦配置好，任何人在任何机器上都可以立即复制它。”在附带的博客文章中，他解释了这种方法使用容器和基础设施代码技术来管理部署、安全性等等。

“下一步进化的真正美妙之处，”Puljak 在 7 月说，“是再也不用在本地安装任何东西了。”

简而言之，现代云 ide 不再是简单的在线代码编辑器，而是提供基础设施的服务 Burazin 称之为“即时开发环境”他点名检查了 GitHub 的新云 IDE 产品， [Codespaces](https://github.com/features/codespaces) ，该产品除了在浏览器中嵌入微软的 Visual Studio(GitHub 为微软所有)之外，还具有“标准化开发环境”和快速设置过程。这是 Codeanywhere 等较小的玩家现在需要与之竞争的。

## 人工智能编码

目前开发人员的另一个大趋势是人工智能辅助编码的出现。这方面最突出的例子是 [GitHub Copilot](https://thenewstack.io/github-copilot-a-powerful-controversial-autocomplete-for-developers/) ，这是一个强大但有争议的工具，可以为开发人员自动完成代码。我问布拉津，开发者是否会变得过于依赖人工智能工具。

“我听说每个人都在积极地使用它(人工智能)，他们喜欢它。所以我想人们会使用它——你没有理由不让你的生活变得更容易。但最终，它可能会让你在某个时候被淘汰。”

他补充说，可能需要一代人或更长时间，人工智能才会让职业生涯面临风险。但就目前而言，人工智能辅助编码是开发人员正在采用的一项功能。

人工智能辅助编码不是 Codeanywhere 的功能，尽管值得注意的是 GitHub Copilot 不是基于浏览器的。Copilot 目前只能作为几个桌面应用程序(包括 Visual Studio)的扩展的[使用。](https://docs.github.com/en/copilot/overview-of-github-copilot/about-github-copilot)

## 为什么要使用云 IDE

在 Infobip Shift 的另一个演讲中，[王自如](https://twitter.com/swyx)提到一些大公司——他提到了 GitHub、Etsy 和 Shopify——已经在使用云 ide 和/或远程开发环境进行他们的全部或大部分开发。(补充说明:我就王的演讲采访了他，他的演讲很快将作为一篇独立的文章发表。)所以我问 Burazin，一家初创公司，甚至一家大型非科技公司，会使用这种服务的主要原因是什么。

他说，开发者做事的速度是首要原因。

“我的意思是，当有人提交时，该服务会立即创建开发人员环境的预构建，因此下次您签出代码时，您可以在五秒钟内启动新的开发环境。因此，这无疑节省了大量时间。”

他补充说，创业公司可以节省很多钱，因为他们不必支付额外的计算机资源。

总之，云 IDE 产品类别目前显然正在经历转型——部分是由更大的参与者(如 GitHub)的创新驱动的。但是 Codeanywhere 已经存在了十多年了，它似乎正在随着时间的推移而演变，向更像 PaaS 的方式发展。

*披露:Infobip 付钱让 Richard MacManus 参加在克罗地亚举行的 Infobip Shift 会议。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>