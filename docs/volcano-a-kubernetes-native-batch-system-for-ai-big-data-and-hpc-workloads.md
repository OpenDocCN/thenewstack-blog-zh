# Volcano:用于人工智能、大数据和高性能计算工作负载的 Kubernetes 原生批处理系统

> 原文：<https://thenewstack.io/volcano-a-kubernetes-native-batch-system-for-ai-big-data-and-hpc-workloads/>

[Futurewei](https://www.futurewei.com/) 赞助本帖。

 [安妮·赖

安妮领导 Futurewei 开源项目的开源运营和营销，涵盖 Kubernetes、Cloud Native、Cloud-Edge、OpenStack、开放存储和 AI/深度学习。她之前在 OpenStack 基金会董事会任职，目前在 CNCF 和 OCI 董事会任职。](https://www.linkedin.com/in/annilai/) 

自 2015 年[云原生计算基金会](https://www.cncf.io/) (CNCF)成立以来，云原生技术在实现企业级成熟度和全球采用方面取得了长足进步。与传统的整体编程范式相比，cloud native 提供了一种更快、更具成本效益的方式，在高度可扩展和可用的应用平台上创新和开发服务。[根据 CNCF](https://www.cncf.io/newsroom/case-studies/) ，云原生服务已经在各个行业部署——如金融服务、电子商务、教育、交通、旅游、媒体&娱乐、政府、电信、IT 等。—主要目标是解决应用程序开发速度、可伸缩性、效率、可移植性、可用性等方面的问题。

随着移动、物联网和边缘计算技术的出现和支持，我们正在看到下一波运行在云原生平台上的工作负载——人工智能(AI；包括机器学习和深度学习)、大数据和高性能计算(HPC)——其中运行**“批处理作业”**的**大量计算资源**连接到**大规模数据湖**是必不可少的。

## **缺口**

Kubernetes 被认为是事实上的云本地编排平台，可移植和可扩展，可以有效地编排和管理容器工作负载和服务。然而，Kubernetes 在满足当今 AI、大数据和 HPC 工作负载的“批量”作业需求方面仍有差距:

*   Kubernetes 的原生调度功能无法有效满足 AI、大数据和 HPC 工作负载的计算需求。
*   Kubernetes 的作业管理能力无法满足 AI 训练的复杂需求。
*   数据管理缺少计算端的数据缓存和数据位置感知等功能。
*   资源管理缺乏时间共享，导致资源利用率较低。
*   异构硬件支持不足。

## **介绍火山**

Volcano 是一个基于 Kubernetes 构建的开源批处理系统，可以满足 AI、大数据和 HPC 工作负载的需求。它包括以下功能:

*   多功能批处理调度，具有许多基于用例部署的选项。
    *   团伙调度
    *   基于工作的公平份额
    *   队列调度
    *   基于名称空间的公平共享交叉队列
    *   随着时间的推移公平
    *   基于作业的优先级
    *   先占和收回
    *   预留和回填
*   增强的作业/队列管理，例如多 pod 模板和灵活的错误处理机制。
*   在计算端增加数据缓存，提高数据传输和读取的效率。
*   多维度的综合评分机制，实现更高效的资源管理和分配。
*   多加速器支持，如 GPU、FPGA 等。

## **火山生态系统**

经过一年多的发展，火山项目组已经达到了它的第一个重要里程碑:在多个 CNCF 成员公司和开发者的支持下，于 2020 年 5 月被接受为 **CNCF 沙盒项目。**

基于各种用例，Volcano 已经集成了许多主流计算框架和社区——包括 Tensorflow、Kubeflow、Spark、PyTorch、Paddle Paddle、Horovod (MPI)、Cromwell、MindSpore 等。

然而，对于火山的能力和它的生态系统来说，还有很多事情要做。我们邀请您来看看火山项目，并加入项目团队。

松弛:【http://volcano-sh.slack.com】T4

github:[http://github.com/volcano-sh/volcano](https://github.com/volcano-sh/volcano)

网址:https//volcano.sh/

邮箱:[volcano-sh@googlegroups.com](mailto:volcano-sh@googlegroups.com)

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

*目前新栈不允许直接在本网站评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>