# 开放策略代理:云授权

> 原文：<https://thenewstack.io/open-policy-agent-authorization-for-the-cloud/>

[](https://www.linkedin.com/in/timhinrichs/)

 [蒂姆·辛里奇

蒂姆·辛里奇是开放政策代理项目的联合创始人，也是 Styra 的 CTO。在此之前，他共同创立了 OpenStack Congress 项目，并且是 VMware 的一名软件工程师。Tim 花了 18 年的时间为不同的领域开发声明性语言，例如云计算、软件定义的网络、配置管理、web 安全和访问控制。他于 2008 年获得斯坦福大学计算机科学博士学位。](https://www.linkedin.com/in/timhinrichs/) [](https://www.linkedin.com/in/timhinrichs/)

聚焦于[开放政策代理](https://www.openpolicyagent.org/) (OPA)的会谈在[kube con+CloudNativeCon Europe](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)的议程中占据显著位置——谷歌、渥太华市 Ada Health 等公司的用户接受了 15 场聚焦 OPA 的会议——表明了授权在云中的重要性。虽然该活动和这些会谈现在被推迟到 8 月，但这并不意味着我们应该推迟学习更多关于应用程序内、跨 Kubernetes 集群和服务网格之上的授权的知识。

OPA 是一个开源项目，于四年前推出，作为跨云原生环境建立授权策略的实际方法，它已经稳步发展。从控制 Kubernetes 和微服务的使用，到什么资源可以被检查到 CICD 管道，组织使用 OPA 做任何事情。随着公司转向生产，他们意识到他们需要一个安全护栏标准。OPA 已经成为整个体系标准。

事实上，你在家工作时使用的许多云原生协作工具(如 [Atlassian 套件](https://www.youtube.com/watch?v=nvRTO8xjmrg&amp;index=2)和 [Chef Automate](https://www.youtube.com/watch?v=jrrW855xL3s) )都采用了 OPA。许多我们都喜欢的娱乐和联系应用也是如此，从你在[网飞上观看的节目，部分是由 OPA、](https://www.youtube.com/watch?v=R6tUNpRpdnY)到在 [Pinterest](https://www.youtube.com/watch?v=LhgxFICWsA8) 上分享的创意。

事实上，您可以从 KubeCon EU 的一些会议中了解 OPA 的广泛使用案例，包括:“使用开放策略代理处理容器漏洞”、“CoreDNS 和 OPA 用于基于策略的多租户 Kubernetes 服务发现”、“帮助—我的集群在互联网上:容器安全基础知识”和“策略作为代码的治理模型”。

虽然 OPA 的使用案例很多，但以下三个可能是当今最常见的，并且可以让您知道从哪里开始:

*   **申请授权。几乎每个应用程序都需要某种形式的授权，如今这通常是由公司开发人员“开发自己的”代码来实现的。除了花费时间和消耗资源之外，结果是一个难以维护的工具大杂烩。代码对应用程序来说很重要，但它是繁重的工作，很少给最终用户的“快乐指数”增加任何东西。**

OPA 通过提供预煮的授权技术使您能够加快上市时间，因此您不必从头开始开发。它使用一种声明性的策略语言，专门用于编写和执行规则，比如“Alice 可以写入这个存储库”或“Bob 可以更新这个帐户”它附带了一套丰富的工具来帮助开发人员将这些策略集成到他们的应用程序中，甚至允许应用程序的最终用户也为他们的租户贡献策略。

如果您已经有了自己开发的应用程序授权解决方案，您可能不希望将它们拿出来与 OPA 交换。至少现在还没有。但是，如果你要分解这些单一的应用程序，并转移到微服务来扩展和提高开发效率，你将需要一个分布式授权系统，OPA 就是答案。

*   **Kubernetes 准入控制。**OPA 的另一个突出用途是在 Kubernetes 周围放置[护栏。Kubernetes 让开发人员能够极大地控制传统的计算、网络和存储孤岛。当然，这也是不利的一面。今天的开发人员可以按照他们想要的方式设置网络，按照他们想要的方式设置存储。负责给定容器集群的管理员和安全团队需要确保开发人员不会搬起石头砸自己(或邻居)的脚。](https://blog.styra.com/blog/kubernetes-security-at-rsa-the-time-is-now)

OPA 可用于构建策略，例如，要求所有容器映像来自可信来源，防止开发人员以 root 身份运行软件，确保存储始终标记有加密位，存储不会因为 pod 重启而被删除，限制互联网访问等。

OPA 直接集成到 Kubernetes API 服务器中，因此它完全有权拒绝任何资源—无论是计算、网络、存储等。—该策略认为不属于某个集群。此外，您可以在开发生命周期的早期暴露这些策略(例如，CICD 管道或者甚至在开发人员的笔记本电脑上)，这样开发人员就可以尽早收到反馈。您甚至可以带外运行策略来监控结果，以便管理员可以确保策略更改不会无意中造成弊大于利。

*   **服务网状授权。**最后，许多组织正在使用 OPA 来规范服务网格架构的使用。因此，即使您没有嵌入 OPA 来实现应用程序授权逻辑(上面讨论的顶级用例)，您可能仍然希望控制 API 微服务。您可以通过将授权策略放入服务网格来执行和实现这一点。或者，您可能出于安全考虑，在服务网格中实施策略来限制微服务架构内的横向移动。另一个常见的实践是将策略构建到服务网格中，以确保即使在涉及修改源代码时也能满足您的法规遵从性。

### 针对云原生环境的基于统一策略的控制

该社区向我们展示了人们从单一用例开始，然后随着他们变得舒适而扩展。最终目标是制定一个统一的策略方法，让您摆脱掌握和管理大量不同授权模型的工作，每个模型都有自己的 API 和 GUI。

除了简化 IT 之外，统一的策略模型还将对安全性(如果您认为有人试图进行某种未经授权的访问，您将不会有 57 种不同的工具来检查)、运营(服务问题是授权问题吗，或者您甚至可以判断吗？)，以及法规遵从性(在异构环境中，您将不必花费如此多的精力去弄清楚如何从各种系统中提取信息来生成法规遵从性报告)。

因此，当我们等待 KubeCon + CloudNativeCon Europe 听取 OPA 用户的意见时，您可以利用这段时间[了解更多关于云原生环境的基于策略的控制](https://www.styra.com/)，并在会议上更好地准备寻找您的授权问题的答案。此外， [OPA slack 频道](https://slack.openpolicyagent.org) l 上也充满了问题和建议。

KubeCon、CloudNativeCon 和 CNCF 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>