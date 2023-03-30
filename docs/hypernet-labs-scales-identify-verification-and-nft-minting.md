# Hypernet 实验室规模鉴定验证和 NFT 铸币

> 原文：<https://thenewstack.io/hypernet-labs-scales-identify-verification-and-nft-minting/>

由于 Web3 技术仍然相对较新，许多开发人员在处理 Web 2.0 中用已建立的第三方 SDK 解决的常见用例时，最终都是从头开始构建。

身份验证是工具相对不成熟的一个关键领域。 [NFT](https://thenewstack.io/how-non-fungible-tokens-are-disrupting-the-art-world-and-more/) 除了个人资料图片，定制解决方案是另一个比利用他人的基础设施轻松部署更常见的领域。

[Hypernet 实验室](https://hypernetlabs.io/)试图用他们的 [Hypernet 解决这些挑战。ID](https://hypernet.id/) 身份验证系统和他们的 [Hypernet。造币厂](https://mint.hypernet.io/) NFT 造币和分销平台。

## 简化 Web3 身份验证

具有财务组件的分散式应用程序(dApps)需要集成某种级别的“了解您的客户”( KYC)验证，以符合全球许多司法管辖区的法律要求。许多应用程序正在实施 KYC 流，这实际上意味着最终用户需要通过他们与之交互的每个应用程序来验证他们的身份。

Hypernet 实验室正试图通过提供一个 KYC 流来简化这个验证过程，这个流只发生一次，但可以被任何 dApp 验证。

超级网络。ID 方法极大地简化了验证用户的过程。用户连接一个加密货币钱包，并通过 Hypernet.ID 完成提交身份信息所需的步骤，如驾照和地址验证。在验证过程结束时，用户的钱包中会生成一个不可转移的 NFT。

Hypernet 实验室的联合创始人兼首席执行官 Ivan Ravlich 告诉新的 Stack，“我们写入 NFT 的更多的是被检查内容的映射。

“例如，一个用户来到 Hypernet。身份证，他们扫描他们的驾驶执照，并通过一个完整的 KYC 流程。在我们的后端，我们使用第三方来检查您是否在制裁名单上，您的 ID 是否经过验证，以及您的地址是否经过验证。我们可以将此扩展到许多其他类型的检查。

Ravlich 继续说道:“一旦这些细节回来了，我们就把不可转让的 NFT 放进用户的钱包里。”“NFT 中编码的是指示哪些细节被检查而没有暴露细节本身的数据，而不是在 NFT 中可识别的国家代码。”

开发人员在他们的智能合约中增加了一行内容，检查用户验证了哪些类型的信息，以及 NFT 是否仍然有效。关于实现的文档可以在[这里找到，](https://docs.hypernet.id/developer-documentation/developer-docs/contracts-integration)在 Github 上可以找到一个实度代码示例[。](https://github.com/GoHypernet/Hypernet.ID-Public/blob/develop/packages/contracts-integration/contracts/Test.sol)

Ravlich 说:“现在，你可以在链上验证身份，而无需任何人向这些智能合同提交更多数据。”“智能合约可以查看 NFT 的状态，并根据那里的元数据进行过滤，所有这些都是本地链上的，您不需要任何其他实体来验证该 ID。”

对于出于合规性原因需要持有驾照等详细信息的应用程序，Hypernet。ID 还提供了更深层次的 API 集成。

NFT 的不可转移性质应该提供最初被验证的用户仍然是同一用户的额外信心，并且消除了身份欺骗的可能性。从实现的角度来看，如果用户选择移动到新的钱包，他们将需要结合该新的钱包重新验证他们的身份，并生成与该新的钱包相关联的新的不可转移 NFT。

## NFT 大规模铸币

到目前为止，大多数受欢迎的 NFT 项目都集中在个人资料图片和艺术项目上，早期采用者已经表现出愿意经历重重困难，并承担[以太坊](https://thenewstack.io/as-blockchain-hype-fades-developers-give-ethereum-a-serious-look/)网络的高额交易费用。人们越来越热衷于为更实用的目的服务的 NFT，比如为订阅服务解锁额外内容，或者作为允许访问体验和活动的唯一令牌。

随着超级网络的发布。Mint，Hypernet Labs 正在采用与应用于 Hypernet.ID. Hypernet 相同的方法来简化用户体验。Mint 通过利用 Polygon 和 Avalanche 之类的第二层区块链提供了更低成本的部署，这些部署不像以太坊 mainnet 那样具有高昂的费用结构。

该公司还帮助 dApps 创建与业务目标一致的创造战略，支持大规模创造或基于用户加入流的创造，随着时间的推移，用户加入流可能会获得更多用户。

“我们正在为新类型的用户开发大量的入职流程，这又回到了用户的易用性上，”Ravlich 说。“假设你是一家动画工作室，你想为会员创造新的非功能性内容，并能够基于这些非功能性内容提供额外的内容。你的许多用户可能不是加密本地的。

“我们有一些动态加入技术，他们可以将用户引向他们的活动，帮助用户将新的非加密原生用户加入到生态系统中，并教育他们什么是钱包。他们得到了他们的第一个钱包，他们可以进来并利用我们的 ID 系统和造币技术，让动画工作室直接向他们通过活动带来的观众铸造这些会员资格。”

目前，NFT 的铸造过程需要与 Hypernet 实验室团队直接合作，以便与您的应用程序集成，但该公司正在考虑转向一种模型，在未来铸造过程可以完全自助服务。

为什么 Hypernet 实验室选择在第二层区块链上寻求支持，而不是直接在以太坊区块链上？Ravlich 说:“这实际上取决于人们想把非功能性食物放在哪里，以及这一潜在链条的性质是什么。”

“我们的许多早期客户已经在 Polygon 上运行 DeFi 类型的应用程序，或者他们喜欢 Stake 模型的证明而不是工作证明。还有一个成本方面，因为如果你在你的网站上创建了数百万个解锁内容的会员 NFT，很多成本要回到实际的公司本身——因为用户并不完全是 Web3 本地人，所以有一个教育部分只是给他们一个钱包，让他们加入系统。因此，你不能将[天然气成本](https://ethereum.org/en/developers/docs/gas/)转嫁给最终用户，因为这可能会令人困惑。”

Unstoppable Domains 之前将自己定位为 Web3 的[单点登录服务](https://thenewstack.io/unstoppable-domains-launches-a-single-sign-on-for-web3/)，看起来像 Hypernet。ID 可能是该角色的兼容附件，也可能是直接竞争对手，尽管现在确定谁将在 Web3 中率先实现身份管理似乎还为时过早。

NFT 的造币空间无疑有降低成本和简化采用途径的空间。无论是超级网络。Mint 成为 mint 工具的赢家还有待确定，但该公司肯定会为开发者和更广泛的用户采用解决一些正确的挑战。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>