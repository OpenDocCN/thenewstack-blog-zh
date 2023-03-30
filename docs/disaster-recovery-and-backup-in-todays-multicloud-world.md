# 当今多云世界中的灾难恢复和备份

> 原文：<https://thenewstack.io/disaster-recovery-and-backup-in-todays-multicloud-world/>

[Portworx](https://portworx.com/) 赞助本帖。

[Portworx 首席技术官谈当今多云世界中灾难恢复和备份的复杂性](https://thenewstack.simplecast.com/episodes/portworx-cto-on-disaster-recovery-and-backup-complexities-in-todays-multi-cloud-world)

无论是在内部部署还是在云环境中，应用程序部署和维护的可用选项数量都意味着巨大的机会。但是，随着微服务、Kubernetes 无服务器平台和其他选项的加入，如何管理所涉及的巨大复杂性的问题显然出现了。除其他外，开发运维的一个关键问题是在这种情况下为备份和灾难恢复(DR)创建最佳实践和流程。

在我们最新的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中， [Portworx](https://portworx.com/) 的联合创始人兼首席技术官[苟饶](https://www.linkedin.com/in/gouthamrao)概述了相关的复杂性，以及新兴的灾难恢复和备份实践。

“人们仍处于学习模式。现在，人们已经部署了他们的应用程序，他们正在处理实际操作中的问题，而且不一定是问题，而是关于“我如何做到这一点？”的最佳实践”饶说。

Rao 说，灾难恢复不是一个新概念，但随着应用程序变得越来越复杂，并且本质上是分布式的，在云原生应用程序和 Kubernetes 的背景下，这是一个正在被重新审视的话题。

Rao 说，这种新的复杂性和对灾难恢复的额外挑战的第一个例子涉及应用程序堆栈如何不再是单片封装在一台机器中。“因此，就在这里，如果您的备份策略是备份一台机器，那么这种策略就行不通了。因此，这些应用程序本质上是分布式的、面向服务的，并且与运行在其他系统上的其他组件相互依赖，这一概念代表了复杂性的一个支柱。”

应用程序也可能在不同的云中运行。Rao 说，在这种情况下，应用程序的一部分可能需要访问云提供商提供的云服务的特定部分。例如，机器学习应用程序可能有一段应用程序需要访问公共云提供商的 GPU。

“整个应用程序不需要使用它。因此，你的应用程序使用基础设施的不同部分，”Rao 说。"这增加了复杂性的第二个支柱."

Rao 说，第三个“复杂性支柱”通常涉及“当人们构建云原生路径时做什么”,作为多个租户的基础设施。Rao 说:“换句话说，您不是为某个业务部门或某个特定用户留出一个特定的 Kubernetes 集群，而是为许多不同的用户托管许多不同的应用程序，这些用户可能有不同的灾难恢复实践或要求。

第四层也是最后一层复杂性涉及“自我服务的概念”，这“变得非常重要”，Rao 说。Rao 说:“作为应用程序所有者，您不希望依赖他人或在流程中使用此票证来触发数据恢复或应用程序连续性请求。“你希望自己能够做到这一点。”

Rao 说，在大多数情况下，这种情况下的用户不是试图在灾难期间恢复数据，而是“可能只是快速迭代应用程序开发，并且您希望回滚某些组件”。Rao 说:“因此，自助服务的概念正在成为现实，而当您想到传统的以机器为中心的灾难恢复时，情况并非如此。“因此，在我看来，这四件事开始具体化某些常见的请求，我看到客户向供应商询问生态系统如何处理这些问题。”

因此，针对灾难恢复和备份的新型服务模式不断涌现。平台运营商可能会说‘这里有一个 Kubernetes 平台和你的用户界面，以及你如何登录来启动你的应用程序——我将确保你的应用程序能够运行，并将管理基础设施，’”Rao 说。同样，还提供了备份和灾难恢复

与此同时，如今许多用户有多个 Kubernetes 集群在运行，例如用于连续异步灾难恢复目的。Rao 说:“如果一个集群出现故障，你可以切换到第二个集群。“这是一个很大的话题，我们最近就多云展开了很多讨论。”

### 在这个版本中:

[2:09:](https://thenewstack.simplecast.com/episodes/portworx-cto-on-disaster-recovery-and-backup-complexities-in-todays-multi-cloud-world?t=2:09) 您需要开始考虑哪些数据恢复问题，从人员的角度来看，您如何理解这些问题？
[5:46:](https://thenewstack.simplecast.com/episodes/portworx-cto-on-disaster-recovery-and-backup-complexities-in-todays-multi-cloud-world?t=5:46) 你是如何看到车队开始适应的？
[12:23:](https://thenewstack.simplecast.com/episodes/portworx-cto-on-disaster-recovery-and-backup-complexities-in-todays-multi-cloud-world?t=12:23) 数据安全、备份、恢复，以及 CSI 如何适应这个故事。
[17:33:](https://thenewstack.simplecast.com/episodes/portworx-cto-on-disaster-recovery-and-backup-complexities-in-todays-multi-cloud-world?t=17:33) 开源生态系统中出现了哪些工具，您看到的最初用例是什么？
[20:29:](https://thenewstack.simplecast.com/episodes/portworx-cto-on-disaster-recovery-and-backup-complexities-in-todays-multi-cloud-world?t=20:29) 必要语法是什么？
[25:20:](https://thenewstack.simplecast.com/episodes/portworx-cto-on-disaster-recovery-and-backup-complexities-in-todays-multi-cloud-world?t=25:20) 如果这些问题如此重要，不容忽视，你如何看待自己参与社区活动？

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>