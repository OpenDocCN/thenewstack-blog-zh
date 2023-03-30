# 思科项目在 Kubernetes 和 SD-WAN 之间架起桥梁，加速微服务消息传递

> 原文：<https://thenewstack.io/cisco-project-bridges-kubernetes-and-sd-wan-to-speed-microservice-messaging/>

SD-WAN(广域网中的软件定义网络)和 Kubernetes 是企业在数字化转型过程中感兴趣的两项主要技术发展。SD-WAN 将 SDN 功能可编程网络和自动化扩展到 WAN 网络。Kubernetes 在很大程度上采用了容器化的应用程序编制器，它具有可靠的 API 架构、自动伸缩、深度监控和负载平衡功能，适用于动态和分布式基础设施。

鉴于业务应用程序分布在不同的数据中心和边缘云位置，许多公司正在一起使用它们。在这里，不同的 Kubernetes 集群连接到最终用户应用和工作负载，SD-WAN 用于连接所有集群和最终用户。

 [萨加尔·南加雷

Sagar Nangare 是技术博客作者，专注于数据中心技术(网络、电信、云、存储)和边缘计算、物联网、机器学习、人工智能等新兴领域。他目前在浦那担任 Coredge.io 的产品营销总监。](https://twitter.com/sagarnangare) 

但是在这个合并的解决方案中仍然存在差距。SD-WAN 多用于公共互联网，在世界不同地区有不同的表现。当我们部署基于微服务的应用时，可能会出现某些微服务有特定延迟要求或需要更多带宽等情况。在这种情况下，解决这种微服务的需求对于网络运营(NetOps)团队来说可能很麻烦。对于微服务的任何特定网络要求，开发运维团队应向网络运维团队提供网络要求。该过程涉及手动配置，这进一步导致时间损失方面的混乱，并且可能导致错误配置，因为它涉及人工干预。

为了解决这一差距，思科团队推出了一个开源项目，[Cloud Native SD-WAN(CN-WAN)](https://github.com/CloudNativeSDWAN)，以改善 SD-WAN 和 Kubernetes 之间的集成。CN-WAN 利用了 SD-WAN 和 Kubernetes 的主要特性。借助 API，SD-WAN 解决方案变得更加先进，具有强大的智能监管功能。Kubernetes 还通过[操作框架](https://thenewstack.io/operators-and-sidecars-are-the-new-model-for-software-delivery/)添加了声明性部署等特性，该框架将 Kubernetes 系统的当前状态与所需状态(配置中设置的状态)相协调。

CN-WAN 的组件协同工作，从 Kubernetes 集群中部署的微服务中提取网络需求，并将其推送到 SD-WAN 软件，以网络策略的形式呈现出来。通过这种方式，CN-WAN 帮助基于微服务的应用通过 SD-WAN 即时提供最佳性能。

在上图的右侧，您可以看到处理语音、视频、幻灯片和聊天等服务的微服务。可以想象，这些微服务应用在 SD-WAN 上可能有不同的带宽和延迟要求。

## **CN-WAN 架构**

CN-WAN 项目有三个组成部分:运营商、阅读器和适配器。这些嵌入到 Kubernetes 和 SD-WAN 控制器中。

一个 CN-WAN 操作员在 Kubernetes 集群中运行以监控微服务。每个微服务都有特定的 CN-WAN 注释，表示服务的网络要求，并描述 SD-WAN 应该如何优化特定微服务的网络流量。这些注释和其余的配置信息在 Service Registry 中注册。CN-WAN 阅读器从服务注册中心获取特定于服务的配置信息和注释，并将其推送到 CN-WAN 适配器。CN-WAN 适配器专用于每个 SD-WAN 解决方案，该解决方案将注释和配置信息呈现和翻译成将要在网络中实施的 SD-WAN 策略。

## **结论**

关键是 SD-WAN 或任何网络需要了解应用程序及其相关组件的各种要求，以避免妨碍服务交付的手动任务。

*代码是 CN-WAN 项目在 [github](https://github.com/CloudNativeSDWAN) 可用。为了获得更多关于该示例的技术见解，[请在即将举行的](https://sched.co/ekCK) [KubeCon+CloudNativeCon 北美](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)会议上查看云原生 SD-WAN 会议，该会议将由思科的[阿尔伯托·罗德里格斯纳塔尔](https://www.linkedin.com/in/rodrigueznatal/)和谷歌的[马克丘奇](https://www.linkedin.com/in/markac/)举办。*

KubeCon 和 CloudNativeCon 是新堆栈的赞助商。

由 [Anders Jildén](https://unsplash.com/@andersjilden?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/s/photos/bridge?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>