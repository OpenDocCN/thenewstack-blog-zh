# 谷歌容器引擎现在说 Kubernetes 1.7

> 原文：<https://thenewstack.io/google-container-engine-now-speaks-kubernetes-1-7/>

谷歌正在宣传其将 6 月底发布的[Kubernetes 1.7](https://www.forbes.com/sites/janakirammsv/2017/06/30/kubernetes-1-7-debuts-with-enhanced-security-and-extensibility/#fca91ce519fc)快速整合到[谷歌容器引擎](https://cloud.google.com/container-engine/)中。考虑到谷歌是开源编排引擎的最初创造者，并且仍然是开源项目的主要贡献者之一，周转时间并不令人惊讶。

谷歌负责 Kubernetes 和 Container Engine 的集团产品经理 [Aparna Sinha](https://github.com/apsinha) 表示，主要的企业客户，如[易贝](https://www.nextplatform.com/2015/11/12/inside-ebays-shift-to-kubernetes-and-containers-atop-openstack/)、[纽约时报](https://open.blogs.nytimes.com/2017/01/12/continuous-deployment-to-google-cloud-platform-with-drone/)和[飞利浦](https://cloud.google.com/customers/philips/)正在推动 Kubernetes 和 Container Engine 更加成熟，并专注于企业级安全性、可扩展性、联网和混合联网功能。

它还宣布了工程工作的结果，以提供更好的容器引擎开发者体验。

她说，谷歌策划的[容器优化操作系统](https://cloud.google.com/container-optimized-os/) (COS)及其网站可靠性工程师团队持续监控和管理容器引擎集群，提供了高水平的基础安全性。此外，新功能增加了安全多租户功能，这对于有许多不同团队共享集群的组织来说非常重要。

“能够隔离这些团队非常重要，这样它们就不会重叠或相互攻击，”她说。

新特性包括:

*   Kubernetes[network policy API](https://kubernetes.io/docs/concepts/services-networking/network-policies/)，允许用户控制哪些 pod 可以相互通信。
*   节点授权者 beta 限制了节点表面的威胁等级。每个 kubelet 只能访问为该节点调度的对象，这有助于保护集群免受受损或不可信节点的影响。

网络策略 API 的网络隔离和节点授权器的节点间资源隔离与 1.6 版中引入的基于角色的访问控制(RBAC)提供的集群资源集中控制相结合，为多租户提供了增强的安全性。

许多使用 Container Engine 的大公司希望将他们的云和本地应用程序连接起来。她说，混合网络的新功能支持这一点。它们包括:

Google 正在响应 Kubernetes 社区对提高可扩展性的呼吁，推出了一些新功能，比如已经进入测试版的 [API 聚合](https://kubernetes.io/docs/concepts/api-extension/apiserver-aggregation/)

“用户喜欢 Kubernetes API——它设计得非常好。但是他们通常有自定义的 API 和其他解决方案，他们希望以与 Kubernetes API 相同的方式添加和管理这些解决方案。一些用户在 Kubernetes API 的基础上构建了一个 PaaS 解决方案，他们希望从他们的 PaaS 中引入额外的对象……API 聚合允许你这样做，而不必重新安装或重启你的软件，”她说。

[alpha 集群中提供的动态准入控制](https://kubernetes.io/docs/admin/extensible-admission-controllers/)，允许客户集成定制的业务逻辑和第三方解决方案。她称 [Istio](https://cloudplatform.googleblog.com/2017/05/istio-modern-approach-to-developing-and.html) 开源项目为微服务增加了网络、安全和监控功能，是动态访问控制解决方案类型的前沿范例。

[StatefulSet Updates](https://kubernetes.io/docs/tutorials/stateful-application/basic-stateful-set/#updating-statefulsets) ，一个新的测试版特性，允许使用滚动更新等各种策略自动更新 Kafka、Zookeeper 和 etcd 等有状态应用程序。

Kubernetes 和 Container Engine 的首席工程师[布莱安·葛兰特](https://github.com/bgrant0607)表示，机器学习工作负载对图形处理单元(GPU)的支持一直有很高的需求。GCE 现在支持 NVIDIA K80 GPUs 在 [alpha 集群](https://cloud.google.com/container-engine/docs/alpha-clusters)中进行实验，并将在未来支持其他 GPU。

他说，为了帮助提高开发人员的效率，GCE 增加了集群本身的[自动升级](https://cloud.google.com/container-engine/docs/node-auto-upgrade) beta 功能，这不会威胁应用程序本身的正常运行时间或有状态应用程序中的数据。它在节点层整合了 API [Pod 中断预算](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/)，允许用户控制应用程序的中断率。它可以在亚马逊 S3 这样的云原生数据商店以及 MySQL 这样的传统商店上运行。

另一个让开发人员不用担心基础设施的功能是测试版的[自动修复](https://cloud.google.com/container-engine/docs/node-auto-repair)，它可以监控不健康的节点并自动修复它们。Container Engine 还提供集群级和单元级的自动伸缩。

[容器引擎 UI](https://console.cloud.google.com/kubernetes) 使用户能够可视化他们的工作负载。格兰特说，它是为开发者的观点而设计的，而不仅仅是显示基础设施资源。

它显示诸如工作负载类型、运行状态、命名空间和群集、注释、标签、副本数量和状态等信息。所有视图都是跨集群的。

展望未来，Sinha 说，她希望在混合环境方面做进一步的工作。在接下来的几个版本中，我们将在自动缩放方面做更多的工作。在 pod 扩展方面，需要根据与应用程序相关的自定义指标(如连接数)进行扩展，并监控集群中的应用程序。

期待看到对 GPU 的更多支持，围绕机器学习工作负载的更多工具，以及与其他服务的更好集成。

“对于开发人员来说，他们不必管理基础设施是一件好事，但我们也希望以更简单、更易于使用的方式为他们提供所需的服务，”Sinha 说。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>