# 容器安全性和 Docker 的可插拔架构

> 原文：<https://thenewstack.io/tns-analysts-bridging-open-source-container-communities/>

在本期的[新堆栈分析师](/tag/the-new-stack-analysts/)播客中，我们将深入探讨网络容器面临的挑战、容器名称空间是如何发展的，以及当今容器安全性的发展状况。讨论还涉及到可插拔生态系统的重要性，以及实现可插拔模型如何让 Docker 的供应商和用户受益。

[IBM](http://www.ibm.com/us-en/) 开放云技术[的高级技术人员 Phil Estes](https://www.linkedin.com/in/estesp) 接受了 TNS 创始人 Alex Williams 关于我们最新的[电子书的采访:容器网络、安全性以及使用 Docker 和容器的存储。](https://thenewstack.io/ebookseries/)

[#105:桥接开源和容器社区](https://thenewstack.simplecast.com/episodes/105-bridging-open-source-and-container-communities)

对话[也可以在 YouTube](https://youtu.be/PQx8DsWzf-U) 上欣赏。

这次谈话引发了对集装箱历史的探究。Estes 指出，相对于像 VirtualBox 和 VMWare 这样的平台，Linux 内核的底层特性通常不为公众所熟知。“码头工人不是从以太里出来的。它发展了我们认为是 Linux 中的容器的计算。对于从非常具体的东西(如虚拟机)来到那个世界的人来说，他们回到容器，看到我们称之为容器的孤立部分实际上是经过一段时间才出现的。”

Estes 还指出了未来几年这些低级组件的安全性的积极前景，强调了 RackN 首席执行官罗布·希施菲尔德为新堆栈贡献的一篇文章，该文章详细介绍了 Docker 容器比传统虚拟机更安全的 13 种方式。

Estes 解释说，安全性的负担并不完全取决于容器执行层。相反，它是在容器和它的应用程序之间共享的。

“我的应用程序必须在如何使用数据、如何传递任何类型的加密密钥、设置或密码方面做一些智能的事情。像往常一样，安全性是应用程序开发人员的共同任务，容器社区对此非常重视，”Estes 说。

可插拔架构是上游 Docker 社区关注的焦点，部分原因是日志记录驱动程序和框架有大量的选项。Estes 指出，Docker 引擎不应该控制这些服务，他解释说，“这应该是一个可插入的组件，如果我是一个日志服务提供商，我应该能够插入该服务。因为很多领域都在快速发展，Docker 选择了一个可插拔的模型，这样供应商就可以把这些部分放进去，而不是让引擎试图跟踪所有这些技术。”

如今，供应商和用户可以使用的编排平台种类繁多，围绕这些平台如何基于安全性进行区分展开了大量讨论。然而，Estes 指出，在容器处理层面，它们有很多相似性和共性。“我们将更多地讨论应用程序级安全性。在应用程序协调层，我认为您会看到差异，其中一个可能会比其他的更好。”

Docker 和 [IBM](https://www.ibm.com/cloud) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>