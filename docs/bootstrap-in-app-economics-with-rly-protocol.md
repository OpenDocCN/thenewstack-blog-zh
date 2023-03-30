# 使用 RLY 协议的自举应用内经济学

> 原文：<https://thenewstack.io/bootstrap-in-app-economics-with-rly-protocol/>

分散式应用程序(dApps)通常包含一种经济结构，这种结构旨在随着应用程序的成熟而鼓励采用并保持用户参与。一些例子包括奖励连续在一定天数内登录的用户或为完成特定活动给予奖金。如果你试图从零开始，建立这些奖励的基本经济结构可能会很复杂，因为创建你自己的象征性经济会带来相当大的复杂性。假设你与你的法律顾问一起解决了任何监管要求，你仍然需要与交易所和做市商接触，以便让你的新代币上市并可供买家购买，以及一个流动性池，以便人们可以在他们想套现的时候套现。

[RLY Protocol](https://rly.network/) 试图通过提供一种解决方案来为 dApp 开发人员消除这种复杂性，开发人员现在可以将该解决方案构建到他们的应用程序中，而无需经历为另一个新令牌创建市场的所有步骤。在接受《新书库》采访时， [RLY 网络协会](https://wiki.rly.network/rly-network/introduction/rly-network-association)的首席运营官[加甘·帕雷查](https://twitter.com/gaganp?lang=en)说，“RLY 的存在是为了让建立代币经济更容易。RLY 协议的要点是我们混淆了建立令牌经济的操作复杂性。我们通过开源智能合约做到了这一点。如今，您可以使用 RLY on FLOW、ether eum[和] Solana，Polygon 支持即将推出，长期计划将支持所有 EVM 兼容链。”

## 将 RLY 添加到应用程序的经济性中

将 RLY 集成到您的应用程序中的最简单的方法是直接使用 RLY 令牌。通过这样做，你使用的硬币已经在一些交易所交易，可以相对容易地转换成其他区块链代币或法定货币。直接使用 RLY 代币的另一个好处是可以获得 [RLY 奖励](https://wiki.rly.network/rly-protocol/overview/rly-rewards)，这是一种激励结构，开发者可以使用它来促进 dApp 参与。

Palrecha 解释道:“通过在您的应用程序中使用令牌，您可以实现 RLY 奖励。我们以 RLY 代币的形式向开发者提供奖励，帮助他们将代币引入他们的社区，并激励他们社区的发展。对开发者的奖励基于交易数量、钱包数量和锁定的总价值。”

这种使用 RLY 代币的一个例子是 Joyride 游戏。根据 DappRadar 的说法，其应用程序 [Solitaire Blitz](https://www.onjoyride.com/games/solitaire-blitz) (一款在 FLOW 区块链上开发的游戏)在过去 30 天内在全区块链的交易量方面位列[十大游戏](https://dappradar.com/rankings/category/games)，在用户总数方面排名第三，仅次于《异形世界》( WAX 区块链)和 Axie Infinity(浪人区块链)。纸牌闪电战使用 RLY 作为其游戏内货币。Palrecha 估计，通过使用代币，Joyride 每周至少可以获得 100，000 美元的奖励。“我们发现，这些奖励补充了人们在游戏中购买使用的东西，”帕尔雷查说。“他们越来越多地参与游戏，因为他们有更多的可用资金，但没有人将这些资金用于套现。”同样值得注意的是，纸牌闪电战目前在美国还不可用。

## 使用 RLY 协议启动您自己的令牌

一些开发者使用 RLY 令牌绑定合同来创建他们自己的令牌。有各种各样的原因可以让你选择这样做，包括给你的应用打上更紧密的烙印，或者从头开始设计你自己的经济。这些令牌通过绑定曲线直接绑定到 RLY。简单地说，作为开发人员，您可以决定为每个现有的 RLY 令牌发放多少个令牌。

有多种方法可以建立令牌绑定契约。贾斯汀·戈罗在媒体上提供了一个[的详细解释](https://medium.com/coinmonks/token-bonding-curves-explained-7a9332198e0e)。RLY 协议令牌绑定合同将您创建的新令牌绑定到 RLY，因此可用令牌的总数取决于您在发行时定义的绑定曲线以及 RLY 令牌的供应。通过绑定到现有的流动代币，用户可以兑换成其他货币，而无需像前面提到的那样为代币建立一个流动市场。

你可以在 [GitHub](https://github.com/rally-dfs/rly-ts) 上查看 RLY Network 的类型脚本库、命令行界面工具和索拉纳区块链的示例应用程序。他们还维护了一个实时的 React 演示。关于如何使用 RLY 协议开源智能合约来创建自己的令牌绑定曲线的大多数问题都在他们的 [Discord](https://discord.com/channels/727244969168863316/986308294152957992) 中得到回答。

使用 RLY 无法解决的一个问题是，您需要聘请法律顾问来确定您的经济结构在您计划开展业务的任何司法管辖区将如何被接受。同样值得注意的是，Palrecha 表示，使用 RLY 创建代币经济并不是为了像首次硬币发行(ICO)那样成为一种筹资解决方案，而是为了让为 dApp 设计经济变得更加容易。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>