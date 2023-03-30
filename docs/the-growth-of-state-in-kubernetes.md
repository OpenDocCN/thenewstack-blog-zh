# 库伯内特斯州的发展

> 原文：<https://thenewstack.io/the-growth-of-state-in-kubernetes/>

[](https://www.linkedin.com/in/cheryljhung/)

 [谢丽尔·洪

谢丽尔是 Ondat 的顾问委员会成员，也是苹果公司的工程负责人。](https://www.linkedin.com/in/cheryljhung/) [](https://www.linkedin.com/in/cheryljhung/)

2017 年 1 月，我第一次与 Ondat(当时的 StorageOS)合作，当时我认为 Kubernetes 存储将在 18 个月内解决问题。事后看来，这有点乐观。五年过去了，我着手研究云原生存储问题的[框架](https://thenewstack.io/achieve-persistent-storage-kubernetes-production)(在奥斯汀的 [KubeCon 上展示)仍然非常受欢迎，因此许多组织仍然在努力解决如何在 Kubernetes 中提供持久性的问题。](https://www.oicheryl.com/2017/12/08/persistent-storage-with-kubernetes-in-production-kubecon-cloud-native-con-2017-austin/)

我最近担任了 Ondat 的顾问委员会成员。Ondat 吸引我的是这样一种愿景，即用户可以利用容器和 Kubernetes 为无状态应用程序提供的优势，并为他们的有状态工作负载实现所有这些优势。鉴于有状态应用程序在大多数业务解决方案中的核心作用，这些在可靠性、可伸缩性、自动化和更敏捷的开发方面的改进意义重大。对我来说，这曾经是，现在仍然是一个巨大的机会。

## 到有状态的 Kubernetes

Kube 和 containers 基于无状态工作负载的思想，所以运行任何有状态的东西都违背了一个基本的潜在假设。就像 Kubernetes 一样，我是从 Google 开始的，在 Google，持久存储是一个已经解决的问题。他们无需担心在云原生环境中运行存储。

但谷歌大多不使用传统的 SQL 存储——他们大多使用自己的分布式数据库和键值存储。相比之下，大多数运行有状态应用程序的公司将使用标准的关系数据库。为了考虑像 Kubernetes 这样用于有状态应用程序的新平台，这些用户需要运行 Postgres 或 MySQL 这样的流行数据库，并且具有大规模和高可用性。

在我最近担任 CNCF 生态系统副总裁期间，我每天都与 Kubernetes 终端用户交谈，很明显，持久存储对他们中的许多人来说仍然是一个问题。当组织使用关系数据库来支持在 Kubernetes 上运行的有状态应用程序时，很大一部分仍然依赖于托管数据库服务，如 Amazon 的 RDS，或者他们完全在 Kubernetes 之外运行数据库。

即使有了 CSI 驱动程序的生产[版本，用户也可能对在 Kubernetes 中部署关键应用程序犹豫不决。这些解决方案没有抓住真正的 Kubernetes——本地有状态开发的许多好处和潜力。用户没有有效地设计一种安全的方式让数据存在于短暂的节点和容器中，而是将存储拉回 Kubernetes 之外。这分离并重复了确保计算和数据恢复能力的任务。它给数据库和应用程序的性能带来了很大的限制。也许最重要的是，它限制了 Kubernetes 的能力，特别是调度程序，以有效地提供围绕工作负载效率和高可用性的核心计算功能。附着外部存储的节点变成了“宠物”而不是“牛”(向任何素食者道歉，但这仍然是最好的比喻)。](https://searchstorage.techtarget.com/answer/What-is-Kubernetes-CSI-and-how-is-it-being-used)

## FinOps

特别是对于托管数据库，采用安全简单的方法来交付有状态应用程序有着更大的意义。成本显然是最明显的。当我写下我的“[2021 年云原生的 10 个趋势和预测](https://www.oicheryl.com/2021/07/27/10-predictions-for-cloud-native-in-2021-fidelity-cloudcast/)”时，FinOps 的崛起是一个简单的选择。如果说有什么不同的话，那就是云成本管理的重要性已经超出了我的预期。

最基本的，FinOps 是关于管理和降低云成本的，这使得 RDS 等托管数据库服务成为一个明显的目标。尽管 FinOps 正在超越这一点发展成为一门手艺，但领先的 FinOps 从业者正越来越多地探索如何更有效地利用云原生环境来优化整体 IT 成本，其中存储成为关键要素之一。

组织需要保持对其存储的完全控制。在 Kubernetes 中安装一个新的数据库现在很简单，但是第 2 天的操作还不明白。持续的数据库和存储维护、升级、回滚等工作都很复杂。看似简单的架构决策可能会对成本、弹性和可伸缩性产生重大影响。

在许多情况下，云存储服务和托管数据库服务是一个合适的解决方案，但值得预先考虑对存储控制和锁定的权衡和影响。

## 期待应用程序的可移植性

我对 2021 年的另一个预测是跨云和云可移植性的成熟，这是我最近与 IBM 的莫·哈吉吉深入探讨的一个问题。应用程序的可移植性对于任何组织与云提供商进行有效谈判都是至关重要的，因此对于 FinOps 也是必不可少的。存储锁定，尤其是托管数据库服务，会严重影响任何组织在云之间移动应用程序的能力。虽然我交谈过的许多最终用户都渴望运行多云以获得弹性并使用特定于云的服务，但多云*存储*仍然是一个挑战。

您可以交付多云有状态应用程序。您可以提供在 Kubernetes 内安全驻留和运行的存储。业界迫切需要开发更好的工具，尤其是最佳实践，但这两种情况下的解决方案都是 Kubernetes-native 数据层，让您能够控制自己的存储。

*[注册 Ondat 技术预览](https://www.ondat.io/tech-preview-signup)了解 Ondat 如何帮助您扩展 Kubernetes 上的持久工作负载。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>