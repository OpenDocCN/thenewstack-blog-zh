# GitLab 将 Brooklyn: DevOps 作为单个应用程序提交

> 原文：<https://thenewstack.io/gitlab-commit-brooklyn-devops-as-a-single-application/>

像软件开发工具和服务领域的许多供应商一样，以版本控制而闻名的 GitLab 正在寻求将软件开发带来的持续集成/持续部署自动化并整合到单个生命周期中，以帮助组织快速开发、修复和更新他们的软件堆栈。

“周期时间压缩是企业成功的关键。GitLab 首席执行官 [Sid Sijbrandij](https://about.gitlab.com/handbook/ceo/) 在该公司于周三在纽约举行的 [GitLab Commit Brooklyn](https://about.gitlab.com/events/commit/) 活动期间表示:“几乎你需要做出的每一项改进都必须在软件中完成。事实上，会议强调、回顾并预测了构建过程(如基于 GitLab 的构建过程)可以扩展和自动化的许多方式，以支持 IT 的许多其他方面，如治理、数据操作和安全性，并尽可能自动化应用程序的构建和部署。

Sijbrandij 承认，就提供一个完整的集成套件来处理软件开发的所有方面而言，该公司还不太到位，尽管他吹捧该公司快速构建功能的积极计划。正如我们现在所知道的，所需工具的范围将跨越许多不同的产品线:计划、代码管理、创建、验证、打包、安全、发布管理、配置和监控。

然而，并非所有这些工作都将由公司内部完成。例如，公司[与](https://about.gitlab.com/2019/09/17/gitlab-hashicorp-terraform-vault-pt-1/)和 [HashiCorp](https://www.hashicorp.com/) 合作，使运营团队可以轻松管理 GitLab 中的基础设施配置，然后可以由 [TerraForm Cloud](/context-new-versions-of-hashicorps-terraform-cloud-for-teams-and-for-governance/) 执行。GitLab 还将 HashiCorp 的 [Vault secrets 管理工具](https://www.vaultproject.io/)纳入其中，为开发人员提供了一种确保分布式应用程序安全性的编程方式。

## DevSecOps

[![](img/8fb37960bf619e3ca10b2eb75c59f73d.png)](https://cdn.thenewstack.io/media/2019/09/3bbc839b-autoremeidate-01.jpg)

在一次即将到来的技术演示中，GitLab 产品战略副总裁马克·彭萨克展示了 GitLab 自动化如何加强安全性。当今组织面临的最大问题之一是第三方包中的错误和安全漏洞，这些错误和安全漏洞已经嵌入到他们自己的软件中(“依赖”)。一旦软件发布，您如何知道哪些依赖项正在被使用，更不用说知道它们是否仍然安全了？

这个特性现在正在内部原型化，它会自动检查依赖包是否有漏洞，如果有，就暂时停止构建。更好的是，该公司还在计划一项功能，该功能将自动启动构建，并将更新的依赖项合并到现有程序中，如果它没有按预期工作，则将其回滚。Pundsack 警告说，虽然这些自动合并可能不适用于所有情况，但它们可能适用于大多数情况，允许开发人员通过异常进行管理，这种方法通常可以节省时间。

数据操作(“DataOps”)可能是另一个受益于自动化和版本控制的领域。在下午的小组讨论中，数据从业者谈到了当前数据操作实践的局限性，以及为什么不能在类似的 CI/CD 管道中管理数据。克莱尔卡罗尔(Claire Carroll)指出，在大多数公司，分析师对他们使用的数据模型有太多的格式怪癖，而且通常他们是组织中唯一知道这些规则的人，这可能是一个瓶颈。在小组讨论中，GitLab Analytics 数据工程师 Emilie Schario 回忆说，她曾经花了 80%的时间来核对两位高管报告的两份销售数据。"我花了太多时间试图弄清楚到底发生了什么。"

Schario 在会后解释说，GitLab 自己的数据团队使用标准的 GitLab CI/CD 工具来管理所有自己的数据，包括数据模型和源数据本身。不需要特殊工具。另一位小组成员，[丹尼尔·莫里尔](https://gitlab.com/dmor)，专注于数据操作的 GitLab 初创公司[梅尔塔诺](https://www.meltano.com)的总经理指出，当数据在企业中移动时，版本控制可以非常方便地跟踪数据，比如说，一个 PowerPoint 演示文稿的冲突版本可能会导致问题。

Morrill 说:“我认为版本控制有很多优点，不仅仅是作为一个工作工具，也是一个交流工具。”

## 机会领域

[![](img/92d721e88edf076fe3bd3579b33034fb.png)](https://twitter.com/Joab_Jackson/status/1173954526790987776)

毫无疑问，CI/CD 领域非常热门，不仅仅是因为它是云原生计算的必要先驱，正如云原生计算基金会 CEO [Dan Kohn 在他的演讲](https://twitter.com/Joab_Jackson/status/1173960987877236737)中所讨论的那样。本周，GitLab 宣布获得了 2.68 亿美元的 E 轮融资，将[公司对投资者的价值推高至 27.5 亿美元](https://about.gitlab.com/2019/09/17/gitlab-series-e-funding/)，因此投资者显然看到了 CI/CD 的使用越来越多。当然，该公司有许多客户认为需要通过工具和服务来扩展他们的软件开发自动化和治理。

在上午的主题演讲中，达美航空公司 DevOps 卓越中心的 IT 经理 Jasmine James 解释了该公司如何发现云原生计算将帮助该公司走上一条更加以客户为中心的业务道路，承诺灵活地为乘客提供个性化服务、更轻松的登机手续、更好的航班重新安排和其他好处。她指出，从历史上看，提供这些好处的最大瓶颈是基础设施。

金融投资公司高盛(Goldman Sachs)副总裁兼技术研究员乔治·格兰特(George Grant)在另一次演讲中指出，高盛(Goldman Sachs)正在从支持其所有应用程序的 10 个独立的软件开发生命周期转向基于 GitLab 的中央软件开发生命周期，这一迁移希望为更灵活地使用云奠定基础。他指出，在建立内部服务的两周内，超过 1600 名高盛开发人员开始使用基于 git 的服务，没有提示。

GitLab 和 HashiCorp 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>