# StackPointCloud 将 Kubernetes 带入数字海洋

> 原文：<https://thenewstack.io/stackpointcloud-brings-kubernetes-digitalocean/>

Kubernetes 托管服务提供商 StackPointCloud 正在为 Kubernetes 用户提供在 DigitalOcean 上运行容器编排引擎的机会。

该公司扩展了其完全管理的 Kubernetes 控制平面，以便能够识别 DigitalOcean 上的块存储卷。StackPointCloud 首席执行官[马特·鲍德温](https://twitter.com/baldwinmathew)表示:“DigitalOcean 的用户现在可以针对 DigitalOcean block storage 提出[Kubernetes]动态卷索赔和持久卷索赔。

实际上，这使得 DigitalOcean [与其他云提供商](https://thenewstack.io/amazon-web-services-joins-cloud-native-computing-foundation/)如亚马逊网络服务和谷歌云引擎一起成为云服务，可以支持 Kubernetes 的动态存储供应。

该服务可用于供应多主、高可用性 Kubernetes 集群。该公司声称，它为 Kubernetes 实例提供了一种“升级、节点自动伸缩、按节点池组织的方式，同时还允许开发人员快速构建和管理 CI/CD 管道，以更快地将代码发布到产品中”。

在这些情况下，用户将为给定的云提供商定义默认存储类别。然后，用户可以提交一个持久的卷声明，比如 10GB，StackPointCloud 将自动在选择的云提供商上提供这个卷。

人们之前已经可以在数字海洋上运行 StackPointCloud 了。Baldwin 解释说，这项新服务在 Kubernetes 内部提供了一个本地接口。以前，用户必须构建他们自己的覆盖文件系统，可能使用 [CephFS](http://ceph.com/ceph-storage/file-system/) 。“在用户方面，所有这些都是非常手动的，”鲍德温说。

数字海洋[去年推出了基于固态硬盘的块存储](https://thenewstack.io/digitalocean-launches-block-storage-service-storage-hungry-cloud-users/)。“这将使客户能够在我们的平台上部署全新类别的 Kubernetes 应用程序，并有可能将持久卷添加到部署中，”DigitalOcean 的工程经理约纳斯·贝吉乌斯在一份声明中说。“客户还将能够利用 StatefulSets，这将使我们离能够在 Kubernetes 上运行数据存储更近一步。”

StackPointCloud 的控制平面[被设计为](https://thenewstack.io/stackpointcloud-solidifies-pricing-managed-kubernetes-cloud-deployments/)允许组织在公共云上运行 Kubernetes 容器编排引擎。用户可以通过各种登录机制登录到控制台，比如使用他们的 Twitter、GitHub 或 Google Apps 帐户。登录后，他们会看到一个菜单，用于在 AWS、Google Compute Engine 和 Google Container Engine、Packet、DigitalOcean 或 Microsoft Azure 上部署基于 Kubernetes 的集群。

除了跨云部署，StackPointCloud 还提供生命周期管理服务，比如设置高可用集群(使用 [etcd](https://coreos.com/etcd) )、自动伸缩以及与 [HAProxy](http://www.haproxy.org/) 合作。用户可以管理 Kubernetes 或 etcd 的升级，或者让服务自动升级这个软件。他们可以添加额外的第三方资源，例如 Sysdig 或 [Linkerd](https://linkerd.io/) 的监控功能。

StackPointCloud 开发人员与 DigitalOcean 工程师合作，为云服务构建了一个原生的 Kubernetes 接口。该公司计划将代码提交给上游 [Kubernetes](https://github.com/kubernetes/kubernetes) 项目本身，该项目由[云原生计算基金会](https://www.cncf.io/)管理。

云本地计算基金会和数字海洋是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>