# 使用多可用性区域 Kubernetes 进行灾难恢复

> 原文：<https://thenewstack.io/use-multi-availability-zone-kubernetes-for-disaster-recovery/>

[](https://uk.linkedin.com/in/vnicolas)

[Nicolas ver mande](https://uk.linkedin.com/in/vnicolas)

[Nicolas 是 Ondat 的首席开发顾问。他是一名经验丰富的实践技术专家、传道者和产品负责人，在过去的 17 年里，他一直在云原生技术、开源软件、虚拟化和数据中心网络等领域工作。他热衷于为用户提供支持，开发解决现实生活问题的酷技术，你会经常看到他在全球科技会议和在线活动上发表演讲。](https://uk.linkedin.com/in/vnicolas)

[](https://uk.linkedin.com/in/vnicolas)[](https://uk.linkedin.com/in/vnicolas)

停机和性能下降是不可避免的。操作员会犯错误；新协议引入错误，自然灾害损坏设备等等。

这就是为什么大多数平台经理选择将其应用程序的基础设施分布在多个可用性区域(AZs ),而不是相信亚马逊设计防飓风数据中心的能力。

AZ 宕机并不常见，但[确实会发生](https://awsmaniac.com/aws-outages/)，性能下降甚至更常见。而且像飓风引起的灾难性停机是可能的，所以负责任的平台管理者围绕故障来设计他们的基础设施。

这是一种良好的本能，应该受到称赞。但是很少有平台经理考虑多 AZ Kubernetes 部署可能带来的新的设计挑战。让我们深入探讨一下多 AZ 生产环境带来的新因素。

## 我不能把我的基础设施分布在 AZs 上吗？

多 AZ Kubernetes 服务可能需要更多的跑腿工作，而不仅仅是简单地声明您希望您的节点跨 AZs 分布。虽然从技术上讲，您可以简单地跨多个 az 部署副本节点，但是大多数应用程序都需要额外的配置。

具体来说，*无状态应用程序*将在多个 az 上运行良好。如果一个 AZ 关闭，Kubernetes 将在下一个 AZ 重新安排您的应用程序。过渡期间不会保留任何有状态的工作负载，因此最终用户不会注意到任何不同。

然而，一个*有状态的应用*不会仅仅在多个 az 上工作。原因如下。

## AZs 中的状态

假设您已经跨多个 az 启动了一个应用程序，以获得灾难可恢复性，但是您没有考虑它的有状态工作负载。

首先，您的应用程序不会长时间正常工作，因为它跨容器运行有状态的工作负载，这在运行[有状态应用程序](https://www.ondat.io/blog/how-to-solve-kubernetes-persistent-storage-challenges)时不是很健壮。

假设有一个需求高峰或其他类型的故障，迫使 Kubernetes 关闭一个容器。当 Kubernetes 的调度程序重启你的有状态应用程序时，它只有在卷最初所在的 AZ 中重启时才会运行。如果在其他地方重新启动，它将无法再访问该卷。因此，平台管理员必须为具有附加卷的应用程序创建和维护关联性规则，以确保它们仅在与其卷相关联的 AZ 中重启。

但是让我们假设您已经建立了一个解决这个问题的方法，可能是通过利用一个合适的不受 AZ 边界约束的[容器存储接口](https://www.ondat.io/blog/storage-for-kubernetes) (CSI)提供者。如果灾难恢复是一个目标，那么您会希望确保您的解决方案能够让您创建持久的卷副本。这样，如果一个容器出现故障，您的副本可以立即接手，几乎不停机。

但是现在，您面临另一个挑战:确保您的副本在 AZs 中均匀分布。例如，您的主卷及其副本可能都位于同一个 AZ 中，这显然会在 AZ 宕机或服务中断时影响您的灾难可恢复性。

此外，您需要找到一种方法来随着时间的推移改变您的副本的托管位置。如果您决定添加另一个 AZ 或更改副本的布局，会发生什么情况？Kubernetes 和您的云服务提供商的基础设施不会自动为您做到这一点。

为了解决这个问题，如果你主要使用 AWS 提供云服务，你可以用 Lambda 编写一些自定义的东西。但是还有其他的东西需要你去维护，当然，这在不同的云服务提供商之间是行不通的。

## 解决方案:Kubernetes 的拓扑键

幸运的是，Kubernetes 提供了一个功能，我们可以用它来构建一个解决有状态多 AZ Kubernetes 部署问题的解决方案，称为拓扑键。这使得 Kubernetes 服务能够基于集群的节点拓扑来路由流量。

因此，使用拓扑键的一种方法是让 Kubernetes 用它所在的 AZ 标记每个节点。有了这些信息，CSI 解决方案就可以分发副本节点，使它们均匀地分布在各个 AZs 上，从而创建一个强大的灾难恢复功能，这是 Kubernetes 的功能集中所没有的。

## 一举两得

上面的方法正是 Ondat 所采取的。使用 Kubernetes 的拓扑密钥，Ondat 在一个称为[拓扑感知放置](https://docs.ondat.io/docs/reference/tap/)的过程中跨 AZs 分布副本节点。

Ondat 还确保您的有状态工作负载在 AZ、集群、节点或容器关闭时持续存在。作为一个[存储协调器](https://www.ondat.io/blog/how-to-solve-kubernetes-persistent-storage-challenges)，Ondat 将您的单个节点的存储汇集在一起，并作为一个中间的 Kube-native 分布式引擎，从而将您的前端持久卷从底层平台拓扑中分离和抽象出来。

如果你对 Ondat 是如何工作的感到好奇，你可以[在这里](https://www.ondat.io/platform/how-it-works)了解更多。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>