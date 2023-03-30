# 云漂移检测:如何解决状态外变化

> 原文：<https://thenewstack.io/cloud-drift-detection-how-to-resolve-out-of-state-changes/>

[](https://www.linkedin.com/in/guy-eisen-3012a597/)

 [盖伊·艾森科特

作为 Bridgecrew 的联合创始人和产品副总裁，Guy Eisenkot 正在为开发人员优先的云安全铺平道路。Guy 热衷于让基础设施安全成为可消费的，并让那些能够产生最大影响的人能够访问到，他对 Bridgecrew 迄今为止的成功起到了重要作用。](https://www.linkedin.com/in/guy-eisen-3012a597/) [](https://www.linkedin.com/in/guy-eisen-3012a597/)

云配置会发生变化。一直都是。为了采用新技术、发布新特性和支持新的业务需求，想象 web 应用程序开发没有持续不断的配置变更是徒劳的。

对于使用基础架构即代码(IaC)来管理云配置流程的组织来说，管理和促进这些变化更加可预测和简单。但是，无论 IaC 的实施多么严密，带外变化(即漂移)都是不可避免的。

简而言之，漂移是指配置发生变化，不再与先前填充的值相同。就 IaC 而言，当实际配置不同于预定的构建时状态时，就会发生漂移。

## IaC 和漂移

IaC 的优势之一是，它通过在整个配置和部署过程中整理预期配置和实施防护，将偏差保持在最低水平。除非出现“玻璃破碎”或“紧急情况”，否则没有理由登录云控制台并直接在 UI 中或通过 CLI 界面进行配置更改。

然而，在现实中，这些情景和变化确实发生了。例如，维护和事件响应任务需要对现有配置进行特别更改，以便对正在发生的问题进行分析和故障排除。团队之间的知识和信息差距也会导致变更，或者一连串的变更，偏离了最初的计划。

无论您的组织处于 IaC 实施之旅的哪个阶段，创建系统的漂移检测策略都是了解和改进您的云状况的关键。

**IaC 到 IaaS 漂移检测策略成功的关键在于:**

*   理解漂移何时成为风险。
*   实施与您的堆栈相关的漂移检测自动化。
*   将他们的回答分类并发送给正确的个人或团队。

## 了解与漂移相关的风险

任何代码到云的差距都可以归类为漂移，但这并不意味着所有的州外配置更改都会暴露您的基础架构。当然，在某些情况下，临时更改可能会导致环境不稳定、部署问题、不可预测的成本以及安全性或法规遵从性方面的差距。

然而，在这个问题上最重要的考虑因素之一是漂移成为一种永久固定现象的潜在风险。在确定帐户的信任边界时，如锁定其网络设置或基于身份的权限，不知道配置更改的原因和位置可能会导致不受管理的盲点。在大规模情况下，这可能会导致这些边界出现裂痕，并因数据泄露而导致灾难性损失。

想象一下，故意打开一个 internet 端口来解决 DNS 问题，或者为某个角色授予管理员权限来完成一个复杂的数据库迁移过程。如果这些设置是使用 CLI 专门定义的，并且在项目或 bug 解决后从未恢复，那么它们有可能成为永久的固定设置。这些正是漂移的形式，可能成为试图渗透暴露的云资产的对手的机会。

另一方面，并不是所有的漂流物都存在真实的或可利用的风险——它们甚至可能是故意的。了解动态基础架构资源创建或变更可能导致的漂移实例以满足可扩展性要求非常重要，尤其是在自动化漂移检测之前。

## 检测 IaC 和云之间的漂移

减轻潜在风险的最佳方式是实时识别变更的配置，了解其原始意图，并恢复它们..

最基本的方法是以编程方式持续比较 IaaS 中的配置和 IaC 计划文件中的配置。因为并非所有的 IaC 框架都以相同的节奏或相同的细节层次来持久化状态，所以如何持久化状态会因持久化配置状态的方法而异。

在声明式 IaC 框架中，如 Terraform 和[Amazon Web Services](https://aws.amazon.com/?utm_content=inline-mention)cloud formation，保持状态是持续评估变更和原始计划文件的关键。这些语言中的漂移非常简单。例如，他们中的大多数已经公开了简单的 API 来通过 terraform apply 或 CloudFormation 的 detect-stack-drift 捕获它们。查询和评估这些状态的主要挑战是跨代码和云实时通信，而不仅仅是在供应新基础设施时。

允许像 Kubernetes(通过 kubectl)这样的命令式控制平面的框架对漂移检测提出了更大的挑战。使用 Kubernetes，在日常工作流程中使用命令性命令越多，就越难有效地检测和响应漂移。虽然 Kubernetes 不包含本地漂移检测 API，但它提供了一些最好的工具来持久化配置——使用准入控制器和 webhook 监听器。

也许检测漂移最具挑战性的配置方法是半声明性框架，如 Serverless、AWS CDK 和 Pulumi。因为它们建立在包含命令性操作符的语言上，所以各种可能的配置排列使得评估什么是状态以及应该如何处理它变得很有挑战性。

根据您的基础架构管理方法，可能有工具或项目可以提供帮助:

*   driftctl 是一款免费的开源 CLI，可对 Terraform 和 AWS 中的基础设施漂移进行跟踪、分析、优先排序和警告
*   [Kubediff](https://github.com/weaveworks/kubediff) 是 Kubernetes 的一个工具，向您展示您的运行配置和版本控制配置之间的差异。
*   AWS 支持从控制台、CLI 或您自己的代码进行特别的[云形成漂移检测](https://aws.amazon.com/blogs/aws/new-cloudformation-drift-detection/)。
*   Bridgecrew 等 SaaS 工具解决了构建时和运行时的配置问题，也可以从 IaaS 提供商和 IaC 状态文件中提供漂移检测。

## 应对漂移

探测漂移只是成功的一半。为了确定如何有效地*应对*漂移，首先回答以下问题:

*   使用 git 流和组织策略是否完全锁定了信任边界配置？
*   IaC 是否是产生非紧急基础设施变更的首选？
*   “碎玻璃”场景是否经常发生，DevOps 工程师是否负责将系统恢复到正确的已知状态？
*   开发人员是否使用一致的系统在运行时直接应用变更？
*   是否正在使用漂移检测功能来实时警告新发现的漂移？

这些答案将有助于确定通知谁、在哪里插入反馈、分配给漂移的优先级等等。

不管您采用什么方法，您在漂移检测工作中应该坚持的一个指导原则是尽可能接近开发人员地发现并*解决*漂移。因为开发人员对任何给定的配置都有最全面的历史和知识，所以将问题直接提交给代码所有者可以节省数小时的时间来找出谁做了什么更改以及为什么做。

依靠 DevOps 通过逆向工程来追踪漂移的起源，其变化的逻辑可能是徒劳的。如果你必须走这条路，首先要像对待 bug 奖励提交一样评估它的潜在风险，而不是盲目接受它并投入时间修复它。您可能会发现，实际上并不需要恢复更改，而是可以将其重新协调到 IaC 状态文件中。

我们通常认为 IaC 是一条单行道，但是随着您的配置之旅的发展，为了实现最佳可用性和强大的云姿态，向两个方向采取措施并不罕见。

继续漂流！

通过 Pixabay 引导图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>