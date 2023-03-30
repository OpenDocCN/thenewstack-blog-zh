# 互联区块链的共享安全

> 原文：<https://thenewstack.io/shared-security-for-interconnected-blockchains/>

对较小区块链的一个合法威胁是，攻击者能够聚集 51%的赌注标记，并利用他们的多数地位从事恶意行为。当连锁拥有大量桥接资产时，参与这种类型攻击的动机特别强烈。攻击者占据多数席位，并有可能提取所有寄存的令牌。以太坊的联合创始人 Vitalik Buterin 在最近的 [Reddit 帖子](https://old.reddit.com/r/ethereum/comments/sgd3zt/a_quick_reminder_of_what_shared_security_means/)中解释了相关风险并提供了一些缓解策略。抵御这种攻击的一种方法是共享安全性，其中较大的区块链将其验证器借给较小的链。

[宇宙枢纽](https://hub.cosmos.network/main/hub-overview/overview.html)是[宇宙](https://cosmos.network/)的第一个区块链，这是一个计划一组互联区块链的项目。Cosmos 刚刚推出了自己的共享安全模型，名为[链间安全](https://informal.systems/2022/02/02/interchain-security-v1/)。

## 链间安全是如何工作的？

Interchain Foundation 的 Cosmos Hub 负责人 Billy Rennekamp 在接受 New Stack 采访时解释了这种共享安全模式的工作原理。“第一次迭代，v1 链间安全性，是一个完整的验证器集复制，其中一个提供者链，如 Cosmos Hub，为接收验证器集的所有网络设置了安全标准。我们称之为消费链。消费者链消费提供者链的安全性和验证器集，在本例中是 Cosmos Hub。

有一个路线图，通过将供应商链的验证器集分层，将这种验证器复制扩展到拥有自己的验证器、市值和安全保证的独立区块链。“这意味着复合安全性，”Rennekamp 解释说，“因为现在它是你的消费者链赌注令牌的市值，加上提供商链赌注令牌的市值。”

## 链间安全性给开发者带来的好处

Cosmos 对 Web3 的开发采取了一种有趣的方法。Cosmos 不是在以太坊或第二层侧链中的一个上构建分散的应用程序，而是设想一个世界，在这个世界中，你可以建立自己的特定于应用程序的区块链，通过其[区块链间通信](https://docs.cosmos.network/master/ibc/overview.html) (IBC)协议与其他链上的应用程序或服务进行交互。

在 New Stack Makers 播客的最近一集中，[inter chain 基金会的软件工程师 Marko Baricevic](https://www.linkedin.com/in/marko-baricevic-ab0b49214/) 将 IBC 比作 TCP/IP 作为网络通信协议的角色。就像 TCP/IP 建立了一个用于联网计算机发送和接收信息的通用协议一样，IBC 建立了一种在区块链之间发送和接收信息的方法。

Rennekamp 将该方法的区别描述为区块链的水平和垂直标度。“我们经常谈论垂直扩展区块链，”他说，“试图将尽可能多的交易放入一个区块。还有另一个尚未开发的水平可伸缩性概念，即您可以部署一个全新的区块链，与第一个并行。”

垂直和水平伸缩都存在安全问题，但是您可能需要以稍微不同的方式来考虑它们。

“这个平行的区块链可能不会像第一个区块链那样安全，”雷纳坎普继续说道。在利害关系证明网络中，通常有一个新的赌注标记；网络的安全性取决于这个标记是否有价值。因此，验证器集复制极大地提高了水平可伸缩性，在这种复制中，您可以在第二个链上重用相同的验证器集(来自第一个链)。从第一个链到第二个链重复使用相同的标记令牌意味着第一个网络的安全性被应用到第二个网络——它具有相同的安全性保证。”

今天，宇宙生态系统由 250 多个应用和服务组成，包括我最近写的一些应用和服务，如 Agoric 的[智能合同](https://thenewstack.io/is-javascript-the-future-of-smart-contracts/)和 Web3 的的 [AWS Lamda，Aleph.im](https://thenewstack.io/aleph-im-is-like-a-decentralized-aws-lambda-for-web3-dapps/)

当被问及共享安全对 Cosmos 的作用时，Rennekamp 说:“链间安全使 Cosmos 忠于其主权和开源的哲学，并使区块链能够在经济上而不是政治上融合。”

随着 Cosmos 继续向新的开发人员扩展额外的 dApps 和服务，集成的愿望也可能会继续增加。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>