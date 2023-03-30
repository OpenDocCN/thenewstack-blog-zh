# GitLab 15 升级解决了安全性、可观测性、数据操作

> 原文：<https://thenewstack.io/gitlab-15-upgrades-address-security-observability-dataops/>

在上周的 [KubeCon + Cloud Native Con，EU](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 上，演讲者探讨了两种日益采用[云原生](https://thenewstack.io/category/cloud-native/)技术的途径:对专业化和利基市场日益增长的兴趣(例如，电信公司，它在会议前有自己的演讲者)和一体化的数字化转型黄金途径。

git lab 的开发者布道者 Brendan O ' Leary 说，云原生和支持它的[生态系统](https://landscape.cncf.io/)的增长既需要专业化，也需要各种组织都可以走过的“铺路”。

“我们将看到两种截然不同的途径——为人们提供入口，但也为人们提供他们需要部署到特定环境中的非常专业的东西，”他告诉 New Stack。

周一，随着 GitLab 15 的发布，GitLab 推出了其在“铺平道路”战略上的最新赌注，其中包括影响[可观测性](https://thenewstack.io/category/monitoring/)、[安全性](https://thenewstack.io/category/security/)和[数据科学](https://thenewstack.io/category/data/)的重大升级。

15.0 版本的 [DevOps](https://thenewstack.io/category/devops/) 平台通过自动生成可导出的[软件材料清单(SBOM)](https://thenewstack.io/securing-the-software-supply-chain-with-a-software-bill-of-materials/) 以及构建工件的签名证明来增强可观察性。

创建和分析 SBOMs 的能力对于那些在其软件中严重依赖开源组件的组织(换句话说，几乎所有的组织)来说已经变得至关重要，尤其是在去年冬天的 [Log4j 崩溃之后。](https://thenewstack.io/burning-down-the-house-quantifying-the-impact-of-log4j/)

随着[云本地计算基金会(CNCF)](https://cncf.io/?utm_content=inline-mention) 于 2021 年发布最佳实践白皮书，保障软件供应链安全已经发展成为一项全球性运动。[Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)的 [OpenSSF](https://openssf.org/) 项目也[在 10 月的洛杉矶 KubeCon 期间宣布了来自供应商的 1000 万美元](https://openssf.org/press-release/2021/10/13/open-source-security-foundation-raises-10-million-in-new-commitments-to-secure-software-supply-chains/)的新投资，旨在努力保护软件供应链。

据 O'Leary 说，一体化 DevOps 平台的一个优势是能够在软件的整个生命周期中拥有更全面的软件视图。

“如果你有一个平台，一个 DevOps 平台，你能够了解软件的所有依赖项是什么？”他说。“供应链的所有部分是什么，并且能够分析整个供应链，而不仅仅是其中的一小部分。”

12 月， [GitLab 收购了 Opstrace](https://about.gitlab.com/press/releases/2021-12-14-gitlab-acquires-opstrace-to-expand-its-devops-platform-with-open-source-observability-solution.html) ，一个开源的可观测性分布。O'Leary 说，这次收购使 GitLab 获得了新的监控和跟踪技术，这些技术将被集成到 GitLab 15 中。( [GitLab 每月都会发布新的迭代](https://about.gitlab.com/upcoming-releases/)。)

将 Opstrace 的工具集成到 GitLab 是一个持续的、迭代的过程，O'Leary 说:“我们正在引入一些零碎的东西。”

他补充说，“当我们收购公司时，我们认为我们将把它们引入平台。我们认为，要做到这一点，就要有一个平台，在这个平台上做所有的事情。”

## 安全审批策略

GitLab 15 的另一个新特性是它如何处理安全批准策略。最新版本允许安全团队在组级别应用一组集中管理的安全策略，缩小了允许谁编辑安全策略的范围，并要求两步批准流程来更改批准规则。

O'Leary 说，这个功能可以帮助比安全专家更了解他们的应用程序的开发人员更加注意他们的工作如何影响安全。

“这实际上是关于社区——加强安全团队和开发团队之间的交流，”他说。“我们希望能够在问题发布之前就发现它们。当我对代码进行更改时，我想知道这会带来安全隐患。”

他说，与更传统的应用程序安全方法相比，这是一个巨大的文化和生产力进步。

“我曾经是联邦政府的合同工，工作周期是八周，”奥利里回忆道。“八周后，他们进行了安全扫描，发现了 195 件东西。好吧，我们要做什么，不把它寄给顾客？问题是这 195 件事情中的每一件本身都没什么大不了的。但是如果它发生在我们输入密码的时候而不是一个月后呢？

“现在，您可以修复它或了解它是否是误报，因为安全的很大一部分是会有误报。但是在你做出改变的时候做出决定，你会有更多更好的信息。”

## 支持数据科学

GitLab 15 还将拥有新的功能，使组织更容易利用他们收集的数据，这些功能旨在实现[数据操作](https://thenewstack.io/how-dataops-can-make-your-data-more-actionable/)和[机器学习](https://thenewstack.io/category/machine-learning/)操作( [MLOps](https://thenewstack.io/what-is-mlops/) )，从而简化 ML 模型的创建和部署。

新版本的 DevOps 平台将使用户能够提取、加载和转换数据，使他们能够轻松地将数据连接到 GitLab 管道。

“人们正在建立模型，并拥有所有这些数据，”奥利里说。“他们需要开发的最佳实践和结构化的环境。该数据团队是整个产品团队的一部分。所以他们也需要在平台上。”

O'Leary 表示，GitLab 也在致力于将更多的人工智能(AI)集成到其平台中，例如帮助处理和跟踪合并请求。

DevOps 平台的最新版本还将包括对企业敏捷规划和工作流自动化的更多支持。“我们有了‘工作项目’的新概念，这样人们就可以更具体地知道某人需要执行什么样的特定任务，作为需要编写的代码，”O'Leary 说。

预计在不久的将来，其他规划和工作流程升级包括:

*   保存的视图和查询，这将允许团队创建带有聚合数据的定制仪表板，以快速检查关键计划的状态。
*   建议的审核者和标签，这将自动推荐正确的团队成员和下一个工作流程步骤，以提高生产率和透明度。
*   增强的建议，它提出上下文相关的建议，以加速决策并减少 DevOps 团队的认知负荷。

GitLab 15.0 版本现已推出；关于更新自管理实例的信息可以在[这里](http://about.gitlab.com/update)找到。GitLab 的软件即服务由 GitLab Inc .自动更新。该公司将于 6 月 23 日在[举办 GitLab 15 网络研讨会。](https://about.gitlab.com/fifteen/?utm_medium=pressrelease&utm_content=gitlab15)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>