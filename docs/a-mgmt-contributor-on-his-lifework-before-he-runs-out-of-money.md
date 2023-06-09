# 终生工作的管理贡献者(在他用完钱之前)

> 原文：<https://thenewstack.io/a-mgmt-contributor-on-his-lifework-before-he-runs-out-of-money/>

[旗语](https://semaphoreci.com/)赞助本帖，由[旗语 CI/CD](https://semaphoreci.com/) 平台为您带来。

 [沃伊泰克·奇乔

沃伊泰克正在 Semaphore 把营销和客户关系联系起来。在职业上，他喜欢与现代技术的创造者和动摇者密切合作。在业余时间，他写并表演口语诗。](https://semaphoreci.com/) 

[James Shubin](https://twitter.com/purpleidea) 是一名来自加拿大的 devo PS/配置管理黑客和生理学家。他写了“詹姆斯的技术博客”他还参与了他发起的名为“ [mgmt](https://github.com/purpleidea/mgmt) 的下一代配置管理项目。

在这次采访中，我讨论了 Shubin 的开源项目，以及它如何对云原生环境做出贡献。

**您是 [mgmt](https://github.com/purpleidea/mgmt) 的首席开发人员，这是一款“下一代分布式、事件驱动、并行配置管理”工具。你能告诉我更多关于这个项目的信息吗？为什么你认为它比市场上的其他配置自动化工具突出？**

从历史上看，人们认为基础架构是非常静态的，它不会改变—您只需设置四台或十台服务器，等等。现在最大的不同是我们把事情变得非常有活力。随着时间的推移，一天中的每一秒，基础架构都会不断发生变化。您将所有这些输入输入到 mgmt 中，输出也是非常动态的，因此我们可以更改内部的任何变量，并拥有一个快速、事件驱动的并行配置管理工具。

mgmt 的三个主要架构弧(并行执行、事件驱动和分布式拓扑)使其速度极快，响应迅速，有些人可能会觉得这在生产中有点冒险。正如 Julien Pivotto 在他的博客中所写的，“使用传统的配置管理，当你搞砸了一些事情，你仍然有时间在它被应用到任何地方之前修复你的配置。”他暗示，有了管理，就不再是交易了，“这让事情变得可怕。” **你认为配置管理世界已经准备好处理一个专注于创建快速且完全自主的复杂分布式系统的工具了吗？**

是的，非常恐怖，但也是必须的。人们说，“哦，太快了。我没有时间控制或查看我的东西。”事实是，即使是使用 Puppet 或 Ansible 或其他工具的人也会使用这些工具来破坏他们的基础设施。如果你真的想让 mgmt 慢一点，很容易让它做一些事情，然后等五秒钟，再做其他事情。这已经是可能的了，但是这是一个愚蠢的特性，实际上我们并不想拥有它。我们对此进行补偿的方式(以及每个人都应该做的方式)是，你用尽可能安全的代码描述你的基础设施，因为我们希望编译器和分析代码的工具在我们编译之前消除所有可能的错误。

以像 Puppet 这样的语言为例——空指针的等价物，或者他们所说的“undef”，在 Puppet 中是可能的，如果你的代码正在运行，你可能会有这个 bug。这种错误场景在 mgmt 中是不可能的，因为我们没有 null 的概念。你总要有一个设定值。这并不意味着你的程序不能有错误，但这只是我们消除一类错误，使你的代码更安全的一种方式。

**您正在使用 [etcd](https://coreos.com/etcd/) 在您的解决方案中实现分布式拓扑。在你的一篇博文中，你称之为“一项了不起的工程”这款软件已经[被 CNCF](https://www.cncf.io/blog/2018/12/11/cncf-to-host-etcd/) 接受为孵化级托管项目，是 Kubernetes 的核心部分。你能告诉我们更多关于你如何在你的项目中使用 etcd 的信息吗？**

我真正使用 etcd 的原因是，我需要一种能够进行分布式一致性的算法。在 etcd 的情况下，这是 Raft 算法。以合理的规模实现这种算法非常困难——这本身就是一个巨大的项目。我们需要解决这个问题，因为在机器集群中，我们希望能够做出所有机器都同意的一些决定。Kubernetes 需要这个，mgmt 也需要。

我们使用它的方式有点不同。我们将所有的 etcd 代码作为一个库导入到我们的代码库中——编译成一个包含所有代码的 mgmt 二进制文件。mgmt 和 Kubernetes 在并行方面的主要区别在于，mgmt 使用这些信息作为一个分布式系统，而 Kubernetes 在方法上相当集中。在 Kubernetes 集群中，只有一个决定因素。它仍然使用 etcd 来知道机器是否还活着，以及把东西放在哪里，但是在我看来，它并不是一个真正的有多个主机的分布式系统。

有了 mgmt，你也创造了自己的语言，对吗？

不幸的是是的。这是一件可怕的事情，因为多年来我知道我需要解决一个特殊的问题。我知道如何解决这个问题。我知道我需要实现小型特定领域语言(DSL)——一种对通用计算没有用的语言——只是为了解决这个问题。它使我能够执行很少几行非常安全的代码(不容易出错)来实时描述基础设施。

这基本上是一个未解决的问题:我如何告诉这个数据中心或世界各地的所有计算机，我希望它们做什么？你是怎么做到的？你写 C 代码，写 JavaScript，写 Golang 吗？这个问题不容易回答。我决定，对于基础设施，我可以建立这种特殊的语言来回答这些问题。我觉得是成功的。这种语言还有更多的东西，但它确实很酷，非常适合构建安全快速的基础设施。

**您是否认为管理在未来会对云环境做出贡献？你认为它会带来其他解决方案没有的实质性内容吗？**

我想这和你之前的问题有点关系。例如，如果你要使用 Kubernetes，Kubernetes 开发人员已经编写了大量代码，他们希望你告诉代码如何运行的方法是从一个 YAML 文件中的一百或一千个不同的开关中选择一个。这里有一个巨大的 YAML 文件；这是它看起来的规格；您可以选择这些值。这就是他们如何让你和那些电脑说话，告诉他们该做什么。这样做的问题是，总有人没有他们想要的功能。于是就出现了“请添加一个新的东西来做这个”的情况，这是一个很大的错误，问题是，“它真的足够灵活吗？”

Mgmt 让您构建自己的东西。比方说，你想实际上建立一个完全像 Kubernetes 那样工作的东西。理论上，你可以用 mgmt 代码编写你自己的小模块，基本上像 Kubernetes 那样运行，这只是一个软件项目。其他人可以根据他们的需求建造完全不同的东西。我认为这将是一个重要的决定性特征。我们在模块系统上投入了相当多的努力，这样最终某个不是我的人，并且对他们的基础设施的一大部分有一些想法，通常可用于许多不同的公司，将能够实现它。我认为人们最终会开始编写这些大模块，而模块本身可以是一个独立的产品，由 mgmt 提供支持。

你是 DevOps 和开源的狂热爱好者。你觉得这两个世界能长期齐头并进吗？正如你在博客中写的，“我不反对使用或贡献于许可授权的项目，但是我确实认为如果我们的大多数软件变成非版权的单一文化是危险的，我想反对这种趋势。” **你为你的项目选择哪种开源许可会影响它的采用过程吗？**

这是一个大问题，然后我们将永远不会得到它的结束。从根本上说，许可证的选择是你所在社区的组成部分。这是法律承诺。这就是你告诉你的社区:“这是我们希望被对待的方式，这是我们将如何对待你。”

我认为许可选择的多样性非常重要。从历史上看，我们称之为许可许可证，如 Apache v2、MIT 许可证等。然后是更强的左版权许可，如 GPL v3、v2、LGPL 和 AGPL，这是非常强的左版权许可。通过将 mgmt 置于 GPL 之下，我有效地告诉我的社区，“我向你们保证，我将保持我的工作是开放的，你们实际上是受益的，因为如果你们发送补丁，你们将得到你们的代码不会被专有的保证。”否则，基本上是获得免费劳动力；有些人可以接受，但有些人不行。甚至有一个笑话:“自由软件是自由的。开源和劳动一样是免费的。”实际上，是个低级的笑话。

我希望我们做正确的事。不幸的是，这非常困难，因为目前，我只是靠我的积蓄生活，而且我做这些工作没有任何报酬。在某个时候，我会花光所有的钱，我必须找到一个不同的计划。我希望我能找到一些资金和愿意贡献时间和金钱的人，为这个项目打补丁，因为如果我们不这样做，我们最终只会得到没有自筹资金的专有解决方案。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>