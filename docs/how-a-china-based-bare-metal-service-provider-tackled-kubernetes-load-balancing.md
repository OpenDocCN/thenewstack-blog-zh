# 一家中国裸机服务提供商如何解决 Kubernetes 负载平衡问题

> 原文：<https://thenewstack.io/how-a-china-based-bare-metal-service-provider-tackled-kubernetes-load-balancing/>

[KubeCon + CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/) 赞助本帖。

[一家中国裸机提供商如何用开源解决问题](https://thenewstack.simplecast.com/episodes/how-a-china-based-bare-metal-provider-solved-a-problem-with-open-source)

Kubernetes 继续在云和本地及裸机服务器环境中传播——随着更大规模的采用，通常会出现成长的烦恼。例如，针对裸机，Kubernetes 平台缺乏可行的负载平衡能力。总部位于中国的裸机服务提供商北京 Yunify Technology 表示，随着开源软件 Porter 的开发，他们已经解决了这个问题，Porter 旨在解决 Kubernetes 生产中裸机的负载平衡问题。

在本次[New Stack Makers](https://thenewstack.io/podcasts/makers)播客中，在 [KubeCon + CloudNativeCon 中国开源峰会 2019](https://www.lfasiallc.com/events/kubecon-cloudnativecon-china-2019/) 上，北京 Yunify Technology 的高级软件工程师[薛涛宋](https://kccncosschn19eng.sched.com/speaker/magicsong1)更详细地描述了 Porter 如何为 Kubernetes 提供负载平衡功能，同时也触及了其他与容器相关的主题。

在播客中，主持人 Alex Williams，The New Stack 的创始人兼主编，提供了关于 Porter 在裸机基础架构中的位置的上下文。他说，裸机上的开源负载平衡的主要问题是后端工作负载通常如何使用 Kubernetes 集群中的负载平衡器公开。通常，云提供商提供必要的负载平衡插件，但是当组织在他们自己的环境中在 Kubernetes 上的裸机服务器上部署应用程序和数据时，Kubernetes 集群缺乏负载平衡，而这正是 Porter 的目的所在。

宋描述了北京 Yunify Technology 如何使用 Porter 将其与裸机服务器和云平台连接起来。通过一个[边界网关协议(BGP)](https://en.wikipedia.org/wiki/Border_Gateway_Protocol) ,“复杂的金属制品”可以被连接起来，Porter 帮助在 Kubernetes 和裸机服务器之间架起一座桥梁。此外，虽然负载平衡是 Porter 的主要特性，但 Porter 还提供路由动态配置和 IP 访问管理功能。

北京 Yunify Technology 创建 Porter 也是其日益认识到容器重要性的一部分，以及容器和 Kubernetes 如何在该公司向客户提供的产品中发挥作用。Song 描述了他的组织如何为计算和数据库提供服务，以及容器基础设施如何发挥了关键作用。“今年，我们(非常)关注集装箱，”宋说。

宋还说，木偶和裸机在北京云风科技的客户中很受欢迎。集装箱是一种[不可逆转的]趋势。”除了安全功能，“裸机速度快，”宋说。

宋说，北京 Yunify Technology 的客户也一直在使用 Kubernetes。除此之外，“Kubernetes 只是比虚拟机更灵活，”宋说。

[https://www.youtube.com/embed/zSWypFKaYcY?feature=oembed](https://www.youtube.com/embed/zSWypFKaYcY?feature=oembed)

视频

### 在这个版本中:

[2:28:](https://thenewstack.simplecast.com/episodes/how-a-china-based-bare-metal-provider-solved-a-problem-with-open-source?t=2:28) 波特是什么？你为什么开发它？
[5:53:](https://thenewstack.simplecast.com/episodes/how-a-china-based-bare-metal-provider-solved-a-problem-with-open-source?t=5:53) 你说波特有三个方面，那是第一，第二是什么？
[11:44:](https://thenewstack.simplecast.com/episodes/how-a-china-based-bare-metal-provider-solved-a-problem-with-open-source?t=11:44) 你为什么决定采取这种方式？在开始使用 Porter 之前，您遇到过哪些问题？
[14:31:](https://thenewstack.simplecast.com/episodes/how-a-china-based-bare-metal-provider-solved-a-problem-with-open-source?t=14:31) 说说你们公司吧，你们公司提供什么？
[15:48:](https://thenewstack.simplecast.com/episodes/how-a-china-based-bare-metal-provider-solved-a-problem-with-open-source?t=15:48) 所以你现在向这些客户提供波特酒，他们会采用 Kubernetes 吗？为什么？
[17:36:](https://thenewstack.simplecast.com/episodes/how-a-china-based-bare-metal-provider-solved-a-problem-with-open-source?t=17:36) 你通过顾客了解到波特和库伯内特的哪些信息？他们面临的挑战是什么？

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>