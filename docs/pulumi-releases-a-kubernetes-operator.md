# Pulumi 发布了一个 Kubernetes 操作器

> 原文：<https://thenewstack.io/pulumi-releases-a-kubernetes-operator/>

基础设施即代码云工程平台提供商 [Pulumi](https://www.pulumi.com/) ，旨在使组织能够管理任何云上的基础设施，于本周发布了其 [Pulumi Kubernetes 运营商](https://www.pulumi.com/docs/guides/continuous-delivery/pulumi-kubernetes-operator/)。

Pulumi 最初于去年推出了 Pulumi Kubernetes 运营商，以帮助企业在其 Kubernetes 环境中部署和管理云基础设施。该公司刚刚在 [KubeCon + CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 北美 2021 上推出了普遍可用的版本。

新的 1.0 版本带来了许多增强，包括可扩展性、性能和质量的提高，例如支持带有分支跟踪和私有 git 回购的 GitOps 工作流，Pulumi 的首席技术官卢克·霍班和该公司的软件工程师 Vivek Lakshamanan 在博客文章中说。

## 1.0 版中的新功能

1.0 版本中的新特性包括操作符现在支持在目标 Git repo 中指定分支而不是提交。Pulumi 的帖子说，当指定一个分支时，运营商将跟踪该分支跟踪的任何变化，并在新代码推出时自动触发部署。

“这是一个‘拉式’模型，操作员观察 Git 回购的变化。这确保了运营商可以在从互联网(或通过 GitHub webhooks)无法到达的私有网络环境中运行，并且运营商完全控制如何发现和处理这些更新，”该帖子说。

此外，在 KubeCon 的一次采访中，Pulumi 的联合创始人兼首席执行官 Joe Duffy 表示，这一举措为 Pulumi Kubernetes 操作者提供了新的用例，允许将声明性模型从纯粹的 Kubernetes 资源中推出，以允许在 Git repo 分支中指定确切的提交部署。

“这允许为给定环境定义一次基础架构配置，然后通过 git 推送进行主动更新。在这种模式下，Pulumi Kubernetes 操作员可以用来取代传统的 CI/CD 集成或其他云基础设施部署工作流，”Pulumi 帖子说。

与此同时，除了支持分支跟踪，该运营商现在还支持访问私有 Git 仓库，这对于通过 Pulumi Kubernetes 运营商部署生产基础设施至关重要。

Pulumi Kubernetes 运营商发布仅几个月后，该公司还发布了 Pulumi Automation API 的初始版本，该版本提供了一个 SDK，用于将 Pulumi 部署嵌入企业自己的软件和系统中，允许开发人员构建自己的界面来管理云基础设施，Pulumi 帖子称。

Pulumi Automation API 在很大程度上受到了该公司构建 Pulumi Kubernetes 运营商的经验的影响，该运营商将 Pulumi 部署嵌入到 Kubernetes 中，提供了一个新的界面——Kubernetes 堆栈资源——用于管理云基础设施。霍班和拉克什马南说，因此，Pulumi Kubernetes 运营商使用 Pulumi 自动化 API，大大减少了运营商实施的规模，建立在与 Pulumi 生态系统中的其他几十个项目共享的强大基础上。今年早些时候，Pulumi 自动化 API 也作为 Pulumi 3.0 版本的一部分正式发布。

Duffy 告诉 New Stack:“我们的 Kubernetes 运营商还可以帮助您从 Kubernetes 集群内部部署软件包，这是我们许多非常先进的云本地客户都感到兴奋的事情。

Duffy 说，如今许多 Pulumi 客户都在使用管道来制造组件。他说，Pulumi 的客户增长显著增加。

## 开发者优先的基础设施

“我们看到许多领域都在加速发展，包括中小型企业、中端市场和大型企业。我们看到了我们称之为开发人员主导的基础设施的兴起，将来您可能会听到我们更多地谈论这一点。“开发人员优先的基础设施意味着开发人员越来越多地掌握主动权并拥抱云，使云与应用程序架构更加紧密，但这并不意味着没有开发运维的位置，”达菲说。

事实上，Duffy 认为“开发者优先”的策略实际上减少了开发者和运营团队之间的任何摩擦。

“这是开发人员优先，因为这意味着基础设施团队经常思考我如何授权给我的开发人员，这是他们的核心任务之一，因为他们不想成为延误时间表、迟到和减缓创新步伐的责任人，”他说。“交付的速度要求他们授权给开发人员，但这必须通过 guardrails，必须通过像 Pulumi 这样的平台，真正帮助他们协作和工作。这就是我们所看到的。”

## Pulumi Kubernetes 运营商的下一步是什么？

自从 Pulumi Kubernetes 运营商的最初版本发布以来，Pulumi 不仅增加了对使用 Pulumi 服务后端的支持，还增加了对所有其他开源后端选项的支持，如用于状态存储的 S3、Azure Blob 和谷歌云存储，以及用于秘密管理的 [KMS](https://searchcloudsecurity.techtarget.com/definition/Google-Cloud-Key-Management-Service-KMS) 、 [KeyVault](https://azure.microsoft.com/en-us/services/key-vault/) 和 [Vault](https://www.vaultproject.io/) ，Pulumi 的帖子说。

最后，Duffy 指出，增强运营商能力和可扩展性的下一项创新是使部署能够在单独的作业中运行；采用来自最新运营商 SDK 的新特性，发布来自运营商的 Kubernetes 事件；并从运营商发布 Kubernetes 事件。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>