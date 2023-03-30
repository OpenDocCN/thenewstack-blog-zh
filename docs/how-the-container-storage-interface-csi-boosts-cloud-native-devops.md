# 容器存储接口(CSI)如何提升云原生开发运维

> 原文：<https://thenewstack.io/how-the-container-storage-interface-csi-boosts-cloud-native-devops/>

[戴尔科技](https://www.delltechnologies.com/en-us/index.htm)赞助了这次播客。

现代数字组织的内在斗争在于速度和安全性。随着软件开发速度似乎不断增加，IT 组织正在寻找他们可以使用的工具来提供防护和治理——而不减慢速度。

基础设施即代码作为解决方案和双方的共同语言而出现。随着开发人员要求类似云的消费和自动化继续成为成功开发运维组织的秘密，工具和规范成为受欢迎的解决方案。

在 [KubeCon + CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) ，New Stack 创始人兼发行人 Alex Williams 与负责容器存储和界面驱动程序的产品经理 [Audrius Stripeikis](https://www.linkedin.com/in/audrius-stripeikis/) 和产品组合营销顾问 [Parasar Kodati](http://linkedin.com/in/parasarkodati) 坐在一起，谈论针对最古老的瓶颈之一的最新修复方案。他们深入探讨了[容器存储接口(CSI)](https://github.com/container-storage-interface/spec) 规范及其接口驱动程序，以及它们如何响应 Kubernetes 支持的企业 DevOps 的需求。

[速度与安全的较量](https://thenewstack.simplecast.com/episodes/the-battle-between-speed-and-security)

CSI 旨在将最终控制权交给 IT 管理员，同时仍然允许开发人员直接调配他们自己的存储，而不是等待他人为他们调配存储。

Stripeikis 解释说,[容器存储接口](https://kubernetes.io/blog/2019/01/15/container-storage-interface-ga/)基本上是一个规范，它定义了存储区域如何连接到 Kubernetes 集群。

“最初当[Kubernetes orchestration]开始时，每个人都对存储区域如何连接到 Kubernetes 提出了自己的定义。这使得美国供应商很难开发那些连接到各种容器编排器的驱动程序，”他说。

因此，Kubernetes 社区尝试了一个名为 [FlexVolume](https://kubernetes.io/docs/concepts/storage/volumes/) 的规范，但它被认为是一个低效、甚至繁琐和复杂的解决方案。驱动程序只能在 Kubernetes 发布期间更新。

因此，Kubernetes 社区决定制定一个规范，允许像戴尔 EMC 这样的供应商提供新的驱动程序，这些驱动程序以软件的形式作为规范的实现。

借助 CSI，存储管理员可以为开发人员用户分配存储空间。然后，消费者将以永久卷的形式使用该分配。

### CSI 让存储管理员设置护栏

Stripeikis 警告说，对于这些接口驱动程序，“存储管理员不习惯这种模式。他们觉得自己现在正在失去控制，事实并非如此。”

他说，CSI 为这些管理员提供了存储类，允许他们定义可以使用哪个存储区域，该存储区域内将分配多少容量，以及谁可以访问它。它使管理员能够设置护栏和配额，就像在特定卷上一次只能有这么多分支一样。

如果开发人员的构建超过了这些配额规则，部署将会停止。

CSI 旨在应用于 CI/CD 管道。Kodati 解释说，无论定义什么样的存储类别，都会自动为他们的应用或微服务调配。

这一切都归结为“您如何教育您的 It 组织，该组织传统上负责通过进入自动化和以代码形式调配基础架构的思维模式来帮助开发人员以他们希望的速度前进？”科达提说。

这是拥抱基础设施的更大趋势的一部分，正如 Kodati 所说，基础设施“嵌入”到 CI/CD 管道中，允许开发人员独立和基于策略的供应、配置管理和流程的自动移交。

[https://www.youtube.com/embed/wsKCJhAxRJk?feature=oembed](https://www.youtube.com/embed/wsKCJhAxRJk?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>