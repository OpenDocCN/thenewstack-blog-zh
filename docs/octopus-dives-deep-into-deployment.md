# 章鱼深入部署

> 原文：<https://thenewstack.io/octopus-dives-deep-into-deployment/>

根据 IDC 的一项调查，开发人员的角色不断增加，使得他们对雇主来说越来越不可或缺，除了编码，他们还可能负责部署、自动化、用户体验和安全等方面。

特别是在云原生部署中，开发者面临的复杂性只会增加，因为 Kubernetes 框架提供商 [Shipa](https://www.shipa.io/) 的创始人 [Bruno Andrade](https://www.linkedin.com/in/bruno-a-a369028/) 和 [Upbound](https://www.upbound.io/) 的创始人兼首席执行官 [Bassam Tabbara](https://www.linkedin.com/in/bassamtabbara) 最近在[上讨论了新的堆栈制造商](https://thenewstack.io/cloud-native-deployments-bring-new-complexities-to-the-developer/)。

总部位于澳大利亚的 [Octopus Deploy](https://octopus.com/) 承担了这些复杂的部署工作，跨环境和部署目标实现了单一部署流程的自动化。它的最新功能，刚刚作为早期访问发布，被称为代码为的 [Config，它将应用程序设置与基础架构代码分离，使配置管理成为自己的过程。](https://octopus.com/blog/config-as-code-what-is-it-how-is-it-beneficial)

虽然这增加了复杂性，但该公司坚持认为它改善了版本化配置的安全性、可追溯性和管理，在 SANS 研究所的安全专家调查中，错误配置是一个越来越令人担忧的问题。Octopus Deploy 的高级解决方案架构师 Derek Campbell 表示，该功能让用户可以选择使用用户界面或通过 Git repo manager 进行更改，无论他们更喜欢哪种方式。

该公司正在考虑在今年年底或明年年初发布这项功能。

## 快速增长

保罗·斯托弗于 2012 年在布里斯班创办了这家公司，并在早期与妻子索尼娅单独经营。该公司现在在澳大利亚、美国和英国有 150 多名员工，其中大约一半是在过去一年加入该公司的。该公司预计，在未来一年到一年半的时间里，员工人数将增加一倍以上。

该公司一直是靠自己起家的，直到 4 月份宣布 Insight Partners 投资了 1.725 亿美元收购少数股权，Stovell 表示，这一举动更多的是因为需要关于公司增长的建议，而不是为了收入。该公司拥有 7，000 多名付费客户，并帮助自动化了 1.8 亿次部署。(Insight Partners】也在 6 月收购了新的堆栈。)

Octopus Deploy 的客户包括微软、美国宇航局、迪士尼、英国在线零售商 ASOS 和新西兰会计软件公司 Xero。

根据 Stovell 的说法，它在 T4 的客户往往是拥有至少 200 名员工的公司，他们拥有复杂的部署和足够大的工程团队，希望在部署工具上实现标准化。

## 深入部署

关于持续交付和发布自动化的 2020 年 Forrester Wave 报告将 CloudBees、IBM、微软、Digital.ai、Broadcom 和 Flexagon 列为该市场的领导者。它将 Octopus Deploy 列为竞争者之一。它说，该市场的关键区别包括支持广泛的平台，包括传统平台和云原生平台；能够可视化复杂的应用程序和部署模型，以及管理部署结果。

坎贝尔承认，虽然这是一个拥挤的市场，但大多数竞争对手都是提供一系列产品的公司，而 Octopus Deploy 只专注于部署。据 Stovell 称，该公司决定深入部署，而不是成为端到端的 CI/CD 解决方案。他还打算成为开发人员想要使用的工具。

该技术最初是作为. NET 工具创建的，现在支持 Java、Linux、Node.js 和其他技术。该公司现在专注于扩大更全面的管道覆盖范围。它获取构建服务器生成的包和工件，并使用一致的过程将它们部署到不同的目标。

“它的作用是获取您的包，它可以是. NET 核心，可以是 Java，可以是 bash 脚本，可以是许多不同的语言，我们可以部署它。坎贝尔说，我们不在乎你的服务器或部署目标在哪里，“不管是 Azure、AWS、谷歌云、内部部署、Kubernetes 集群、云区域，还是笔记本电脑。

[https://www.youtube.com/embed/Z77T3SHRLKE?feature=oembed](https://www.youtube.com/embed/Z77T3SHRLKE?feature=oembed)

视频

您可以安装 Octopus 服务器的自托管实例，或者使用托管版本的 Octopus Cloud。

您定义部署应用程序的过程；它提供了 400 多个步骤模板来帮助简化最复杂的部署。

它为配置变量、环境定义、API 密钥、权限、自动化逻辑等的重用提供了一个单一的平台，有助于开发人员、发布经理和运营工程师保持一致。

然后指定应用程序部署到的环境，例如开发、测试、生产环境，以及谁可以部署到哪些环境。开发人员可以访问某些环境，但不能访问其他环境，同时保持部署过程的一致性。

## 多种部署模式

Octopus Deploy 支持多种部署模式——金丝雀、滚动、蓝/绿——以及跨多租户架构部署的能力。它的 API 优先架构包括 300 多个插件和适配器。

坎贝尔说:“我们不是[像其他供应商那样]与我们的其他产品集成，而是与许多产品集成。”。“我们通常发现大多数组织可能有多个配置项。你知道，某个团队有詹金斯。也许有人在用 CircleCI。外面有那么多。…我们将从任何配置项获取您的数据包，并部署到任何位置。”

Octopus Server 提供了自己的只写存储库，据说它提供了最好的性能，但也支持来自 Docker、Maven、GitHub 和其他存储库的提要。

[Runbooks](https://octopus.com/docs/runbooks) 使用户能够自动执行日常维护和紧急操作任务，如基础设施供应、数据库管理以及网站故障转移和恢复。例如，CircleCI 需要一个测试服务器。坎贝尔说，操作手册可以自动设置操作系统，应用依赖关系和其他相关任务。

Insight Partners 副总裁 [Philine Huizing](https://www.insightpartners.com/team/philine-huizing) 表示，作为尽职调查的一部分，insight Partners 与 30 多个客户、合作伙伴和市场利益相关者进行了交谈，显然 Octopus 的定位是独特的。

“Octopus 的核心一直是以产品为导向，为开发者制造产品并向他们销售产品。结果是，你只剩下开发团队在倡导他们喜欢使用的平台，”她说。“Octopus 不仅是开发人员的明确选择，也是更广泛的企业部署自动化的主要选择。”

Insight 还与金融服务、网络规模技术和医疗保健领域的几家成熟企业客户进行了交流，这些客户已经在 Octopus 上实现了关键任务核心应用部署的标准化。这些核心应用程序跨越多种框架——Java、.网络核心、节点等。以及部署目标——EKS 的 Linux 容器和 AWS，本地服务器，她说。Octopus 自动化了这些部署，为复杂的手动过程带来了简单性和可靠性。

“Octopus 通过其 Runbook Automation 产品和即将推出的 Config as 代码，继续将自动化构建到产品中，以最终用户为中心。Octopus 已经成为第一个平台，使公司的开发人员、发布经理和运营团队能够将所有自动化功能集中到一个地方，”她说。

*查看网上技术交流讲座“[深入了解代码为](https://octopus.com/events/technical-deep-dive-with-config-as-code)的配置”，东部时间 9 月 29 日上午 9 点、东部时间 9 月 30 日下午 3 点和东部时间 10 月 4 日上午 1 点。*

[https://www.youtube.com/embed/JUKWhXWulOA?feature=oembed](https://www.youtube.com/embed/JUKWhXWulOA?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>