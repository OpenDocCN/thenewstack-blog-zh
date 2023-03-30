# Kubernetes 上关于边缘计算的战争故事

> 原文：<https://thenewstack.io/war-stories-about-edge-computing-on-kubernetes/>

[Kubecon + CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/) 赞助了这个播客。

[Kubernetes 上关于边缘计算的战争故事](https://thenewstack.simplecast.com/episodes/war-stories-about-edge-computing-on-kubernetes)

Kubernetes 上的边缘计算正在成为一种强大的大规模共享、分发和管理数据的方式，而云或内部部署不一定能提供这种方式。New Stack 的编辑总监 Libby Clark 在西雅图举办了一场播客，讲述了其中涉及的一些挑战。讨论他们与 Kubernetes 合作进行边缘计算部署的项目和目标的有:

Milinkovich 说，对于 Eclipse 基金会来说，主要挑战之一是管理物联网网关结构或边缘网关的边缘和云之间的交互。Eclipse Foundation 还与云计算原生计算基金会(CNCF)、Red Hat、华为和其他公司合作，并在 Kubernetes 内部共同创建了一个物联网/边缘工作组,专注于将边缘需求纳入 Kubernetes 项目。

“这只是开始，这是一个过程——而不是一个事件——但肯定有很多要求需要纳入 Kubernetes，我们在这里帮助实现这一点，”米林科维奇说。

具体到边缘计算，Milinkovich 描述了“关于什么是边缘还没有一个共同的命名法，”他说。“在某种程度上，这实际上是这个物联网边缘工作组的首要任务，”米林科维奇说。“这只是决定一些术语，以便当我们使用这些术语时，我们实际上彼此共享一些含义。”

与云不同，边缘计算的一个关键共同属性是组织可以准确定位其数据驻留的位置。米林科维奇说:“所以，位置的物理性实际上有助于确定边缘。”“当你谈论 700 亿台设备时，挑战之一就是处理数据。”

徐介绍了 PingCAP 的“关键值”存储层如何被称为 TiKV，这是的成员项目。该企业还部署在 Kubernetes 以及“所有不同的云环境”中。

徐说，PingCAP 的边缘部署“针对边缘，但肯定针对物联网”。随着自行车共享公司摩拜单车的部署，其物联网数据库必须扩展到能够容纳全球 900 万辆自行车。

“你可以称它们为边缘设备或物联网设备等，但它们的物理设备希望在世界各地不同的位置保持跟踪，我们经常遇到的一个真正的大用例是世界各地所有这些不同的设备，”徐说。“这实际上可以归结为一个单一的数据层，您可以利用这些数据并从中获取情报。”

Synadia Communications 正在开发一项技术，允许数字系统、服务和设备在世界各地进行连接和通信。世界上有 700 亿个数字事物试图一起交谈和通信，“这是一个神奇的时间，既可以交流数据，存储和处理数据，然后找出如何运行工作负载，使自己更接近数据，希望以安全和认证的方式，”科利森说。

“在他所说的基础上，我认为很重要的一点是，生产线会不断变化。因此，如果你说，“我们将以物联网的特定方式、边缘的特定方式和云的特定方式来实现，”我不知道我是否认为这是正确的方法，”科利森说。“这是因为这些线一直在移动，特别是当边缘转向物联网时。所以我认为，从长远来看，尝试找出一种在所有三个层中都一致且可用的技术将有助于我们。”

### 在这个版本中:

[5:03:](https://thenewstack.simplecast.com/episodes/war-stories-about-edge-computing-on-kubernetes?t=5:03) 您认为 Kubernetes 在大规模使用 edge 时会扮演什么角色？
[6:45:](https://thenewstack.simplecast.com/episodes/war-stories-about-edge-computing-on-kubernetes?t=6:45) 定义“什么是 edge”并建立其命名法
[10:46:](https://thenewstack.simplecast.com/episodes/war-stories-about-edge-computing-on-kubernetes?t=10:46) 您如何看待 Kubernetes 作为该问题的潜在解决方案？
[13:56:](https://thenewstack.simplecast.com/episodes/war-stories-about-edge-computing-on-kubernetes?t=13:56) 数据方面存在哪些挑战？
[15:26:](https://thenewstack.simplecast.com/episodes/war-stories-about-edge-computing-on-kubernetes?t=15:26) Kevin，您在使用 Kubernetes 进行数据管理和数据存储时面临哪些挑战？
[17:14:](https://thenewstack.simplecast.com/episodes/war-stories-about-edge-computing-on-kubernetes?t=17:14) Derek，您认为 edge 和 Kubernetes 面临的主要挑战是什么？

云计算原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>