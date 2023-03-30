# 使用 Velero 备份、恢复和迁移 Kubernetes

> 原文：<https://thenewstack.io/back-up-restore-and-migrate-kubernetes-with-velero/>

VMware 的 [Velero](https://github.com/vmware-tanzu/velero) 是 [Tanzu cloud 原生产品组合](/vmware-bridges-kubernetes-and-vsphere-with-launch-of-pacific-beta/)的一部分，是一个开源项目，为 Kubernetes 提供备份、恢复和迁移功能。Velero 最初由 Heptio 开发，名为 Ark，由[戴尔的 PowerProtect](https://www.dellemc.com/en-us/data-protection/powerprotect-software.htm) 提供支持，允许 PowerProtect 用户备份他们的 Kubernetes 集群。

在 kube con+CloudNativeCon North America 2019 上录制的这个 [The New Stack Makers](/podcasts/makers) 播客采访中，我们与 Velero 的维护者和 VMware 技术人员成员 [Carlisia Campos](https://twitter.com/carlisia) 讨论了 Velero；[Tom spoon more](https://www.linkedin.com/in/tspoone/)，VMware 的云原生应用主管；以及戴尔产品管理总监 Efri Nattel-Shay。

[Kubernetes 备份、恢复和迁移同](https://thenewstack.simplecast.com/episodes/kubernetes-back-up-restore-and-migration-with-velero)

Velero 是一个命令行工具，它可以备份集群并在丢失时恢复集群，将集群资源迁移到其他集群，并将生产集群复制到开发和测试集群。它由运行在群集上的服务器和本地运行的命令行客户端组成。最近一篇关于 Velero 的帖子说得很好:

*“[Velero]使用您的云提供商的块存储快照功能拍摄您的群集的持久卷的快照，然后可以将您的群集的对象和持久卷恢复到以前的状态。”*

这项技术是 Go 内置的。Velero 有一个与 Kubernetes API 集成的 Go 客户端 SDK，使用插件提供跨多个云环境同步的功能。

“我们有一个同步系统，”坎波斯说。“一旦创建了备份，它就会持续同步。因此，无论何时您想要恢复，您的备份都是最新的。”

Velero 社区在 GitHub 上有大约 3300 颗星星，部分原因是能够提供即时备份，增加了一定程度的安全性和恢复 Kubernetes 集群的能力。

## **Velero 使用案例**

通过其插件功能，Velero 是备份 Kubernetes 环境的基础技术，无论是在云中还是在内部。“顾客不想被锁在里面，”斯普纳莫尔说。“他们使用 Velero 从一个云提供商迁移到另一个云提供商。”Velero 的可扩展性允许 Power 平台使用可以在 AWS、Google、Digital Ocean 和 Portworx 中工作的插件。

Velero 适用于灾难恢复用例，以及在集群上执行系统操作之前拍摄应用程序状态的快照。Velero 不仅备份 pod 和集群，还备份永久卷中的数据。可以有选择地进行备份:例如，可以通过名称空间和/或标签来备份大型集群。PowerProtect 软件使用 Velero 并将其放入单个堆栈中。VMware 的 Tanzu Mission Control 用于管理整个集群。它集成了跨 Tanzu 的 Velero，用于 Kubernetes 集群的备份、恢复和迁移。它支持数据保护，并利用 Velero 来备份 K8s 资源。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>