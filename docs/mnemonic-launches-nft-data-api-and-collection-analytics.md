# 助记推出 NFT 数据 API 和收集分析

> 原文：<https://thenewstack.io/mnemonic-launches-nft-data-api-and-collection-analytics/>

NFT 的繁荣在相对较短的时间内创造了大量的 T2 数据。这些数据也分布广泛，定义不可替代令牌项目的智能合约存储在区块链上，但许多支持元数据在其他地方。

一些数据在[星际文件系统(IPFS)](https://thenewstack.io/interplanetary-file-system-could-pave-the-way-for-a-distributed-permanent-web/) 中，一些存储在像 AWS 这样的公共云基础设施中。将所有这些不同的数据点结合起来并分析它们以获得可行的见解是一项艰巨的任务。

[Mnemonic](https://www.mnemonichq.com/about) 建立了一个实时智能平台，该平台聚合了[以太坊](https://thenewstack.io/as-blockchain-hype-fades-developers-give-ethereum-a-serious-look/)上 100%的 NFT 的所有 NFT 数据，包括所有 NFT 收藏、 [ERC20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) 代币、 [ERC721](https://eips.ethereum.org/EIPS/eip-721) 和[ERC 1155](https://eips.ethereum.org/EIPS/eip-1155)NFT、历史交易数据以及定价和元数据。

在汇总了所有这些数据后，Mnemonic 更进一步，通过 API 公开了这些数据，为希望分析数据或将数据合并到自己的应用程序中的开发人员提供了一个数据基础架构层。

自去年 12 月以来，记忆法一直处于封闭测试阶段。在此期间，它与许多 NFT 创作者合作，通过助记 API 和可视化 API 数据的仪表板，提供他们对 NFT 系列的见解。

## 为什么要为 NFTs 构建实时数据平台？

在接受 New Stack 的采访时，Mnemonic 联合创始人兼首席执行官 [Andrii Yasinetsky](https://twitter.com/yasik) 说:“在我们的 API 发布之前，即使是简单的事情，如查看收藏的所有持有者都是谁也不容易。它还允许更复杂的分析，如收集时间序列数据。

“为了让更多用户进入 Web3 领域，我们需要这种基础设施。所有区块链上的数据量都在增长，数据增长的速度在加快，并且变得越来越复杂，以确保任何开发人员都可以利用所有这些数据，并在此基础上构建丰富的用户体验。”

这种体验的一个关键部分是实时验证 NFT 的当前所有者，这应该会增加对交易市场的信任，并可能导致 NFT 持有者验证的新方法。

## 从封闭测试中获得的经验

我问助记团队在封闭测试期间有没有什么有趣的发现。

据公司联合创始人、拥有机器学习博士学位的 Elena Ikonomovska 称，“构建初始仪表盘的一个体会是，早期用户希望知道如何对仪表盘进行逆向工程，并获得对其集合的额外分析。

“然后我们意识到这是除了基础 API 之外我们需要启动的第一件事。”

## 面向 dApp 开发人员的两个 API

如果您正在构建分散式应用程序，或者想要构建工具来更好地理解 NFT 空间，助记法有两个关键的 API 可供您使用。

该公司的[基础 API](https://www.mnemonichq.com/signup) 自去年 12 月以来一直处于私人测试阶段。这个 API 包括所有权信息、定价数据、转让和交换以及元数据。目前，它每秒钟可以免费调用 30 次，每月可以调用 500，000 个 API，助记法团队预计，这对大多数开发人员来说已经足够，可以在不产生任何成本的情况下构建和推出一个产品。

集合 API 提供了通过一个 API 调用来查询每个集合的历史时间序列和历史所有权的能力。

关于集合 API，Yasinetsky 说，“该 API 使查看集合的性能变得容易，只需几行代码就能获得高效的结果。例如，你可以一次查看一整年，或者细化到 15 分钟这样的粒度级别。”

这些 API 既可以作为 [gRPC 服务](https://docs.mnemonichq.com/api-usage/grpc/)使用协议缓冲区定义语言不可知的规范，也可以通过标准的 [REST 端点](https://docs.mnemonichq.com/api-usage/rest/)获得。API 请求的代码示例可以在 [Golang](https://thenewstack.io/go-1-18-the-programming-languages-biggest-release-yet/) 、Node.js 和 curl 中找到。

该团队在开始记忆之前拥有丰富的构建大规模数据服务的经验，承诺不会对 API 进行突破性的更改，并永久向后兼容。

## 助记 API 的用例

助记法的 API 有哪些常见的用例？Ikonomovska 说:“我们的平台今天正在为一系列广泛的用例提供支持，从一些更明显的用例，如 DeFi 空间，在那里你可能会认为 NFT 是可以交易的有价值的资产。

除此之外，API 还可以帮助回答其他问题。例如，她说，“看看可以创造的效用，想更好地了解什么样的钱包真正参与了这个系列。这些用户是创造者想在下次空投时奖励的吗？”

她补充说，API 还提供了“理解观众、粉丝、市场和钱包的创作工具。”

最后一个例子似乎是一个特别有趣的用例。API 允许您从特定的集合中获取关于已经获得 NFT 的钱包的数据。数据也可用于查看同一个钱包还有哪些其他收藏。

理论上，你可以开始利用这些数据来创建长相相似的用户档案，或者在 NFT 发布之前制定未来的营销策略。或者可能有其他用例，允许开发人员基于一群用户做出具体的实现决策，这些用户都参与了您的 dApp 并持有具体的 NFT。

对于认真的 NFT 收藏家来说，我还可以看到历史交易数据等用例，这些用例会揭露哪些藏品试图人为抬高底价。或者通过观察众所周知有影响力的钱包的购买习惯，或许可以抓住一个热门的新趋势。

这些 API 从今天开始供公众使用。在撰写本文时，如果你从助记术注册了一个免费的 API 密钥，你还将收到 1000 个免费的 API 调用，用于他们的新收集分析 API。助记符目前正在索引以太坊 NFT，但预计将来会添加额外的区块链。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>