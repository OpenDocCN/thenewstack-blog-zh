# 红帽:人为错误是库本内特安全事故的主要原因

> 原文：<https://thenewstack.io/red-hat-human-error-a-leading-cause-of-kubernetes-security-mishaps/>

当红帽收购 StackRox 时，你可能想知道 StackRox 关于 T2 Kubernetes 安全状况的半年度报告是否会继续存在。不用担心，[红帽](https://www.openshift.com/try?utm_content=inline-mention)会继续产生 Kubernetes 安全报告的[状态。相反，应该担心我们有多经常被 Kubernetes 和集装箱安全事故绊倒。](https://www.redhat.com/rhdc/managed-files/cl-state-kubernetes-security-report-ebook-f29117-202106-en.pdf)

有多糟糕？非常糟糕。94%的受访者表示他们在过去 12 个月中经历过 Kubernetes 和 container environments 安全事件。更糟糕的是，超过一半的受访者(55%)由于过去 12 个月的安全失误而推迟了 Kubernetes 应用程序的生产开发。

你能说“嗷！”我可以。

所有这些失败的根本原因是什么？不是讨厌的老黑客攻击。哦不。我们更经常对自己这样。近 60%的受访者表示，人为错误是数据泄露和故障的原因。特别是，大多数人在过去 12 个月内都经历过配置错误事件。

我们根本没有足够多的人真正了解如何正确部署 Kubernetes，更不用说足够多的专业人员知道如何保护它。正如 [Charlie Fiskeaux](https://www.linkedin.com/in/charlie-fiskeaux-4293a54/) 最近观察到的，监测公司 [Circonus](https://www.circonus.com/) 的 ux 领导人，“ [Kubernetes 监测是……复杂的](https://thenewstack.io/why-monitoring-kubernetes-is-so-challenging-and-how-to-manage-it/)。了解集群运行状况的指标、发现问题并找出解决问题的方法是组织面临的常见障碍，这使得组织很难充分实现其 Kubernetes 部署的优势和价值。”

这是因为配置管理对安全专家来说是一个非常困难的挑战。虽然有许多工具可用于容器映像的漏洞扫描，但配置管理需要您处理许多问题。当然，人们知道他们应该避免部署 Kubernetes 仪表板——你确实知道这一点，对吗？但是配置一个 [pod 的安全上下文](https://kubernetes.io/docs/tasks/configure-pod-container/security-context/)或者实现 [Kubernetes 基于角色的访问控制(RBAC)](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) ？这可不容易。

此外，这些错误配置导致近三分之一的时间被发现的主要漏洞。另有三分之一的人说他们遭遇过运行时安全事故。而且，请注意，这些只是公司的云原生开发者和管理员在部署程序之前发现的问题。我们一想到有什么安全漏洞存在于野外等待黑客去发现，就不寒而栗。

组织最担心的是运行时问题。乍一看，这似乎与绝大多数受访者将错误配置视为最常见和最大的安全风险的来源相反。然而，当您考虑到运行时安全性问题的出现是因为运行时安全性失误是那些相同的构建或部署错误配置的结果时，这就更有意义了。当然，只有您的团队可能在早期阶段就知道问题。但是一旦应用程序在生产中运行，每个人都可以看到什么时候出现了错误。

然而，只有 47%的调查受访者担心由于其容器和 Kubernetes 环境中的错误配置而暴露。我自己也会担心死的。

这个的答案？Red Hat 建议，我也同意，“应对这一挑战的最佳方式是尽可能自动化配置管理，以便安全工具——而不是人类——提供护栏，帮助开发人员和 DevOps 团队安全地配置容器和 Kubernetes。”普通人(或者非凡的人)根本不可能手动掌握不断发展和变化的云原生应用及其环境。

这是谁的工作？许多人将管理安全的责任直接放在了 DevOps 的肩上。15%的受访者认为开发人员是 Kubernetes 安全性的主要所有者，只有 18%的人认为安全性团队最有责任。

仔细想想，这是有道理的。DevOps 通常是推动容器和 Kubernetes 采用的人，所以他们也有责任保护它们。

提醒你有一个小问题。开发人员和管理员不是安全专家。Red Hat 认为，要真正保护 Kubernetes 的环境，“需要一个村庄。”他们的意思是“容器和 Kubernetes 安全工具必须促进不同团队之间的密切合作——从开发人员到开发人员、运营人员到安全人员——而不是延续可能困扰组织的孤岛。”

梅？也许你在一家公司的香格里拉工作，在那里所有的工作都非常和谐。只是我自己从来没见过。尽管如此，最起码，你公司负责 Kubernetes 的人需要和安全部门交朋友。你会做得更好。调查发现，绝大多数受访者都有某种形式的发展合作计划。你应该以他们为榜样。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>