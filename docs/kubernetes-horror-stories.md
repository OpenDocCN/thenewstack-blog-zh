# 库伯内特恐怖故事

> 原文：<https://thenewstack.io/kubernetes-horror-stories/>

本文中总结的故事可以在资源库中找到，

[Kubernetes Failure Stories](https://k8s.af/)

。每个单独的故事也在下面链接。

Kubernetes 是一个功能丰富的复杂容器管理系统，可以在所有环境中运行——多个公共云、本地和混合环境。因此，毫不奇怪，Kubernetes 经常是应用程序或基础结构恐怖故事中的主角。

在这篇文章中，我们介绍了五个这样可怕但真实的故事，在我们的白皮书中有详细的描述。警告:即使是这些删节版也不适合胆小的人——但它们可能会让你免于经历自己真实而昂贵的恐怖故事。

## 末日准备者:耗尽资源

 [塞尔坎·奥扎勒

塞尔坎是桑德拉的联合创始人兼首席技术官。他在软件开发方面有 10 多年的专业经验，是 AWS 认证专家，拥有分布式环境专利。他主要从事无服务器架构、分布式系统和监控工具方面的工作。](https://www.linkedin.com/in/serkanozal/) 

[Moonlight](https://www.moonlightwork.com/) ，一项为软件开发人员和招聘公司牵线搭桥的服务，通过谷歌 Kubernetes 引擎(GKE)使用 Kubernetes 托管其基于网络的应用程序。

故事开始于一个[星期五](https://updates.moonlightwork.com/outage-post-mortem-87370)，与 Redis 数据库的连接问题，Moonlight API 使用该数据库来验证会话的每个认证请求。这是他们工作流程中的重要组成部分。与此同时，谷歌云[报告](https://status.cloud.google.com/incident/cloud-networking/19002)网络服务中断，出现数据包丢失，因此 Moonlight 团队认为谷歌云导致了连接错误。但后来事情变得更糟了。接下来的周二，可怕的末日场景发生了:“月光”的网站完全崩溃了。

在谷歌云支持团队的帮助下，他们跟踪了应用程序和资源的使用情况，并确定了根本原因。GKE 将高 CPU 消耗的 pod 调度到同一个节点，该节点消耗了 100%的 CPU。因此，该节点将进入内核崩溃状态，并变得无响应。起初，只有 Redis pods 出现故障，但随着这种模式的继续，所有为流量服务的 pod 都离线了。

Moonlight 团队设计了集群中 web 应用程序的三个副本部署。他们假设每个节点都有一个 pod，并且在系统关闭之前可能会有两个节点出现故障。不幸的是，他们不知道 Kubernetes 调度程序可以将 pod 分配到同一个节点**，除非实施**[pod 间反关联性规则](https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/#inter-pod-affinity-and-anti-affinity)来定义哪些 pod 或其他 CPU 密集型应用程序永远不应该在一起。通过使用规则将 CPU 密集型应用程序和关键应用程序相互排斥，从而产生一个更可靠的系统，解决了这个问题。

*[月光故事](https://updates.moonlightwork.com/outage-post-mortem-87370)。*

## 坠落的桥:没有反应的网钩

[Jetstack](https://www.jetstack.io/) 帮助企业使用 Kubernetes 创建和运营云原生环境，包括供应多租户应用。为了定义定制需求，他们开始使用[开放策略代理](https://www.openpolicyagent.org/)在准入控制器中执行定制策略。

在一个晴朗的日子里，该团队使用 Terraform 升级在 GKE 运行的开发集群，之前他们已经成功地对预生产环境执行了相同的过程。然而，升级 20 分钟后，Terraform 超时。似乎这还不够糟糕，API 服务器开始对传入的请求超时。由于节点无法将它们的状态传送到控制平面，GKE 认为它们已经损坏，并开始替换它们。这种模式一直持续到整个集群崩溃。

Jetstack 和谷歌云支持团队发现，当 GKE 无法完成第二台主机的升级时，它停止了升级。根本原因:不匹配的名称空间配置导致 OPA webhook 无响应。吸取的教训是，webhooks 是集群中的单点故障，必须密切监控并小心配置。

*[通过 Jetstack 的故事](https://blog.jetstack.io/blog/gke-webhook-outage/)。*

## 海底总动员:缺失的 CNI 形态

[MindTickle](https://www.mindtickle.com/) 弥合面向客户的销售团队中的知识和技能差距。当他们将 Kubernetes 集群管理从 kops 迁移到 Amazon Elastic Kubernetes 服务(EKS)时，他们的恐怖故事开始了。突然，站台开始缓慢运行。AWS 支持从一个数据包捕获中了解到，所有内部网络请求都正常，但是 Kubernetes 集群外部的调用失败了。

在一周的时间里，他们在通常的可疑点(节点、配置、负载平衡器)中寻找但没有发现错误。AWS Kubernetes 专家随后告诉他们检查 CNI 国旗:AWS _ VPC _ K8S _ CNI _ external snat = true。原来，CNI 插件的源网络地址转换(SNAT)被禁用，阻止了插件正确地将 pod 的私有 IP 转换为 pod 运行的 Amazon EC2 节点的主网络接口。在 CNI 配置中启用 SNAT 后，他们能够顺利完成迁移。

这个故事的寓意是:怀疑堆栈中的每个组件，甚至是托管服务中的组件，并添加可观察性工具来了解工作流幕后发生的事情。

*[故事经由亚什·梅赫罗特拉](https://yashmehrotra.com/post/2020-03-16-case-of-missing-packet/)。*

## 炼金术士:将 CPU 转换成比特币

[JW Player](https://www.jwplayer.com/) 是一个由 HTML5 在线视频播放器支持的视频平台。去年年初，JW Player DevOps 团队发现他们的[开发和升级集群被加密货币矿工劫持了](https://medium.com/jw-player-engineering/how-a-cryptocurrency-miner-made-its-way-onto-our-internal-kubernetes-clusters-9b09c4704205)。当他们开始在 JW Player 的一个合法服务中获得高负载警报时，他们发现了入侵。经过四天的警告，团队意识到相同的 gcc 进程在他们集群的节点上以 100%的 CPU 运行。

在检查这个 gcc 过程时，他们看到父应用程序是一个 [Weave Scope](https://www.weave.works/oss/scope/) Docker 容器。仔细检查发现这个 gcc 应用程序不是 GNU 编译器集合，而是一个名为 gcc 的加密货币挖掘器！当团队进一步调查时，他们发现任何拥有负载平衡器 URL 的人都可以在没有身份验证的情况下访问 Weave Scope 仪表板。他们还可以打开外壳并执行命令，这为恶意活动打开了一个典型的通道。

*[蔡志勇的故事](https://medium.com/jw-player-engineering/how-a-cryptocurrency-miner-made-its-way-onto-our-internal-kubernetes-clusters-9b09c4704205)。*

## 纵向限制:GKE 没有 pod 的 IP

LoveHolidays 帮助人们找到梦想中的假期，但该公司很快发现自己陷入了 GKE 相对较大的 Kubernetes 集群的噩梦中。一条 Slack 消息通知团队部署已经停滞了一个多小时，并警告集群中的 256 个节点中没有可用的节点。进一步的调查显示子网已经耗尽。这看起来很奇怪，因为他们对 IP 辅助范围使用/16 子网掩码，最多产生 65，536 个 pod，但群集中的 pod 要少得多。

简而言之，问题的根本原因是 GKE 处理 pod IPs 和节点的方式，这导致 Kubernetes 集群意外达到配置的限制，没有进一步扩展的可能性。

*[故事经由德米特里·莱尔科](https://deploy.live/blog/the-shipwreck-of-gke-cluster-upgrade/)。*

## 最后

这篇文章向你介绍了五个由 Kubernetes 主演的恐怖故事。集群停滞不前，部署失败，web 应用程序停止运行，团队彻夜难眠，试图找到并解决根本原因。从这些故事中学习并分析你的库伯内特风景是很重要的。如果您避免了这些错误，您将拥有更加可靠、可伸缩和健壮的 Kubernetes 设置。

*关于所有血淋淋的细节，请查看我们的白皮书。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>