# 提供高质量的厨师烹饪书

> 原文：<https://thenewstack.io/delivering-high-quality-chef-cookbooks/>

在 DevOps 的世界里，工程师很像西部荒野中的牛仔。当涉及到测试时，他们通常会尽可能快地修复任何问题，以便将他们的更改推向生产。因此，经常不可避免地会有东西坏掉。本文可以提供一些关于测试 Chef Cookbooks 时实现最佳实践的实用建议。

### 测试文化(警告:可能导致代码的突然变化)

 [尼古拉斯·基

Nicholas Key 是 Okta 测试部门的首席软件工程师。他是主要关注基础设施的测试、测试过程和自动化文化的大力支持者。](https://www.okta.com/) 

首先，值得注意的是，我是自动化测试的大力支持者，作为一种积极开发、维护和改进组织的测试框架的方式，特别是针对 Chef cookbooks，这是我在 Okta 自己的组织所做的很多事情。作为一个简单的背景和例子，我们的业务主要集中在身份即服务(IDaaS)上，适应性多因素身份认证、单点登录和通用目录是其中的一些主要应用。我们与客户合作，通过 IDaaS 应用和组织来帮助连接他们的组织和用户，以此帮助他们在数字化转型过程中更高效、更安全。因此，让我们的客户安全地保持联系是我们业务的一个关键部分。如果我们的系统宕机，那么我们的客户将无法再根据我们的系统进行身份验证，从而导致停机和生产力损失。您可以看到测试成为确保您的核心产品更加可靠和不太可能失败的关键部分。

总的来说，虽然我们不一定能够防止食谱中的所有错误和问题，但是在您的 DevOps 团队中拥有强大的测试文化可以大大减少失败。由于团队能够在开发生命周期中尽可能早地测试变更，他们就能越早地发现错误，并最终在更简单的修复上节省资金。否则，如果这些更改被直接推送到生产环境中，并在随后被发现导致了问题，那么在生命周期的后期修复这些更改的成本往往会更高，并且回滚机制的修复可能会更加复杂。通过拥有强大的测试文化和过程，您可以在 DevOps 团队之间建立信任，同时也验证和确认食谱。记住这一点，在为您的组织实现测试系统时，有三个基本原则需要考虑:测试厨师食谱的文化、测试过程和附带的工具，以及最后的部署编排。

说到测试文化，典型的 DevOps 模型包括编写代码，部署代码，然后将代码发布到产品中。然而，您能想象如果一个团队对他们的代码所做的任何更改都使用这种模型直接部署到产品中吗？如果这些变化没有经过很好的测试，事情很容易出错。因此，你要问自己的问题(就信心水平而言)是:如果我的团队将他们的工作推向生产，他们有多少信心没有破坏别人的代码，同样，别人也没有破坏他们的代码？这让我想起了电视上的那些药物广告，它们列出了服药时所有可能的副作用和风险。冒这个险和可能的副作用真的值得吗？

考虑到这一点，建议组织考虑一个更成熟的开发部署模型，包括同行评审。或者更好的是，让 DevOps 组织内的质量保证团队测试食谱。这包括测试他们应该问自己的一系列事情，并交叉引用以确保更高水平的信心来发布他们的变更。这个新模型包括编码、测试、部署和监控。

### 测试流程和附带工具

作为一名测试工程师，我推荐五个关键的测试过程和工具，分别是林挺、单元测试、食谱依赖解析、食谱融合测试和集成测试。

例如，让我们来看看 ShellCheck 和 Ruby -c。在大多数情况下，会有一些 shell 脚本绑定到 cookbooks 中，这是一种常见的做法，没有多少用户真正测试或使用过 shell 脚本。因此，通过在林挺测试阶段使用 ShellCheck，这些 shell 脚本可以被替换，这样，当它们被部署到实际的机器上时，它们就不会被破坏或丢失。此外，由于 Chef 主要是用 Ruby 编写的，因此 Ruby -c 可以对 Ruby 模块进行语法检查。想象一下，如果用户编写和发布的任何 Ruby 模块没有经过语法检查。当他们试图聚合这些模块，运行检查聚合，并启动和运行实例时，事情可能会失败。因此，这里的目标是，当这些模块被捆绑到厨师烹饪书中时，它们已经被很好地链接了。

因此，一个定义良好的测试过程和工具的正确使用可以确保交付高质量的厨师食谱。

### 部署编排

现在，让我们想象一个组织没有大规模使用任何 Chef 工具，但希望编写自己的工具和脚本。此外，如果他们在部署编排中没有任何安全措施或风险缓解策略，这些更改将应用于所有 Chef 节点。

这可能导致潜在的系统范围的中断、未经测试的极端情况、很少甚至没有验证工作的烘焙时间，并且可能导致昂贵的回滚过程。

然而，部署编排就绪(包括 Canary、A/B 测试或分阶段推出)后，组织能够从风险缓解策略(风险接受、规避和限制)中受益，留出时间来验证和监控工作，减少与回滚程序相关的费用，并最终确保对部署工作的更高信心。

从根本上说，它是关于在所有实例中发布变更之前，将变更推出到实例的子集。通过将变更推送到实例的子集，团队可以监控这些变更，验证没有失败，如果有失败，分析这些失败是否属于风险接受类别的可接受的失败。如果所有的变更都通过检查，那么这些变更就可以被签署并发布到所有的实例中。这种方法清楚地表明了团队的成熟程度，即他们的变更是经过深思熟虑的，从而给予整个组织更高的信心。在将变更部署到生产环境中时，这种级别的信心尤为重要。总而言之，在部署变更之前，一定要计划和评估风险。

总之，当谈到测试厨师烹饪书时，有三个基本原则要记住。首先，测试厨师烹饪书的文化有助于确保信任，同时验证和核实代码。第二，有一个定义良好的测试过程，并正确使用工具，有助于确保交付高质量的厨师食谱。最后，在部署任何变更之前，始终要规划和评估风险。测试愉快！

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>