# 左移:安全专家应该如何为开发人员准备 DevSecOps

> 原文：<https://thenewstack.io/shift-left-how-security-pros-should-prepare-developers-for-devsecops/>

从传统的安全方法(我们可以称之为“路障”模型，其中安全团队由于安全问题而阻止部署应用程序)转移到 DevSecOps 方法需要组织如何管理安全以及如何定义工程组织中所有利益相关者的责任的巨大转变。除了改变日常职责之外，许多转向 DevSecOps 的组织增加了新的角色，以帮助弥合开发、运营、安全和管理人员之间的差距。

下面是随着组织向 DevSecOps 发展，开发人员、操作员和安全专业人员的角色如何变化。

## **安全专家**

安全专家在 DevSecOps 模型中的角色与信息安全和应用程序安全的传统方法截然不同。DevSecOps 组织中的安全专家不是亲自评估更新或新应用程序的安全性，而是内部顾问，他们的主要职责是帮助开发人员获得工具和培训，以便他们自己部署安全代码。

在 DevSecOps 世界中，安全团队的职责通常包括创建或选择工具，开发人员和操作人员可以使用这些工具在开发过程的早期捕捉安全问题，或者在运行时响应安全事件。他们制定政策并决定安全策略。“他们也是需要更深入专业知识的案件的升级点，”云原生安全公司 Snyk 的创始人兼总裁 [Guy Podjarny](https://www.linkedin.com/in/guypo/) 解释道。“他们应该是一个管理机构，组织作为一个整体和不同的团队各自以一种保持组织安全的方式运作。”

> 安全专家在 DevSecOps 模型中的角色与信息安全和应用程序安全的传统方法截然不同。

DevOps 咨询公司[boxsboat](https://boxboat.com/)的培训主管 [David Widen](https://twitter.com/davidwiden) 解释道:“内部顾问应该对 DevSecOps 堆栈中的不同部分有相当好的理解。“他们必须弄清楚如何将 DevSecOps 作为一种产品或服务，供所有受影响的不同团队使用。”

安全专业人员的职业道路也发生了变化。特别是随着安全重心的左移，安全专业人员与开发人员产生共鸣变得越来越重要。尽管传统上进入 infosec 的途径是通过运营，但越来越多的安全专业人员具有开发背景。无论如何，能够理解开发人员，包括什么是难的，什么不是，对于 DevSecOps 组织中的任何安全团队来说都是一项关键技能。

## **开发商**

根据 Logz.io 的这份[报告，大约 63%的 DevOps 工程师认为自己和他们的团队对安全负责，而只有 31%的开发者认为自己对安全负责。然而，DevSecOps 通过将安全性纳入开发人员在构建/测试阶段需要解决的反馈循环中，将安全性的责任极大地转移给了开发人员。](https://logz.io/devops-pulse-2020/#security)

“现在，开发人员进行代码签入，一些自动化功能会告诉开发人员对不起，我们同意这段代码不能进入存储库，不能投入生产，”首席技术官、云原生安全提供商 [Sysdig](https://sysdig.com/) 创始人[洛里斯·德吉奥安尼解释道。“这完全没有人情味。开发人员的职责是找到这种东西并自动修复，而不需要安全人员告诉他。”](https://www.linkedin.com/in/degio/)

这对开发人员来说可能意味着更多的工作，因为在构建/测试阶段有更多的事情需要解决。另一方面，当安全专家因为开发人员不知道存在的漏洞而阻止发布时，没有发布日压力。此外，DevSecOps 非常依赖自动化，因此开发人员为确保代码安全而必须做的实际手工工作应该是最少的。事实上，可以说让开发人员尽可能容易地获得安全性是安全团队的工作。

## **系统管理员和 SRE**

在来自 Logz.io 的同一份[报告中，54%的系统管理员和 54%的 sre 认为他们自己和他们的团队负责基础设施和应用安全。Podjarny 说:“传统上，运营部门是与安全联系最紧密的部门，他们必须在日常业务中应用和操作大量安全措施。事实上，在 DevSecOps 的所有角色中，系统管理员和 SRE 的角色可能是变化最小的，因为工作流中的大多数变化都与代码开发和安全检查点之间的交互有关，而不是基础设施和运行时安全。](https://logz.io/devops-pulse-2020/#security)

## **新角色**

采用 DevSecOps 还包括在 infosec 组织内创建新的角色。一个想法是创建一个[安全冠军](https://thenewstack.io/devops-needs-security-champions/)，他不仅可以弥合安全、开发和运营之间的差距，还可以与执行团队沟通，以确保他们参与安全实践，并确保安全团队拥有运营所需的资源。

在其他新职位方面，越来越多的组织正在寻找安全工程师或安全自动化工程师，这突出了对能够创建和配置定制安全工具的安全专业人员的需求。

## **改变关系**

虽然角色的变化很重要，但开发、安全和运营之间关系的变化对开发安全运营的成功可能更为关键。Palo Alto Networks 的高级副总裁[Varun Badhwar](https://www.linkedin.com/in/vbadhwar/)[Prisma Cloud](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention)解释说:“将 DevOps 团队、传统信息安全从业人员、基础设施人员、网络人员纳入一个单一的工作组或委员会非常重要。“在这些团队中强制推行共同的目标和实践是朝着正确方向迈出的第一步。”

理解任何关于组织结构和角色的讨论都是建立在普遍性的基础上，这一点也很重要。“如果你是一名软件工程师，你想进入 DevSecOps，你绝对必须知道安全在真空中是如何工作的，而且还要知道安全在你的公司中具体是如何工作的？”加宽解释道。从建立适当的工作流程到选择正确的工具，了解组织内部的具体环境至关重要。因为每个人都以不同的方式管理他们的技术团队，并且有不同的优先级和技术堆栈，所以不仅要了解 DevSecOps 最佳实践的一般情况，还要了解它们如何与您的特定基础结构和业务相关联，这是成功的重要部分。

Badhwar 说:“我们真的看到对话转移到安全方面，在这个过程中成为顾问，真正关注政策和治理，并确保需求得到充分理解。”“这是一个巨大的转变，因为它为 DevOps 团队提供了更多的所有权和责任，使他们能够在流程的早期发现安全问题，并围绕安全建立意识和培训。”

由 [andrea krug](https://unsplash.com/@andreakrug?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash 上拍摄的专题图片。](https://unsplash.com/s/photos/prep?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>