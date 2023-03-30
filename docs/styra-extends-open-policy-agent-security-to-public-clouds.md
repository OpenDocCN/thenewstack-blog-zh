# Styra 将开放策略代理安全性扩展到公共云

> 原文：<https://thenewstack.io/styra-extends-open-policy-agent-security-to-public-clouds/>

曾几何时，我们试图将政策立场编码到我们的程序中。它没有——真的没有——很好地发挥作用。然后在 2016 年，一家名为 [Styra](https://www.styra.com/?utm_content=inline-mention) 的公司的一些开发人员为云原生环境开发了[开放策略代理](https://www.openpolicyagent.org/) (OPA，发音为“oh-pa”)。有了 OPA，在代码中执行策略变得更加实际。 [Styra 最近将 OPA 商业化为一个三层产品，称为声明式授权服务(DAS)](https://thenewstack.io/open-policy-agent-for-the-enterprise-styras-declarative-authorization-service/) 。现在，Styra 通过使用 [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) 的 [Terraform](https://www.terraform.io/) 将 DAS guardrails 扩展到公共云存储、网络和计算资源配置中 [Styra DAS for Terraform](https://www.styra.com/terraform-cloud-config-management-with-styra-das-and-open-policy-agent) 。

借助该产品，您可以在 AWS、Google 云平台和 Azure 上部署 DAS。此外，Styra DAS 现在将提供基于 OPA 的统一策略即代码解决方案，以确保云基础设施、Kubernetes 和服务网格部署的安全性和合规性。我喜欢这个主意。我很喜欢这个想法。

如果您是 OPA 的新手，您应该知道它是一个开源的通用策略引擎，可以在整个云堆栈中统一策略实施。你用它的高级声明性语言，[减压阀](https://www.openpolicyagent.org/docs/latest/policy-language/)来编写你的策略。这是基于旧的基于 Prolog 的 [Datalog](https://docs.datomic.com/on-prem/query.html) 查询语言。借助减压阀，您可以将策略指定为代码，并创建简单的 API 来从您的软件中卸载策略决策。然后，您可以使用 OPA 在微服务、Kubernetes、CI/CD 管道、API 网关等中实施策略。

我们到底在谈论什么政策引擎？Styra 软件工程师兼 OPA 技术主管 Torin Sandall 解释说:“在不同的环境下，政策对不同的人有不同的意义。在软件系统的上下文中，[策略是管理系统行为的规则](https://blog.openpolicyagent.org/what-is-policy-part-one-enforcement-bad8ea8eb35c)。

例如，允许“Joe 用户”更改服务的配置吗？是否允许该虚拟机接受来自该虚拟机的 TCP 连接？这些容器可以部署在哪个主机上？诸如此类。通过使用减压阀策略，OPA 策略引擎将“[策略和数据作为输入，并将策略问题的答案作为输出](https://blog.openpolicyagent.org/what-is-policy-part-two-policy-engines-7ee1d972386b)

这个很厉害。例如，现在您可能使用一般规则和特定工具来制定安全策略决策。那是许多工作。在越来越复杂的云计算世界中，您的 IT 团队真的能继续工作并保护他们的系统吗？我表示怀疑。

当然，您的工程师和安全团队可以管理和保护十几个系统，但是在一个现代云应用程序中有数百甚至数千个不同的组件？不，你的人需要帮助。

这就是 Styra DAS to Terraform 云基础架构控制平面的用武之地。有了它，您的团队可以:

*   借助单一策略框架进行云基础架构授权，消除定制工具的持续管理并加快部署。
*   管理云平台从设计到部署的整个生命周期。
*   通过跨团队协作的单一平台消除策略孤岛。
*   自动化配置验证，基于成熟的标准部署平台安全性，并证明合规性。
*   通过 OPA 创始人构建的安全策略库快速入门。

想试试吗？你可以注册一个[的 Styra DAS 免费试用](https://www.styra.com/pricing)，看看它是否适合你。我打赌你会很高兴你这么做了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>