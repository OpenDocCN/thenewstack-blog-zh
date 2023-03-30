# Kubernetes 1.9 中的所有乐趣

> 原文：<https://thenewstack.io/fun-kubernetes-1-9/>

最新版本 Kubernetes 1.9 的文档还在整理中，但是我们看到了很多新特性被引入到 alpha 和 beta 频道中。例如，那些对亚马逊的新 Kubernetes 产品感兴趣的人会很高兴看到 [AWS 网络负载平衡器支持](https://github.com/kubernetes/features/issues/423)进入 alpha。像这样的变化让亚马逊更接近与谷歌云的 Kubernetes 服务竞争。

当然， [Kubernetes](https://kubernetes.io/) 是微软领导的 1.8 版本和谷歌支持的 1.9 版本的合作成果。在 1.9 中，我们有三个特性进入稳定，35 个进入 alpha/beta。此版本的亮点实际上是围绕存储指标。

## 详细的存储指标

这一新功能公开了关于装载、空间、失败的附件等更多信息。对于任何坚持不懈的人来说，这将是一个受欢迎的变化。事实上，当我问特殊兴趣小组(SiG)成员他们最感兴趣的是什么时，[存储排在了列表的首位](https://github.com/kubernetes/features/issues/496)。

## 短路拒绝

 [丹·加菲尔德

Dan Garfield 是 Codefresh 的全栈工程师和营销副总裁，code fresh 是世界上第一个为 Kubernetes 和 containers 构建的连续交付平台。他是一个老派的酷黑客，怀念超级马里奥、BBSes 和 80 年代的科幻小说。问问他关于他的机器人鸡舍的事情，来看看丹在奥斯汀 Kubecon 17 的演讲。你可以在推特上找到他，名字是@ todaywasawesome。](http://codefresh.io) 

增强安全性的一个举措是增加了短路拒绝。Kubernetes 设计了一个默认拒绝权限模型。除非某个特定的授权者允许某事，否则它将被拒绝。如果您想要拒绝一些其他配置授权的东西，这可能会产生意想不到的后果。使用短路拒绝，您可以设置一个策略来禁止某些操作，它将覆盖任何后续授权者不允许该操作。

如果这让你困惑的话，就像你小时候想吃冰淇淋一样。首先，你问你妈妈，她说不，然后你去问你爸爸，他说是。然后突然你在厨房吃冰淇淋，而你妈妈给爸爸一个臭眼睛。短路否认是指当妈妈说不的时候，爸爸连发表意见的机会都没有。虽然它可能对试图黑进冰淇淋的孩子不利，但它对安全性(和胰岛素水平)有很大的好处。

## 工作负载 API

工作负载是 Kubernetes 的核心，这个 API 已经开发了几个月了。将 API 转移到稳定意味着核心控制器 API(如“部署”、“DaemonSet”、“复制集”和“状态集”)更加规则和一致这里的目标是继续使 Kubernetes 易于使用。

## Windows 支持转向测试版

Kubernetes 由 Cloud Native Computing Foundation 管理，将成为第一个功能齐全的跨平台集群管理器，并将使许多 Windows 管理员非常高兴能够运行他们所有基于 Windows 的容器。

## 结论

Kubernetes 1.9 归结为更好的安全性、API 的更成熟性以及云提供商之间更多的支持。生态系统的承诺得到了充分展示。虽然 Google 和 Red Hat 的贡献最大，但我们也看到了来自社区的许多活动，包括个人贡献者和公司，如 Heptio、华为、思科和 Apprenda。

要了解 1.9 中所有变化的更多细节，请查看[特性跟踪板](https://docs.google.com/spreadsheets/d/1WmMJmqLvfIP8ERqgLtkKuE_Q2sVxX8ZrEcNxlVIJnNc/edit#gid=0)。

[云本地计算基金会](https://www.cncf.io/)、[谷歌](https://cloud.google.com/kubernetes-engine)、[微软](https://azure.microsoft.com/en-us/?v=17.14)和[红帽](https://www.openshift.com/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>