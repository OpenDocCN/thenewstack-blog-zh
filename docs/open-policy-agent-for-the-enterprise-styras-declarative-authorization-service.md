# 面向企业的开放策略代理:Styra 的声明式授权服务

> 原文：<https://thenewstack.io/open-policy-agent-for-the-enterprise-styras-declarative-authorization-service/>

[蜂巢](https://www.honeycomb.io/)赞助了新栈对 Kubecon+CloudNativeCon 北美 2020 的报道。

很久很久以前，在我们将策略执行编码到我们的云中之前，我们试图将它编码到我们的程序中。我们创建的大多数答案都是硬编码的，难以维护，并且几乎不可能更新。但是，在 2016 年，用于云原生环境的[开放策略代理](https://www.openpolicyagent.org/) (OPA，发音为“oh-pa”)被创建，并且在代码中执行策略变得更加实用。现在，它的开发者，在他们的公司 [Styra](https://www.styra.com/) 下，宣布了一个新的用于 Styra 声明式授权服务(DAS) 的[三层产品。](https://www.styra.com/pricing)

不过，在深入 DAS 之前，让我们确保我们对 OPA 和一般政策有相同的理解。

OPA 是一个开源的通用策略引擎，它统一了整个体系的策略实施。您用它的高级声明性语言[减压阀](https://www.openpolicyagent.org/docs/latest/policy-language/)编写这些策略，而这种语言又基于旧的基于 Prolog 的 [Datalog](https://docs.datomic.com/on-prem/query.html) 查询语言。借助减压阀，您可以将策略指定为代码，并创建简单的 API 来从您的软件中卸载策略决策。然后，您可以使用 OPA 在微服务、Kubernetes、CI/CD 管道、API 网关等中实施策略。

你问什么是策略引擎？Styra 软件工程师兼 OPA 技术主管 Torin Sandall 解释说:“在不同的环境下，政策对不同的人有不同的意义。在软件系统的上下文中，[策略是管理系统行为的规则](https://blog.openpolicyagent.org/what-is-policy-part-one-enforcement-bad8ea8eb35c)。

例如，允许这个用户改变服务的配置吗？是否允许该虚拟机接受来自该虚拟机的 TCP 连接？这个容器应该部署在哪个主机上？诸如此类。通过使用减压阀策略，OPA 策略引擎将“[策略和数据作为输入，并将策略问题的答案作为输出](https://blog.openpolicyagent.org/what-is-policy-part-two-policy-engines-7ee1d972386b)

这种方法非常成功。OPA 已用于创建 [Kubernetes](https://kubernetes.io/) 访问策略；设置[云安全策略](https://blog.openpolicyagent.org/what-is-policy-part-two-policy-engines-7ee1d972386b)；网飞使用 OPA 来控制内部 API 资源访问； [Chef](https://www.chef.io/) 使用它在其最终用户产品中提供身份和访问管理(IAM)功能。

OPA 也是[云原生计算基金会(CNCF)](https://www.cncf.io/) 孵化器项目。在那里，平均每周有相当惊人的一百万次下载。

当然，和过去一样，你可以强制执行政策。但是，正如 [Mohamed Ahmed](https://www.linkedin.com/in/mohamedfahmed) ， [Magalix](https://www.magalix.com/) 首席执行官所观察到的，在 Kubernetes 中，“你绝对可以使用 [RBAC](https://www.magalix.com/blog/kubernetes-rbac-101) 和 Pod 安全策略对集群实施细粒度控制。但同样，这仅适用于集群。库伯内特 RBAC 是没有用的，除非在一个库伯内特集群。这就是 OPA 发挥作用的地方。 [OPA 的引入是为了创建一种在堆栈中实施安全策略](https://www.magalix.com/blog/introducing-policy-as-code-the-open-policy-agent-opa)的统一方法。”

所有这些都很棒，如果你想学习如何使用 OPA 和在减压阀写作。如果你宁愿花时间在你的项目上，而不是学习如何自动化策略，你需要 Styra 的 DAS。

DAS 有两个新版本，DAS 免费版和 DAS 专业版，以及现有的 DAS 企业版。有了这些，您可以获得一个预算友好且快速的选择，为 Kubernetes 大规模部署 OPA。使用这三种策略中的任何一种，您现在都可以在几分钟内部署 DAS，并访问 100 多种内置策略。这些新产品实现了自助服务体验，消除了学习和定制 Kubernetes 准入控制编码 OPA 策略的需要。

如果你和我一样，更喜欢看代码示例，那么政策本身就值这个票价。

虽然它不完全是交钥匙——每个公司都有自己的政策——但也很接近了。DAS 为应用程序内的授权和运行应用程序的基础架构提供了单一的控制平面。有了它，您可以为 Kubernetes 和微服务获得易于部署的安全性、合规性和运营护栏，从而帮助客户降低风险、减少错误并加快软件开发。

Styra 并不是唯一一个歌颂其方法的人。根据 Gartner 的报告《DevOps 中合规自动化工具的市场指南》，“随着组织将工作负载迁移到云或从虚拟化环境迁移到容器化环境，I/O 领导必须评估现有的保护云和基于容器的基础架构的工具。这些工具支持实施基础架构合规性策略，以最大限度地降低与配置相关的风险。在不同的敏捷基础设施环境中，存在着协调策略的机会。具体来说，OPA 开源计划已经开始成为一个创业公司生态系统的来源，这些创业公司通过 OPA 构建企业能力。”

你可以自己看看新的 DAS Free 有什么大惊小怪的。这是一个完全免费的自助服务选项，最多可用于两个集群或 10 个节点，以简化采用流程。对于具有较大生产规模需求的团队，DAS Pro 为多达 50 个节点提供了清晰透明的定价模型，以便在 Kubernetes 集群从初始测试/部署发展到全面生产环境的过程中保护和管理它们。最后，DAS Enterprise 为团队提供无限制的 OPA 部署和规则，并提供全天候支持。无论版本如何，所有人都可以访问相同的管理平面、策略库、影响分析、监控和决策日志。

OPA 和 Styra 首席技术官的联合创始人 Tim Hinrichs 说:“这些新版本将使许多开始 Kubernetes 之旅的团队受益。“它还将帮助不熟悉 OPA 的平台工程师，他们希望立即部署社区最佳实践，而无需定制编码。最终，这将有助于减轻任何需要使用 OPA 监控、验证和测试 Kubernetes 准入控制的人的负担。”

通过 Pixabay 的特色图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>