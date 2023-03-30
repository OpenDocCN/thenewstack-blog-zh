# Infura 为多链开发增加了 NEAR 协议

> 原文：<https://thenewstack.io/infura-adds-near-protocol-for-multichain-development/>

如果你已经研究过在以太坊生态系统中构建去中心化的应用程序(dApps ),你可能已经看到 Infura 出现在你的研究中。它是以太坊区块链开发基础设施和工具的最大提供商之一。本周，Infura 的母公司 Consensys 宣布与 [NEAR Protocol](https://near.org/) 建立合作关系，该协议在名为[茄](https://near.org/papers/nightshade/)的第一层股权证明(PoS)区块链上运行。

此举是 Infura 继 2020 年整合 [Filecoin](https://docs.filecoin.io/about-filecoin/what-is-filecoin/) 之后，在以太坊虚拟机(EVM)兼容技术之外的第二次扩张。NEAR 协议的优势是能够实现比以太坊当前的工作证明设计更高的交易吞吐量，这意味着开发人员和用户的交易成本更低，并且还导致更低的能源足迹。

鉴于 Infura 在 EVM 空间的活动，我很好奇他们为什么选择扩大对其他区块链的支持。在接受 New Stack 的采访时，Infura 的联合创始人[比如 Galano](https://twitter.com/egalano) 解释说，“NEAR 团队从很早开始就是以太坊开发者社区的参与者。”

Galano 说，NEAR 已经“努力理解开发者的问题，并致力于最小化以太坊开发者在 NEAR 生态系统中工作所需的摩擦”。“他们的两项创新，在以太坊和 NEAR 之间转移资产的彩虹桥和 Aurora 网络(NEAR 支持的以太坊虚拟机兼容层)允许开发人员将 NEAR 作为一个部署网络，工作和摩擦少得多。”

## 近了会生锈

对于开发人员来说，部署到 NEAR 而不是以太坊的一个关键吸引力是支持在 Rust 中编写智能合同。鉴于 Rust 作为 web 应用程序的高性能解决方案越来越受欢迎，这消除了需要学习 Solidity 或找到 Solidity 开发人员来处理 dApp 中使用的智能合同的障碍。Galano 还说，“另一个吸引人的特点是快速的确认时间。NEAR 上的数据块大约每秒创建一次，这意味着更快的交易确认，从而改善了终端用户体验。”

NEAR 还在培训材料上投入了大量资金，通过丰富的[教育门户](https://near.org/education/)让你开始构建应用程序——包括开发者认证计划、[API](https://github.com/near-examples/workshop--exploring-near-apis)以及帮助 web 开发者和以太坊开发者学习 NEAR 协议的过渡材料。Galano 表示，Infura 正在进一步增加这一资源，为已经以某种身份参与 Infura 的 400，000 多名开发人员提供扩展的知识库和教程。

## 以太坊和 NEAR 之间的桥梁

正如本文前面提到的，Infura 在这种新关系中的吸引力之一是 NEAR 的彩虹桥技术。彩虹允许在以太坊和 NEAR 之间架设桥梁。例如，如果您从以太坊桥接到 NEAR，一个 staking relayer 将监视 NEAR 区块链，等待一个由所有 NEAR 验证器签名的 blockheader，然后将签名的 blockhead 发布到桥契约。这实际上允许 dApp 存在于以太坊区块链，但是利用了附近区块链的交易效率。

桥已经成为试图从区块链提取代币的不良行为者的常见攻击媒介。从安全的角度来看，Galano 解释说，“彩虹桥被认为是一座乐观的桥，它受到防欺诈措施的保护。桥梁安全的一个重要方面是团队对桥梁安全的持续关注和投资。NEAR 和 Aurora 团队制定了一个出色的 bug 奖金计划，为发现影响彩虹桥的关键奖金支付高达 600 万美元。”

这里有一个很好的解释彩虹安全的 Twitter 帖子:

## 结论

总的来说，对于已经利用了 Infura 工具和基础设施的开发者来说，这似乎是一个胜利。它提供了一个构建可扩展应用程序的机会，这些应用程序仍然可以完全集成到现有的以太坊 dApps 中。这也为熟悉 Rust 的开发人员提供了一个新的机会，让他们可以快速上手，在熟悉的基础上开始构建 Web3。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>