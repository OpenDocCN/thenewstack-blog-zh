# 微软对 Kubernetes 管理的实用方法

> 原文：<https://thenewstack.io/microsoft-takes-practical-approach-to-kubernetes-management/>

当涉及到容器、Kubernetes、微服务、无服务器功能和以 API 为中心的设计等云原生技术时，微软正在采取一种实用的方法——以 Azure 为先导，让客户拥有自己的方式。

例如，云软件和服务巨头最近指出，在 7 月底，它将推出一个由该公司的[Azure Arc](https://thenewstack.io/azure-arc-is-developing-into-a-full-hybrid-infrastructure-system/)multi Cloud portability service 支持的版本的 [Azure SQL](https://www.zdnet.com/article/microsoft-announces-arc-enabled-azure-sql-general-availability/) 数据库即服务，这样数据库就可以在竞争对手的云上运行，包括[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)和谷歌云平台，以及用户自己的数据中心。

该公司表示，这种支持 Azure Arc 的 Azure SQL 产品将在任何 Kubernetes 集群上运行，并从 Azure 门户网站进行管理。

总部位于纽约的 IT 咨询公司 Blue Badge Insights 的创始人兼首席执行官 Andrew Brust 说，微软在容器方面的总体策略，特别是 Kubernetes，“一直是清醒的、务实的和以结果为导向的”。

Brust 告诉 New Stack，事实上，微软致力于增强 Kubernetes，而不是与之竞争，优先考虑 Linux 作为容器部署的首选目标，并支持那些希望以最少的复杂性和麻烦追求多云和混合云策略的客户。

“无论是 Linux 上的 SQL Server 和 containers、Azure Arc、[Azure Kubernetes Service](https://thenewstack.io/how-the-azure-kubernetes-service-makes-developers-more-productive/)(AKS)还是更简单的 Azure Container Instances (ACI)，微软已经认识到容器化是事实上的行业平台转移，”他说。

微软致力于为企业在 Azure 及其内部环境、边缘位置和其他云上的云原生工作负载提供一流的开发和管理服务。在这方面，该公司已经在 Azure 应用服务中提供了增强的功能，以在 Kubernetes 和其他前述环境中运行。

微软 Azure 开发者体验副总裁 Gabe Monroy 表示，任何通过 Azure Arc 连接的[符合云计算原生计算基础](https://cncf.io/?utm_content=inline-mention) (CNCF)的 Kubernetes 集群现在都是 Azure 应用服务支持的部署目标。

微软的这一举措在微软的 Build conference 上以预览的形式发布，旨在帮助开发团队避免纠结于一些可能影响生产力的晦涩难懂的 Kubernetes 概念和 API。

像应用服务、函数、逻辑应用、API 管理和事件网格这样的 Azure 应用服务现在可以在任何地方的 Kubernetes 集群上运行。Monroy 说，开发者不需要在 PaaS 的生产力和 Kubernetes 的控制之间做出选择，因为相同的应用服务可以在任何一种模式下运行。

“开发人员可以使用 Azure Arc 支持的可移植应用服务来节省构建混合应用程序的时间，”Monroy 在一篇博客文章中写道。“当与支持 Arc 的数据服务(如 Azure PostgreSQL 和 Azure SQL)结合使用时，应用程序及其数据现在可以使用完全托管的云服务在任何地方运行，这是行业首创。”

Monroy 在接受采访时表示，零售、制造、旅游和金融服务等垂直行业的微软客户一直在寻求一种方法来结合 Azure 应用程序和数据服务，并在任何地方运行它们，并指出一些企业客户已经进入了预览。

“我们目前正在评估 Azure Arc 是否可以帮助我们将工业、研究和医疗[集团]中面向客户的工作负载转移到其他云或边缘上——根据客户偏好或法规要求, [Kai Walter](https://www.linkedin.com/in/kaiwalter/?originalSubdomain=de) 表示，他是德国奥伯科辰卡尔蔡司公司企业 IT 部门的杰出技术顾问和个人贡献者。“由于 Kubernetes 是关键，我们正在将 Azure Arc 与我们在 K8s 生态系统上使用定制的基础架构/部署脚本实现相同目标的成本进行匹配。”

[Forrester Research 的分析师 Jeffrey Hammond](https://www.linkedin.com/in/jeffrey-hammond-770630) 说，微软与 Kubernetes 的战略只是该公司实用主义的又一个例子。

“首先是 Linux，然后是 Java，现在是 K8s……如今，任何让 Azure 转盘旋转的工作负载在雷德蒙似乎都是受欢迎的，”他说。“我们离‘开源是毒瘤’的日子还很远很远。除了我，还有人记得吗？”

然而，这一举措有点不同，因为要拥抱 Kubernetes，微软必须投资于可移植性和混合云。

哈蒙德说:“这未必是一件坏事，因为数据中心运行着许多 Windows，但我猜想许多非 Azure K8s 工作负载都运行在 Linux 上，所以让微软的转盘旋转变成了一场更长的比赛。”

他指出，这个“游戏”将围绕微软让 Azure Arc 成为管理所有部署的“单一平台”。当开发团队在混合环境中扩展 Kubernetes 基础设施时，他们很快就需要决定哪里需要“管理重心”，微软将能够提供解决方案。

“对于微软来说，在企业 K8s 中向上移动，他们需要在移动时抓住管理工作负载，”Hammond 说。“随着他们开始管理工作负载并对其进行扩展，下一个目标是让开发人员尽可能轻松地使用平台/基础架构。我想几乎所有人都同意，对于大多数企业开发者来说，K8s 目前还没有达到足够高的抽象水平。他们想编写代码来解决业务问题，而不是花几个小时和 YAML 一起配置控制、网络和数据平面。这就是应用服务、Azure 功能和类似 [Dapr](https://cloudblogs.microsoft.com/opensource/2019/10/16/announcing-dapr-open-source-project-build-microservice-applications/) 的东西出现的地方。微软正在 K8s 之上慢慢推出更抽象的编程模型。你可以称之为基于 K8s 的 PaaS 的新浪潮，但我现在还不这么认为。”

然而，哈蒙德继续解释说，他相信如果微软在 Kubernetes 的管理和开发中获得立足点，那么该公司可以专注于尽可能简单和廉价地在 AKS 或其他 Azure 服务上部署。

“这是他们过去的闪光点，让开发和部署体验尽可能简单——尽管有 [DLL hell](https://en.wikipedia.org/wiki/DLL_Hell) ，”他说。“如果做得正确，长期的重头戏就变成了‘给我一个可信的/成本上的理由，让我不要只为商店部署 AKS’。”

Azure 应用服务组合的组件包括 [Azure App Service](https://azure.microsoft.com/en-us/services/app-service/) ，这是一个用于构建和管理 web 应用和 API 的平台， [Azure Functions](https://azure.microsoft.com/en-us/services/functions/) 用于事件驱动编程，以及 [Azure Logic Apps](https://azure.microsoft.com/en-us/services/logic-apps/) 用于创建自动化工作流，以将应用、数据、服务和后端系统与 400 多个连接器的库集成。Monroy 说，此外，还有 [Azure Event Grid](https://azure.microsoft.com/en-us/services/event-grid/) ，它简化了基于事件的应用程序，使用单一服务来管理从任何源到任何目的地的事件路由，还有 [Azure API Management](https://azure.microsoft.com/en-us/services/api-management/) 来提供跨所有内部和外部 API 的统一管理体验和可观察性。

Azure 应用平台的产品管理总监 Jeff Hollan 在演示如何使用 Azure Arc 和 Azure 应用服务构建基于 React 的 web 应用并从 Kubernetes 集群提供服务时表示:“我们希望让每个开发人员使用 Azure Arc 和我们的应用服务在任何地方发布应用都变得非常简单。

“我们让开发者变得简单，”蒙罗伊告诉新堆栈。“当他们以某个地区为目标，从“地区”下拉列表中选择该地区时，他们实际上可以以 Kubernetes 集群为目标，而不是像‘美国西部’这样的普通云地区，而不是美国西部，他们可以以我的 Kubernetes 集群为目标。除此之外，开发人员的体验与他们通常使用公共 Azure 区域获得的体验是一样的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>