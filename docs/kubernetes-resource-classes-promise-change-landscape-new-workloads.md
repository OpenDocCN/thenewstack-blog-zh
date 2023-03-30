# Kubernetes 资源类如何承诺改变新工作负载的前景

> 原文：<https://thenewstack.io/kubernetes-resource-classes-promise-change-landscape-new-workloads/>

*本文是 12 月 6 日至 8 日在奥斯丁举办的 [Kubecon/CloudNativeCon](http://events.linuxfoundation.org/events/kubecon-and-cloudnativecon-north-america) 系列活动的一部分。Red Hat 的 Jeremy Eder 将在活动中深入探讨 Kubernetes 资源管理工作组。*

科林·鲍威尔法则(Colin Powell rule)指出，当你有 40%到 70%的信息来做决定时，你应该做出决定。随着像 Kubernetes 这样的 Linux 容器技术发展如此之快，公司很难感觉到他们拥有了他们需要的 40%的信息，更不用说 70%了。

客户经常联系我和 Red Hat 的其他人，帮助他们超过 40%的分数，以决定是否购买基于 Kubernetes 的 Red Hat OpenShift。

对于这些客户中的许多人来说，公共云对于工作负载来说已经变得司空见惯。然而，从时间和成本的角度来看，将他们的内部架构转化为适合每个云的设计/架构是一项挑战(至少可以这么说)。Kubernetes 和 OpenShift 的承诺是一个在任何地方都一样的架构，但这也是工程师们最沉重的负担之一。

## 利用集装箱潜力

自 2012 年初以来，我一直与 OpenShift 团队合作开发 1.0 版风格的容器。2014 年，有人找我谈 Docker 的工作。没多久就意识到了这项技术的潜力。事实上，几个星期后，我说服自己，有一天世界上最关键的工作负载将在这个下一代架构上运行，我们应该在 Red Hat 的产品堆栈上发挥我们的作用。

作为该堆栈的一部分，OpenShift 容器应用程序平台基于 Docker 容器和 Kubernetes 容器集群管理器，用于企业应用程序开发和部署。对于做出 OpenShift 决策的公司来说，考虑 Kubernetes 如何发展以及如何发展以支持新的工作负载尤为重要。

Kubernetes 目前支持多样化和日益复杂的应用程序类别。我们可以基于微服务、批处理作业和具有持续存储需求的有状态应用程序，装载并横向扩展现代的云原生 web 应用程序。但是，仍然有机会改进 Kubernetes 并扩展其有用性和可用性。例如，增加对需要专用硬件的工作负载的支持，或者在考虑硬件拓扑结构时性能明显更好的工作负载的支持，可能会增加 Kubernetes 在许多垂直行业的采用。

## 以客户为中心的变革催化剂

 [杰里米·埃德尔

Jeremy Eder 是 Red Hat Performance Engineering 的高级首席软件工程师，他专门从事性能指标的测量和分析，并使用该分析来指导现实世界基础设施的性能调整，并领导一个高产出的工程师团队，专注于 Red Hat 产品的 Atomic 和 OpenShift 系列中基于容器的基础设施的性能、可伸缩性和容量规划，包括这些下一代技术在高性能领域的应用。Jeremy 在金融服务领域拥有十多年的经验，专注于极低延迟架构设计、调优和抖动分析。他是《Red Hat Enterprise Linux 6 和 7 的低延迟性能调优》一书的作者。Jeremy 是 Kubernetes、Docker 和 Linux 内核的贡献者，涉及许多需要快速发展的领域。他是 2014 年红帽主席奖的获得者。](https://www.openshift.com/) 

这就是 Kubernetes [资源管理工作组](http://blog.kubernetes.io/2017/09/introducing-resource-management-working.html)的作用。该小组与其他 SIG(特殊兴趣小组)一起，正在努力实现客户的愿景，同时使解决方案能够在完全集成、精心规划的端到端堆栈中良好运行。

资源管理工作组将其根源追溯到旧金山 DockerCon 1 之后不久向 [docker-dev](https://groups.google.com/forum/#!msg/docker-dev/xR_SexGtrug/vuHIy8TjRJ4J) 发送的邮件列表。

在大量的 R&D 和客户访问之后，我们开始讨论运行高性能容器的想法。但直到去年，事情才真正开始加速发展。我在内部向任何有耳闻的人推销这些想法和概念，包括几个领导委员会，并一再获得批准。

后来，德里克·卡尔，第一批在上游库本内特工作的红帽子工人之一，加入了这场争论。这些对话为在西雅图举行的 2016 年 KubeCon 大会的讨论提供了种子材料，从 [KubeCon](http://events.linuxfoundation.org/events/kubecon-and-cloudnativecon-north-america) 中产生了一个想法，即我们需要[使](https://groups.google.com/forum/#!msg/kubernetes-dev/Sb0VlXOM8eQ/La3YCe2-CgAJ)正式化。谷歌的德里克和唯帅·坎南已经开始引领潮流。

我们最近举行了第一次面对面的工作组会议，非常有成效。事实上，很难挑出最大的技术要点，但也许最有影响力和最广泛的是[资源类](https://github.com/vikaschoudhary16/community/blob/53c2a804aa6fc936baa2bf35e854c62737b58dba/contributors/design-proposals/resource-class.md)的概念。

资源类代表了一种从应用程序访问硬件资源的可移植方式，类似于久经考验的 Kubernetes 技术，称为 [StorageClasses](http://blog.kubernetes.io/2017/03/dynamic-provisioning-and-storage-classes-kubernetes.html) 。像 HugePages 和 GPU 这样的东西就属于这一类，还有更奇特的硬件，如 TPUs (TensorFlow 处理单元)和 FPGAs。随着时间的推移和新硬件的开发，设备插件和资源类的组合可以用于将功能加载到 Kubernetes 中，并提供优雅和无缝的用户体验。

事实上，CPU 是运行每个工作负载最有效的地方的日子已经一去不复返了。专用 FPGAs 和 GPU 越来越多地被用于提高性能。将专业硬件整合到一个弹性的软件定义的基础设施中是非常明智的。您不需要为了灵活性而放弃性能。

## 真实世界用例的资源类

这是一个快速发展的领域，但在最基本的层面上，资源类意味着向用户提供更细粒度的资源选择元数据。

从 Kubernetes 1.9 开始，提供对除 CPU 和内存之外的集群级资源的访问需要使用设备发现、节点标签(通过扩展资源)、选择器，甚至污点和容忍。随着我们努力实现基本的设备插件功能，用户已经认识到需要更复杂的选择标准。比如我有一个工作负载在某个型号或者厂商 GPU 上运行的最好怎么办？如果一个节点有不止一个型号的 GPU 在里面呢？如果我需要确保某个工作负载只在使用某个版本的应用编程的 FPGA 上运行，该怎么办？

虽然可以使用自制的编排脚本来实现这些功能，但是随着时间的推移，Kubernetes 可以获得其中的一些功能来提供友好的、可移植的用户体验，这是合乎逻辑的。

## 快速移动的目标

集装箱在快速移动，尤其是 Kubernetes，像火箭船一样移动。这是最受欢迎的、社区驱动的容器编排项目，这使得用户很难跟踪进度。

但是，与此同时，正是这些用户在推动我们的工作。事实上，只有通过客户的合作，我们才能确保上游发生的事情朝着真正有用的方向发展。基于与客户的对话，我向社区中的开发团队提供了上下文。我的团队还通过运行反映客户需求和目标的[基准](https://stacresearch.com/news/2017/10/31/NVDA171018)和性能测试来验证原型。

Red Hat 致力于客户宣传——与客户交谈，确定他们的需求，在社区中充当催化剂以代表他们实现功能，并提供有关社区发展方向的信息。

![](img/abd40672eff2baf60fc4b155b08a5092.png)

[红帽](https://www.openshift.com/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>