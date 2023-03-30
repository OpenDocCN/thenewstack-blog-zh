# Codefresh 通过 Argo 开放核心，预览开放的 GitOps 1.0 版本

> 原文：<https://thenewstack.io/codefresh-goes-open-core-with-argo-previews-open-gitops-1-0-release/>

基于 Kubernetes 的持续部署和持续集成(CI/CD)平台背后的公司 Codefresh ，本周在今年的 [KubeCon+CloudNativeCon 北美](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)之前发布了 Codefresh Argo 平台，向完全开放的核心方法迈进。虽然之前 Codefresh 参与了开源项目，但它的核心产品仍然是独立和专有的。随着 Codefresh Argo 平台的发布，其核心将是开源的 [Argo](https://argoproj.github.io/) 工作流引擎，并在其上添加额外的企业功能和支持。

“我们决定让我们的公司完全开源，”Codefresh 联合创始人兼首席开源官丹·加菲尔德说。“在过去的 Codefresh 中，我们为 Helm、[[Cloud Native Application Bundles](https://thenewstack.io/what-is-cnab-and-why-it-is-important-for-cloud-native-computing/)]以及其他一些重要的开源项目做出了贡献，在过去的一年中，我们一直在帮助领导[Cloud Native Computing Foundation](https://cncf.io/?utm_content=inline-mention)下的 GitOps 项目，我们决定做的是，与其在这里或那里做出一些开源贡献，拥有一些开源的组件，我们已经决定逆转并拥有一个完全开放的核心方法。”

Codefresh Argo 平台采用了四个主要的 Argo 组件— [Argo 工作流](https://argoproj.github.io/argo-workflows/)、 [Argo 事件](https://argoproj.github.io/argo-events/)、 [Argo CD](https://argoproj.github.io/argo-cd/) 和 [Argo 展示](https://argoproj.github.io/argo-rollouts/) —并将它们合并到一个平台中。虽然之前 Codefresh 一直在独立开发功能，然后将其中一些功能贡献给 Argo，但现在该公司将把其平台的核心变成 Argo 开源项目，将企业功能分离出来。Garfield 解释说，这里的部分好处是 Codefresh 通过提供可伸缩性、安全性和对 Argo 部署的支持来帮助公司，否则 Argo 部署可能不会定期升级。

“如果你看看一家大公司，他们会有 5000 个 Jenkins 实例，其中 60%到 70%会有远程代码执行漏洞，因为维护所有这些实例非常困难，”Garfield 说。“使用 Codefresh Argo 平台，我们能够做的是，我们基本上可以启动、管理、更新和处理许多实例的安全性，同时提供对所有实例的洞察。”

相比之下，Codefresh Argo 平台允许其用户处理所有关于部署和运行 Argo 的企业管理任务，但只需从一个仪表板上进行。

加菲尔德说:“开放源代码是 Argo，你可以运行它的单个实例，你可以运行它的多个实例，然后在它上面的层-控制平面，允许你大规模管理工作流，允许你处理安全，允许你进行更新和配置，并在防火墙后工作，工作部署到边缘集群等-这都是 Codefresh 企业平台和 Codefresh Argo 平台的一部分。”

Garfield 解释说，Codefresh Argo 平台的另一个好处是，当前的 Argo 用户可能正在构建自己的实现来将 Argo 的四个部分连接在一起，而 Codefresh Argo 平台处理这种集成。同时，通过迁移到 Argo 作为开放核心，Codefresh 的最终用户受益于 Argo 开源社区的指导和贡献，并获得更多的工作流模板、更好的集成和更好的管理路径。

加菲尔德说:“我们开始受益并为社区提供好处，并且总是有一些更新的东西，我们不必投入太多的资源来更新核心引擎。”“我们可以更多地关注那些支持规模、安全性和支持的差异化功能。这与谷歌从 Kubernetes 中获益的原因非常相似。”

在这一点上，Codefresh Argo 平台正在发布以供早期访问，用户可以从现在开始[请求加入](https://codefresh.io/codefresh-argo-platform/)，预计将于 2022 年 1 月全面上市。

## Open GitOps 即将发布 1.0 版本

除了 Codefresh 转向开放核心模型的消息，Garfield 还提供了一项倡议的更新，我们[去年](https://thenewstack.io/codefresh-launches-gitops-2-0-as-a-gitops-working-group-takes-flight/)与他谈到了这项倡议，即 [GitOps 工作组](https://github.com/gitops-working-group/gitops-working-group/)的努力，该工作组现在是 CNCF 沙盒项目，也是 [CNCF 应用交付特别兴趣小组(SIG)](https://github.com/cncf/tag-app-delivery) 下的一个工作组。

该组织于去年由亚马逊、Codefresh、GitHub、微软和 T2 的 Weaveworks 组成，加菲尔德说，从那时起，它已经看到了 60 多家公司对其开放 GitOps 原则的反馈。本周，该组织准备最终宣布 [Open GitOps 1.0](https://github.com/open-gitops/documents) 的发布，根据新的 [Open GitOps 网站](https://opengitops.dev/about)，它打算在其中展示“GitOps 的供应商中立、原则主导的含义”。

Garfield 提到，在最近的一次活动中，他们非正式地调查了一群人对 gitop 的使用情况，近一半的人回答说他们确实采用了 gitop 原则。然而，在做了一个关于 gitop 的演讲后，同一人群中的一小部分人说他们实际上在练习 gitop。

“我们发现，人们对 gitop 的理解和 gitop 是什么之间实际上有很大的差异，”他说。“这是我们推出 1.0 版的一个很好的原因。当人们阅读它时，我认为许多人会惊讶地意识到他们只实施了 GitOps 的一部分，实际上还有几部分要做并符合标准。”

虽然许多公司已经建立了基于 Git 的基础设施作为代码，但许多公司还没有实现任何东西来监控漂移并使基础设施与期望的状态相协调——这在 [Open GitOps 1.0 原则](https://github.com/open-gitops/documents/blob/main/PRINCIPLES.md)中有所阐述。

虽然 Open GitOps 1.0 在此次发布时尚未正式公布，但 Garfield 表示，预计将在本周发布。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>