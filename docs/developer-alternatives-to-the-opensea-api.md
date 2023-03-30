# OpenSea API 的开发者替代品

> 原文：<https://thenewstack.io/developer-alternatives-to-the-opensea-api/>

就在同一天，推特宣布 [NFT 个人资料图片](https://help.twitter.com/en/using-twitter/twitter-blue-fragments-folder/nft)作为其优质推特蓝用户的新功能，他们遇到了一个障碍，因为[NFT 开放海域 API](https://docs.opensea.io/reference/api-overview) 关闭了。按交易量计算，OpenSea 是 NFT 最大的以太坊市场；它还有一个 API，被许多其他服务普遍实现，如 Twitter 和加密货币钱包 MetaMask，在各种背景下向用户显示 NFT 艺术品。当 API 关闭时，这些映像变得不可用，许多服务失去功能。

OpenSea 最近因为频繁的停机时间而受到了相当多的批评，包括最近的这起事件——这与 Twitter 早期频繁出现“失败鲸”的情况没有什么不同(这种情况的 NFT 在哪里？).它的许多用户正在寻找其他的替代品。一个这样的用户是 [NFT 的 Salesbot](https://www.salesbots.xyz/) 服务，当 OpenSea 关闭时，它实际上已经死了。

## 分散生态系统中的集中化

对这种停机时间的核心批评之一是，OpenSea 在 Web 2.0 的集中式云基础设施上建立了一个分散式生态系统的市场，而不是利用分散式基础设施。在许多情况下，通过 OpenSea API 提供的图像托管在 Opensea.io 上，而不是对 NFT 智能合同中包含的 IPFS 元数据的引用。

关于那条推文的背景，Yaniv Tal 是 Graph 协议的项目负责人，这是一种基于 GraphQL 的索引和查询区块链数据的方法，由 Edge 节点开发。在区块链和 IPFS 的以太坊中穿行是一件复杂的事情，这使得查询起来既费钱又费时。该图可以索引区块链的数据，包括 NFT 智能合同、NFT 项目中各个项目的特征和销售历史，并以直接查询不可能的方式解析数据。

在与新堆栈的采访中，Edge&Node 的开发者关系 Nader Dabit 详细阐述了 Tal 的评论。

“OpenSea 是一种集中式服务，具有单点故障，一些其他应用程序依赖于它，所以当它关闭时，它会关闭一些其他应用程序，”Dabit 说。“我们目前正在对图形节点进行一些改进，以显著提高索引性能。这将允许我们部署一个 ERC721 子图，作为 OpenSea API 之类的东西的分散式替代。(它)可能还要几个月才能准备好，但我们有几个团队正在努力改进。”

## OpenSea API 的替代方案

 [杰克·卢丁顿

Jake 是一名自由记者和博客作者，对 Web3 技术、企业 IT 和流媒体视频充满热情。在推特上关注他@ jakeludington。](https://twitter.com/jakeludington) 

对于像 MetaMask wallet 这样的应用程序，依赖 OpenSea 的集中式 API 会给客户服务带来潜在的麻烦。当用户的钱包里看不到任何非功能性桌面时，他们会怎么想？MetaMask 缓存来自 OpenSea 的数据来防止这种情况，但理论上，除了性能优势之外，分散的基础设施会使缓存变得没有必要。也可能有用户更喜欢选择哪些 NFT 在他们的钱包应用中可见，而不是查看 OpenSea API 知道的每个 NFT。

MetaMask 的创始人丹·芬利(Dan Finlay)在[的一篇媒体文章](https://medium.com/@danfinlay/what-moxie-missed-on-web3-wallets-8dc572e7f39b#:~:text=Viable%20Alternatives%20to-,the,-Centralized%20NFT%20Index)的一部分中展示了集中依赖 OpenSea 的一些替代方案，这篇文章回应了来自 Signal 创始人[莫邪·马林斯派克](https://twitter.com/moxie)在 Web3 上的[反馈。例如，芬利说，“更好的解决方案是让资产检测成为以客户为中心的同意行为。大多数钱包允许添加自定义令牌。通过 EIP-747，MetaMask 还允许一个网站向用户的钱包建议一个定制的资产，因此用户的钱包成为资产的索引，不需要中央服务器。我们打算为非功能性测试做类似的事情。”](https://moxie.org/2022/01/07/web3-first-impressions.html)

Finlay 还建议 Uniswap 的[令牌将](https://uniswap.org/blog/token-lists)列为介于 OpenSea 集中化水平和个人用户输入钱包的手动收集 NFT 之间的一种中间地带。这里的想法是，社区可以将 NFT 收藏添加到列表中，并通过这种监管，在收藏中建立某种程度的信任——这分散了非功能性文献的索引。

到目前为止，没有迹象表明 Twitter 计划采用除了 OpenSea API 之外的东西。对于一个作为 Web 2.0 核心平台之一出现的公司来说，OpenSea 模式肯定是熟悉的。对于正在考虑去中心化的 Web3 公司，比如围绕 NFT 指数建立的钱包和服务，可能有其他的选择。但在短期内，它们需要定制工作来实现，而不是利用一个可以免费实现并准备集成的 API。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>