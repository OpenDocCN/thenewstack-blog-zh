# Web3 堆栈的构成:Agoric、IPFS、宇宙网络

> 原文：<https://thenewstack.io/makings-of-a-web3-stack-agoric-ipfs-cosmos-network/>

想要一个简单的方法开始使用 Web3 吗？IPFS 生态系统成长工程师[协议实验室](https://protocol.ai/)的[迪特里希·阿亚拉](https://www.linkedin.com/in/dietrich/)在我们最新一期[新堆栈制作者播客](/podcasts)中建议，下载 [IPFS](/interplanetary-file-system-could-pave-the-way-for-a-distributed-permanent-web/) (星际文件系统)的[桌面副本](https://ipfs.io/#install)，并安装在你的电脑上。

我们已经听到了很多关于 Web3 及其去中心化承诺的炒作——它将如何通过使用区块链把网络的力量带回给人们。那是怎么回事？你如何构建一个 Web3 堆栈？你能用 Web3 栈构建什么？工具化和易用性社区走了多远？

这个虚拟面板播客开始回答所有这些问题。

除了与 Ayala 交谈之外，我们还与 Agoric 的产品经理 Rowland Graus 和管理宇宙网络的软件工程师 Marko Baricevic 进行了交谈。帮助区块链进行互操作的开源技术。每个参与者描述了他们各自的技术在 Web3 生态系统中扮演的角色。这些技术经常一起使用，所以它们代表了一种新兴的区块链堆栈。

TNS 主编约阿布·杰克森主持了讨论。在这里听一听，或者仔细阅读我们下面的笔记:

[web 3 Stack:Agoric、IPFS、宇宙网](https://thenewstack.simplecast.com/episodes/makings-of-a-web3-stack-agora-ipfs-cosmos-network)

## **智能合约开发工具**

Agoric 提供了一个智能合同框架和工具，供开发人员部署面向用户的应用程序，特别是在新兴的分散金融领域(DeFi)，Graus 说。特别是，Agoric 帮助开发人员管理构建基于 JavaScript 的智能合同所需的利益证明链。传统上，增加区块链需要计算机解决任意困难的难题(“工作证明”)，但 Agoric 的技术[利害关系证明](https://seekingalpha.com/article/4468656-proof-of-work-vs-proof-of-stake)使用对环境不太有害的方法来产生增加区块链所需的支付。格劳思解释说，利害关系证明“利用区块链本身的实际经济价值来保证安全”。

“这个想法是，如果有人把一个不正确或无效的东西放进去，他们这样做实际上会受到很大的经济惩罚，”Graus 说。

Agoric 本身实际上早于当前的区块链热，它一直在研究智能合同技术[几十年前由公司首席科学家](https://papers.agoric.com/papers/)[马克·s·米勒](https://en.wikipedia.org/wiki/Mark_S._Miller)开创。

## 用于可寻址内容的文件系统

Ayala 解释说，IPFS 之于 Web3 就像 HTTP 之于 Web 一样。您可以通过 IPFS 节点(您自己的或商业托管的服务)将文件发布到区块链，而不是将照片等内容发布到 HTTP 服务器。除了通过 URL(统一资源定位器)访问照片，您还可以通过其唯一的签名来引用内容。

签名是基于组成文件本身的实际位，所以他们可以验证文件是真实的。IPFS 是一种对等网络协议，因此数据的多个副本可以由不同的节点托管。但是对于用户或开发人员来说，可以在不知道文件在区块链上的位置的情况下检索文件。阿亚拉说:“这是寻址数据，不管它在网络上的什么位置。

像 Agoric 的利害关系证明一样，围绕 IPFS 的研究早于现代区块链，借鉴了几十年来围绕创建全球“内容寻址存储”目标的工作当然，内容可寻址数据非常适合多方分类帐。它也是维护 NFT 记录的基本元素([不可替换令牌](/nfts-in-the-uncanny-valley/))。

## 区块链互通

也许不可避免的是，不知疲倦的 Web3 企业家将会建造出不止一个区块链。那么他们是如何交流、交换信息的呢？这是宇宙网络着手完成的任务。像任何好的集成工具一样，它消除了为两个特定的区块链编写和维护专门代码的需要。

Baricevic 解释说:“一个区块链不必维护 500 个连接，它可以有一个到宇宙中心的单一连接，宇宙中心的服务器和验证器可以管理这 500 个连接。”整合工作并不简单。它涉及多个托管提供商、交易所和其他第三方提供商之间的协调。巴里切维奇称这种区块链和相关商品的聚集为“连锁”Cosmos 生态系统的骨干建立在[区块链间通信](https://ibcprotocol.org/) (IBC)协议上，该协议处理跨不同区块链的传输。

“在许多方面，你可以认为 IBC 就像 TCP/IP，其中定义了底层协议，但没有定义区块链之间的消息。开发这些消息，以及如何与其他链通信，实际上取决于应用程序，”他解释道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>