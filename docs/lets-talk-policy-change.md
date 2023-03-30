# 充分利用 Kubernetes 的新网络策略 API

> 原文：<https://thenewstack.io/lets-talk-policy-change/>

这是一系列论文中的第一篇，来自即将到来的

[KubeCon](http://events.linuxfoundation.org/events/kubecon)

和

[CloudNativeCon](http://sched.co/8K3m)

会议将于 11 月 8 日至 9 日在西雅图举行。

[](http://www.tigera.io)

 [安迪·兰德尔

安迪·兰德尔是 Tigera 的首席执行官，该公司正在通过其旗舰开源项目 Calico 保护云网络。Andy 是云原生技术的热情倡导者，作为云原生计算基金会营销委员会的成员，他积极推动这项技术。安迪住在加州伯克利，但作为一名(合法)移民，他无法在即将到来的选举中投票。](http://www.tigera.io) [](http://www.tigera.io)

虽然美国选举季节将世界的大部分注意力集中在除了实质性的政策讨论之外的任何事情上，但 Kubernetes 网络社区有其他想法。早在 7 月份， [Kubernetes 1.3](https://thenewstack.io/kubernetes-1-3-supports-stateful-applications-federated-clusters/) 发布了对网络策略的支持，使其成为第一个内置这种功能的容器编排器。

目前，在测试阶段， [Kubernetes 网络策略 API](http://kubernetes.io/docs/user-guide/networkpolicies/) 让开发人员能够定义规则，以确定哪些 pod(Kubernetes 术语，指由一个或多个容器组成的工作负载)可以连接到哪些其他 pod。把它想象成每个微服务周围的动态防火墙(但我们不会让墨西哥为此买单)。

您可能会认为，由于几个相互竞争的供应商都参与了 API 的定义，这项工作会因为政治而陷入困境。然而，与 DC 的 Washington 不同，networking special interest group 是一个合作的典范，专注于技术优势和明确的最终用户使用案例。事实上，参与该规范的一些供应商将在即将到来的 CloudNativeCon 上参加一个[小组——所以可以把这看作是对可能在那里讨论的内容的一次窥探。](http://sched.co/8K3m)

## 为什么是政策？

许多人遇到的第一个用例是将网络划分为“层”(通常为三层)，例如，能够指定后端数据库层只能从应用层 pods 访问，而不能直接从前端层访问。

然而，这仅仅触及了网络策略 API 的表面。随着开发人员采用云原生应用程序架构，它的全部功能开始发挥作用，在云原生应用程序架构中，数十或数百个[微服务](/category/microservices/)以一种不完全映射到传统“三层”模型的方式相互通信。

在这种情况下，连接矩阵要复杂得多，并且随着 pod 的创建和销毁而动态变化。网络策略为开发人员提供了一种描述这些更复杂的关系的方式，使用的语言对他们来说是自然的，但是映射到强大的基础设施层实施。

## 网络政策被解构

网络策略 API 看似简单，因为它利用了现有的核心 Kubernetes 概念，如[标签](https://thenewstack.io/all-about-microbadger-com/)和选择器。然而，结果是一个强大的、声明性的 API:开发人员声明她的意图，底层系统的工作是解决如何将其转换成实现预期结果的网络原语。

Kubernetes 中的标签是分配给 pod 的任意键/值对。例如，开发人员可以指定“role: db”来表示 pod 的功能，或者指定“location: us-west”来表示它位于特定的地理位置。在大多数情况下(例如，通过复制控制器识别的 pod ),这样的标签将已经存在，因此可以容易地被网络策略使用。

选择器是组合标签的表达式，用于定义集群中所有窗格的子集。它们是描述库伯内特斯豆荚群的基本机制。例如，匹配“role: db”和“location: us-west”会标识 us-west 位置中的所有数据库窗格。

网络策略定义包括一个 pod 选择器和适用于符合选择器标准的所有 pod 的规则。这些规则(目前仅限于入口，即什么外部资源可以建立入站连接)可以引用标签或特定 IP 地址范围，还可以将通信限制到特定端口。

例如，以下策略规定，所有数据库单元都可以在端口 6379 上接受来自任何具有“前端”角色的单元的入站 TCP 连接:

```
apiVersion:  extensions/v1beta1
  kind:  NetworkPolicy
  metadata:
 name:  test-network-policy
  spec:
 podSelector:
 matchLabels:
   role:  db
 ingress:
   -from:
      -podSelector:
       matchLabels:
        role:  frontend
   ports:
      -protocol:  tcp
      port:  6379

```

为了理解这个 API 的强大功能，考虑一个包含许多数据库单元和许多前端单元的大型集群。如果应用了这个策略，那么每当开发人员创建一个标签为“role: frontend”的新 pod 时，所有的数据库 pod 都会立即允许从它进行访问。部署前端 pod 的开发人员不必考虑防火墙规则，策略会自动应用它们。当然，这也适用于由于[自动缩放](http://blog.kubernetes.io/2016/07/autoscaling-in-kubernetes.html)而自动创建的 pod。

此外，如果从 pod 中删除了“role:”标签，对数据库 pod 的访问将立即“自动”删除。如果更新了策略，应用于集群中所有数据库单元的防火墙规则也会相应地更新。

## 网络政策与 CNI 插件:有什么区别？

如果您跟随 Kubernetes 文档，您会看到这个有点令人担忧的免责声明:

"除非您选择的网络解决方案支持网络策略，否则将此发布到 API 服务器不会有任何效果。"

这是怎么回事？嗯，作为一个开放系统，Kubernetes 的许多关键组件都支持可插拔性。特别是，由于有了[集装箱网络接口](https://github.com/containernetworking/cni) (CNI)，联网有了几种不同的选择。

有点令人困惑的是，网络政策不是 CNI 标准的一部分。因此，您需要确保您用于网络策略的任何实现也将与您选择的网络解决方案一起工作。

在某些情况下，您必须对网络和网络策略使用同一个控制器。其他的可以组合起来——例如，您可以只部署带有许多不同网络插件的 [Project Calico](https://www.projectcalico.org/) 的网络策略组件，包括法兰绒。甚至有一个名为 [Canal](https://github.com/tigera/canal) 的项目，致力于使这种特殊的组合更容易部署。

## 网络策略:云原生安全图景的一部分

关于向云原生应用架构演进的安全含义，已经有很多讨论。Kubernetes 的网络策略 API 及其实现(如 Project Calico)将是解决这些问题并使企业满足严格合规要求的关键要素。

[Tigera](https://www.tigera.io/) 是[kube con](http://events.linuxfoundation.org/events/kubecon)(2016 年 11 月 8 日至 9 日)的白金赞助商。我们期待在那里见到您，与您更多地交流您的社交经验和关注点。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>