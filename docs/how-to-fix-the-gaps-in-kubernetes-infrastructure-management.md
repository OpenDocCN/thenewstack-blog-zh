# 如何弥补 Kubernetes 基础设施管理中的差距

> 原文：<https://thenewstack.io/how-to-fix-the-gaps-in-kubernetes-infrastructure-management/>

SaltStack 赞助了这个播客。

围绕 Kubernetes 的大肆宣传已经在 IT 行业产生了许多反响——尽管对于许多组织和 DevOps 团队来说，并非所有的影响都是积极的。基础设施管理就是一个典型的例子。用于 Kubernetes 部署和基础设施管理的安全管理工具经常缺失。最终，这些工具应该有能力通过自动漏洞检测和修复来弥补安全和 IT 技能缺口以及人才短缺。

[salt stack——如何弥补 Kubernetes 基础设施管理中的不足](https://thenewstack.simplecast.com/episodes/saltstack-on-how-to-fix-the-gaps-in-kubernetes-infrastructure-management)

SaltStack 的工程副总裁 Moe Abdula 说:“Kubernetes 是一种强大而有影响力的东西，但它有太多的组件和移动部件。“你如何确保能够围绕像 Kubernetes 这样的东西构建一个易于维护、易于支持、易于扩展的架构和系统？”

在本期 New Stack Makers 播客中，我们采访了 Abdula 和 SaltStack 工程副总裁 Gareth Greenaway ，探讨 Kubernetes 的基础设施和安全管理方面以及基础设施是如何和为什么被忽视的，风险是什么，以及可以采取什么措施来解决这些问题。

除了以越来越快的速度部署应用程序和更新的压力之外，Kubernetes 基础架构管理方面的差距在很大程度上可以用所涉及的复杂性来解释。Abdula 说，在许多情况下，DevOps 团队正在构建多个 Kubernetes 集群，并发现集群之间的许多配置不一致是应用程序无法一致部署或执行的主要原因。“他们意识到，自行开发的脚本类型或自行开发的人工干预方法无法扩展或防止重复错误，”阿卜杜拉说。

Abdulla 说，这就是为什么许多组织都在积极寻求复杂 Kubernetes 和容器环境的配置和基础设施管理工具，特别是在经历了上述与当今日益复杂的环境中的基础设施管理相关的问题之后。Abdula 说，一旦他们意识到这一点，DevOps 团队成员通常会说“‘让我想想如何实现自动化，这样我就可以创建一致性了。”。

这种需求反映了 SaltStack 作为容器和 Kubernetes 配置管理的解决方案是如何发展的。“在管理这些集群和基于容器的基础设施方面，管理这些集群的工具无法扩展到 SaltStack 这样的工具，”Greenaway 说。

在安全和 DevSecOps 领域，“你不可能指望通过寻找漏洞和手动维护来管理容器，”Greenaway 说。“我认为很多用手工方式做事的概念已经消失了，”格林纳维说。“我们已经放弃了这项技术的[手动]阶段，因为它不再是可持续的，”格林纳维说。

Abdula 说，去年发布的 SaltStack 6.1 的生产版本不仅有助于自动化基础设施和安全管理，而且“加快了政策与补救的结合”。

Abdula 说，SaltStack 6.2 的发布引入了一个组件，“允许我们实际上与安全工具链的其余部分集成”。“如今，人们已经在扫描漏洞或确定漏洞优先级的工具上投入了大量资金。因此，我们没有要求人们扔掉已经产生价值的东西，而是在前端创建了许多许多与扫描工具的集成，并自动转换结果，无需手动操作，”阿卜杜拉说。“然后，开箱即用，我们有自动化补救的基准，因此客户只需点击一个按钮就可以选择。”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>