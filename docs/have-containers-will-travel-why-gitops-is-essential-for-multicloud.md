# 拥有容器将会旅行:为什么 GitOps 对多云至关重要

> 原文：<https://thenewstack.io/have-containers-will-travel-why-gitops-is-essential-for-multicloud/>

[](https://www.linkedin.com/in/corneliadavis/)

[![](img/c995f6c533185539e6f4b5d2e150623c.png)](https://www.linkedin.com/in/corneliadavis/) [科妮莉亚·戴维斯

作为 WeaveWorks 的首席技术官，科妮莉亚·戴维斯负责公司的技术战略，包括开源项目、商业产品和服务。她渴望通过利用云平台来帮助企业实现业务转型。她在 Pivotal 的现代应用程序平台领域崭露头角，当时她所在的团队将 Pivotal Cloud Foundry (Pivotal 的 PaaS)和 Pivotal Container Service(Pivotal 的 Kubernetes Service)推向市场。科妮莉亚目前在云计算原生计算基金会的技术监督委员会任职。她是《云原生模式:设计容忍变化的软件》一书的作者。作为一名在图像处理、科学可视化、分布式系统和 web 应用架构以及云原生平台领域拥有近三十年经验的行业资深人士，Cornelia 拥有加州州立大学北岭分校的计算机科学学士和硕士学位，并在印第安纳大学进一步学习了计算理论和编程语言。不做这些事情的时候，你可以在瑜伽垫上或厨房里找到她。](https://www.linkedin.com/in/corneliadavis/) 

公司出于各种原因采用混合和多云策略，包括可靠性、地理必要性和供应商独立性，这带来了复杂性，即没有两个私有云或混合云是相同的。尽管该行业在 Kubernetes 上实现了标准化，但它如何呈现自己对于每个云都是不同的。亚马逊的弹性 Kubernetes 服务(EKS)与微软的 Azure Kubernetes 服务(AKS)或谷歌的 Kubernetes 引擎(GKE)需要不同的配置。大多数私有云构建在像 [VMWare](https://tanzu.vmware.com?utm_content=inline-mention) 的 Tanzu/VSphere 或 Nutanix 这样的平台上，在这些平台上安装和部署的功能通常是高度定制的。

任何试图维护多云或混合云基础设施的系统工程师都知道，这种可变性使得管理非常困难。不仅是不同的 Kubernetes 配置，而且登录和应用更改所需的脚本也是独特的。即使采用基础设施作为代码方法，在 git 中管理这些脚本，跨一组 git 存储库和分支管理脚本，并确保将正确的配置应用于正确的运行时环境仍然是一项艰巨的任务。比方说，一些新的监管相关配置需要添加到 AWS 和 vSphere 的部署中，SRE 需要首先将适当的配置添加到 git 中的 AWS 和 vSphere 分支，然后他们需要确保将前者应用到 EKS 实施，将后者应用到 Tanzu 集群。这些配置更改的应用通常是手动完成的，比如使用 AWS cli 或 vSphere 控制台，因此会出错。

现在想象一个拥有多地区甚至跨国基础设施的全球环境。向此设置添加一些边缘网络。由此产生的复杂 DevOps 工作流是不可持续的——然而这正是许多工程师现在正在做的事情。我们需要更好的方法。

自动化至关重要。在规模上，自动化需要以特定的方式完成。

当部署拓扑变得更加复杂时，GitOps 使多云和混合云变得可行。云、Kubernetes 和应用程序配置以声明的方式存储在 Git 中，允许将更改作为拉请求提交，由维护人员批准，并由软件代理自动应用。GitOps 允许工程师进行自动化编程，以确保正确的配置并应用于正确的环境，而不是管理混合环境中众多不同目标的配置部署。当运行配置与 git 不一致时，一系列代理会注意到这一点，并自我修复差异。此外，尽管混合拓扑中的配置总是存在差异，但使用 GitOps，我们指定了通用的基本配置(我们在所有环境中只管理一次)和 kustomizations(是的，用“k”拼写；-))与特殊化。所有这些都意味着 GitOps 提供了一个跨异构环境的标准化运营模型。

## 让集装箱安全地旅行

想象一下，位于北弗吉尼亚州的 AWS-East 出现了重大的[服务中断。因为大部分配置是通用的，并且您已经为 GCP 提供了专门化，所以您只需要为 GCP us-east1-b 地区启用该配置，标准化的 GitOps 流程将生成一个部署来补偿中断。或者考虑你的公司扩张到中国或者 AWS 没有到达的任何国家，所以你会在 Azure 或者你自己的基础设施上运行。是的，您在 git 中维护一个基本配置和一组特定于环境的专门化，并且在需要的地方应用正确的组合。](https://www.theverge.com/2020/11/25/21719396/amazon-web-services-aws-outage-down-internet)

如果维护多层不同的配置和应用程序脚本是一种逻辑上的痛苦，那么与它可能导致的安全问题相比，这算不了什么。本杰明·富兰克林说过:“三个人可以保守一个秘密，如果其中两个人死了。”然而，今天的 DevOps 策略通常以这样一种方式管理混合环境的秘密，即少数个人可以访问每个系统。GitOps 允许秘密从配置管理过程中分离出来。这使得配置管理过程可以在 git 中进行——有人对配置进行了更改，提交了一个 pull 请求，然后授权的维护人员合并它——然后该配置的应用程序以一种独立的、非常安全的方式进行处理。不同于多人登录不同的基础设施来应用更改，GitOps 流程具有非常本地化的安全访问，可以注意到差异并应用它。没有任何凭证以 DevOps 的名义泄露。

> 当部署拓扑变得更加复杂时，GitOps 使多云和混合云变得可行。

叶芝说得很好，“事物分崩离析。中心守不住。”总有一天，在某个地方，以某种方式，某些东西会断裂，而这种断裂通常是由于一些结构的改变。为了防止类似事件再次发生，我们将进行彻底调查，查看所有已应用的变更，并确定它们如何影响停机。有了 GitOps，审计变更变得很简单。Git 自动记录更改，提供了一定程度的透明度和准确性，极大地有助于此类调查。操作员不再登录服务器，误用没有可追溯性的脚本；所有的变更都被记录下来，只需要理解什么变更被合并，由谁合并，以及何时合并。

## 手工制作、自动化还是不断变化？

最终，这一切都归结于有多少自动化到位，以及所述自动化的特定性质。如果一个开发组织使用 CI/CD 管道，交付持续的变更，并负责大规模的基础设施，手动应用命令性脚本不是他们能承受的低效。必要性是为什么 GitOps 的第一批采用者是大规模铺设基础设施的人。他们正在管理跨越数万个节点的 5G 网络，或者是金融服务管理系统的工程师，这些系统全天候运行数百万笔交易并处理真实货币。

没有人认为多云是在单一云提供商的单一区域部署这么简单。管理这种复杂性的最安全、最直接、最优雅的方式是使用 GitOps 技术和方法。幸运的是，这些工具现在对你来说是现成的。[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)最近将 [Flux 推进到孵化阶段](https://www.cncf.io/blog/2021/03/11/cncf-toc-votes-to-move-flux-from-sandbox-to-incubation/)。Flux 是一个实现 GitOps 的开源工具包。

使用 Flux，工程师可以创建一个单一的、可审计的、版本化的事实来源，准确描述集群和工作负载将如何运行。这个“真相”可以传播到其他星团、其他区域、其他星云，甚至其他大陆。它应用的配置是云开发人员和工程师习惯使用的术语:Flux 使用 git、YAML 和 Kubernetes。

最终，为大型复杂环境进行 GitOps 需要可视化和监控工具，使系统工程师能够实时了解正在发生的事情，并探索拓扑结构，尤其是在拓扑结构发生变化时。创造了“GitOps”一词，最初创造了 Flux 并将其捐赠给 CNCF 的 Weaveworks ，扩展了 Flux 来做到这一点。

[Weave Cloud](https://www.weave.works/product/cloud/) 为团队提供全面支持的服务，只需几次点击操作即可实现 GitOps，提高可观察性，并简化对 GitOps 流程和整体拓扑的管理。 [Weave Kubernetes 平台](https://www.weave.works/product/enterprise-kubernetes-platform/)通过管理整个开发和部署生命周期以及添加额外的可观察性功能进一步扩展了这一点。

## GitOps 不仅仅是一项技术

在探索 GitOps 的过程中，我们不应该低估或高估 Git、Flux 甚至 Kubernetes 等工具的重要性。GitOps 不仅是技术，也是一套最佳实践，它是一种范式。它完全接受，甚至依赖于这样一个原则，即系统管理是通过声明性配置来完成的，该配置与实际运行的内容保持一致。也就是说，sys admin 变成了一个表达系统期望状态的过程，以系统的方式(例如在 git 中)管理这个表达，并利用正确的自动化类型来交付配置和自动操作部署。它像对待代码回归一样对待系统管理。如果出现问题，您可以回滚并让 GitOps 进程负责纠正系统。

GitOps 的入门相当简单，而且有价值，比如审计和回滚更改的能力，即使您没有管理大规模、复杂的系统。然而，如果您是一个在多个云上运行复杂基础设施的大型团队，GitOps 可能不仅仅是管理这种复杂性的最简单方法，它可能是唯一可持续的方法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>