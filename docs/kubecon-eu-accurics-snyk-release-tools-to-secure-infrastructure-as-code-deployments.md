# KubeCon EU: Accurics、Snyk 发布工具，确保基础设施即代码部署的安全

> 原文：<https://thenewstack.io/kubecon-eu-accurics-snyk-release-tools-to-secure-infrastructure-as-code-deployments/>

云原生安全提供商 Accurics 和 [Snyk](https://snyk.io/) 都发布了新的工具，承诺帮助组织保护基础设施即代码(IaC)部署。

这些公司在本周举行的[kube con+CloudNativeCon Europe 2020](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)上发布了这些产品，这是[云本地计算基金会](https://www.cncf.io/) (CNCF)的旗舰会议。

IAC 是一种新兴实践，在开发环境中定义如何为应用程序部署云或数据中心资源(如网络和存储),从而消除了在应用程序上线前运行和管理这些资源的需要。

然而，随着组织采用 IaC 技术，越来越多的人了解到不适当的配置如何会导致安全错误。

上个月，以开发者为中心的安全厂商 [Bridgecrew](https://bridgecrew.io/) ，[发布了一份报告](https://thenewstack.io/bridgecrew-all-these-misconfigured-terraform-modules-are-a-security-issue/)显示，可供下载的所有社区构建的 Terraform 模块中，多达一半的模块配置错误，为潜在的安全漏洞打开了通道。由 [HashiCorp](https://www.hashicorp.com/) 管理的 [Terraform](https://www.terraform.io/) 是一款用于管理云和基础设施组件以及服务的开源软件。

Gartner 报告称，“到 2025 年，70%针对容器的攻击将来自已知的漏洞和错误配置，而这些漏洞和错误配置本来是可以补救的。”。

Accurics 已经更新了其 [Terrascan 开源静态代码分析器](https://github.com/accurics/terrascan)，因此它可以在基础设施即代码部署中进行策略检查。新版本强调了亚马逊网络服务、微软 Azure 和谷歌云平台等热门云提供商的 Terraform 模板中的常见安全缺陷。

该架构依赖于 CNCF 的开放策略代理(OPA)，可以轻松扩展到其他流行的技术，如 AWS CloudFormation、Kubernetes 以及服务网格和无服务器部署。据该公司称，OPA 引擎可以大大简化希望创建自定义策略的开发人员的策略定义，并为 CIS 基准提供 500 多种现成的策略。

Accurics 开发人员宣传主管塞萨尔罗德里格斯(Cesar Rodriguez)在一份声明中表示:“IaC 的快速采用显然符合其预期目标:通过在开发生命周期的早期以编程方式嵌入策略检查，帮助组织实现更高的可靠性。”。“组织需要实施策略护栏，以确保安全地定义和管理云原生基础架构。Terrascan 已经在许多组织的这一过程中发挥了关键作用，最新的版本将这些重要的功能发挥得更大。”

Terrascan 现在作为 GitHub 动作可用(也包含在流行的 Super-Linter GitHub 动作包中)，可以作为预提交钩子安装。它还可以集成到 CI/CD 管道中。在那里，它可以在代码被放入存储库之前帮助检测问题。

Snyk 也瞄准了“基础设施即代码”市场，推出了新版本 Snyk IaC。该产品旨在上线之前发现并修复 Kubernetes 和 Terraform 代码中的错误配置，最大限度地减少人工代码审查和广泛的研究，以检测潜在的安全错误。

Snyk 联合创始人兼总裁 Guy Podjarny 在一份声明中表示:“关键是要有一种安全方法，承认基础设施已经成为应用程序本身的一部分。

据该公司称，Snyk 基础设施作为代码将对 Snyk 的免费用户开放，并作为 Snyk 开源和 Snyk 容器的付费附件，为团队和大型组织提供附加功能。

Accurics、Amazon Web Services、Bridgecrew、云计算原生计算基金会、HashiCorp 和 Snyk 是新堆栈的赞助商。

来自 Pixabay 的 Omar González 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>