# 灵活的控制平面如何帮助在 Kubernetes 上部署应用

> 原文：<https://thenewstack.io/how-a-flexible-control-plane-helps-deploy-apps-on-kubernetes/>

如果所有开发人员都必须担心用他们选择的编程语言创建杀手级应用，而不知道 Kubernetes 如何工作，这不是很好吗？

这些场景可能存在于孤立的情况下，例如当工程师为谷歌或特斯拉等公司的[机器学习(ML)](https://thenewstack.io/category/machine-learning/) 进行纯研究时，他们可以自由地创建明天的应用程序。然而，大多数云原生工程师的开发体验并不像这样。

今天的开发人员必须对 Kubernetes 有一个扎实的了解——这本身就不是一件容易的事——并且通常需要至少有关于 [GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 流程和[云本地计算基金会](https://landscape.cncf.io/) (CNCF)旗下的数百个工具的工作知识。

在自包含、全栈开发团队的时代，开发人员不再简单地为整体部署创建应用程序，并在此基础上进行进一步开发，将应用程序管理部分留给运营团队。

但是没有一个开发人员能够了解他们可以使用的每一个工具。将平台、工具和流程拼凑在一起，仅仅是为了开发在容器化的 Kubernetes 环境中运行的应用程序，就需要大量的资源投资——由于所涉及的内在复杂性，这往往会导致失败。

已经成功转移到[原生云](https://thenewstack.io/category/cloud-native/)的组织通常依赖于为其开发人员提供一个合适的控制平面，作为一种与工具和平台无关的底层方式来管理 Kubernetes。

[Ambassador Labs](https://www.getambassador.io/?utm_content=inline-mention) 将[开发者控制平面(DCP)](https://www.getambassador.io/developer-control-plane/) 定义为可以指导云原生开发者创建他们的代码和应用，将它们部署到生产中，并在部署后管理它们。

它应该支持从 A 到 Z 的源代码控制、 [CI/CD](https://thenewstack.io/category/ci-cd/) 、GitOps、API 和容器管理，当然还有 Kubernetes 运行时和[可观察性](https://thenewstack.io/category/monitoring/)。虽然 Kubernetes 非常复杂，但是有助于其编排的 DCP 应该很容易被开发人员采用和使用。

## 将“建筑工具包”粘合在一起

企业管理协会(Enterprise Management Associates)的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉 New Stack，尚未为 Kubernetes 环境采用控制平面的组织通常会遇到很多困难——如果不是现在，那么在不久的将来。

Volk 说，DCP 通常是维持 Kubernetes 集群的安全性、自动化和管理的必要粘合剂。他说，这是因为 Kubernetes 世界由众多类别和子类别的产品组件组成，它们可以构成一个应用程序堆栈。

> 任何开发人员或开发团队都应该可以访问开发人员控制平面，无论他们处于云原生之旅的哪个阶段。

“CNCF 已经统计了近 2000 个这些云原生元素，为 DevOps 团队提供了一个庞大的‘构建工具包’，以创建松散耦合的堆栈来构建、部署和运行云原生应用，”Volk 说。“这种难以置信的灵活性是以缺乏一致性为代价的，只有通过统一的控制平面才能解决这一问题。”

任何开发人员或开发团队都应该可以访问 DCP，无论他们处于云原生之旅的哪个阶段。这可能包括已经在云原生环境中部署应用程序的组织，或者寻求以小本经营的软件即服务提供商的身份扩大业务范围的初创公司。

在这两种情况下，开发人员都可以从适当的控制平面中受益。同样，它的采用应该很容易，因为 DCP 的想法是使 Kubernetes 的开发过程尽可能无缝。

通过这种方式，一个合适的 DCP 应该允许开发者创建一个云帐户来开始。正如 Ambassador 的联合创始人兼首席执行官 Richard Li 告诉新堆栈的那样，访问 DCP 提供的实时开发环境应该“只需几次点击”就可以完成。

## 灵活性或破产

DCP 的目的还在于协调和简化现有工具和平台的流程；控制平面应该与工具和平台无关。

“DCP 是关于协调和管理您已经拥有的基础设施，而不是供应商说，‘我知道您正在使用 [Argo](https://thenewstack.io/argo-the-kubernetes-native-workflow-engine-joins-the-cncf/) 和其他工具，但是让我们把它拆掉，用我们的平台替换它，因为有所有这些您应该使用的好东西，’”李说。"相反，DCP 应该充当云用户界面管理器，而不必重新开始."

DCP 的功能可能会有所不同。以 Ambassador 为例，其[大使云产品](https://www.getambassador.io/products/ambassador-cloud/)，一个位于 SaaS 的 DCP，为开发者提供单一界面:

*   使用由 Ambassador 维护的开源[网真](https://github.com/telepresenceio/telepresence)提高开发人员和测试人员的反馈质量和速度，这有助于在本地处理单个服务，这些服务也连接到远程 Kubernetes 集群和相应的应用程序依赖项。
*   通过 Argo CD 和针对 GitOps 和 CI/CD 的 Argo 推广将软件更新发布到生产环境中，并通过服务目录监控发布进度
*   使用 [Edge Stack](https://www.getambassador.io/products/edge-stack/) 运行服务，扩展 API 网关和具有 [edge](https://thenewstack.io/category/edge-iot/) 特性的入口控制器，实现开发人员主导的自助服务和全周期开发模式。

Volk 说，Ambassador 的 DCP 显示出了希望，这主要归功于它对远程呈现的使用，因为大多数开发人员都是在他们自己的开发环境中开始他们的项目的，通常是在本地开发环境中。

“将本地环境与测试、试运行和生产集群同步，让软件工程师不再头疼，”Volk 说。“这一切都归结于‘一次编码，随处部署’的范式，它让开发人员专注于他们擅长的事情:编写应用程序逻辑，而不是担心基础架构代码。”

## 案例研究:Zipcar 自动化 YAML 配置

Kubernetes 开发人员面临的一个主要难题是非常可怕的 YAML 文件配置。这是 Ambassador 特别改进其 DCP 的地方，以便减轻所涉及的大量工作。

使用 Ambassador 的 DCP，开发人员输入信息以响应 API 查询，然后自动创建一个拉请求，并自动配置 YAML 文件。

> “DCP 指的是协调和管理您已经拥有的基础设施，而不是供应商所说的‘我知道您正在使用 Argo 和其他工具，但是让我们把它拆掉，用我们的平台替换它，因为有所有这些您应该使用的好东西。’"

— Richard Li，大使实验室首席执行官

“我们的想法不是中断工作流程，而是进一步自动化它。我们正在减少手工劳动量和可能出现的人为错误，”李说。“如果你把我们赶出去，并决定不再使用大使，YAML 仍然完好无损，因为它只是 YAML。换句话说，DCP 不是专有的，因此您不会受到限制。”

对于部署，Ambassador 的 DCP YAML 配置功能帮助汽车共享提供商 Zipcar 简化了跨多个地理区域的开发人员代码部署。

Zipcar 的 DevOps 平台工程师 Bo Daley 告诉 New Stack，Zipcar 开发人员创建了一个他们“需要向全世界开放”的应用程序。

“如果没有 DCP，身份验证系统和其他安全检查会降低部署速度。戴利说，这个过程也可能很复杂，而且“充满了你可能陷入的安全问题”。

他说，Ambassador 的 DCP 在 Zipcar 网络的不同集群中以安全的方式自动整合开发者的 YAML 文件方面派上了用场。

戴利说，Zipcar 开发者和 Ambassador 的 DCP“采用了一些相对简单的 YAML”，开发者描述了这些应用程序如何适用于不同的网址大使负责编写将使这一切发生的所有 YAML 配置。这无疑为我们节省了大量时间。"

李说，比 Zipcar 国际组织更小的开发团队也可以从云大使中受益。例如，他的公司的客户包括全球财富 500 强公司，但也包括小得多的组织。

“我们与许多甚至没有首席信息官的创业公司合作，”李说。“无论组织的规模如何，我们的最佳点都是面向已经开始在 Kubernetes 上进行开发并拥有特定计划的 DevOps 团队，无论是开发 CI/CD 还是运行时编排需求。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>