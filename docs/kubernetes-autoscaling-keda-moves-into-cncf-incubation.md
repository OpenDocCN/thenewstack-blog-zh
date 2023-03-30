# kubernetes-自动缩放 KEDA 进入 CNCF 孵化

> 原文：<https://thenewstack.io/kubernetes-autoscaling-keda-moves-into-cncf-incubation/>

[KEDA](https://keda.sh/) ，Kubernetes 事件驱动的 Autoscaler 项目，本周已经从[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)的沙盒层继续前进，加入了其他 21 个正在孵化的项目，如 Argo、Falco、gRPC 和 Rook。

KEDA [最初由微软和红帽于 2019 年创建，于 2020 年 3 月加入 CNCF](https://github.com/cncf/toc/pull/383) ，此后见证了 KEDA 2.0 的[发布，并被](https://thenewstack.io/microsoft-keda-2-0-scales-up-event-driven-programming-on-kubernetes/)[阿里巴巴](https://www.cncf.io/blog/2021/03/30/why-alibaba-cloud-uses-keda-for-application-autoscaling/)、[卡斯泰](https://keda.sh/blog/2021-08-04-keda-cast-ai/)、毕马威(KPMG)、融水(Meltwater)、微软[和其他](https://keda.sh/community/#users)等公司采用。

KEDA 由两个主要组件组成，一个是 KEDA 代理，它激活和停用 Kubernetes 部署，以便从零开始扩展，另一个是度量服务器，它向横向扩展的水平 Pod Autoscaler 公开事件数据。KEDA 可以添加到任何 Kubernetes 集群中，根据由[缩放器](https://keda.sh/docs/2.4/scalers/)提供的数据提供事件驱动的自动缩放，该缩放器充当 KEDA 与各种数据库、消息传递系统、遥测系统、CI/CD 等之间的集成。

在沙盒中的时间里，KEDA 将可用的缩放器的数量从 15 个增加到 37 个，KEDA 维护者 Tom Kerkhove 说更多的正在路上。目前，应用程序可以根据基本的东西进行扩展，例如 CPU、内存和 T21，也可以根据 Apache Kafka 主题提供的信息进行扩展，或者根据 Prometheus metrics 提供的信息进行扩展。

除了增加缩放器的数量，KEDA 还花时间在 CNCF 沙盒中重新设计其安全方法，以分离身份验证，添加 TriggerAuthentication 和 ClusterTriggerAuthentication。

Kerkhove 说:“例如，如果您想在多个应用程序中重复使用该身份，如果您想将开发和运营分开，或者如果您想使用 Hashicorp 保险库中的机密，通过使用 TriggerAuthentication，您可以做到这一点。

类似地，ClusterTriggerAuthentication 意味着“一个人可以定义如何通过 Microsoft Azure 进行身份验证，然后群集中的每个人都可以使用该身份，”Kerkhove 解释道。

在转移到 CNCF 的孵化层时，Kerkhove 表示，尽职调查过程帮助该项目解决了一些治理问题。例如，现在来自同一家公司的维护者分享他们的投票，这有助于防止任何一家公司拥有多数席位。

展望未来，KEDA 有许多计划，包括可能采用 Kubernetes 项目本身，但 Kerkhove 说这仍然是遥远的事。

“最终我们希望做到这一点，甚至更多，但改变 Kubernetes 很难，因为它是一种可持续的产品。你需要确保，如果你改变它，你不会打破任何人，”克霍夫说。

Kerkhove 解释说，阻碍 KEDA 实现最终目标的一个因素是，KEDA 只能在 Kubernetes 上作为单个实例运行，这意味着它不能高度可用。这是因为 Kubernetes 的局限性，Kerkhove 说“我们试图做的是看看 Kubernetes 的局限性，看看我们能否解决它，这样 Kubernetes 和 KEDA 现在都从中受益。”目前，该项目将继续自己迭代，同时考虑对项目的各个部分做出上游贡献。

Kerkhove 说，其他潜在的计划包括分离出 CNCF 项目的一部分[服务网格接口(SMI)](https://smi-spec.io/) 规范，并将其扩展到不仅仅用于服务网格。

Kerkhove 说:“我们正在尝试在社区中引入一种新的流量标准，以便 KEDA 可以依赖一种规范，基本上为所有客户群和所有场景提供服务。”。“我们希望将流量指标 API 从 SMI 规范中分离出来，并创建一个流量指标规范。”

Kerkhove 说，最后一个近期目标是进行预测性自动缩放。

“还没有开始，因为我们最近才提出计划，但这肯定是我们希望作为下一个主要功能来做的事情，”他说。“这又回到了使用数据的成本效益，并通过这样做来拯救环境。”

在拯救环境方面，Kerkhove 注意到在即将于 10 月举行的 [KubeCon+CloudNativeCon 北美 2021](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/) 上的一个兴趣小组:“[Kubernetes 中事件驱动的自动缩放如何应对气候变化](https://kccncna2021.sched.com/event/lV4B)”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>