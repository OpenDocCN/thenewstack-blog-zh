# Koii 网络对 dApps 采取基于模板的方法

> 原文：<https://thenewstack.io/koii-network-takes-a-template-based-approach-to-dapps/>

我们继续看到 Web3 的进入者将 JavaScript 放在他们的开发者解决方案的中心，这在很大程度上是因为 1600 万开发者社区。 [Koii Network](https://www.koii.network/) 是在 JavaScript 上下大赌注的公司之一，其首席执行官 [Al Morris](https://twitter.com/al_koii) 将该公司的五层堆栈比作基于类似 WordPress 模型的 Web3 的 MERN 堆栈【MongoDB、ExpressJS、ReactJS 和 NodeJS】。

## Koii 网络有什么不同？

Koii Network 是 Morris 作为芝加哥区块链研究所的一部分教授人们区块链的经验的结果，该研究所经营[我们教授区块链](https://weteachblockchain.org/)。他说:“Koii 是我所教的许多开发人员训练营的解决方案。我们遇到了很多大学生，他们真的想开发一个去中心化的应用程序，但技术确实还不存在。”

我所考察的每一家区块链公司在吸引开发人员的方式上都略有不同。在接受 New Stack 采访时，莫里斯这样解释 WordPress 的类比:

“这是关于有一个每个人都在其中运作的标准模式，”他说。“如果你制作了一个 WordPress 插件或主题，它的外观和功能是有规范的，这允许你从一个模板开始并修改它。我们试图实现的是多层堆叠。对于我们的五个核心层，我们所做的是为每个组件制作[模板](https://docs.koii.network/build-dapps-with-koii/template-library)，这应该允许人们使用一整套模板来构建一个完整的分散式应用程序。”

> 五个核心层是身份、接口、任务、结算和存储。

为了身份，Koii Network 发布了一款名为 [Finnie](https://koii.me/finnie) 的多链钱包，目前作为 Chrome 扩展提供。与 MERN 相比，Koii 接口层是使用 React 构建的，任务层是基于 Node.js 构建的。结算层是 Solana 的一个分支，用 Rust 编写，但 Koii 以一种不需要开发人员对 Rust 有任何经验的方式来实现它。存储层也可以通过 JavaScript 寻址。

Morris 强调的一个关键优势是，整个 Koii 网络栈可以在您的本地机器上运行，这允许更快的原型开发。

## 就消费设备达成共识

Koii Network 使用的另一种新方法是他们的节点实现，它可以在消费级 PC 上运行，并最终在移动设备上运行。Morris 解释说:“Koi 被设计为首先使用分散存储，并围绕它构建一层任务节点，这是人们的个人设备。我们这样设计是为了解决早期以太坊原型的很多问题。目前使用以太坊，每个节点都试图计算每个合同的新状态。有了 Koii，我们就有了所有这些消费设备。我们有 24，000 人注册运行 42，000 个节点，他们说他们想贡献一部电话和一台电脑。有了所有这些计算设备，我们基本上能够做到的是提供网络即服务，因此您可以设置自己的任务节点组，每个任务节点运行一项任务，它们检查彼此的工作，这就是共识节点，因此您可以按需创建高度可扩展的系统，所有这些都在分散的存储上运行。”

## Koii 网络的当前使用案例

Koii 网络的一个主要用例是莫里斯所说的“注意力挖掘”Koii Network 有这样一个概念:真实流量的证据，这是一种基于用户在其浏览器中安装了 Finnie wallet 的事实来奖励网站访问和内容查看的机制。这感觉有点像[勇敢浏览器](https://brave.com/)奖励你冲浪，但我可以看到这种可能性，如果这个概念被更广泛地采用，微交易可以降低内容网站的一些收费墙。

另一个有趣的应用是分散 cdn 的概念。Arweave 和 Filecoin 是分散存储的优秀解决方案，但在大规模使用时存在一些效率挑战。Koii 网络节点可以像边缘服务器一样运行，允许内容在人们访问它的地方被缓存，这极大地提高了性能。

就像我对其他区块链和 Web3 公司一样，我对 Koii 网络获得大规模采用的长期前景持怀疑态度。我对依靠人们在个人机器上运行节点来获得报酬的奖励结构特别怀疑，这可能是因为过去没有成功实现这一概念。像许多其他的 Web3 项目一样，Koii Network 有一个资助项目来帮助开发者启动应用程序。JavaScript 是开发框架的核心这一事实可能有助于获得更广泛的采用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>