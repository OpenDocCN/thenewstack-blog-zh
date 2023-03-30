# PurpleUrchin: GitHub 操作因加密挖掘而被劫持

> 原文：<https://thenewstack.io/purpleurchin-github-actions-hijacked-for-crypto-mining/>

Sysdig 威胁研究小组发现了一个广泛的加密挖掘操作 PurpleUrchin，它滥用免费的[持续集成](https://thenewstack.io/category/ci-cd/)和部署服务帐户。

这就是我们不能拥有美好事物的原因。许多[云](https://thenewstack.io/category/cloud-native/)和[持续集成/部署(CI/CD)](https://thenewstack.io/how-continuous-integration-and-continuous-delivery-ci-cd-enhances-devops/) 提供商，如 [Buddy.works](https://buddy.works/) 、GitHub 和 Heroku 提供免费服务，这很好。但现在，在一个新的大规模免费劫持案件中， [Sysdig 威胁研究团队(Sysdig TRT)](https://sysdig.com/blog/topic/threat-research/) 发现攻击者使用超过一百万个免费的无服务器函数调用，如 [GitHub Actions](https://github.com/features/actions) ，来运行一个巨大的自动化加密货币挖掘操作 [PurpleUrchin](https://sysdig.com/blog/massive-cryptomining-operation-github-actions/) 。

## 绝对规模

你问“免费抢劫”？这是滥用免费服务的旧技术的新名称。在这种情况下，释放计算资源。使 PurpleUrchin 与众不同的是它巨大的规模。这种高度混淆的多级攻击不是建立几个免费帐户，而是不断创建新帐户，然后植入 130 多个 Docker Hub 映像，同时定期在多个平台上轮换 [CI/CD](https://thenewstack.io/a-primer-continuous-integration-and-continuous-delivery-ci-cd/) 帐户。总共发现了 30 多个 GitHub 帐户、2000 个 Heroku 帐户和 900 个 Buddy 感染的帐户，威胁行为者同时瞄准了几个平台，并且似乎总是在寻找更多。

这些免费攻击可以很快累积起来。例如，GitHub 每月提供 2000 分钟的免费 GitHub 操作时间。对于 PurpleUrchin 来说，每个账户加起来大约有 33 个小时的免费运行时间。

当然，天下没有免费的午餐。在这种情况下，是提供商支付费用。Sysdig TRT 估计，每个“免费”的 PurpleUrchin GitHub 账户每月要花费 GitHub 15 美元。来自其他服务提供商的免费层帐户估计每月要花费提供商 7 到 10 美元。如果不加以控制，陷入困境的供应商最终可能会提高合法客户的价格，以弥补故意抬高价格的成本。

乍一看，PurpleUrchin 背后的人似乎只是为了从加密采矿中获得加密现金。但是，奇怪的是，PurpleUrchin 的所有者至少目前正在开发低利润的加密货币。Sysdig 认为，在 PurpleUrchin 的控制者转向比特币或 Monero 等更高价值的货币之前，这可能是“一种低风险、低回报的测试”。

## 更大，更恶心

然而，除此之外，Sysdig 担心 PurpleUrchin 有更大、更坏的想法。他们担心自己会追求加密货币的验证区块链机制。这些[工作证明算法容易受到 51%的攻击](https://www.investopedia.com/terms/1/51-attack.asp)，

51%的攻击可以工作，因为通常当挖掘者找到正确的散列组合时，新挖掘的块然后被添加到区块链并被加密网络批准。当网络一致认为某个块是合法的时，就会进行这种批准。然而，如果因为 51%的网络在你的控制之下，所以你控制了网络，你就可以破坏网络的不变性。完成后，PurpleUrchin 控制器可以验证与攻击者控制的任何加密货币钱包相关的任意交易。除了能够“伪造”硬币之外，他们还可以从其他矿工那里窃取价值数百万美元的加密货币，阻止其他用户的交易，或者通过[的双重消费](https://www.investopedia.com/terms/d/doublespending.asp)将它们反转并再次花费相同的加密货币。

这不仅仅是理论上的漏洞。2019 年有一个[成功 51%攻击以太坊经典区块链](https://cointelegraph.com/news/ethereum-classic-51-attack-the-reality-of-proof-of-work)。虽然比特币很难处理，但由于其庞大的规模，处理更小、更少的硬币相对容易。

我对加密货币一点都不信任，这有什么奇怪的吗？

但是等等！还有呢！

Sysdig 还担心这种“大规模的操作可能是其他邪恶活动的诱饵。”2020 年， [APT32](https://attack.mitre.org/groups/G0050/) (铋，OceanLotus)在受害者网络上部署了加密采矿操作，以逃避对他们同时进行的网络间谍活动的检测。

他们可能有所发现。PurpleUrchin 已经远远超出了普通的加密骗子。其攻击的范围和数量表明，背后可能有一个民族国家或主要犯罪组织。

Sysdig 总结道，“这是我们以前从未见过的，我们打算继续跟踪这项活动。”我们都应该如此。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>