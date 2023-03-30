# 陶瓷的 Web3 可组合性复活了 Web 2.0 混搭

> 原文：<https://thenewstack.io/ceramics-web3-composability-resurrects-web-2-0-mashups/>

可组合性已经成为 Web3 世界中的新流行语。一家名为 Syndica 的 Web3 基础设施公司[写道](https://twitter.com/Syndica_io/status/1499822891197739010)“如果一个应用程序可以作为另一个应用程序的构建模块，那么它就是可组合的”。在[的另一个定义](https://twitter.com/cdixon/status/1451703070589587456)中，a16z VC Chris Dixon 将可组合性定义为“像乐高积木一样混合和匹配软件组件的能力”

如果这个概念听起来很熟悉，那是因为自 20 世纪 90 年代以来，web 开发人员一直在用可重用的组件构建应用程序。在 Web 2.0 中，可组合的应用程序被称为“混搭”、“Web 服务”、“小部件”以及许多类似的术语。甚至在网络出现之前，像微软这样的软件公司就为开发者提供了重用软件对象的方法——微软的系统被称为[组件对象模型](https://docs.microsoft.com/en-us/windows/win32/com/the-component-object-model) (COM)。你甚至可以说这个概念可以追溯到 20 世纪 60 年代，当时 Doug Engelbart 的“ [bootstrapping](https://www.dougengelbart.org/content/view/226/269/) ”哲学帮助他的团队开发了第一个网络计算系统。

有了这些历史之后，为什么我们需要在 Web3 中将可重用组件重新发明为“可组合性”呢？

## 为什么 Web3 支持一个新的术语

当我在 Twitter 上问“可组合性”与前几代可重用应用程序的不同之处时，Chris Dixon [回答](https://twitter.com/cdixon/status/1501309630319939589)“可组合性是早期 web2 的一大部分(还记得“混搭”)但当它变得明显时，获胜的 web2 策略是不互操作和 API 被否决等，它基本上消失了。”

这是一个公平的观点。在 Web 2.0 的初期，“混搭”的潜力被戴着玫瑰色的眼镜看待。在我 2006 年 3 月写的一篇博文中，年轻的我表达了对混搭潜力的兴奋。“mashup 开发者可以通过多种方式将他们的产品货币化，”我写道。作为例子，我引用了 Simplyhired.com，一家从各种来源收集数据的“垂直求职”公司，以及一个名为“伙计，我的二手车在哪里”的网站。来自易贝汽车公司和谷歌地图的混搭数据。

虽然一些伟大的企业确实是以 mashups 起家的(简单雇佣继续增长，并最终在 2016 年被[收购)，但到了 2010 年初，集中式平台开始在网络上行使控制权。其中一些公司限制甚至关闭了对其 API 的访问，这使得 mashup 商业模式岌岌可危。科技行业一个著名的例子是 Twitter，直到 2011 年](https://techcrunch.com/2016/07/01/indeed-owner-recruit-holdings-confirms-acquisition-of-simply-hired/)[还公开鼓励](https://web.archive.org/web/20120808003122/https://dev.twitter.com/blog/ecosystem-showcase) mashup 公司使用它的数据，但是[在 2012 年](https://web.archive.org/web/20120818080005/https://dev.twitter.com/blog/changes-coming-to-twitter-api)严重限制了开发者对其 API 的访问。

所以，是的，Web 2.0 对开放 API 和混搭业务生态系统的梦想在 2010 年破灭了。这是一个耻辱，因为早期 Web 2.0 的吸引力很大一部分是自由流动的数据网络的潜力。

## 陶瓷:为 Web3 带来数据可组合性

Web 2.0 在 2006 年，Web3 在 2022 年。开发者越来越兴奋——至少在[信徒](https://twitter.com/developer_dao)中——并且期待数据很快会从大技术的魔掌中解放出来。玫瑰色的眼镜又戴上了，只不过这一次它们被放在了 NFT 猿人和朋克的鼻子上。

Web3 中出现的一个更有趣的可组合性项目是 [Ceramic](https://ceramic.network/) ，它自称为“一个分散的数据网络，为 Web3 应用程序带来无限的数据可组合性。”它基本上是 dApps(分散式应用程序)、区块链和各种类型的分散式存储之间的数据管道。这个想法是 dApp 开发者可以使用 Ceramic 来管理“数据流”,这些数据流可以被其他 dApp 通过一个开放的 API 重用或重用。

与大多数区块链不同，陶瓷也很容易缩放。陶瓷网站上的一篇博客文章解释说“每个陶瓷节点都是一个独立的执行环境，用于执行计算和验证数据流上的事务——没有全局分类账。”

关于 Ceramic 还有一点值得注意，那就是它使用了 [DIDs](https://www.w3.org/TR/did-core/) (分散标识符)，这是一种 W3C 网络认证标准，我在去年[中提到过](https://thenewstack.io/did-you-hear-decentralized-identifiers-are-coming/)。DID 标准允许陶瓷用户使用分散的身份与流进行交易。

陶瓷背后的公司是 [3Box Labs](https://3boxlabs.com/) ，它在 2 月宣布了一轮 3000 万美元的投资[，由 Multicoin Capital 和 Union Square Ventures (USV)牵头。Multicoin Capital 的管理合伙人凯尔·萨马尼(Kyle Samani)写了一篇附带文章解释他对陶瓷的兴奋。“在陶瓷上构建应用程序看起来就像浏览数据模型的市场，将它们插入你的应用程序，并自动访问网络上存储在这些模型中的所有数据，”他写道。](https://www.coindesk.com/business/2022/02/16/usv-multicoin-lead-30m-raise-for-3boxs-ceramic-data-network/)

Samani 引用的一个潜在用例是 Twitter 的分散版本，这将使每个用户能够控制自己的“数据流”——并有可能将这些数据带到互补甚至竞争的 dApps。

让我们花一分钟时间来讨论一下 Twitter 的克隆主题。从开发者的角度来看，这个想法是其他 dApps 可以使用第一个 Twitter 克隆版本构建的相同数据模型。假设你是一个 dApp 开发者，你想建立一个非常适合的 Twitter 版本(例如，为缝被子的人)。一个简单的方法是为你的 dApp 使用原始 Twitter 克隆的数据模型，这样使用原始产品的绗缝者可以立即开始使用你的产品——甚至可能导入他们所有的绗缝相关内容。

## Solana 区块链和可组合性

虽然可组合性是一个可以应用于以太坊区块链的时髦词——在一篇博客文章中，风投 Linda Xie 认为 20 标准是可组合性的一个例子——但与这个术语联系最紧密的是索拉纳公司。在其主页上，索拉纳声称其区块链“确保了生态系统项目之间的可组合性”相比之下，以太坊的主页没有提到这个词。

陶瓷项目小心翼翼地将自己定位为对区块链不可知论者(事实上，Solana 甚至没有在它的主页上被提及，但以太坊的标志是存在的)。不管怎样，索拉纳看起来确实是陶瓷的最大补充区块链。与以太坊相比，Solana 的主要优势是 dApps 的交易速度更快。凯尔·萨马尼(Kyle Samani)的风险投资公司 MultiCoin 也是索拉纳的大投资者，他认为“下一代应用程序将是建立在索拉纳基础上的乐高城堡。”

我将以我对 Web3 项目的标准免责声明结束:在我们做出判断之前，让我们看看陶瓷实际上能建造什么。但是理论上，我喜欢 Web3 中的可组合性将 mashups 带回 Web 的想法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>