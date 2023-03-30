# CloudSkiff 计划通过 Terraform 代码生成来自动化多云 Kubernetes

> 原文：<https://thenewstack.io/cloudskiff-plans-to-automate-multicloud-kubernetes-with-terraform-code-generation/>

如果你在原生云领域，你会发现两个已经变得太熟悉的论点或痛点。首先，Kubernetes 太复杂了，其次，公司需要一个解决方案来处理由于这样或那样的原因强加给他们的多云环境。

[CloudSkiff](https://www.cloudskiff.com) 已经清楚地听到了这些抱怨，并在今年晚些时候推出了一款新工具来应对这两个问题，该工具将帮助“推出生产就绪的基础设施即代码，并使用 Terraform 部署托管的 Kubernetes 集群，如 EKS、AKS 和 GKE”——或者更简单地说，“跨越多个云缩短学习曲线。”

CloudSkiff 声称，63%的 IaaS 用户现在部署到多个云，但指出一个云的专业知识并不意味着另一个云的专业知识。[CloudSkiff 联合创始人兼首席技术官夏羽·乔丹](https://www.linkedin.com/in/stephanejourdan)在北美呆了一段时间，然后回到欧洲，并在与不同公司进行了多次非正式交谈后，注意到了这个问题。

“我们遇到了很多 CTO 和 DevOps，我们问他们，你们现在在做什么，你们的问题是什么？大多数反馈是很难使用 Kubernetes，”Jourdan 告诉新的堆栈。“对他们中的一半人来说，多云是一个问题。他们中的一半人决定在 AWS 上全力以赴，但另一半人说他们不想这样。他们出于多种原因想要多云环境。”

当然，公司使用多云的原因是多种多样的。一些公司可能希望避免局限于单一供应商，而其他公司可能需要不同云的不同功能。其他公司在收购另一家公司后仍可能继承多云解决方案。Jourdan 将 CloudSkiff 视为所有这些场景的解决方案，因为它可以在一个云上获取 Kubernetes 部署的配置，将其转换为 Terraform 代码，然后帮助将该环境迁移到另一个云。

“复杂性转移到了基础设施层面。管理复杂的云基础架构已经够难的了。Terraform 是一种解决方案，但你需要知道如何为一种云和另一种云做这件事，”Jourdan 说。“我们希望通过提出基础设施生命周期管理工具来减轻痛苦。这个想法是为多云 Kubernetes 生成随时可用的 Terraform 代码。”

尽管目前细节尚不多见，但该公司在一份声明中对其服务进行了如下描述:“通过基础设施自动化，CloudSkiff 帮助开发人员加快了 Kubernetes 的学习曲线并缩短了价值实现时间。CloudSkiff 通过使用干净的基础设施即代码管理基础设施堆栈的生命周期，实现了 Kubernetes 部署的工业化，因此开发人员可以专注于构建和运行他们的应用。”

当 CloudSkiff 于 2019 年 12 月推出公共测试版时，它将与 AWS、Azure 和 GCP 合作，并计划在不久的将来与腾讯合作。虽然 CloudSkiff 只开发了三个月，Jourdan 说，除了这些基本功能之外，他们还打算为团队提供额外的工作流和治理工具。

来自 Pixabay 的 S T 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>