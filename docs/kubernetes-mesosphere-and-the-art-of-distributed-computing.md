# Kubernetes，中间层和分布式计算的艺术

> 原文：<https://thenewstack.io/kubernetes-mesosphere-and-the-art-of-distributed-computing/>

[当 Kubernetes 不是唯一答案](https://thenewstack.simplecast.com/episodes/when-kubernetes-is-not-the-only-answer)

集群管理器的价值是什么，什么时候有必要？这是上个月在奥斯汀的 [KubeCon 和 CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2018/) 的《新栈制造者》节目中被问到的问题。

“真正好的基础设施的目标是你不知道它在那里。人们可以直接使用它，”中间层创始人本·欣德曼说。“有很多组织在使用 Mesos，我们对它们一无所知，因为希望它只是在做自己的工作。”

Hindman 与戴尔技术副总裁 Joshua Bernstein 一起讨论了为什么 Kubernetes 可能不是探索容器编排平台的公司的唯一答案。

伯恩斯坦说，作为一个平台，Mesos 与众不同的是它的双层或应用程序感知调度，允许你同时协调各种各样的应用程序。

Hindman 指出，作为这种两级模型一部分的资源提供可以以更好的方式完成，并且 Mesosphere 正在不断思考改进调度程序的方法，以便它更加智能:根据可用性操纵条件，以允许更高的集群利用率、更好的故障分布等等。最终，这是一个好的集群管理器的工作——智能的资源分配和利用。

[https://www.youtube.com/embed/BMRbmyOLhi8?feature=oembed](https://www.youtube.com/embed/BMRbmyOLhi8?feature=oembed)

视频

### 在这个版本中:

[1:27:](https://thenewstack.simplecast.com/episodes/when-kubernetes-is-not-the-only-answer?t=1:27)SMACK 堆栈及其如何包含 Mesos
[6:11:](https://thenewstack.simplecast.com/episodes/when-kubernetes-is-not-the-only-answer?t=6:11)Kubernetes 中围绕资源争用会出现哪些冲突
[11:20:](https://thenewstack.simplecast.com/episodes/when-kubernetes-is-not-the-only-answer?t=11:20) 容器中的调度、存储和资源管理
[13:10:](https://thenewstack.simplecast.com/episodes/when-kubernetes-is-not-the-only-answer?t=13:10) 解决生态系统中的成熟度问题
[15:08:](https://thenewstack.simplecast.com/episodes/when-kubernetes-is-not-the-only-answer?t=15:08)Mesos 在其早期如何处理发布版本
[11](https://thenewstack.simplecast.com/episodes/when-kubernetes-is-not-the-only-answer?t=17:31)

[编排成为商品如何增值](https://thenewstack.simplecast.com/episodes/how-to-add-value-when-orchestration-becomes-a-commodity)

另一个来自 KubeCon 和 CloudNativeCon 的直播关注于容器和容器编排平台的持续商品化。TNS 创始人 Alex Williams 与微软杰出的工程师 Brendan Burns、{code}的技术总监克林顿·麦显杰和谷歌的首席软件工程师蒂姆·霍金坐在一起，讨论所有的基础设施和容器编排平台的商品化。

随着 Kubernetes 变得无处不在——这是蒂姆·霍金斯更喜欢的一种替代描述，而不是“商品”——你可以开始假设这就是组织正在使用的东西。

伯恩斯说:“如果你认为它无处不在，你可以在它的基础上进行建设，因为你知道你不会通过建设它来限制人们。”

“人们实际上是在它上面运营他们的业务。我们必须在兼容性上采取强硬的立场，确保我们不会破坏用户，测试，并确保我们不会对 API 的变化掉以轻心。门槛已经很高了，而且只会越来越高，”霍金补充道。

麦显杰接着指出，拥有一个用户可以依赖的稳定的基础将使 Kubernetes 达到这一点。“当你看到 CNCF 和围绕如何使用这些环境而构建的工具时，你必须在架构上保持以 Kubernetes 为中心。”

[https://www.youtube.com/embed/9VHAQmDM0NA?feature=oembed](https://www.youtube.com/embed/9VHAQmDM0NA?feature=oembed)

视频

### 在这个版本中:

[1:05:](https://thenewstack.simplecast.com/episodes/how-to-add-value-when-orchestration-becomes-a-commodity?t=1:05) Kubernetes 作为一种商品
[7:13:](https://thenewstack.simplecast.com/episodes/how-to-add-value-when-orchestration-becomes-a-commodity?t=7:13) CSI、存储和 1.9 版中 Kubernetes 的持续发展
[10:38:](https://thenewstack.simplecast.com/episodes/how-to-add-value-when-orchestration-becomes-a-commodity?t=10:38) 授权和政策
[13:53:](https://thenewstack.simplecast.com/episodes/how-to-add-value-when-orchestration-becomes-a-commodity?t=13:53) 伯恩斯、麦显杰和霍金解决这些问题的方法是什么
[15:44:](https://thenewstack.simplecast.com/episodes/how-to-add-value-when-orchestration-becomes-a-commodity?t=15:44)Kubernetes 内部服务网格的发展

[{code}](https://www.influxdata.com/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>