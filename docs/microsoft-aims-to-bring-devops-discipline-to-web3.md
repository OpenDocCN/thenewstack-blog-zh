# 微软的目标是将 DevOps 规则引入 Web3

> 原文：<https://thenewstack.io/microsoft-aims-to-bring-devops-discipline-to-web3/>

虽然 [Web3](https://thenewstack.io/its-a-web3-world-now-how-the-hype-compares-to-web-2-0/) 已经被[去中心化社交媒体](https://thenewstack.io/devs-are-excited-by-activitypub-open-protocol-for-mastodon/)的崛起所超越，但加强 [dApp 基础设施](https://thenewstack.io/web3-stack-what-web-2-0-developers-need-to-know/)的长期努力仍在继续。有点令人惊讶的是，微软现在已经加入了 Web3 革命，尽管是以一种低调的方式。微软 Azure 孵化团队的合作伙伴项目经理 Donovan Brown 告诉 New Stack，他希望将 DevOps 规则引入 Web3，以帮助新兴的行业规模化。

通过使用 Azure Pipelines 作为他的 DevOps 管道和 GitHub 来存储他的源代码，Brown 一直在进行一系列的 Web3 实验，并在介质上记录结果[。在一次电话会议中，我们讨论了他迄今为止取得的进展，以及为什么微软对区块链技术感兴趣。](https://betterprogramming.pub/building-a-devops-pipeline-for-the-ethereum-blockchain-3d30cba87ffb)

那么首先，考虑到加密行业已经收到来自开发者社区的批评，微软为什么对区块链应用程序感兴趣呢？

布朗回答说，Azure 孵化器团队是微软的一部分，“它着眼于未来，关注开发者(将)需要什么——他们未来将不得不解决什么挑战？”

他说，由于 Web3 已经成为互联网技术的一种趋势，该团队决定更密切地关注它，“并弄清楚这是什么东西。”

## 开发很多，但运营不多

布朗称自己有“很深的 DevOps 背景”,当他调查 Web3 时，他发现 web 3 缺乏运营严谨性。

“当我观察社区并四处闲逛时，我注意到，你告诉我如何编写智能合同，但我们都将它们从我们的机器上部署到 mainnet 上，就像，管道在哪里？开发人员、质量保证人员和生产人员在哪里？我在部署软件时所期望的保护在哪里？我意识到它不在那里。”

更重要的是，他发现这在 Web3 中比在 Web 2.0 应用程序中是一个更大的问题，因为区块链对错误的容忍度要低得多。

“这是永久性的——失败将永远伴随着你，因为没有办法将失败从区块链上抹去。这就像是，他们为什么没有实施 DevOps 最佳实践？”

他通过 Twitter 联系了 Web3 社区，并表示他收到了积极的回应——他们欢迎他的意见，并询问他将如何在 Web3 中实施 DevOps。因此，布朗开始使用 ConsenSys 拥有的“智能合同开发工具套件” [Truffle](https://trufflesuite.com/) ，并编写了一个测试 React 应用程序。

他告诉我，他的目标是让应用程序“在 CI/CD 管道中很好地发挥作用，并使用我们在微软拥有的所有工具。”

布朗指出，微软“正在与著名的以太坊软件公司 ConsenSys 建立合作关系”。(今年 3 月，微软成为 T2 咨询公司的投资者。)

## 蔚蓝来救援了

除了 React，布朗在 dApp 实验中还使用了什么技术？

“我们使用了 [Azure Static Web Apps](https://azure.microsoft.com/en-us/products/app-service/static/) ，”他回答道，“它几乎是特意为托管 dApp 而构建的，因为 dApp 只是一个 SPA(单页应用)前端，使用 JavaScript 与你的智能合同进行链上对话。好吧，静态 Web 应用程序就是为承载这些而设计的。这就像哇，这是一个完美的契合。”

然而，实现 DevOps 部分更加困难。Brown 发现，当将 SPA 部署到区块链时，“API 会在 JSON 底部的每个[智能]合同部署的地址中乱涂乱画。”这是不可接受的，因为这意味着他必须“重新包装我的整个前端”，以便从测试网转移到主网。

“嗯，在德沃普斯，”他说，“这是一件坏事。”

“你不会一遍又一遍地构建，”他继续说道，“你构建一次，然后一遍又一遍地部署相同的二进制文件。所以我必须进去弄清楚，这些模板是怎么写的？幸运的是，因为 Azure Static Web Apps 免费为您提供 Azure 函数，所以我能够编写一个 API 来为我查询和查找地址，然后将地址注入到我的 SPA 中。所以现在，我能够一次性打包我的 SPA，并使用 Azure DevOps 或 GitHub 操作反复部署它。”

至于部署，他在他的 Medium 系列的第一篇文章中解释说，“开发环境将使用在容器中运行的 [Ganache](https://next-stack.github.io/ganache/) 将应用程序部署到个人以太坊区块链”，然后“QA 将部署到 [Rinkeby testnet](https://www.rinkeby.io/#stats) ，最后 Prod 将部署到以太坊 mainnet。”

他在我们的谈话中补充说，他使用的容器是通过 Azure 容器实例——“Azure 的另一个功能，我们已经有了。”

根据 Brown 的说法，使用上述过程给 Web3 开发者提供了安全部署到 mainnet 所需的验证。

“我们正在运行单元测试，我们能够完成您的验收测试，我们能够获得这种正常的 DevOps 体验，即使我们实际上使用区块链作为技术。”

## Azure 是否正在取代另一款 ConsenSys 产品？

布朗提到的一件事引起了我的注意。他说微软在 Web3 的合作伙伴 ConsenSys 正在“将他们的很多 Infura 网络转移到 Azure 上”

和松露一样，Infura 也归 ConsenSys 所有。早在四月，[我采访了 Infura 的联合创始人](https://thenewstack.io/web3-tools-and-tipping-points-a-chat-with-infura-co-founder/)，[例如 Galano](https://twitter.com/egalano) ，关于它如何补充松露。后者是一个开发者如何创建一个 app，所以它基本上是一个 IDE。但是我发现 Infura 更难找到。

Galano 解释说，Infura“就像一个持续运行的服务，最初由开发团队用来部署他们的应用程序，然后让用户与应用程序进行交互。”他把它比作网络托管服务，只是它不托管文件，而是使用 API 指向实际的数据源，在区块链或像 IPFS 这样的分散存储解决方案中。即使是现在，当我再次把它打出来时，我仍然对 Infura 是什么感到困惑。

我从 Brown 的评论中推断，像 Infura 这样的解决方案在正常的 DevOps 过程中可能不够健壮。如果是这样，这表明一些 Web3 基础设施很可能会被传统软件公司(在这种情况下是微软)篡夺。我们将不得不等待，看看 ConsenSys 如何处理这一进展，以及 Infura 会发生什么。 ***更新:**微软在发表后发邮件要求澄清:“多诺万并不是暗示 Infura 对于正常的 DevOps 程序不够健壮，而是将 Infura 视为 dApp 开发的必要步骤。”*

布朗补充说，微软还将与 ConsenSys“在开发者体验方面”合作他说，两家公司正在“弄清楚如何利用微软已经为所有开发者提供的生态系统，就像(ConsenSys)可以为 Web3 开发者利用的那样。”

## 微软的 Web3 探索

最后要注意的是，微软也在与其他 Web3 合作伙伴合作，主要是通过其风险基金 M12。一个例子是名为[时空](https://www.spaceandtime.io/)的去中心化数据平台，该平台计划[将](https://techcrunch.com/2022/09/27/microsofts-m12-led-20m-investment-in-web3-platform-space-and-time/)与微软 Azure 整合。

虽然这一切都处于试验阶段，但我毫不怀疑 Web3 行业将受益于微软的技术力量及其高度扩展的 Azure 堆栈。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>