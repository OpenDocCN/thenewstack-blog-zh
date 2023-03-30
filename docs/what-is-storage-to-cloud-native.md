# 什么是云原生存储，为什么它很重要？

> 原文：<https://thenewstack.io/what-is-storage-to-cloud-native/>

数据存储和持久数据是今年 KubeCon/CloudNativeCon 的热门话题。新的堆栈已经就该主题进行了多次讨论，从新兴的存储模式和供应商产品到围绕 gRPC 和容器存储接口(CSI)标准的社区工作。

[https://www.youtube.com/embed/sffqqRruACk](https://www.youtube.com/embed/sffqqRruACk)

视频

在一次讨论中，New Stack 创始人亚历克斯·威廉姆斯与{code}的技术总监克林特·麦显杰坐在一起；贾斯汀·加里森(Justin Garrison)和克里斯·诺瓦(Kris Nova)是 Heptio 的宣传主管，他们是新书《云原生基础设施》的合著者；Stephen Watt，Red Hat 新兴技术首席架构师。他了解了 Kubernetes 存储特别兴趣小组(SIG)的最新进展，随后的讨论重点是如何最好地将独立于供应商的存储引入 Kubernetes。

它们还包括来自[云本地基础设施的亮点:动态环境中可扩展基础设施和应用的模式](http://shop.oreilly.com/product/0636920075837.do)。当被问及为什么要写这篇文章时，两人很快给出了以下理由:

Nova 说:“我真的想给基础设施工程师一个与应用工程师交流的机会。“对我来说，这是回馈社会，”加里森补充说。

“软件并不容易，能够捕捉这些模式来看看先驱们是如何做事情的是伟大的，”麦显杰指出。

在应用他们在书中学到的东西时，加里森注意到他们写的东西都已经过时了。外卖不应该是一个产品或一项技术，而是模式。

“存储信号本身仍在学习各种模式。人们管理存储的老派方式是，你提交一张票，也许第二天你就能取回它。“云原生方式是他们有一个 API，”瓦特说。“我们在 Kubernetes 采取了同样的模式。我们已经掌握了进行生命周期存储管理的权力，并将它交给了开发人员。”

麦显杰后来继续解释说，“当你拥有云的弹性并将其暴露给一个应用程序时，你可以开始放在这个基础架构之上的应用程序就会变得非常强大。你把非常复杂的东西拿出来，通过随时给他们所需的资源，让他们有能力开发出优秀的应用程序。”

[什么是云原生存储，为什么它很重要？](https://thenewstack.simplecast.com/episodes/what-is-storage-to-cloud-native-and-why-is-it-important)

### 在这个版本中:

[6:42:](https://thenewstack.simplecast.com/episodes/what-is-storage-to-cloud-native-and-why-is-it-important?t=6:42) 讨论 Garrison 和 Nova 写的书《云本地基础设施:动态环境中可扩展基础设施和应用的模式》。
[15:01:](https://thenewstack.simplecast.com/episodes/what-is-storage-to-cloud-native-and-why-is-it-important?t=15:01) 服务网格、存储、SIGs、价值观和 Kubernetes 社区中的新发现之路。
[20:39:](https://thenewstack.simplecast.com/episodes/what-is-storage-to-cloud-native-and-why-is-it-important?t=20:39) 一个组织的价值观是什么，它们如何反映在他们的总体使命、目标和目的中？

[云原生架构和存储的作用](https://thenewstack.simplecast.com/episodes/cloud-native-architecture-and-the-role-of-storage)

在第二场以存储为中心的讨论中，{code}开源软件工程师 Vladimir Vivien 和 Google Container Engine 和 Kubernetes 的工程总监 Mike Rubin 谈到了通过 gRPC(CSI 标准)为 Kubernetes 带来通用的、与供应商无关的存储，以及 Kubernetes 1.9 和 CSI 中的存储新特性。

Vivien 指出，他一直在努力实现 Kubernetes 1.9 中发布的 CSI。

“任何想为 Kubernetes 编写自己的卷驱动程序的人都可以使用 CSI 界面来完成，”Vivien 说。

Rubin 还指出，这对于供应商来说尤其令人兴奋，因为 CSI 支持树外存储，具有易于理解的界面。  This 允许存储解决方案与 Kubernetes 一起工作，并增加了使用分布式架构和消耗存储的机会，同时降低了 Kubernetes 的整体复杂性。

“我认为这也是对供应商的解放，只要它遵守 CSI 协议，就可以以任何方式与 Kubernetes 进行存储交互，”Vivien 说。“他们实现的方式可以是他们想要的，所以我认为从这个意义上说，用户将从我们现在所做的事情中受益。”

[https://www.youtube.com/embed/mEgv3pSyYMM?feature=oembed](https://www.youtube.com/embed/mEgv3pSyYMM?feature=oembed)

视频

### 在这个版本中:

[5:01:](https://thenewstack.simplecast.com/episodes/cloud-native-architecture-and-the-role-of-storage?t=5:01) CSI 和 Libstorage。
[10:12:](https://thenewstack.simplecast.com/episodes/cloud-native-architecture-and-the-role-of-storage?t=10:12) CSI 作为供应商的解放以及存储如何与 Kubernetes 互动。
[14:10:](https://thenewstack.simplecast.com/episodes/cloud-native-architecture-and-the-role-of-storage?t=14:10) 将扩展到未来 CSI 版本的主题方面。

{code}，Google 和 Red Hat 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>