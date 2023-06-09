# 如何在云中进行微服务集成测试

> 原文：<https://thenewstack.io/how-to-do-microservices-integration-testing-in-the-cloud/>

长期以来，在企业内部测试应用程序主要是基于实验室的事情。20 年前，一屋子的 Mercury 许可证和服务器副本应该来自一个测试团队。如今，复制数据中心环境几乎是不可能的，更不用说基于云服务的架构了。

当一个低级的测试人员不能构建像生产系统一样完整的测试系统时，他/她该做什么呢？有多种类型的解决方案，但是每一种在集成测试工作上都有自己的整体倾向。CA Technologies 公司长期支持的一个解决方案是服务虚拟化。

[亚历克斯·马丁斯](https://www.linkedin.com/in/alexmartinsit/)是 CA 技术公司负责持续质量测试的首席技术官。他谈到集成测试时说，“有很多实验正在进行，因为这是一个真正的挑战。我在大多数企业客户中看到的是，人们试图在他们的管道中引入某种程度的控制，而实现这一目标的唾手可得的结果是使用服务虚拟化作为一种快速而肮脏的技术来隔离您正在测试的内容。马丁斯说:“如果你正在进行内部测试，并且它需要云中的一些服务，那么你可以隔离这些服务，不要担心云。

然而，这仅仅是开始。“他们遇到的下一个挑战是，他们需要这些虚拟场景中的多样性。我需要大量不同类型的数据和不同的数据相关性来进行测试。这就是测试数据开始进入对话的地方。他们很快意识到，在基于云的环境中复制一个具有所有连接性和所有依赖性的真实测试环境成本很高，”Martins 说。

“他们的系统——尽管有些是基于云的——并不是以一种可以向多个地区或多种类型的受众或用户推出变更的方式来设置的。在生产中进行 A/B 测试需要不同类型的思维和技术。马丁斯问道:“期待银行这么做……出于明显的安全原因，他们这么做需要很多时间。”。

Martins 认为，这个问题主要是通过管理和过程而不是工具来解决的。“我不认为我们需要更多的工具。我们需要一种不同的方法来管理生产。如果我们看看更现代化的公司，以及他们将代码从生产环境转移到用户手中的过程:他们不认为生产是一件大事，我们将事情分割开来，由另一个团队处理，他们真的不理解代码做什么。这实际上更多的是一种思维方式的改变，以及一种流程和文化的改变。工具就在今天，将环境构建到云中。利用容器和适当的编排是一个开始，但要实现它并获得任何形式的投资回报都需要付出很多努力，但这是可能的。这项技术让你今天就能做到。这不是小事，但技术是存在的，”马丁斯说。

## 真实世界测试

StubHub 的首席技术官 Matt Swann 表示，生产测试是公司日常工作的一部分。他分享了一些关于集成测试的技巧和诀窍。我们通过电子邮件与他聊天，讨论他的团队如何能够在生产中进行测试。

**一个团队如何从标准测试转移到生产测试？**

测试是一个重复的术语，所以让我们从一些快速的定义开始。我们从以下几个方面考虑测试和学习:

“预构建假设测试”:我们正在实施一个基于精益 UX 的过程，关注于在周期中尽可能早地获得反馈，其中大部分将发生在“预构建”阶段

“轻量级基于证据的优化”[使用 Optimizely 这样的工具，我们可以在前端和服务器端修改上进行实验。

这些过程中的每一个都有以下元素:观察、假设、实验参数、度量(确定我们如何知道我们是对还是错)，以及后续步骤(如果我们是对的，我们将做什么，如果我们是错的，我们将做什么)。

将团队从“标准测试”转移到新的方法需要清晰的沟通新的过程，并帮助团队理解角色和好处。从小处着手，赢得一些胜利。从一个或两个团队开始，在那里投入时间进行培训和支持，收集证据(成功和学习),并调整流程以适应组织。当你的初始团队开始茁壮成长时，向其他团队推广这些变化。

**你如何确保基于生产的测试不会损害业务线？**

这里重要的部分是确保团队专注于获取“信号”并尽快学习。团队需要学习尽可能早地获得数据，证明我们的假设是正确的(小努力-小风险)，而不是实现大的、耗时的特性，然后学习(大努力-高风险)。当你是正确的，继续下去，并执行另一个测试，以了解更多。通过确保测试规模小且集中，您可以将公司的整体风险降至最低。

**为什么要在生产中测试？**

我们的测试理念基于始终以客户为中心的重要性。作为技术人员，我们可能会陷入这样的陷阱:假设我们知道什么对产品最有利，但这种想法可能是危险的。只有通过获得客户反馈并爱上客户的问题，我们才能创造创新空间并建立卓越的客户体验。

**在生产测试中，传统测试的哪些方面仍然存在？**

两种类型的测试保持一致的一点是过程的清晰交流，并确保团队理解角色和好处。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>