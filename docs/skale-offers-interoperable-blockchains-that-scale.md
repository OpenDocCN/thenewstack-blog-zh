# SKALE 提供这种规模的可互操作区块链

> 原文：<https://thenewstack.io/skale-offers-interoperable-blockchains-that-scale/>

随着 Web3 的不断发展，扩展区块链的方法也随之发展。第 1 层区块链在每分钟可以处理多少交易方面有一些已知的容量限制，这也导致在高峰需求期间交易费用激增。SKALE 通过本周推出的 [v2 升级](https://skale.network/blog/modular-skale-chains-and-the-new-hub/)对区块链容量采取了模块化方法，将以太坊网络的优势与允许开发人员轻松增加额外可互操作区块链的设计相结合。

SKALE 与众不同，它是一个混合的第 1 层，具有第 2 层区块链特征。它是第 1 层区块链，因为它有自己的令牌和在 SKALE 网络中发生的交易。它还与以太坊集成，因此它提供了与以太坊第二层区块链类似的功能。通过增加额外的区块链，SKALE 能够动态增加容量。

在接受《新堆栈》采访时，SKALE 首席执行官[杰克·奥霍勒兰](https://twitter.com/jackoholleran)说:“当你想到 SKALE，而不是一个区块链，SKALE 网络是许多许多连锁店。现在斯卡莱有七家 EVM 连锁店。我们预计下个月会有 30 多个。这个 v2 版本所做的是让所有这些链开始相互对话，而不仅仅是与 mainnet 对话。”

如果你看看扩展以太坊的传统方法，其中第 2 层区块链卸载了一些事务工作负载，在互连方面有一些限制，导致用户摩擦。O'Holleran 说，“第二层汇总的问题是，在汇总环境中，用户无法在汇总之间进行沟通或桥接。他们必须回到以太坊主网，然后去另一个汇总。如果你考虑一个 Web3 应用的生态系统，用户不想支付过渡费用来从一个玩到赚的游戏中换出代币，然后去另一个第二层环境中购买 NFT。”

围绕 SKALE v2 升级讨论的一个更有趣的方面是，从推广的角度来看这是什么样子。节点于 4 月 19 日开始升级，并将在一周内升级。当我问 O'Holleran 任何区块链的潜在停机时间时，他说，“有 42 个独特的验证组织运行 152 台服务器，他们有一个升级计划。v1 上的任何当前链，如果超过 5 个节点同时升级，它将停止链的活动；所以部署是分阶段进行的，以确保没有停机时间。”

## 在 SKALE 网络上推出区块链

当你启动一个新的 SKALE 区块链时，连接到以太坊主网的另一个好处是分配给你的节点实际上是由以太坊主网分配给你的，这保证了 SKALE 中节点的随机选择有助于维护安全性。它还轮换为您工作的节点操作符，这在支持链的共享资源之间创建了一个抗共谋模型。O'Holleran 说:“你可以把它想象成 SKALE 网络中的以太坊链即服务，这些链速度快，吞吐量高。他们可以做存储，你可以免费制造 NFT，进行无汽油交易。”

我发现 SKALE 方法特别有趣的一个方面是专注于减少费用波动所固有的一些不稳定性。波动性给开发者带来了定价的不可预测性，也可能导致费用转嫁到最终用户身上，这在传统的 web 开发中并不常见。

关于波动性，奥霍勒兰说:“波动性影响利用率。SKALE 让开发者提前一年为链付费，并在此期间锁定这些资源，这意味着最终用户的交易费用为零。SKALE 让最终用户远离了这种不确定性，也让开发人员最小化了这种不确定性，因为资源被锁定了。”

这种波动性的降低也可以在围绕链定价的 SKALE 方法中看到。O'Holleran 说，“每区块链的价格也会根据网络负载而变化。供求比率有助于平衡连锁租赁者的波动性，因为定价与激励验证者建立更多节点的机制相结合，这反过来减少了所需的 SKALE 令牌的数量。这实际上是引入了现代供求经济学，并向区块链引入了更多的 B2B 平台即服务价格模型，以消除最终用户采用的波动性。”

## SKALE 方法与 Cosmos 有何不同？

我们在之前的几篇文章中提到过 [Cosmos](https://cosmos.network/) 是区块链的互联网。从表面上看，SKALE 似乎采取了相似的方法，所以我让 O'Holleran 强调一下不同之处。他说，“如果你看看宇宙生态系统，任何人都可以在任何时候启动宇宙区块链，但你需要获得自己的验证器，推出令牌，并创建自己的安全模型。Cosmos 与 SKALE 的不同之处在于，在 Cosmos 中，所有这些不同的链都使用相同的代码，然后他们有一个协议，允许人们在不同的链之间转移，但他们不共享这些不同链之间的任何安全性。SKALE 实际上在不同的链上汇集了安全性，这是一个由通用令牌支持的网络。”

SKALE 实现听起来确实非常简单，因为不需要建立自己的验证器。O'Holleran 进一步解释说，“SKALE 让人们启动依赖于一个令牌和这个大验证器池的链，这实现了一个更加互联的环境。这是一个区块链世界的愿景，但由于共享安全，这是一个建立积极网络效应的愿景。推出一个新的链更容易，因为你不需要获得一个根令牌，在那里获得验证器，并试图建立足够的股份来提供安全性，安全性已经在所有链中共享。”

Cosmos 试图通过允许区块链在其生态系统中采用共享安全模式来解决安全问题。听起来这可能是一个架构决策，您需要做出一些决策，决定您需要对您的区块链进行多少控制，以及您希望实现什么类型的互操作性。

## SKALE 上的建筑

为了激励更多的开发者去建设，SKALE 引入了一个 1 亿美元的[生态系统激励基金](https://skale.network/blog/skale-100million-usd-ecosystem-incentive-program/)。作为一名开发者，你可以申请项目资助来启动你的 dApp。目前有一个特定的重点是游戏开发商。

如果你有兴趣申请资助，有一个申请过程，需要提交一份建议书。该提案将提交给一个权力分散的委员会，该委员会将对项目进行评估，并批准或拒绝该请求。我没有得到拨款申请批准率的具体信息，但 O'Holleran 愿意分享积极建设项目的开发商在申请中获得批准的比例相当高。他将赠款模式描述为一种份额模式，在这种模式下，您可以在开发过程中达到里程碑时释放额外的赠款。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>