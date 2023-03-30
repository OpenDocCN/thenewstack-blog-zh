# Web3 堆栈:Web 2.0 开发人员需要知道什么

> 原文：<https://thenewstack.io/web3-stack-what-web-2-0-developers-need-to-know/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是 New Stack 的高级编辑，每周撰写一篇关于网络和应用程序发展趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其发展成为世界上最有影响力的博客之一。在 Twitter @ricmac 上关注他。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

尽管 Web3 的[开发者生态系统在更大的 Web 开发者生态系统中只占很小的一部分，但它似乎正在快速增长——因此尝试并查明 Web3 技术堆栈由什么组成是有意义的。我们知道它包括区块链去中心化和加密货币钱包作为身份的一种形式。你可能也听说过像星际文件系统(IPFS)这样有着浮夸名字的分布式存储解决方案。但是开发人员还需要学习什么才能进入 Web3 世界呢？此外，传统的网络技术——如 JavaScript——如何适应 Web3 的前景？](https://thenewstack.io/web3-developer-ecosystem/)

到目前为止，我所遇到的关于 Web3 栈的最好的定义是由 Nader Dabit 编写的，他是一家名为 Edge Node 的 Web3 公司的开发者关系工程师。我第一次采访 Dabit [是在 2020 年 8 月](https://thenewstack.io/theres-a-service-for-that-amazon-web-services-and-serverless-computing/)，当时他作为一名无服务器专家在亚马逊网络服务公司工作。当时，他刚刚发布了一本名为《全栈无服务器:使用 React、AWS 和 GraphQL 的现代应用程序开发》的 O'Reilly Media book。2021 年 4 月，他将这些技能带入了新生的 Web3 世界。他与 Edge & Node 合作的一部分是帮助构建[图](https://thegraph.com/en/)，“一个用 GraphQL 索引和查询区块链数据的 Web3 协议。”

我联系了 Dabit，询问他作为 Web3 的开发人员与他之前在 Web 2.0 公司的工作有何不同。但是首先，让我们仔细看看他的 Web3 参考文章。他将 Web3 堆栈分类如下:

*   区块链
*   区块链开发环境
*   文件存储器
*   P2P 数据库
*   API(索引和查询)
*   身份
*   客户端(框架和库)
*   其他协议

正如他所指出的，这个堆栈与传统的 web 架构“在许多方面完全不同”——区块链和基于加密货币的身份是两个最明显的区别。达比特还警告说，“Web3 的工具、技术和生态系统不如 Web2 成熟。”

“从网络基础设施的角度来看，”达比特告诉我，“主要的区别确实在于我们所认为的‘后端’技术，但在 Web3 中，它们通常被称为‘协议’。”

## 前端

让我们先从简单的部分开始。根据 Dabit 的说法，Web3 的客户端技术(框架和库)本质上与 Web 2.0 相同。JavaScript 在前端被大量使用，并且——与 Web 2.0 的当前状态一样——React 是一个领先的 JavaScript 框架。Dabit 指出“React 内置了大量的[Web3]项目和示例。”

“除了实际的 HTTP 客户端库，前端技术没有太大的区别，”Dabit 向我解释道。因此，要通过 HTTP 协议与服务器通信，“您可以使用 web3.js 或 ethers.js 与 RPC[远程过程调用]对话，或者使用 graphql 客户端与图形对话，而不是 fetch 或 axios。”Web3.js 和 Ethers.js 都是 JavaScript 库，使开发人员能够与以太坊区块链进行交互。

达比特说:“在前端，身份和我们如何处理身份也是不同的。”“要读取数据，你不需要了解用户的任何信息，因为几乎所有的数据都是公开的。但是对于写数据，通常需要连接到用户的钱包。有几种方法可以做到这一点。在桌面应用程序上，用户通常有一个针对其钱包的浏览器扩展，它会自动为网络注入一个全局窗口对象(例如 solana、ethereum、arweave)。或者在手机上，[它]将允许你在钱包应用程序中进行身份验证，并在签署交易后进行重定向。”

如果你曾经尝试过购买加密货币或 NFT，或者尝试过 dapps(去中心化应用)，那么你很有可能使用过[meta mask](https://metamask.io/)——它有一个针对 Chrome、Firefox 和基于 Chrome 的浏览器(如 Brave)的浏览器扩展。MetaMask 归 [ConsenSys](https://consensys.net/about/) 所有，该公司称自己是“领先的以太坊软件公司”

ConsenSys 还拥有 Web3 中领先的 ide(集成开发环境)之一。 [Truffle](https://trufflesuite.com/) 是一个“使用以太坊虚拟机(EVM)的区块链的开发环境、测试框架和资产管道。”除此之外，它还提供了“智能合同生命周期管理”和“自动化合同测试”

## 学习以太坊(和 Rust)

现在我们来看看 Web3 栈更复杂的方面。到目前为止，大多数开发人员都熟悉区块链的概念——基本上，它是一个分布式的数据分类帐。但是有许多不同类型的区块链。两个最重要的是比特币和以太坊(并非巧合的是，与这些区块链相关的加密货币是两个市场领导者)。但是，尽管比特币几乎像计算器一样可编程——正如以太坊研究员[贾斯汀·德雷克](https://www.linkedin.com/in/drakefjustin)在[播客的一集](https://www.joincolossus.com/episodes/14242194/drake-ethereum-into-the-ether)、 *Web3 故障*中所说——以太坊是一台完全可编程的“[图灵完成](https://en.wikipedia.org/wiki/Turing_completeness)计算机。

以太坊的可编程本质导致了以区块链为中心的 web 开发栈的新范式——也就是所谓的“Web3”。以太坊的原则之一是，理论上，你可以在它上面建造任何东西。用 Web 2.0 的说法，这是一个网络平台。以太坊是最大的 Web3 平台，它也兼容其他一些区块链。因此，成为 Web3 开发者的主要途径是学习如何使用以太坊。

你可能听说过以太坊区块链的编程语言 [Solidity](https://soliditylang.org/) ，有点像 JavaScript。虽然这是真的，但 Solidity 只用于为区块链编写“智能合同”——将数据放在区块链上，以及对这些数据的任何指令。

“在区块链世界中，学习可靠性和 EVM(或以太坊虚拟机)可能是区块链开发者入门的最佳选择，”达比特在他的文章中解释道。“使用这个技能组合(和技术堆栈)，你不仅可以建造以太坊，还可以建造其他以太坊二层、侧链，甚至其他区块链，如 Avalanche、Fantom 和 Celo。”

然而，作为对 Web 2.0 世界的另一种认可，Rust 也正在成为智能合约开发人员的必备技能。达比特引用索拉纳、尼尔和波尔卡多特作为区块链拥有“一流铁锈支援”的三个例子

“我想说，Solidity 和 Rust 是智能合约开发中使用最多、需求最大的语言，”Dabit 告诉我。他补充说，有经验的聪明的合同程序员，因为他们相对较少，可以轻而易举地获得“几十万美元的年薪，我甚至见过一些最有经验的人年薪达到 100 万美元的例子。”

## 如何存储数据和查询数据

Web3 开发中最棘手的部分之一是存储和使用数据。虽然区块链擅长于成为不可变数据的“无信任”链，但它们在存储和处理大量数据方面的效率也低得令人难以置信——尤其是对于 dapps。这就是 IPFS、Arweave 和 Filecoin 等文件存储协议的用武之地。

Arweave 是一个开源项目，它将自己描述为“一个允许你永久、可持续地存储数据的协议，只需一笔预付费用。”它本质上是一个点对点(P2P)网络，但有自己的一套加密术语——它的挖掘机制被称为“随机访问的简洁证明(SPoRAs)”，开发者可以将应用部署到“permaweb”(一个建立在 Arweave 之上的永久和分散的网络)。

更复杂的是，dapp 开发人员可以选择使用“链外”解决方案，将数据存储在主区块链以外的地方。两种常见的形式是“侧链”(二级区块链)和所谓的“[第二层](https://academy.binance.com/en/glossary/layer-2)”(L2)解决方案，如比特币闪电网络和以太坊等离子体。关于如何在 Web3 中进行数据管理的更多信息，请查看[最近发表的这篇关于新堆栈的文章](https://thenewstack.io/how-blockchain-startups-think-about-databases-and-dapp-efficiency/)，作者是来自 data API 公司 Fauna 的 [Shashank Golla](https://www.linkedin.com/in/shashankgolla/) 。

至于如何索引和查询区块链上的数据，这是一个相对较新的发展领域。但是如上所述，Dabit 正在开发一个解决方案 Graph，由 GraphQL 提供支持。此外，它使开发人员能够在应用程序中使用 GraphQL 直接从 L1 或 L2 连锁店进行查询。

## 去中心化:Web3 开发者的困惑

根据 Dabit 描述的 Web3 堆栈，很明显，传统的 Web 编程技能——从 JavaScript 到 Rust——将在 Web3 开发中给你带来好处。但是你也必须学习如何使用智能合约来编程区块链，并适应加密文件存储和离线解决方案的陌生世界。

从开发者的角度来看，Web3 目前似乎正处于过渡期，试图找到摆脱对比特币基地、OpenSea 和 Alchemy 等集中式服务的依赖的方法。但这样做是所有复杂性的来源，因为对于 dapps 来说，真正的去中心化真的很难实现。

我很想知道 Web3 栈在 2022 年将如何发展，因为它正在寻找实现自己的去中心化宣传的方法。与此同时，如果你想了解更多，请查看 Nader Dabit 的 [Web3 开发者指南](https://edgeandnode.com/blog/defining-the-web3-stack)。还有[去年 10 月在 Next.js Conf 上做的一个演示](https://www.youtube.com/watch?v=f9XRH7bjV8M)，他在其中解释了堆栈(这就是这篇文章的特征图片的来源)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>