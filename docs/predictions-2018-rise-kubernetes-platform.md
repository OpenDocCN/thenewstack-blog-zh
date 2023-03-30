# 对 2018 年 Kubernetes 走向的 4 个预测

> 原文：<https://thenewstack.io/predictions-2018-rise-kubernetes-platform/>

[](https://portworx.com/)

 [Murli Thirumale，Portworx 联合创始人兼首席执行官

Murli Thirumale，Portworx 联合创始人兼首席执行官，曾担任 Ocarina Networks，Inc .联合创始人兼首席执行官。他还担任 Citrix Systems，Inc .高级解决方案集团副总裁兼总经理。Thirumale 拥有西北大学凯洛格管理研究生院的 MBA 学位，是 F.C. Austin 杰出学者。](https://portworx.com/) [](https://portworx.com/)

互联网的容器、DevOps 和云角落经历了一个糟糕的 2017 年！如果我必须总结 2017 年，对于我们的社区，一个词将是 Kubernetes。Kubernetes 的崛起在本月早些时候奥斯汀的 Kubecon 上达到了狂热的程度，这是一个为期四天的爱情盛会，有超过 4000 名开发人员、DevOps 工程师、建筑师、IT 高管和行业大师参加。听到 Kubernetes 作为一个构建和运行云原生应用的平台，已经在用真实的客户改变真实的业务，这是令人兴奋的。

有两种方式来看待这种欣快。一个最好的总结是这句谚语，“享受聚会，但要靠近门跳舞。”这种观点认为，Kubernetes 社区现在经历的高潮只是整个事情崩溃和燃烧之前的短暂现象。让我先说我认为这不会发生。Kubernetes 为人们提供了太多的价值，以至于不能简单地转移到下一件大事上，比如“无服务器”。

### 预测 1: Kubernetes 项目在企业中最终会取得成功，但道路上会有很多坎坷。

但坐在 2017 年底，展望 2018 年，我认为流行文化的另一个表达更贴切:“坚持住，这将是一段颠簸的旅程。”我对 2018 年的预测是，财富 500 强的 Kubernetes 项目将在年底软着陆，但在到达最终目的地之前会有一些动荡。原因如下:

**Kubernetes 很难**

让我们从显而易见的开始:Kubernetes 是复杂的。Kubernetes 经常被爱好者描述为优雅。但它的优雅并没有让它变得简单。弦理论是优雅的，但是除了最不精确的类比之外，理解它需要很多努力。Kubernetes 也是一样。使用 Kubernetes 构建和运行应用程序并不是一件简单的事情。

**文化变革很难**

此外，企业 IT 的整个文化正在从由首席信息官推动的、对开发人员和运营人员的角色进行严格定义的命令和控制系统转变为民主、混乱的“ [DevOps](/category/devops/) ”文化。因此，我们不仅在努力实施一些艰难的事情，而且在我们的组织经历大规模文化变革的同时也在这样做。这从来都不容易。

**业务需求难**

除此之外，驱动应用程序开发的业务需求也在不断变化。

*“必须能够在任何主要的公共云上运行。”*

*“必须加密所有静态和动态的客户数据。”*

*“每台设备每天必须能够存储和处理 15TB 的数据。规划 100 万台设备。”*

满足任何一个需求都是微不足道的。对于复杂的任务关键型应用程序，满足全球用户的所有需求是另一回事。在 Kubernetes 的辩护中，日益严格的业务需求推动了对像 Kubernetes 这样的系统的需求。如果不必支持一百万并发用户，就不需要入口控制器之类的东西。

我曾在 Kubernetes 项目上与许多财富 100 强企业合作，亲眼目睹了这些动力的发挥。一个团队将被给予一个积极的业务目标，并确定 Kubernetes 是解决问题的正确平台。团队通常会将具有可测量里程碑的阶段列表放在一起，理解他们需要先走才能跑。但是即使有这些受限的里程碑，他们也会遇到与配置和运行 Kubernetes 依赖项(如 etcd)相关的问题。否则他们会遇到网络问题。或者他们运行的云、操作系统或容器映像版本存在一些小的兼容性问题。

这些问题没有一个是不可克服的，但是随着项目时间表的下滑，它们会很快让人们从兴奋状态中走出来。结果，团队发现自己陷入了漫长而艰难的过程中，一个问题接一个问题地出现在他们的内部吉拉上，而高管们开始猜测或质疑这种解决问题的方法。Kubernetes 是正确的选择吗？有更简单的解决方法吗？

### 预测 2:构建和运行 Kubernetes 应用程序的复杂性将随着 Kubernetes 平台的兴起而得到解决

我之前说过，我不认为社区会从 Kubernetes 继续前进。那么如何解决这些问题呢？我相信 Kubernetes 平台将会解决这些问题。[云本地计算基金会](https://www.cncf.io/) (CNCF)已经意识到实施 Kubernetes 是一项挑战，因此创建了一个平台认证模型， *Kubernetes 认证服务提供商*。目前， [kubernetes.io](http://kubernetes.io) 列出了 16 家 KCSP 供应商。最大的 Kubernetes 平台 [Red Hat OpenShift](https://www.openshift.com/) 明显不在这个列表中，但我认为这更多地表明 OpenShift 在这一点上不太需要 CNCF 的外部帮助，因为它已经成为运行大规模 Kubernetes 应用程序的权威。

### 预测 3:到 2018 年底，我们将看到近 50 家 Kubernetes 认证服务提供商

2018 年，Kubernetes 认证服务提供商的数量可能会增加三倍，但大部分客户要么会选择由他们的云运行的发行版，如 Azure Container Service (AKS)、谷歌容器引擎(GKE)或亚马逊的新服务，要么会选择与云无关的平台，如 RedHat 的 OpenShift 或 architectural。客户为什么选择某个特定选项，很大程度上取决于复杂性和对服务提供商的熟悉程度。

### 预测 4:70%的客户将选择他们的云提供商 OpenShift 或 constructive 的 Kubernetes 平台

规模较小的客户可能会选择他们的云提供商提供的全套服务，即使他们会受到限制，并发现难以实施多云战略。这些平台为定制配置提供的选项较少，但它们的简单性超过了这一点。大型企业将更经常地选择云无关平台，这不仅是因为这种平台允许更多的定制，还因为他们不太可能被他们的云提供商所束缚，这在谈判价格时很有帮助。同样，拥有一个可以在任何地方运行的平台使得在多个站点上运行一个应用程序变得更加简单，这也日益成为可用性一致性企业的一个需求。

既然 Portworx 是 Kubernetes 存储库的供应商，你可能想知道我们是怎么做的。我们的观点是，解决持久存储将继续是几乎所有 Kubernetes 项目的要求，这就是 Portworx 与所有主要 Kubernetes 平台集成的原因。人们常说 99%的企业应用程序是有状态的。我们认为，这些应用程序中的很大一部分将在 Kubernetes 上运行，企业将需要高可用性(HA)、备份、加密、共享卷、动态预配置、调整大小和他们期望的其他操作功能。

2018 年真正会带来什么，我无法知道。但我知道的一件事是发现真相会很有趣。

T2 云计算基金会 T3 和 T4 红帽 T5 是新堆栈的赞助商。

由 [Brenda Godinez](https://unsplash.com/photos/OY6QR6-EiWQ?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>