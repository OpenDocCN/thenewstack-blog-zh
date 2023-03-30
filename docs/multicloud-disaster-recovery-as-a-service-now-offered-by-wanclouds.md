# Wanclouds 现在提供多云灾难恢复即服务

> 原文：<https://thenewstack.io/multicloud-disaster-recovery-as-a-service-now-offered-by-wanclouds/>

制定灾难恢复计划的公司经常不得不在两个令人不快的选项之间做出选择。

他们要么建立整个基础架构的副本并保持同步，随时准备切换到另一个基础架构；要么创建数据备份，但如果发生灾难，则必须从头开始重建整个环境。

在第一种选择中，维护两套或更多全套基础架构的成本可能会高得令人望而却步。在第二种选择中，从重大灾难中恢复可能需要数周时间，同时需要重新创建所有网络和配置。

之前以云到云迁移服务闻名的 Wanclouds 提供了一种介于这两种选择之间的选择。

本周，[公司在](https://blog.wanclouds.net/Wanclouds-LaunchesMulti-CloudDisaster-Recovery-As-A0Service-A-tKubeCon)[kube con+CloudNativeCon EU 2021](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)正式推出了其云计算灾难恢复即服务。

该服务目前支持 IBM 云 IKS 和 OpenShift，谷歌云 VPCs 和 GKE，[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) ' VPCs 和 EKS，以及本地或云中的 Linux 集群。对 Azure 的支持即将到来。

Wanclouds 为备份系统的初始设置及其持续管理提供技术基础设施和实际支持。

## 云迁移的挑战

Wanclouds 成立于 2014 年，主要专注于迁移即服务。

在云之间移动系统的问题是，即使应用程序是容器化的，每个云供应商都有自己的网络、存储、安全、管理和基础设施管理的其他方面的方法。

[Wanclouds](https://www.wanclouds.net/) 的创始人兼首席执行官 [Faiz Khan](https://www.linkedin.com/in/faiz-khan-1a82302/) 表示:“我们最大的优势之一是我们正在创建基础设施抽象快照。

Wanclouds 创建了翻译，在不同的云服务之间进行映射。

Khan 说，但它对于同一云中的备份或迁移也很有用。

“如果你有 Kubernetes 运行在某个地区的 AWS 上，它关闭了，你要在不同的地区恢复它，你基本上必须假设其余的基础设施已经准备好，你可以在那里部署，”他说。

当云提供商说他们有灾难恢复时，他们的意思是他们自己的基础设施有灾难恢复，他说。“对你来说不一定。你需要重建你的网络结构，你的安全和防火墙政策，你的负载平衡。”

Wanclouds 会处理所有这些问题。

“只要告诉我们是哪个地区，我们就会让整个基础设施重新旋转，不管云能让它旋转多快，”他说。

因此，不仅仅是 Kubernetes 容器被恢复，整个私有云设置也被恢复。

或者，不是恢复到同一云的不同区域，而是可以恢复到不同的云。

“我们实际上可以在谷歌和 AWS 之间恢复，”他说。

而且过程很快。基础架构可以在几分钟内启动并运行，然后数据从其备份位置恢复。

“总的来说，我们认为您应该在不到一个小时的时间内启动并运行，”Khan 说。

他补充说，如果数据集非常大，可能需要更长时间。

它不像完全镜像设置那样即时，但它明显更便宜。

“我们正在迎合那些希望有一个备份灾难战略，但不想花很多钱的客户，”他说。

Wanclouds 还实现了灾难恢复系统初始设置的自动化。

“我们实际上可以在一分钟内创建你的 DRaaS，”Khan 说。“我们可以发现您的基础架构，并将整个蓝图备份到云对象存储中。”

他说，备份可以是双向的。

例如，如果在 RedHat OpenShift 上运行 Kubernetes 集群的本地数据中心出现问题，备份可以加速到 IBM cloud。然后，当数据中心问题得到解决时，“如果您需要，我们可以恢复到您的本地，”Khan 说。

客户可以计划备份的频率，例如，每小时有一个新的快照。并且可以保留多个备份生成器，这样，如果发生勒索软件攻击，基础架构可以恢复到感染发生之前的某个时间点。

他说，Wanclouds 目前没有扫描备份以寻找勒索软件的迹象。"这是未来版本中将会出现的东西."

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>