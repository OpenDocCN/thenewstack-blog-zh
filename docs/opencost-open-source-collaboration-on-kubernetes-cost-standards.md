# OpenCost:关于 Kubernetes 成本标准的开源合作

> 原文：<https://thenewstack.io/opencost-open-source-collaboration-on-kubernetes-cost-standards/>

Kubernetes 成本管理公司 Kubecost 与云、供应商和用户合作伙伴合作，向[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)提交了一个管理 Kubernetes 成本的开源项目。叫做 [OpenCost](https://github.com/kubecost/opencost) ，它结合了[规范](https://github.com/kubecost/opencost/blob/develop/spec)以及这些详细需求的 Golang 实现。

“开始与越来越多的合作伙伴交谈，但在如何衡量 Kubernetes 的成本方面没有达成一致，”Stackwatch 的联合创始人兼首席执行官[韦伯·布朗](https://www.linkedin.com/in/webbbrown/)在接受采访时说，stack watch 创建了 [Kubecost](https://www.kubecost.com/) 。

“当你搬到 Kubernetes 时，一个大问题是，成本本质上是一个黑箱。对于单个应用程序或单个团队来说，您不再需要单独的虚拟机或机器。在 Kubernetes 的土地上，每个人都在同一个集群或一小组集群中运行。这真的可以让您非常准确地理清这些成本，显示按存储容量使用计费，或者以非常高的准确度提供整个组织的成本可见性。”

它在该项目的合作伙伴包括[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)、Armory、D2iQ、谷歌、Adobe、SUSE、Mindcurv 和 New Relic。他们一直致力于为 Kubernetes 在任何环境下的成本监控创建一个标准。

![](img/84340b9068afbd537b487ad9d2b786fe.png)

在宣布提交给 CNCF 时，他说:“从一开始，我们的目标就是让使用 Kubernetes 的团队能够使用单一模型来衡量和管理他们所有环境的成本。我们不断从用户和我们的合作伙伴那里听到，跨云平台、Kubernetes 发行版和团队的标准化是非常需要的。为了最有效地推动一个标准，我们认为重要的是 OpenCost 不是由任何单一实体推动的——并且该项目在更广泛的 Kubernetes 社区中继续发展和繁荣。我们相信 CNCF 是帮助实现这一目标的最佳组织。”

CNCF 尚未宣布是否接受该项目。

该项目基于 Kubecost 引擎，该引擎是在 Apache 2.0 许可下开源的。它包括:

*   Kubernetes 服务、部署、名称空间、标签、statefulset、daemonset、pod 和容器的实时成本分配
*   通过与 AWS、Azure 和 GCP 计费 API 的集成实现动态资产定价
*   支持具有自定义价格表的内部 k8s 群集
*   分配集群内资源，如 CPU、GPU、内存和持久卷。
*   AWS 和 GCP 集群外资源的分配，如 RDS 实例和带键的 S3 存储桶(可选)
*   将定价数据导出到 Prometheus 的能力

OpenCost 旨在标准化成本跟踪、分配、方法和测量，以帮助使用 Kubernetes 的团队更容易地了解他们的基础设施成本。OpenCost 将为各种集群内资源类型(包括计算、存储、网络和负载平衡器)提供指导，并将通过提供标准成本模型、最佳实践和指导来解决这一问题。使用 OpenCost，开发团队可以就如何分配工作负载成本达成一致，并确保他们以标准、统一的方式进行分配。该标准使团队能够在其组织和所有基础设施环境中使用单一的成本分配模型。该公司报告称，其目标也是在云平台、Kubernetes 发行版和使用 Kubernetes 的团队之间建立标准化。

“我们从最终用户和客户那里不断听到的一件事是，他们对 Kubernetes 的好处感到兴奋。他们想收养 Kubernetes。但是这种成本可见性的缺乏表现为这样做的摩擦。所以…我们正在为团队大规模采用 Kubernetes 消除一些障碍。所以我认为，最终，通过提供这种更好的成本分配引擎，它有望帮助团队在成熟时采用越来越多的 Kubernetes，”Stackwatch 业务发展负责人 Alex thi len 说。

11 月，Stackwatch 宣布扩展 Kubecost，为用户提供单一视图，查看 Kubernetes 和 T2 在云资源上的“集群外”支出。但这不是唯一一家解决 Kubernetes 财务问题的公司。其他还有[铸艾](https://thenewstack.io/5-expensive-kubernetes-cost-traps-and-how-to-deal-with-them/)、[出铁](https://www.finout.io/)和[挽具](https://thenewstack.io/harness-cost-transparency-could-slash-runaway-cloud-bills/)。

来自 CNCF 和 [FinOps 基金会](https://www.finops.org/introduction/what-is-finops/)的[报告](https://www.cncf.io/wp-content/uploads/2021/06/FINOPS_Kubernetes_Report.pdf)将[缺乏成本监控归因于](https://thenewstack.io/cost-overruns-rank-low-on-list-of-challenges-for-kubernetes-and-containers/)超支。据报道，只有 38%的受访者可以在 10%的误差范围内预测他们的每月云账单。然而，在一项典型的调查中，Kubernetes 用户报告的挑战列表中，成本超支排名很低。(缺乏内部技能/人力有限被列为最大挑战。)

“我们非常希望有其他人加入我们，”布朗说。“我们想要更多的捐款。我们需要更多的发布合作伙伴，包括最终用户和供应商。因此，这份声明的一部分是让 OpenCost 计划走向世界，征求反馈，并邀请其他人加入我们的行列。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>