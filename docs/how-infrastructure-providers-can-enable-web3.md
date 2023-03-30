# 基础设施提供商如何支持 Web3

> 原文：<https://thenewstack.io/how-infrastructure-providers-can-enable-web3/>

[](https://www.linkedin.com/in/joshneuroth/)

[Josh Neuroth](https://www.linkedin.com/in/joshneuroth/)

[Josh Neuroth 是 Ankr 的产品负责人，之前曾在两家全球最大的数据中心提供商担任产品领导职务。](https://www.linkedin.com/in/joshneuroth/)

[](https://www.linkedin.com/in/joshneuroth/)[](https://www.linkedin.com/in/joshneuroth/)

最近，我离开了在数据中心和数字基础设施提供商领域工作了七年的职业生涯，加入了一家名为 [Ankr](https://www.ankr.com/) 的 Web3 初创公司，该公司现在是多链 Web3 基础设施的领先平台。

在跟踪 crypto 多年后，我开始看到 Web3 运动如何比“神奇的互联网货币”更深入，并有可能解决网络(可能是世界)内围绕隐私、自我主权和经济的一些最大问题。

Ankr 具有独特的定位，可以增强不同 Web3 应用程序及其底层区块链的功能，这是 Web3 最基本的支柱之一。自从我来到 Ankr，我们已经集成了 50 多个区块链，并向 70，000 名开发人员推出了 25，000 多个节点端点。换句话说，我们一直在以极快的速度工作，以跟上这项新技术的步伐。

## 什么是 Web3，它的数字基础设施有何不同？

让我们来看看网络的各个阶段。

### 网络 1.0 (1990 年至 2004 年):阅读和写作

互联网用户在雅虎、Geocities 和 MapQuest 等只读网站和目录上浏览信息，并创建自己的网站。Web 1.0 公司在办公室、电信数据中心或早期的托管数据中心托管服务器。

### Web 2.0 (2004 年至今):与云计算巨头一起阅读和写作

互联网用户不仅可以在网上查找信息，还可以实时交流并创建丰富的媒体内容，首先是在 Xanga 和 MySpace 等网站上，后来是 YouTube、脸书和 Twitter。数据的大规模创建引发了公共云服务和大规模集中式数据中心的创建。

### Web 3.0 (2021):阅读、写作和拥有

在 Web3 中，网站仍然需要托管在传统的 Web 服务器上，但是用户拥有并操作项目的一部分。为了促进所有权，网站直接连接到底层的区块链网络，如以太坊、币安智能链、索拉纳或 Fantom。

## Web3 如何工作

让我们用运行在 Fantom 区块链上的分散式金融网站 [SpiritSwap](https://www.spiritswap.finance/) 来探索这意味着什么。SpiritSwap 的网络应用托管在传统的网络服务器上，运行在[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)中。但当我想与 SpiritSwap 交互时，我需要使用浏览器扩展钱包，如[比特币基地钱包](https://www.coinbase.com/wallet)或 [MetaMask](https://metamask.io/) ，来连接和验证 web 应用程序。

可以把它想象成一个通用的单点登录工具。我不再使用 SpiritSwap 控制的用户名和密码登录 SpiritSwap，而是使用我的钱包登录。我的钱包包含我所有的数字资产，如加密和 NFT 的，同时也充当我的数字身份，由一个以“0x”开头的唯一十六进制地址表示。通过连接我的钱包，我可以交换和交易数字资产——就像我是纽约证券交易所大厅里的交易员一样。

在后端，我的钱包直接连接到另一台服务器，运行一个名为 node 的区块链应用程序。

该节点存储有关区块链的数据，并与网络上的其他节点通信，包括称为验证器的块创建者。请记住，这与加密货币挖掘完全不同；这些节点使用与典型服务器相同的电力。

因此，需要访问两台服务器:一台运行 web 应用程序，另一台运行区块链。

这就是数字基础设施提供商通过提供最佳服务器解决方案而在这些新系统中脱颖而出的地方。

## Web3 需要更强大的服务器基础设施

### 更多服务器

Web3 需要访问大量的服务器，由于担心集中化，该运动从根本上反对使用公共云。根据我们的估计，在 2021 年 5 月至 2021 年 11 月期间，Web3 项目和协议通过各种提供商租用了至少几千台裸机服务器。租赁如此多的服务器引起了 Equinix Metal 的注意，该公司在 9 月份举办了未经审查的区块链活动，以讨论帮助这一新领域发展的最佳实践。

> 仅在阿根廷，Ankr 的 RPC 服务每月就为超过 7 亿次请求提供服务，在尼日利亚和越南也有类似的统计。

[Hetzner](https://www.hetzner.com/) 推出了具有竞争力的 AX101 和 AX161 配置。然而，它只在德国和芬兰可用。不幸的是，提供商目前储备的绝大多数裸机服务器还不符合 Web3 的理想规格。

### 较少冗余

区块链是对等网络，本质上是分散的和分布式的。冗余无缝地存在于网络本身中。如果物理硬件出现故障或网络中断，区块链本身实际上不会受到损害。

在传统的企业环境中，通常会有多个电源、多层硬件和网络冗余。对于 RPC 完整节点，冗余的额外成本很少值得权衡。

### 更高的磁盘速度、大小和存储

把区块链想象成一堆乐高积木。第一块被称为创世块。栈一直延伸到天空，同时新的块不断被添加到顶部。每个块包含一组形成分布式分类账的交易。实际上，这是一个巨大的数据存储，通常在 [LevelDB](https://github.com/google/leveldb) 中运行，每天都在变大。

该数据库需要极快的磁盘读取速度和大量空间。我们已经测试了数十家提供商的数百种配置，在大多数情况下，网络连接存储选项和虚拟化技术都跟不上需求。这意味着，大多数采用常规固态硬盘和 4TB 以下存储的裸机配置都不足以满足高流量、生产级 Web3 工作负载的需求。

虽然 4TB 的 NVMe 是最小值，但对于 RPC 完整节点，我们更希望每台服务器至少有 8TB 的 NVMe。对于存储区块链完整副本的归档节点，我们倾向于每个物理服务器 12-30TB 的 NVMe，对于某些链，甚至更多。

Web3 节点的类型:

## 速度和低延迟至关重要

对于大多数基于以太坊的链，典型的 RPC 完整节点在块高度同步时仅使用大约 50mbps 的带宽。这意味着每台服务器每月传输 30TB 的数据绰绰有余。

去年，阿根廷比索对美元的汇率下跌了 20%。结果，仅在阿根廷，Ankr 的 RPC 服务每月就为超过 7 亿次请求提供服务，尼日利亚和越南也有类似的数据。

随着 DeFi 开始补充甚至取代传统金融，到附近节点的连接和更低延迟的连接已经是至关重要的金融基础设施。随着游戏应用程序采用不可替代令牌(NFT)进行游戏内购买和交易，延迟将变得越来越重要。

## 最后的想法

总之，Web3 有一个非常有前途的未来，正以闪电般的速度展开。成功的数字基础设施提供商可以通过提供新的裸机配置来帮助推动这一运动，这些配置速度极快，包含超大存储容量，并为传统和新兴市场提供低延迟。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>