# 带有定制 Kubernetes 资源验证器的开发人员防护栏

> 原文：<https://thenewstack.io/developer-guardrails-with-custom-kubernetes-resource-validators/>

如果您的组织开始采用云原生技术，您可能仍在研究如何将 Kubernetes 知识内化并分发给团队的其他成员。这并不是对您团队的打击——这是一个如此普遍的问题，以至于云计算原生计算基金会已经开发了[云原生成熟度模型](https://www.cncf.io/blog/2022/05/18/cloud-native-maturity-model-2-0/)，该模型可以帮助组织了解他们如何有效地解决他们进入新工具和不同文化需求的不稳定的第一步。

但是需求是明确的:为了高效地工作并产生高质量的部署，您组织的整个技术团队需要扩展它的 Kubernetes 知识。

这甚至更有先见之明，因为 DevOps 文化和 GitOps 过程规定更多的工作和认知负荷应该“向左转移”,并更早地纳入软件开发生命周期。开发人员现在被要求从他们的第一行代码开始就融入安全和 IT 操作的最佳实践。他们对系统的更多方面负有责任，但他们通常并不完全理解。

技术组织结构图的另一个分支是平台工程，它的任务是阻止开发人员部署新的应用程序和资源，这些应用程序和资源会崩溃，导致级联问题或过度利用昂贵的云资源。毕竟，平台工程师的工作是建立自动化和流程，将基础设施推向梦寐以求的零错误状态。

但是，随着新技术和 Kubernetes 知识的发展，平台工程师需要一个基于自动化的可行策略，在保持高质量代码的同时，解除开发人员的障碍并对他们进行培训。

文档很棒，但是平台工程师不应该把时间花在以这种方式整理知识上——正如我们许多人从自己的经验中所知，目标受众真正阅读它(更不用说遵守它)的可能性非常低。

平台工程真正应该做的是为他们组织中的开发人员提供护栏，这些护栏可以作为正在进行的部署前开发人员工作流的一部分轻松应用、实施和自动化。提供这些防护的一个令人惊讶的简单方法是为您的 Kubernetes 应用程序配置使用一个易于部署的验证框架来创建定制策略。

## 为什么要验证？

答案很简单:不应该允许开发人员提交违反组织策略的代码或配置。

验证器在提交阶段执行策略，或者直接在开发人员使用的集成开发环境(IDE)中执行，或者作为 CI/CD 管道中的初始检查(或者，理想情况下，在两个阶段都执行)。在您的 CI/CD 管道花费宝贵的时间和云资源部署不可避免会失败的代码之前，像无效 YAML 语法这样的简单错误会被验证器捕获并拒绝。

通过在提交阶段实施标准，您可以在软件开发生命周期的早期构建质量，并在整个过程中简化流程。

您可以通过遵循两条相对简单的规则来建立一种验证文化:

*   如果您的组织犯了两次同样的错误，那么平台工程师就应该将它整理成一条规则，供您的验证器标记和阻止。
*   您的组织的策略应该是独特的，并符合您的需求、目标和文化，而不是从 StackOverflow 或 GitHub 复制粘贴的东西。

## 自定义验证器的威力

现在，任何开发人员都可以直接从他们的 IDE 中使用验证器。一个最流行的例子是在 VS 代码中直接使用 ESLint 来执行各种代码质量标准，因为他们在处理 TypeScript/JavaScript 项目，如 React 或 Svelte。

但是捆绑在这些工具中的政策——或者开发者可以从 Airbnb 等主要组织中集成的政策——并没有涵盖开发者可能将 Kubernetes 部署引向错误方向的大多数方式。

当您的组织两次犯同样的错误时，它们不能满足制定新策略的需要，并且它们不是为您的组织的独特技术堆栈和文化冲动而设计的。

自定义验证器通过自动化无缝地解决了这两个问题。您的平台工程师将他们对 Kubernetes 的深入了解和强烈意见编入了特定于组织的策略中。平台工程师被动地防止错误配置，而不是不断的手动干预，比如在一个接一个的拉请求(PR)中请求改变。

从开发人员的角度来看，自定义验证器不会对他们的日常工作产生太大的影响。当他们开发 Kubernetes 应用程序和资源时，他们的 IDE 会在警告或错误阶段通知他们策略配置错误，这是由平台工程设置的护栏，从一开始就阻止他们提交违反组织策略的代码。

您的定制验证器现在被动地提高了您的代码库的质量，而没有为开发人员增加任何额外的认知负荷，这使得他们可以快速地交付。平台工程师自动实现零错误，开发人员开始从每一行新代码中学习 Kubernetes 的最佳实践。

## 超越验证作为错误

大多数组织可能很幸运，每 10 个开发人员就有一个平台工程师，这意味着他们需要专注于自动化和 GitOps，而不是手动干预，以消除部署到生产的瓶颈。

记住任何平台工程团队的主要[职责和目标](https://platformengineering.org/blog/what-is-platform-engineering):

*   关注铺平的道路和过程改进，比如选择正确的工具或实现自动化，为他们的“客户”，他们的应用程序开发伙伴提供价值。
*   防止开发团队一次又一次地重新发明轮子，因为他们必须担心配置和供应基础设施。
*   自动化他们在开发人员和他们丰富的特定于 Kubernetes 的最佳实践之间架起知识桥梁的方式。
*   创建“胶水”和护栏，帮助开发人员构建和部署高质量的应用程序，而不必了解整个工具链，也不需要 DevOps 工程师的手动干预。

如果他们能够实现其中的任何一项，那么他们正在做扎实的工作，让每个人都能够专心工作、高效工作并成功部署到集群。

定制验证器不仅仅从技术角度帮助平台工程师实现这些目标。他们还帮助团队接受教育和持续改进的文化。我们喜欢说自定义验证器的策略不是惩罚，而是帮助开发人员每天学习 Kubernetes 细微差别的资源。

平台工程师通过编写新的规则为这种文化做出了贡献，这些规则包括有价值的上下文，这些上下文可以自动化他们如何分发他们所知道的东西。当开发人员工作时，他们可以将鼠标悬停在 IDE 中的错误/警告图标上，阅读规则实施的策略以及他们可以采取的补救措施的描述。

## Monokle 是“袖珍平台工程师”

如果您的组织中有平台工程师，他们肯定听说过或者已经尝试过定制验证器。但是这些工具中的许多需要一种独特的领域特定语言，当编写规则太困难时，它永远不会发生。平台工程师再次浪费时间编写文档或委婉地提醒他们的开发同行，如何停止将如此多的错误引入集群。

如果这是您的组织正在努力解决的问题，或者您清楚地看到了在平台工程师和开发人员之间架起桥梁的价值，那么您应该将 Monokle 的开源验证框架放在您的雷达上。

[Monokle](http://monokle.io) 是一套工具，通过统一他们创作、验证和将 Kubernetes 配置推向生产的方式，帮助开发人员、DevOps 工程师和平台工程师充满信心地进行部署。

Monokle 最近引入了一个基于[类型脚本的定制验证框架](https://kubeshop.github.io/monokle/resource-validation/)，使得添加新规则变得非常简单。可以使用命令行界面、GitHub 操作、Monokle 桌面工具和 Monokle Cloud 来应用验证规则。甚至还有一个本地开发服务器，它与 Monokle Cloud 通信，帮助您在将新规则应用于您的组织之前测试它们。

随着开发人员在 Monokle 中编写新的资源，Kubernetes 政策和左移革命背后的所有复杂性都被抽象为红灯或绿灯——不再有认知负荷。由于 Monokle 内置的上下文信息，开发人员可以开始将每个错误配置转化为教育机会。

想先看看自定义验证的效果吗？查看我们的两个视频，分别关于[开发您的第一个策略](https://youtu.be/RnkPsGTf684)和[通过 Monokle 的 IDE 部署定制验证器](https://youtu.be/7stLFzD0ff0)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>