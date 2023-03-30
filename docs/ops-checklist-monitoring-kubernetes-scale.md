# 大规模监控 Kubernetes 的操作清单

> 原文：<https://thenewstack.io/ops-checklist-monitoring-kubernetes-scale/>

根据设计， [Kubernetes](/category/kubernetes/) 开源容器编排引擎不是自我监控的，一个裸安装通常只有您需要的监控工具的一个子集。在之前的一篇文章中，我们根据[肯赞](https://kenzan.com/)的建议，介绍了[大规模监控 Kubernetes 生产的五种工具](https://thenewstack.io/5-tools-monitoring-kubernetes-scale-production/)。

然而，您的组织选择用来监控 Kubernetes 的工具集只是等式的一半。您还必须知道要监控什么，在哪里设置流程以吸收监控结果，以及如何采取相应的纠正措施。最后一项经常被开发团队忽略。

所有 Kubernetes 组件——容器、pod、节点和集群——都必须包含在监控操作中。让我们来了解一下每一项的监控要求。

## 监控容器

 [肯赞·克雷格·马丁

克雷格·马丁(Craig Martin)是肯赞的工程界 SVP，他领导着工程运营部门，自称的使命是找到应对复杂挑战的优雅解决方案。在他的职位上，Craig 帮助领导公司的技术方向，确保探索新的和新兴的技术并将其纳入战略愿景。最近，克雷格一直专注于通过构建大规模微服务应用来帮助公司进行数字化转型。他长期从事专业服务领域的定制软件开发，在加入 Kenzan 之前，Craig 是 Flatiron Solutions 的工程总监。他在乔治梅森大学获得了理学学士学位。](http://kenzan.com/) 

容器是 Kubernetes 生态系统中最底层的实体。这一级别的监控不仅对于容器化应用程序的健康是必要的，而且对于确保伸缩正常进行也是必要的。Docker 提供的大多数指标都可以用于监控 Docker 容器，您也可以利用许多传统的监控工具(例如， [Datadog](https://www.datadoghq.com/) ， [Heapster](https://github.com/kubernetes/heapster) )。Kenzan 倾向于关注最底层的数据，以帮助确定每个单独容器的健康状况；例如:

1.  CPU 利用率:呈现为每分钟、每小时或每天的平均值。
2.  内存利用率:呈现为每分钟、每小时或每天的平均使用/限制。
3.  网络 I/O:确定网络中的任何主要延迟，因为网络延迟常常会放大流量峰值的影响。监视 I/O 还可以发现在应用程序中进行更好的缓存或断路的机会。

[cyclone slider id = " kubernetes-series-book-1-赞助商"]

这三个类别将揭示容器是否正在承受压力，容器级别的延迟在哪里，以及是否在需要时进行扩展。

## 监控舱

Pods 是 Kubernetes 围绕容器(或多个容器)的抽象层。这是 Kubernetes 将自我扩展和修复的层。豆荚定期出现和消失。您可能会发现在 pod 级别最有用的监控类型涉及这些 pod 的生命周期事件。您可以从这种监控中获得的数据可能非常有用，有助于了解您的扩展是否正确，峰值是否得到处理，以及 pod 是否正在进行故障切换但会自我纠正。

许多数据可以从 Kubernetes 获取；对 Kubernetes 文档的深入研究将会得到完整的列表。以下是 Kenzan 的经验告诉其团队要关注的内容:

*   规模事件发生在圆荚体被创造和存在的时候。这些事件从更高的层面展示了应用程序如何处理规模。
*   荚果终止有助于了解哪些荚果被杀死及其原因。有时终止是由于负载波动，而其他时候，如果简单的健康检查失败，Kubernetes 可能会杀死 pod。在你的头脑中把这两者分开是至关重要的。
*   集装箱重新启动对于监控箱内集装箱的健康是重要的。
*   过长的启动时间间隔是不健康应用程序的常见信号。容器应该很快旋转起来，然后消失。

如果你保持你的监控简单而整洁，那么管理起来就容易多了。当您需要更深入地研究指标时，您可以依赖像 [Grafana](https://grafana.com/) 这样的服务提供的定制仪表板。

## 监控集群

涉及监视生产系统的进程要么彼此足够相似，要么逐渐变得相似，特别是关于这些进程正在寻找什么数据。但是监控这些不同组件的理由会有所不同。在集群级别，我们倾向于更全面地看待应用程序。我们仍然在监视 CPU、内存利用率和网络 I/O，但是是针对整个应用程序的行为。

当一个应用程序的扩展超出了其配置的内存和 CPU 分配时，我们经常会看到一个集群失败。弹性应用程序提出了一个独特的挑战:它将继续扩展，直到无法再扩展。因此，您得到的唯一真实信号是彻头彻尾的失败，通常是在集群级别。由于这个独特的原因，密切监视每个集群非常重要，在集群故障发生之前寻找它们的信号。

我们做了一种时间序列分析，其中我们监控四个关键变量:

1.  总体群集 CPU 使用率
2.  每个节点的 CPU 使用率
3.  总体集群内存
4.  每个节点的内存使用量

虽然相对较少，但每个节点的 CPU 使用率可以揭示一个节点的性能严重低于其他节点，而每个节点的内存使用率可以揭示路由问题或负载共享问题。使用时间序列分析，你应该能够在一个启发式图表上画出这些变量。

## 监控网络

随着越来越多的应用转向采用微服务的弹性应用，人们很容易忽视它们对网络健康运行的依赖程度。在性能不佳的网络上，高弹性的微服务应用程序永远不会平稳运行。再多的防御性开发或自动修复都无法让它正常运行。

[cyclone slider id = " kubernetes-series-book-1-赞助商"]

这就是我们非常重视网络监控的原因。幸运的是，像 Heapster 这样的工具可以捕获网络及其性能的指标。虽然我们通常发现这些指标对于发现瓶颈是有用的，但是它们对于诊断根本原因还不够。这需要进一步挖掘网络特定的应用。

我们通常喜欢监控几个项目，并发现将传输和接收分开很有用:

*   Bytes received over network 显示指定时间范围内的字节数。我们通常在这个系列中寻找峰值。
*   通过网络传输的字节揭示了传输流量和接收流量之间的差异，这非常有用。
*   网络收到的错误揭示了网络在指定的持续时间内丢失的数据包或错误的数量。
*   网络传输错误告诉我们传输中发生的错误数量。

您对 Kubernetes 环境基础的洞察力将取决于您的指标。我们建议您定期收集调查结果，并制定可行的计划来解决您发现的问题。行动计划需要针对应用程序、Kubernetes 环境或运行它的平台。值得注意的是，团队往往会忘记这个反馈循环的重要性。

## 描摹

微服务面临的最大挑战之一是监控服务之间的所有通信流。了解容器、pod 和集群内部发生的事情是有用的，但是了解应用程序组件之间发生的事情是至关重要的。这就是分布式跟踪系统非常有用的地方。像 [Zipkin](https://zipkin.io/) 或 [Jaeger](https://uber.github.io/jaeger/) 这样的工具是跟踪单个线程的常用工具，可以用来将数据推入监控或仪表板工具。

虽然可以写一整篇关于分布式跟踪系统的文章，但它是一个非常有用的工具，可以帮助我们发现服务之间的瓶颈，监控调用之间的 SLA，并跟踪各个调用在系统中处理的数据流。分布式跟踪确实会给使用它的线程带来性能损失。我们通常建议采用抽样(例如 10%)方法进行跟踪，以便将对最终用户的影响降至最低。

管理 Kubernetes 项目的云计算原生计算基金会(Cloud Native Computing Foundation)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>