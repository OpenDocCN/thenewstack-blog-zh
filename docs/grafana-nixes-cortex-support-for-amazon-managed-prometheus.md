# Grafana Nixes Cortex 对亚马逊管理的普罗米修斯的支持

> 原文：<https://thenewstack.io/grafana-nixes-cortex-support-for-amazon-managed-prometheus/>

过去几周，Grafana Labs 对其一些核心产品、许可协议，尤其是其 [Prometheus 相关产品](https://prometheus.io/)进行了一些重大修改，取消了 Cortex 开源项目的维护，并引入了[米伊美](https://grafana.com/oss/mimir/)取而代之。Grafana 服务也将很快在 Azure 上提供。

我们首先描述这些变化是什么，并详细说明对 Grafana 广受欢迎的仪表板和工具的数百万用户的影响。

## 无弹性搜索聚类

由于 Grafana Labs 不再维护 Cortex——基于 Prometheus 的开源时间序列数据库监控工具——这对于在 Cortex 上运行的亚马逊管理的 Prometheus runs 有一定的影响。Grafana Labs 的产品副总裁 Tom Wilkie 告诉新的堆栈，在 Cortex 的位置上，米伊美拥有“许多优于 Cortex 的内置优势，主要是由于我们大约六个月前在内部转向米伊美的工程努力，”，他也是 Prometheus 的维护者和 Loki 与 Cortex 的共同创造者。

同样值得注意的是，尽管表面上可能如此，Grafana Labs 的举动并不是为了保护其来自 Cortex 的收入，这让人联想到 AWS 和 Elastic 争议。这是因为虽然亚马逊管理的普罗米修斯是建立在 Cortex 之上的，但与 Elastic [在](https://www.elastic.co/blog/why-license-change-AWS) [AWS 分叉 ElasticSearch](https://thenewstack.io/what-the-fork-amazon/) 并将其作为服务提供后，通过使许可更具限制性来改变 ElasticSearch 的许可时相比，环境是不同的。为了反击 Elastic 的举动，AWS 随后在发布之前完成了开源的 Elastic search[AWS 发布了 OpenSearch](https://thenewstack.io/this-week-in-programming-aws-completes-elasticsearch-fork-with-opensearch/) 。

相反，Grafana Labs 的商业模式并不是基于为其开源项目提供支持服务。相反，Grafana Labs 的收入是基于同名的 Grafana、Loki、Tempo 和现在的米伊美等企业版，以及注册 Grafana 服务后可以获得的其他服务和工具。

令人惊讶的是，在估计超过 1000 万的 Grafana 用户中，只有一小部分 Grafana 用户为企业账户付费，并为 Grafana 的收入做出贡献。Loki 估计有数万名用户，但只有数百名付费用户。

“我们希望米伊美有几十万——如果不是几百万——用户，我们希望有几千个付费用户，”威尔基说。

换句话说，Grafana Labs 的商业模式与 Elastic 非常不同，因此 Grafana 对 AWS“分叉 Cortex”或 Grafana Labs 维护的任何其他开源项目的担忧都变得毫无意义。威尔基是一名软件创作者，看起来是一名开源倡导者，他说，亚马逊或任何其他方越多地参与其开源项目，在其上建立商业服务，越好。

“开源项目是建立一个社区的一种方式，让一大群人使用我们的软件，因为我们试图在开源社区中增加真正的价值，”威尔基说。“这也给了我们一个草根期权动议，允许我们向少数非常大的公司销售。”

转移到米伊美是有道理的，但这对亚马逊管理的普罗米修斯意味着什么“仍然令人费解”，[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉新堆栈。“亚马逊肯定注意到了 Grafana 对 Cortex 的代码贡献在前几个月有所下降，所以他们肯定知道变化即将到来，因此有一些时间来准备，”Volk 说。“另一方面，亚马逊没有接手和维护开源项目的历史。因此，看看他们下一步如何确保他们管理的普罗米修斯服务的未来将会很有趣。”

在谈到背景时，AWS 代表表示，AWS 不仅计划继续提供基于 Cortex 的亚马逊管理的 Prometheus，还计划进一步开发和促进 Cortex 开源项目。AWS 还表示，它没有计划分叉 Cortex。这一回应结束了对亚马逊管理普罗米修斯未来方向的质疑和不确定性。

## 许可发言

AGPLv3 许可证适用于米伊美的使用，而不是 Cortex 的 Apache2 许可证，这可能会在 AWS 如何潜在地派生 Cortex 和/或开发亚马逊管理的 Prometheus 方面发挥作用(下文将详细介绍 Cortex 项目和许可含义)。

然而，米伊美是在 AGPLv3 许可下使用，而不是在 Cortex 的 Apache2 许可下使用，这一事实对用户来说可能不会有太大变化。事实上，Grafana、Tempo 和 Loki 也使用 AGPLv3 许可证。

“从根本上说，AGPL 许可证给我们的东西是，如果有人拿走我们的项目，修改它们，然后在互联网上提供它们或供下载，他们必须在 GPL 许可证下使他们的修改可用，”Wilkie 说。

因此，与 Cortex Apache 许可证相比，Grafana 没有为米伊美的使用增加更严格的许可证，以帮助维持其服务收入基础。“我们做出这种改变不是为了保护——我们做出这种改变是因为它为合作提供了一个更公平的竞争环境，我们认为这是建立开源项目和围绕它们建立成功社区的正确方式，”威尔基说。

## AWS 的和现在 Azure 的 Grafana 未来

与此同时，Grafana 与微软结成了新的联盟。在微软和 Grafana 宣布微软称之为“战略合作伙伴关系”的开发托管服务以在 2021 年 11 月在 Azure 云平台内原生运行 Grafana 之后，微软本月表示 Azure 托管 Grafana 可在预览版中使用。Grafana 和微软的代表向新的堆栈确认，Azure Managed Grafana 的普遍可用版本将于今年年底发布。

那么，这一切将 Grafana 与 AWS 的关系置于何处？

“我们是战略合作伙伴，将继续在亚马逊管理的 Grafana 上密切合作，并且已经看到合作势头越来越好。格拉法纳米伊美的宣布不会改变任何事情，亚马逊仍然可以使用和改进 Cortex，”格拉法纳实验室企业发展副总裁 Ash Mazhari 告诉新的堆栈，“亚马逊是一个积极的合作伙伴，我们定期合作，研究如何最好地服务于我们的客户，我们看到这种关系在未来将继续发展。”

2020 年 12 月，在 AWS 的年度用户大会 re:Invent 期间，Grafana 宣布“正式”升级到亚马逊管理的 Grafana。在该版本发布之前，组织可以在其 AWS 托管环境中运行 Grafana Enterprise 和 Grafana Cloud，Grafana、Loki 和 Cortex 的开源版本，以及 Prometheus。当时发生变化的是现在 Grafana Enterprise 和其他 Grafana 工具成为 AWS 直接提供给客户的工具。此举有助于解决 Grafana 用户可能面临的潜在操作和实施挑战。

在 re:Invent 期间还宣布了 Grafana 与 AWS 在亚马逊管理的普罗米修斯上的合作。

Grafana 似乎与微软采取了类似的策略，当 Azure 管理的 Grafana 普遍可用时，帮助 Azure 用户更直接地体验 Grafana。这一举动也表明，Grafana 正在寻求扩大其在主要云供应商产品中的影响力(目前还不知道 Grafana 实验室是否会在谷歌云服务中推出类似的产品)，而不是在结束对 Cortex 开源项目的维护后离开 AWS。

“Grafana 已经成长为不仅仅是亚马逊、Azure 或谷歌云的初级合作伙伴。他们这样做是为了保护他们对新米伊美项目的代码贡献，以免诱使任何人将他们代码的分叉版本商业化，”Volk 说。“在 Grafana 不必担心此举会对其与亚马逊的整体合作伙伴关系产生负面影响的情况下，这具有良好的商业意义。”

## Cortex 帮助

与此同时，Grafana 还将为 Cortex 用户转换到米伊美提供支持。然而，这并不意味着皮层已经死亡。只是 Grafana 不再支持 Cortex 的发展。本着开源的精神，威尔基告诉新栈:

“历史上，Grafana 实验室赞助了大部分关于 Cortex 的工作。虽然 Grafanistas 将不再被要求在 Cortex 上工作作为他们日常工作的一部分，但他们也欢迎在空闲时间做出贡献——就像其他任何人一样。Cortex 项目的未来取决于 Cortex 项目的维护者。我们坚信个人，而不是公司，是任何给定开源项目的成员。因此，欢迎 Grafanistas 继续作为 Cortex 或任何其他项目的维护者。如果维护者选择下台，那是他们自己的个人决定。”

格拉法纳也在寻求尽可能平稳地从大脑皮层转移。

“我们已经尽了最大努力为未来的成功建立 Cortex。威尔基说:“就在几个月前，所有的皮层维护人员都在格拉夫纳实验室工作。“我们一直在努力培养新的 Cortex 维护者。到今天为止，Cortex 已经有三个非 Grafana 实验室的维护者了。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>