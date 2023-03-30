# 您的安全可能会扼杀您的无服务器

> 原文：<https://thenewstack.io/your-security-just-might-kill-your-serverless/>

[](https://www.protego.io/)

 [希勒尔·索洛

希勒尔·索洛是 Protego 的 CTO 和联合创始人。在此之前，他是思科物联网安全部门的首席技术官，负责为新技术市场开发创新的安全解决方案。](https://www.protego.io/) [](https://www.protego.io/)

我先说个趣闻。在与一家采用无服务器的大公司的安全人员进行的一次有趣的讨论中，我问她，安全组织为什么不拥有对应用程序的安全控制。"你们是如何让开发人员拥有 IAM 角色和 VPC 决策的？"我问。她的回答令人吃惊，但也很有启发性:“我们试过，但开发商威胁说他们会全部离开。”

我的本能，也许也是你的本能，是想，“哦，我的上帝，这些开发者真的已经接管了世界。”很容易将此归因于某种自大狂，并将其转化为一个故事，说明如今找到一个好的开发人员有多难。但这完全没有抓住要点，而要点很重要。

现实远比这更有启发性。要理解它，你需要回到无服务器的基础。当谈到无服务器时，公司往往会联想到几个关键价值，包括更低的计算成本、简化的操作和无限的可扩展性。不过，最终最大的收益往往来自应用速度。向无服务器的转移倾向于创建敏捷到极致的 DevOps 环境，在这种环境中，开发人员通常每隔几天甚至几小时发布一次错误修复和新特性。

这些应用程序的用户并没有忘记应用程序速度的提高，他们越来越期待新的功能和改进以惊人的速度出现。无服务器有助于实现这一速度，但也带来了一些成本。对于许多组织来说，管理流程和不断变化的代码山正成为一个挑战。监控和故障排除也是一项挑战。

安全也处于十字路口。故事中的开发商并没有醉心于自己的力量。他们只是陈述显而易见的事实。我们进行安全保护的传统方式，即开发人员编写代码并打包工作负载，安全运营人员围绕这些工作负载进行安全控制，不适用于无服务器系统。如果开发人员需要等待安全来为他们打开端口、IAM 角色或安全组，他们就不可能跟上他们自己创造的超加速速度。

> 找到平衡，开发人员不拥有安全性，但他们也不能免除责任。重新设计安全控制是如何应用的，这样开发人员就有了他们的控制，同时也防止了他们做那些会带来风险的事情。

相反，在可能的情况下，他们已经抓住了缰绳，这使得安全组织试图赶上并决定如何做出反应。一种选择是接受这种命运，并尝试专注于问题的监控和警报，但我们都知道安全打地鼠是一个糟糕的地方。另一个是尝试并收回控制权，但如果有一个安全规则，那就是确保您与业务保持一致，拖开发人员的后腿通常与业务不一致。

所以你做了就被诅咒，不做就被诅咒。除非你尝试第三种选择，那就是接受无服务器。找到平衡，开发人员不拥有安全性，但他们也不能免除责任。重新设计安全控制是如何应用的，这样开发人员就有了他们的控制，同时也防止了他们做那些会带来风险的事情。使用让安全性应用他们需要的控件的工具，但不要干扰开发人员快速更改代码的能力。创建让开发人员意识到他们的代码或配置带来的安全风险的流程，以帮助他们以无服务器的速度解决这些风险。

也许一个例子会使这一点更加具体。让我们举一个简单的例子，但它可以产生重大影响。无服务器功能有超时。开发人员可以将这个超时设置为从十分之一秒到几分钟的任意值。作为一名开发人员，我的直觉通常是将时间设置为最大值，因为我不会为我实际上不使用的时间付费。作为一名安全操作人员，我的直觉是尽量缩短这个超时时间，因为如果攻击者攻击我们的应用程序，他们的日子会更难过。

旧世界的选项要么是开发人员自己的超时，安全人员只能在以后检测到问题，并将其放在报告中，*或*安全人员控制超时，但开发人员需要协商超时更改，因为他们修改了他们的函数，这减慢了过程。

无服务器选项是拥有自动识别这种差异的工具，并与开发人员和安全操作员进行通信。开发人员获得了支持做出更好的安全决策的所有信息，包括*问题是什么，我们如何知道这是一个问题，为什么它会产生安全风险，*以及*如何减轻问题。*安全操作员获得工具来跟踪问题，并与开发人员就如何处理问题进行沟通，如果需要，还可以选择从安全级别进行补救，或者围绕有问题的功能重新配置安全性，直到问题得到妥善解决。

旧的“我们对他们”的世界已经一去不复返了，首先是因为它从来没有那么好，其次是因为它在无服务器环境下根本就不工作。拥抱新的世界，在这个世界中，每个团队都有自己的安全难题，但拥有支持与其他同行协作进行预防、检测和补救的工具和流程，您的组织将充分利用云原生和无服务器迁移。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>