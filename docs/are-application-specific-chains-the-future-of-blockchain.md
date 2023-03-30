# 应用专用链是区块链的未来吗？

> 原文：<https://thenewstack.io/are-application-specific-chains-the-future-of-blockchain/>

随着分散式应用程序(dApps)开发人员获得了更多使用区块链的经验，一些开发人员遇到了区块链架构参数带来的限制。例如，以太坊允许通过智能合约创建应用程序，但不允许自动执行代码。它还对向这些应用程序公开共识和网络功能的方式保持相当严格的控制。为了克服这些限制，一些开发人员转向了特定于应用程序的区块链——为他们特定的应用程序需求而专门构建和调整的，俗称“应用程序链”

构建 appchains 的一个更受欢迎的选项是 [Cosmos SDK](https://v1.cosmos.network/sdk) ，这是由于内置的可组合性、互连的区块链以及开发人员维护其区块链主权的能力。我们在过去报道过 Cosmos，包括一个用于学习在 Cosmos 网络中构建的[开发者学院](https://thenewstack.io/create-your-own-blockchain-at-interchain-developer-academy/)，以及新增的[链间安全](https://thenewstack.io/shared-security-for-interconnected-blockchains/)，它允许多个 Cosmos 区块链在维护主权的同时围绕共同的安全协议保持一致。

## Cosmos SDK 和应用模块化

在接受 New Stack 采访时， [Osmosis](https://osmosis.zone/) 的联合创始人 [Sunny Aggarwal](https://twitter.com/sunnya97) 表示，“Cosmos SDK 可以轻松构建您的定制区块链并修改核心代码。我们可以改变区块链非常核心的部分，以创造新的功能或创造其他 dex 没有的新的用户体验；例如，大多数区块链要求你使用本地令牌来收费，这总感觉像是真正糟糕的 UX。因此，我们对我们的连锁店所做的，为了获得大规模采用，我们意识到我们需要允许用户用他们想要的任何令牌支付交易费。”

这种创造支付灵活性的概念听起来可能像允许用户同时使用欧元和美元支付一样简单，但对于以太坊这样的区块链实施来说要复杂得多，因为区块链并不直接了解其他连锁店。由于 Cosmos 生态系统是为 Cosmos 区块链设计的，可以相互感知，因此可以更容易地定制支付等功能，同时保持对其他 Cosmos 兼容的区块链的感知。

Cosmos 构建应用链的一个优势是 Cosmos SDK 的模块化特性。Aggarwal 说，“有一组核心模块，所有基于 Cosmos 的区块链都可以重复使用，尽管人们会修改它们。例如，我们修改了打桩模块，但我们试图让它与上游模块保持一致。”模块化方法的真正力量是能够采用其他开发人员编写的模块来扩展核心 SDK 之外的内容。“开发人员编写额外的模块，其他应用链可能会复制这些模块，并将它们分支到一个 repro 中，”Aggarwal 说。“例如，我们已经编写了链上计时器模块，允许自动执行代码，并且许多链已经派生了该模块。”

## CosmWasm:使用 WebAssembly 的宇宙方式

Cosmos 区块链的关键优势之一是智能合同模块 [CosmWasm](https://docs.cosmwasm.com/docs/1.0/) ，它允许开发人员编写跨链智能合同。它主要适用于使用 Rust 的特定应用程序，并可结合 Cosmos SDK 进一步定制。Aggarwal 说:“CosmWasm 是作为 SDK 的一个模块构建的 Cosmos 智能合同系统。”“这已经成为如何在宇宙中建造东西的一种次要标准。更多的应用程序代码开发将转移到 CosmWasm 中，并像对待内核代码一样对待 Cosmos SDK，只有在没有其他选择的情况下才会修改内核代码。”

由于其灵活性，CosmWasm 也引起了一些政党的兴趣，这些政党希望将其应用于其他区块链。[可组合](https://www.composable.finance/)已经[将 CosmWasm](https://docs.composable.finance/products/technical-stack-overview.html) 实现到了 Substrate 和 DotSama 区块链，可以让他们结合可组合的跨链虚拟机做跨链智能签约。

## 分散式应用程序开发的经济学

根据 Aggarwal 的说法，支持 appchains 的一个特别论点是消除了[最大可提取值](https://ethereum.org/en/developers/docs/mev/) (MEV)泄漏。一般来说，在区块链，人们有强烈的动机去发现最有价值的交易，并在其他交易之前以更高的价格提交，部分原因是这是对共识解决方案的补偿。“更多的应用开发者将意识到拥有自己的应用链是有意义的，”Aggarwal 说。“第 1 层区块链的价值是您可以获得的 MEV。应用开发者将开始质疑他们为什么要向 L1 泄露价值，相反，他们可以在自己的链中获取价值，并将其作为收入分配给令牌持有者。”

7 月，HOPR 强调了围绕即将到来的以太坊合并的一些潜在风险，以及它可能如何为攻击验证器漏洞创造新的激励(见下面的 Twitter 帖子)。运行您自己的区块链可以从您的应用程序所依赖的底层基础结构中消除这类问题。

另一种看待运行您自己的区块链的经济方面的方式是创造成本效率的潜力，这与传统应用程序模型评估内部开发功能而不是支付第三方 API 调用的方式非常相似。特定于应用程序的区块链还消除了使用该链的其他人对资源的竞争，这意味着链上的所有事务都与应用程序用户的活动直接相关。理论上，这转化为更好的应用程序性能，进而转化为更好的用户体验。

从长远来看，我们可能会看到区块链本身更加商品化，更加关注应用程序以及这些应用程序如何支持用户的需求。Aggarwal 是这样说的:“我的论点是，随着时间的推移，L1 会被商品化，有价值的是应用程序，因为应用程序是与用户有关系的东西。如果你看看早期的互联网，押注互联网崛起的方式不是押注 AOL 和 Compuserve 的崛起，而是押注亚马逊和谷歌，它们是互联网的早期应用。以太坊应用将慢慢开始意识到这一点。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>