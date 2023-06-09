# 为什么 DevSecOps 是云本地团队的新瓶颈

> 原文：<https://thenewstack.io/why-devsecops-is-the-new-bottleneck-for-cloud-native-teams/>

[Bridgecrew](https://bridgecrew.io/) 赞助本帖。

 [伊丹·滕德勒

Idan 是旧金山的一名连续网络安全企业家，他利用自己在 IDF 的精英情报和网络部门 8200 的服务经验，建立了一个不断扩大的成功企业组合。他的冒险包括在以色列领先的国防集成商 Elbit 建立网络安全业务部门；共同创立并主导 Fortscale，2018 年被 RSA Security 收购；现在是布里奇克鲁。](https://www.linkedin.com/in/idan-tendler/) 

*这篇文章是两篇文章中的第一篇，讲述了为什么 DevSecOps 最终会在云原生组织中适得其反，以及你可以做些什么。*

DevSecOps 和“左移”运动无需在 2020 年的新堆栈中介绍。多年来，开发人员、工程人员和安全人员都在谈论在开发生命周期的早期嵌入安全性。也有一些成功——AppSec 和容器安全肯定有过“左移”的时刻，像 Snyk 这样的工具率先将安全工具交到开发人员手中。

另一方面，云安全在发展前沿已经落后了。在不混淆相关性和因果关系的情况下，我们正在处理后果。云错误配置是数据泄露的[头号原因——数据泄露](https://securityboulevard.com/2019/04/most-cloud-breaches-are-due-to-misconfigurations-2/)[只会变得更加昂贵](https://www.ibm.com/security/data-breach)，而高管们只会变得[更加关注数据泄露](https://stripe.com/files/reports/the-developer-coefficient.pdf)。

在过去的一年中，在构建 Bridgecrew 平台时，我们与许多团队进行了交谈，以了解他们在云安全方面的成功和挑战。安全性和开发运维之间的协作是一个常见的(如果不是最常见的话)讨论话题。我们听说了一些云原生工程和安全团队是如何将极左的 DevSecOps 超级成功地整合到云中的。我们也听说了 DevSecOps 如何对其他人产生了反效果，制造了几乎不可逾越的瓶颈。在由两部分组成的系列文章中，我们将分享双方听到的共同主题。

## 冲突的目标和过程

众所周知，开发和安全的动机经常是不一致的。DevOps 被迭代工作和快速移动所激励，而安全性却因为成为障碍而受到指责。

DevSecOps 应该解决这个问题——通过 CI/CD 将安全性嵌入到代码审查过程中，从而将安全性集成到开发生命周期中——但是云安全性还没有实现。当前的云安全模型传统上关注的是已部署资源的安全性和合规性。虽然在一定程度上有效，但是该模型是在开发生命周期的之外由设计*产生的。它是被动的，而不是主动的，并且经常因为与它异步移动的敏捷流程而变得多余。GRC 工具和审计也是如此，其中云环境的时间点分析发生在工程冲刺和开发运维流程之外。*

这些摩擦点的发生部分是因为安全思维主要是保护性的，而不是预防性的。[云中的开发合作](https://bridgecrew.io/cloud-devsecops)也很困难，因为缺乏通过代码大规模开发基础设施的整体流程——更不用说保护它了。

## 不明确和不一致的政策治理

基础设施即代码(IaC)是对这一要求的回应，缓解了大规模部署基础设施的性能和成本相关挑战。像 CloudFormation 和 Terraform 这样的 IaC 框架为云基础设施带来了巨大的可扩展性和可重复性。它们也有自己的缺点。

IaC 创建了云基础架构的其他组合，由不同的团队使用不同的工作流进行管理。这些工作流在何时何地执行策略方面造成了层层复杂性和模糊性。在最好的情况下，这种模糊性造成了冗余；但在最坏的情况下，它会导致风险。想象一下，当工程人员假设云提供商工具或其他安全性购买的解决方案正在资源级别实施安全性和合规性策略时，会发生什么情况。同时，安全部门甚至不知道所有的配置框架都已到位，也不知道他们正在部署的资源是否有适当的策略。

同样，有了 DevSecOps 和 IaC，这些问题应该会得到缓解。但是，如果没有一致的努力来定义在哪里以及如何治理政策，最终会产生更多的工作。在此之前，治理将始终是某种程度上的手动，因此是不一致且耗时的过程。对于使用 IaC 时在运行时得到修复的问题(如 S3 桶上的加密缺失，或过于宽松的安全组规则)，我们发现有 70%的可能性会再次发生。如果没有一个工作流来从源头解决问题，那么当固有的错误配置的代码部署云资源时，就会产生更多的工作。

## 技能和准入差距

自动化工具——包括我们自己的开源 IaC 扫描仪，[Checkov](https://www.checkov.io/)——使得在开发和部署的不同阶段实施策略变得更加容易。它们揭示了从关键安全问题到信息最佳实践违规的一切。从表面上看，这似乎是解决我们的云开发人员困境的办法，但它往往会导致 it 部门试图缓解的瓶颈。

当发现配置错误时，这意味着需要做一些工作。安全性和合规性通常没有必要的权限访问代码仓库或云控制台来实施修复。即使他们知道，他们也可能缺乏专业知识和完整的应用程序或基础架构意识来自行修复云错误配置。

因此，他们打开一个票证，将其分配给一个团队领导，该团队领导可能在或不在与问题相关的团队中工作。然后补救就变成了麻木的冲刺。与此同时，又创造了十张“P0”票。有了自动扫描，这些票很容易滚雪球般增加到数百张，从一个团队转移到另一个团队，开始堆积在积压的工作中。

从另一端看，你有[有据可查的](https://threatpost.com/cybersecurity-skills-gap-career-development/158253/)网络安全技能短缺——这加剧了上述问题。结果，安全性和遵从性的责任被放到了开发人员的盘子上，他们通常[没有做好充分的准备](https://info.veracode.com/analyst-report-devsecops-global-skill-survey.html)。无论手头是否有安全资源，期望开发人员全面了解他们在构建云基础设施时可能面临的所有配置问题都是不现实的。这使得错误配置很容易被部署。这些未解决的错误配置不仅代表风险，而且在生产中解决它们的成本会成倍增加。然后循环重复。

DevSecOps 旨在将安全性纳入考虑范围，将其直接纳入软件开发生命周期，以尝试和避免可能导致应用程序、服务和基础设施易受攻击的错误配置或薄弱实现。随着我们继续将云安全硬塞进 DevSecOps，我们必须意识到这些问题，否则可能会降低流程速度，并在此过程中产生不必要的成本——这与 DevOps 的目标完全相反。

在第二部分的[中，我们将分享我们如何看到一些云原生团队克服云开发合作瓶颈。](https://thenewstack.io/three-ways-to-overcome-cloud-devsecops-bottlenecks/)

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>