# KubeCon: 14，000 多名工程师完成了他们的 GitOps 基础知识

> 原文：<https://thenewstack.io/kubecon-14000-more-engineers-have-their-gitops-basics-down/>

GitOps 由将 [DevOps](https://thenewstack.io/category/devops/) 的文化转型转化为代码(IaC)的工具和实践组成。DevOps 已经有大约 20 年的历史，而 GitOps 只有大约 4 年的历史，仍然处于萌芽状态。这使得 [很难上手 GitOps](https://thenewstack.io/getting-started-with-gitops/) 。虽然没有哪家公司的数字化转型是相同的，但有必要为公司提供更标准化的培训，以找到 GitOps 真理的单一来源。

这就是为什么去年 1 月 Codefresh 推出了 Argo 认证计划 的 [GitOps。自那以后，近 14，000 名工程师注册了 1 级](https://learning.codefresh.io/) [GitOps 基础课程](https://learning.codefresh.io/course/gitops-with-argo) ，该课程目前仍然免费。

New Stack 与 CodeFresh 的联合创始人兼首席开源官 [Dan Garfield](https://twitter.com/todaywasawesome) 在 kube con+CloudNativeCon North America 谈论了这一社区认证的影响，这超出了注册预期的 10 倍。我们了解了 Peloton 如何成功优化其 GitOps onboarding。

## GitOps 101 里有什么？

在过去的十个月里参加 GitOps 课程的学生都不在大学。加菲尔德说，这些人已经在使用 Kubernetes 和部署软件，“只是想弄清楚如何提升他们的过程”。主要是 DevOps 工程师和基础设施工程师，“然后是只想更深入了解堆栈的开发人员。”

这是同类课程中的第一门，它基于两个开源云计算基础项目，这两个项目来自 [GitOps 工作组](https://github.com/cncf/tag-app-delivery/tree/main/gitops-wg) :

加菲尔德解释说，第一门课程包括组织存储库以实现规模化，配置应用程序同步策略，深入指导在 GitOps 切换期间交付软件，以及如何使用上述 Argo GitOps 工具来完成 GitOps。

该课程为学生的浏览器提供了完整的环境，并预装了 Kubernetes 集群和其他组件。

“培训的首要问题，也是所有培训的首要问题，是试图考虑每个人的机器。加菲尔德解释说:“Docker 配置错误或错误的 Kubernetes 集群、内存不足或人们在途中迷路是很常见的。相反，他说，这个 GitOps 101 是为了“你可以专注于学习”

培训包括整个云体验，因此学生不会因为已经达到的提供商配额等问题而分心。

“大多数培训没有一种机制来检查人们是否正确地做了该做的事情。如果他们在第二步遗漏了某些东西，那么在第五步就没有用了，”他说。加菲尔德认为，这门课程的彻底性是独一无二的。因为我们托管所有环境，所以我们标记问题并在每个步骤进行检查

大多数人能够在不到六个小时的时间内完成 1 级认证，70%的人在第一次尝试时就通过了测试。

## **Peloton 将工程师入职人数削减 83%**

在上个月的 ArgoCon 主题演讲期间，CodeFresh 的首席执行官[拉结尔·塔比](https://www.linkedin.com/in/razielt/)和 Peloton 的技术学习和见解负责人 [Thansha Sadacharam](https://www.linkedin.com/in/thansha-sadacharam-3a850288/?originalSubdomain=ca) 反思了扩大演习和媒体公司的 GitOps 之旅。

Tabib 开始了他们的讨论，思考了他们观察到的科技行业发生的三种演变:

*   **开发者体验的崛起。** [DevOps 工具](https://thenewstack.io/category/tools/) 现在也迎合开发者成为一等公民。
*   **GitOps 的兴起和渐进式分娩。**随着时间的推移，越来越多的人采用 GitOps 作为主要的声明性方法来进行战略部署。
*   ****云原生的兴起。**从整体架构进一步向微服务架构转移，使用短期代码和快速发布。**

 **这些趋势提出了对更可预测的流程的需求，以将更多的工程师带到云原生的 GitOps 道路上。Peloton 对此了如指掌，因为它希望提高各种工程角色的入职速度。

“在 Peloton，我们的许多工程师使用各种不同的工具。如果你是机器学习团队的工程师，你使用的工具看起来会与我们排行榜团队或 e-com[merce]团队的工程师略有不同，”Sadacharam 说。“Argo 是这方面的一个很好的例子，因为它并没有在所有工程领域得到同等的应用。相反，我们的平台工程师大量使用它来创造出色的开发人员体验。”

平台团队的任务是找出如何有效地扩展入职工程师，他们构建不同的东西，对基础设施有不同程度的热情。

Sadacharam 的团队决定创建一个新的“通用但定制的”入职培训，融合了整个组织的观点和单个工程团队正在做的工作类型。他们通过点对点学习建立了自己的 Argo 课程。他们采用 GitOps 和适当的培训使他们将新队友提出请求的时间减少了 83%,只有三天半。

## **实现下一级 GitOps**

上个月，开设了二级课程。大约需要 8 到 10 个小时来完成，到目前为止只有 30%的人第一次就通过了。加菲尔德说，这是因为它专注于大规模执行 GitOps 的更严峻的挑战。

他们还围绕这一培训建立了一个名为 GitOps Champions 的不和谐社区。虽然目前这两门课程都是免费的，但他们预计第一年内会有大约 1000 名学生，而在头 10 个月内他们已经有了大约 14000 名学生。加菲尔德警告说，无限期免费的课程是不可持续的，所以尽可能地利用它。与此同时，他们正在寻找在更小的咬口中提供更多 gitop 训练的方法，并创建另一个训练课程来处理更复杂、更新的边缘 gitop。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**