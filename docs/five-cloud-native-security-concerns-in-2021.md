# 2021 年的五个云原生安全问题

> 原文：<https://thenewstack.io/five-cloud-native-security-concerns-in-2021/>

云本地计算越来越受欢迎。例如，在 2020 年，[云本地计算基金会(CNCF)](https://www.cncf.io/) 报告称 [91%的被调查公司都在使用 Kubernetes](https://www.cncf.io/blog/2020/11/17/cloud-native-survey-2020-containers-in-production-jump-300-from-our-first-survey/) ，其中 83%用于生产。得益于[云原生计算](https://thenewstack.io/category/cloud-native/)，团队可以使用[容器](https://thenewstack.io/category/containers/)、[微服务](https://thenewstack.io/ebooks/microservices/cloud-native-microservices-2018/)、[不可变基础设施](https://thenewstack.io/why-well-oiled-devops-rides-on-immutable-infrastructure/)和[声明式 API](https://thenewstack.io/the-declarative-power-of-apis/)轻松构建和管理云服务，而无需担心底层服务器。然而，云原生安全性仍然是一个真正的挑战。

奇怪的是——或许一点也不奇怪——云原生安全性的最大问题与所有新技术都没有任何关系。不，这是同样的老安全问题回来困扰我们。根据 [Matthew Chiodi](https://www.linkedin.com/in/mattchiodi/) 、 [Palo Alto Networks](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention) 公共云首席安全官的说法，事实上，如果组织希望在新的一年中处于更有利的地位，他们应该解决五个主要的云原生安全问题。有些很容易解决，有些则需要更大的组织改革。让我们一个一个来看。

## 关注点 1:未能使用多因素身份验证

在[帕洛阿尔托网络公司的](https://www.paloaltonetworks.com/) [Unit 42 云威胁报告，2H 2020](https://www.paloaltonetworks.com/prisma/unit42-cloud-threat-research) 中，Unit 42 Red 团队发现了一个简单的身份和访问管理(IAM)错误配置，该配置使他们能够破坏整个基于[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)的云环境，并绕过基本上所有的安全控制。是的，我们如何管理用户 ID、密码和身份验证在云原生环境中是一个真正的问题，比您的 PC 用户坚持使用“password”作为其 Windows 密码时更是如此。它们只会以“零售”规模伤害你的公司。对于云，我们谈论的是大规模的破坏。

“云原生身份和访问管理应该是组织的首要关注领域。你会听到很多关于“嘿，确保你启用了多因素身份认证(MFA)”的谈论这是最佳实践，”Chiodi 解释道。但是，这样做的次数仍然不够多。

雪上加霜的是，正如威胁演员黑暗光环在[太阳风安全惨败](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/)中所展示的，破解多因素认证措施是有[可能的。尽管如此，正如 Chiodi 所观察到的，部署 MFA 将使您的服务更加安全。Chiodi 建议在“云原生身份访问管理中使用 MFA，如果不是现在的第一重点，也应该是最优先的。”](https://www.volexity.com/blog/2020/12/14/dark-halo-leverages-solarwinds-compromise-to-breach-organizations/)

Chiodi 还注意到，“[网络安全和基础设施安全局(CISA)](https://www.cisa.gov/) 最近发布了关于 MFA 云服务攻击的警告，这些攻击使攻击者能够登录某个组织的云服务。”具体来说， [CISA 发现成功的 MFA 云攻击](https://us-cert.cisa.gov/ncas/analysis-reports/ar21-013a)使用了网络钓鱼、电子邮件转发漏洞，以及使用糟糕的网络卫生和“ [pass-the-cookie](https://stealthbits.com/blog/bypassing-mfa-with-pass-the-cookie/) ”攻击对远程用户进行暴力攻击。这里失败的关键不是复杂的云原生黑魔法，而是简单的旧终端用户安全失败。

换句话说，Chiodi 说，“安全领域有很多低挂的果实。”涉及的不仅仅是网络钓鱼。例如，在 Palo Alto Networks 最新的云威胁报告中，“我们发现，大约 66%的组织没有按照应有的频率轮换其访问密钥。最佳实践应该是每 90 天一次，但 66%的组织没有这样做。所以，只要注意你的基本身份卫生，你就能在游戏中领先。”

## 关注点 2:过度特权访问

也就是说，还有另一个相关的问题，您从过去的经验中也知道:特权过多的非管理员用户帐户。我们什么时候才能明白让用户以 root 身份运行程序只是自找麻烦？

最常见的例子仍然是基于 Docker 的容器作为 root 运行。仅仅因为你可以以 root 用户身份运行容器，并不意味着这是一个好主意。正如猫蔡所说， [Fair Financial 的](https://fairfinancial.org/)平台工程总监说，你应该使用[最小特权原则](https://thenewstack.io/three-realistic-approaches-to-kubernetes-rbac/)。也就是说，“运行在中的应用程序和访问集群的开发人员都应该只能访问他们需要的资源。”

## 关注点 3:错误配置

Chiodi 指出，另一个常见的安全漏洞是“对互联网开放的云存储桶和数据库”。这些都是错误的配置，不应该存在于任何人的云环境中。”答案不是一次解决一个问题，而是“自动解决这些简单的问题”

这需要以最糟糕的方式修复。由 Advantage Capital Funding 和 Argus Capital Funding 创建的云存储桶没有使用任何形式的加密、认证或访问凭据。结果呢？超过 50 万份机密的法律和财务文件在[被泄露。这些公司远不是唯一犯有这种简单的安全罪的公司。](https://www.zdnet.com/article/financial-apps-leak-425gb-in-company-data-through-open-database/)

Chiodi 说，“云存储是便宜的”，但“如果你看看合规要求，如加州消费者隐私法案(CCPA)和欧盟的 GDPR 都有严格的个人数据保护标准，罚款非常昂贵。”这些法律成本比你从糟糕的云存储和数据库安全中得到的任何节省都要昂贵得多。

## 关注点 4:忽视建筑安全

Chiodi 也是安全左移的忠实信徒。这个短语意味着将安全性转移到开发过程中尽可能早的阶段。正如 Chiodi 指出的，这一点尤其重要，因为在[持续集成和持续交付(CI/CD)](https://thenewstack.io/a-primer-continuous-integration-and-continuous-delivery-ci-cd/)[中，安全团队通常只参与部署和运营的最后步骤](https://blog.paloaltonetworks.com/2019/07/4-practical-steps-shift-left-security/)

通过左移，您不仅可以降低安全风险，还可以降低开发成本。IBM 的系统科学研究所发现，在设计中解决安全问题比在实现过程中便宜 6 倍，比在测试过程中解决安全问题便宜 15 倍。

Chiodi 说，这一切都始于“掌握软件在你的组织中是如何以及在哪里被创建的。根据你公司的规模，这可能从简单到极具挑战性不等。”

多有挑战性？非常。

“大型组织可能会花几个月的时间来挖掘，”Chiodi 观察到。这是因为“开发外包给多个供应商，这将需要额外的工作，有时还需要合同审查，并且每个业务部门都有自己的软件开发过程和工具。”

Chiodi 补充道，“您还必须将基础设施视为代码模板。我们发现大多数模板都有一个或多个安全错误配置。作为贵公司左移战略的一部分，您必须确保在其中寻找常见的安全错误配置。”

在做这项工作的同时，明智的公司也会关注他们的构建环境。大卫·a·惠勒，[Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)的开源供应链安全主管在最近的报告[中提到,](https://www.linuxfoundation.org/en/blog/preventing-supply-chain-attacks-like-solarwinds/)防止像网络安全管理软件产品这样的供应链攻击，网络安全管理软件产品灾难的部分原因是攻击者破解了企业的构建系统。

Chiodi 同意，“需要同样关注实际的构建环境本身，因为正如我们在这些供应链攻击中看到的那样，如果您的构建环境不安全，会使软件的每一部分和通过它的每一行代码都面临同样的风险。”

根据 Wheeler 的说法，解决方案是使用[经过验证的可重复构建](https://reproducible-builds.org/)。

Wheeler 写道，有些构建“总是在给定相同输入的情况下产生相同的输出，因此构建结果可以被验证。经过验证的可再现构建是一个过程，在该过程中，独立组织根据源代码生成构建，并验证构建结果来自所声明的源代码。”

实现这一点的工具仍在开发中。Linux 基金会和[民用基础设施平台](https://www.cip-project.org/)正在资助[可复制构建项目](https://reproducible-builds.org/)，以使经过验证的可复制构建成为可能。

Chiodi 说，在那一天到来之前，您应该使用他已经提出的基本安全建议尽可能多地锁定您的构建环境。

完成后，您可以使用您所了解的关于您的组织如何构建软件的信息来提高组织的安全性。Chiodi 继续说，这将使你能够“制定一个关于如何在你的开发团队中处理安全性的战略计划。”

## 关注点 5:关注警报

最后，Chiodi 指出，“您的组织应该关注的最后一个领域是风险度量和警报。一个警告告诉你可能出了问题。风险度量侧重于有效性和效率，因此您可以在出现问题之前发现漏洞。对于许多组织来说，这将是一个巨大的转变，因为他们非常关注警报。但是，我认为他们需要更加关注基于风险的指标。”

这是因为公司应该更加主动，而不是被动应对安全问题。如果你只是在看警报，那么问题已经发生了。但是，如果您正在监控您的风险，您可以在系统管理员在凌晨 2 点被召集来修复一个行为不当的服务之前阻止它们。监控这些指标在很大程度上依赖于为安全和开发团队提供跨所有部署的可见性，这也有其缺点。

“随着公司向云迁移或扩展其云业务，安全团队需要增强对公司数据所在位置的可见性。帕洛阿尔托网络公司(Palo Alto Networks)的客户 [Prologis](https://www.prologis.com/) 的 IT 安全主管[泰勒·沃伦](https://www.linkedin.com/in/tylerwarren1/)说。“云使基于云的工具之间的集成更加容易，应该利用这一点来实施警报整合、数据丰富和自动化。”

此外，Chiodi 继续说，“关注有效性和效率的风险度量实际上可以帮助你发现开发管道中的漏洞。他们还可以帮助您确定开发运维团队在发现漏洞、生产前和生产后的效率。”

最后，正如帕洛阿尔托网络公司的首席执行官兼董事长尼科什·阿罗拉最近谈到网络安全管理软件产品时说的那样，“[100%的预防，100%的时间是不可能的。](https://blog.paloaltonetworks.com/2020/12/next-solarwinds-modernizing-cybersecurity/) …但是，针对那些总是试图在创新上超越我们的坏人，安全性必须更加积极主动，面向未来:如果您无法实时阻止攻击，您需要近乎实时地检测和调查。支离破碎的安全和漫长的调查周期的日子已经成为过去，我们需要良好的数据和现实世界的人工智能来取得进展。……老练的黑客花费数年时间策划活动，我们必须投入类似的资源进行防御。”

容易吗？没有必要吗？是的。哦，我的是的。

[*构建云安全可扩展策略:1 月 26 日将举办虚拟活动*](https://register.paloaltonetworks.com/building-scalable-strategy-for-cloud?utm_source=thene%5B%E2%80%A6%5Dte&utm_campaign=PANWDigitalSummit-Jan2021-Registration) *。2021.*

由乔纳森·彼得森在 [Unsplash](https://unsplash.com/s/photos/five?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>