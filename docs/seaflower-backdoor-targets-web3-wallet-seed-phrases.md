# SeaFlower 后门目标 Web3 钱包种子短语

> 原文：<https://thenewstack.io/seaflower-backdoor-targets-web3-wallet-seed-phrases/>

Web3 和 Web 2.0 世界的核心区别之一是货币是工作流的核心。代币或者直接代表数字货币(在钱包中持有 BTC 的情况下),或者像 SOL 和 ETH 这样的代币可以服务于双重目的，作为投机货币和作为支付机制，用于访问建立在 Solana 和 Ethereum 区块链上的软件和服务的效用。这种内在价值促使不良行为者瞄准区块链网络中价值集中的点。

我过去曾写过关于桥梁安全风险的文章，这要求开发者将货币作为在区块链之间移动数据的一种方式。今年早些时候，一家防范在线广告中不良行为者的安全公司 Confiant 发现了一系列被其标记为“SeaFlower”的恶意活动，这些活动的目标是 Web3 钱包用户。

根据 Confiant 的威胁情报总监塔哈·卡里姆(又名 [@lordx64](https://twitter.com/lordx64) )在[发表的博客文章](https://blog.confiant.com/how-seaflower-%E8%97%8F%E6%B5%B7%E8%8A%B1-installs-backdoors-in-ios-android-web3-wallets-to-steal-your-seed-phrase-d25f0ccdffce)，受影响的钱包包括 iOS 和 Android 版本的比特币基地钱包、元掩码、令牌袋和 imToken。如果你从最初的开发者那里下载了这些钱包中的任何一个，它们使用起来都是绝对安全的。SeaFlower 正在分发折中版本的钱包。

## 什么是 SeaFlower？

在 Karim 的博客文章中，他说，“SeaFlower 是我们今年早些时候在 2022 年 3 月发现的一系列活动。我们认为 SeaFlower 是针对 web3 用户的技术上最复杂的威胁，仅次于臭名昭著的 Lazarus Group。”

Confiant 的检测工作发现，SeaFlower 不会以任何方式修改钱包功能，而是添加代码，最终允许获取钱包种子短语，这可能会导致受害用户丢失他们钱包中存储的任何资金。

用户获取与其他类型的网络钓鱼攻击类似。SeaFlower 正在流行的搜索引擎上开展广告活动，目的地网站与被欺骗的真实公司相似。如果你点击其中一个网站上的下载按钮，你会被重定向到假冒的 Web3 钱包应用程序。一旦安装了假版本并添加了资金，您就暴露了。

## Confiant 是如何识别被入侵的钱包攻击的？

大多数针对 Web3 种子短语的攻击都是网络钓鱼，就像 Confiant 在二月份强调的那样。

SeaFlower 攻击相当复杂，因为攻击者对实际的 Web3 钱包软件进行逆向工程，修改软件，然后发布新版本。他们还完全克隆钱包软件公司的合法网站，这意味着你需要既谨慎又精明，以免上当受骗。

iOS 攻击使用预置描述文件绕过需要 app store 批准。这导致攻击者能够远程管理受损设备。一般来说，请求远程管理应该是一个巨大的危险信号。

像这样的侦探工作之所以成为可能，部分是因为美国国家安全局(NSA)提供了像 [Ghidra](https://github.com/NationalSecurityAgency/ghidra) 这样的工具，用于软件逆向工程，对此@lordx64 明确表示感谢。

卡里姆在帖子中详细介绍了这次攻击，包括 React 本机元掩码应用程序是如何被入侵的。初始后门位于 MetaMask main.jsbundle 中，根据 Karim 的说法，“这个条件后门代码将在任何时候对路径包含“persist-root”的文件调用 writeFile()时执行。如果我们使用真实的 iPhone 来查看该文件的位置，它存储在 MetaMask 应用程序容器中，这是一个配置文件，包含在其他运行时配置数据中加密的种子短语。”

网络请求在种子短语生成后立即发生，这很可能意味着钱包从第一次使用就被破坏了。

根据 Confiant 对 SeaFlower 的报道，目标用户似乎位于以中文为主要书面语言的国家。这并不是说模仿者不能在其他地方尝试类似的方法，也不是说在其他市场没有类似的坏演员在运作。Windows 软件市场当然看到了其包含恶意软件有效载荷的商业软件替代版本的份额。下载 Web3 钱包时要记住的关键是要确保你是从原始开发者那里获得的，而不是某种代理网站。

请务必阅读一下[的完整博客文章](https://blog.confiant.com/how-seaflower-%E8%97%8F%E6%B5%B7%E8%8A%B1-installs-backdoors-in-ios-android-web3-wallets-to-steal-your-seed-phrase-d25f0ccdffce)——关于这种类型的攻击是如何发生的，有很多东西需要学习。同样值得一提的是 Confiant 的在线威胁分析的[矩阵，它包含了广泛的威胁，包括一些影响 Web3 的新案例。](https://matrix.confiant.com/#matrix)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>