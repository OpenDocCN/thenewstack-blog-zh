# Kubernetes 1.3 支持有状态应用、联合集群

> 原文：<https://thenewstack.io/kubernetes-1-3-supports-stateful-applications-federated-clusters/>

谷歌继续完善其开源容器编排引擎，以应对越来越大的工作负载。周三发布的 1.3 版本包括一些新功能，如跨不同网络(包括云和内部部署)管理 pod 的“联合”能力，以及对有状态应用程序的支持。

“我们生活在一个多云的现实中，企业在内部云和公共云中部署应用程序和数据。企业希望能够灵活应对不断变化的客户和业务环境，”[负责谷歌容器引擎和 Kubernetes 的谷歌云平台高级产品经理大卫·阿龙奇克](https://github.com/aronchick)在一封电子邮件中说。“通过提供集群联合服务，Kubernetes 现在迈出了为企业提供真正的可移植性和灵活性的第一步。”

Kubernetes 1.3 现在可以在 GitHub 上作为[下载](http://get.k8s.io/)或[代码](https://github.com/kubernetes/kubernetes)获得。

## 联合服务

跨集群联合服务允许服务跨越多个集群，甚至远程集群。这对于提高服务可靠性，甚至灾难恢复操作都有很大的帮助。

联合功能将允许组织在不同的可用性区域设置多个集群，从而即使在区域或数据中心停机时也能保持运行。

“只需一个命令，他们就可以将每个集群加入一个联合 API，允许用户同时跨多个集群部署服务，”Aronchick 解释道。部署新服务时，每个群集都可以创建适合其环境的自己的负载平衡器，从而进一步简化管理

该功能的一部分是跨集群服务发现，允许容器“一致地解析服务，不管它们是部分还是完全在其他集群中运行，”根据谷歌博客帖子的详细描述。

## 终于有状态应用了

Kubernetes 1.3 也是第一个正确支持有状态应用程序的版本，比如那些使用数据库或键值存储的应用程序。支持有状态工作负载是编排软件的一个重要举措，因为当今大多数工作负载都倾向于以某种形式涉及状态。

“每个使用状态存储的应用程序都必须以一种超越单个资源生命周期的方式存储数据，无论是容器、虚拟机还是持久磁盘，以避免出现单点故障，”Aronchick 说。

迄今为止，已经有大量的 Kubernetes 插件将无状态服务连接到有状态应用程序，如 MySQL、PostgreSQL 和 Zookeeper。但是 Kubernetes 开发团队想要实现一个更加集成的方法。

有状态支持是通过一个名为 PetSet 的新对象实现的。例如，它支持在重启后持续存在的永久主机名，这样就不需要每次重启都获取新的主机名，然后用新地址更新整个系统。

PetSet 还可以识别初始化容器。“初始化容器在启动时运行一次，允许诸如领导者选举、复制数据或与组中的其他服务器共享身份等操作，”Aronchick 解释道。作为正常启动服务的一部分，初始化容器可以准备数据或从以前的重新启动中恢复状态。

此外，PetSet 可以在磁盘上为未使用的容器提供永久空间。

## 盒子里还有什么？

Kubernetes 1.3 的其他显著特性包括:

*   **增加规模和自动化**:根据谷歌的说法，现在更容易自动扩大和缩小集群，同时将每个集群的最大节点数量增加一倍。该软件现在可以跟踪每个集群多达 2，000 个节点，是旧限制的两倍。
*   Kubernetes 学习工具 MiniKube:一个在笔记本电脑上启动集群的命令行工具，具有与 Kubernetes 完全兼容的 API。适合本地测试。
*   **更新的用户界面仪表板**:仪表板现在显示集群的大部分活动，允许用户创建、编辑和控制所有工作负载资源。

该公司还宣布了对其托管的、完全托管的 Kubernetes 版本[谷歌容器引擎](https://cloud.google.com/container-engine/) (GKE)的一些升级。最值得注意的是，该公司已经将 GKE [谷歌云身份&访问管理](https://cloud.google.com/iam/) (IAM)角色整合进来，允许管理访问。

“集中式身份和访问管理是安全策略的基石之一，”Aronchick 说。通过提供一种集中的方式来管理角色、审核用户和限制行为，组织可以限制其总外围应用并增强其安全保护

GKE 现在可以识别固态硬盘，并能够通过一个名为[节点池](https://cloudplatform.googleblog.com/2016/05/introducing-Google-Container-Engine-GKE-node-pools.html)的功能跨多个区域运行不同类型的机器，这开辟了一种针对特定工作负载定制集群的方式。

另外值得注意的是，除了 Docker 的容器格式，Kubernetes 1.3 现在提供了对 CoreOS 的 rkt 容器格式的完全支持。产品负责人[党微](https://www.linkedin.com/in/weiliendang)在一封电子邮件中说:“社区现在可以根据最适合某个架构、站点或部署的特定需求，灵活地选择 Kubernetes 中支持的运行时。

CoreOS 提供了一个名为“构造”的商业版 Kubernetes，该公司在 Kubernetes 上做了很多工作，特别是在为 Kubernetes APIs 添加认证和授权方面，这些 API 允许围绕管理对单个资源的访问进行更细粒度的控制。

为了跟踪容器，Kubernetes 1.3 还使用了最新版本的 CoreOS-develop [etcd](https://thenewstack.io/coreos-updates-etcd-large-scale-container-coordination/) ，版本 3 提供了生产就绪的扩展增强，包括一组分布式协调原语，如分布式锁、选举和软件事务内存。

[**CoreOS**](https://coreos.com/) 是新栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>