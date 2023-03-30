# Dynatrace 通过 Ruxit 预览下一代监控

> 原文：<https://thenewstack.io/dynatrace-previews-ruxit-next-gen-app-monitoring-tool-container-age/>

如果你曾经用松散的木块搭建过一堆柱子——无论是和你的孩子一起，还是在没人注意的时候，在你办公室的一个小角落里——你就知道用一块木板架起两根柱子的挑战是实现完美的平衡。这同样适用于跨代 IT 架构。

理论上，新的 IT 堆栈对旧的 IT 堆栈有以下依赖关系:zip。没有。理论上，部署到混合云的容器化应用程序不需要包含任何属于早期虚拟化时代的组件。但完美的理论世界主要存在于实验室中，关键的例外是世界上最大规模的网络公司，如脸书、Twitter 和谷歌，在这些公司中，旧的堆栈不再适用。

是的，您也可以拥有自己的原始、裸机、脸书时代的数据中心。但是，你也许可以指望一方面那些企业，那些超过 5 年的企业，实际上是这样做的。

## 平衡动作

上周在奥兰多举行的 Dynatrace Perform 2015 大会上，我和我的新 stack 同事 Alex Williams 会见了几十位每天都在使用旧 Stack 和新兴 Stack 生活和工作的人。他们的工作之一是应用程序性能管理，包括从现场的服务器和现场运行 web 应用程序的客户机(通常是 web 浏览器，但也包括 IBM WebSphere 和早期分布式应用程序的插件)中获取指标。这是 Dynatrace 的专业领域。

虽然应用程序监控已经建立，但是监控容器化应用程序的行为仍然是一门全新的、尚未完全定义的科学。Dynatrace 及其最大的竞争对手 New Relic 都利用注入服务器和客户端的代理来收集指标并向其中心报告。[其他公司，如 Sysdig](https://thenewstack.io/no-agents-needed-to-monitor-containers-says-sysdig-just-linux-kernel-changes/) ，认为在集装箱化的环境中使用代理实际上扰乱了流程。他们指出了一种可能的“观察者效应”，借用量子物理学中的一个术语来描述在亚原子水平上观察粒子的行为是如何扰乱该水平上正在发生的事情的，以至于你不可能知道你所观察到的是否是真正的自然行为。

数据中心经理(以及签署工资支票的人)对使用一种工具观察或管理传统应用程序的性能，并在另一种工具上监控容器化的应用程序不感兴趣。几年前，它们是基于“单一窗格玻璃”的理念而出售的，如果仅仅是为了简单起见，这也是理所当然的。APM 行业的最高目标是保留观察所有应用程序(WebSphere、JBoss、Oracle DB、vSphere、Hadoop 以及 Docker)的单一平台。

在 Perform 上，Dynatrace 首席技术官 Bernd Greifeneder 介绍了他的最新作品， [Ruxit](https://blog.ruxit.com/announcing-ruxit-managed/) ，这款产品整个星期都被吹捧为“下一代 Dynatrace”，直接针对[为集装箱时代](https://ruxit.com/managed-trial/)提供应用程序监控。直到最后一天，当 Bernd 透露了对 Ruxit 和他的公司的过渡计划的第一次具体了解时，与会者才确定这意味着什么。

## 反向迁移

当我们在会议的后半部分采访 Greifeneder 时，当过渡计划仍然有点神秘时，我们问 Dynatrace 结束和 Ruxit 开始在哪里？

“这实际上是个错误的问题，”格里芬尼德回答道。“实际上，重点是它们正在一步步融合在一起，走向统一。”

他解释说，Dynatrace 的当前版本包括经典的 APM 代理，该代理最近被调整为与 node . js 一起工作的[，增加了 Dynatrace 可以监控的基础设施和面向客户端的软件的](https://thenewstack.io/getting-handle-node-js-deployments-dynatrace/)[冗长列表。同时，在块的另一个支柱上，有部署在公共和混合 PaaS 平台上的应用程序，这些平台包含任意数量的语言。这些是 Ruxit 设计用来监视的。](http://www.dynatrace.com/en_us/application-performance-management/products/application-monitoring.html)

我指出，现有的 Dynatrace 生态系统已经有了一个庞大的业务交易库——已经汇总的指标，特别是为了电子商务目的，以便业务经理可以将在线活动与创收相关联。到目前为止，我们还没有看到任何证据表明 Ruxit 代理会考虑这些交易。

“关键是，在这种统一中，[开发人员和管理员]目前从 Dynatrace 接收的数据流也将出现在 Ruxit 中，并出现在他们的商业智能中，”CTO 回应道。“这意味着，这不是一个非此即彼的问题；这意味着您可以利用现有资源，还可以使用我们今天称之为 Ruxit 的数据，但它将位于统一的 Dynatrace 中。”

Dynatrace 首席执行官 John Van Siclen 从商业角度向我们讲述了这种平衡之道。他说，Greifeneder 实际上在几年前就构思并原型化了 Ruxit，作为一个监控基于云的应用的系统。最初的原型与 Dynatrace APM 毫无相似之处。在历史上的这个时候，“Dynatrace”是 Compuware 的全资子公司，还不确定 Ruxit 是 Dynatrace 的产品还是一个独立的实体。

这位首席执行官说，Greifeneder 没有为现有的 Dynatrace 客户创建某种类型的奇特迁移计划来迁移到 Ruxit，而是设想了一种反向迁移，分阶段将 Ruxit 迁移到可以集成到 Dynatrace 环境中的位置——两类代理，具有客户要求的“单一控制台”。

因此，多年来，Greifeneder 和他的 Ruxit 团队默默地改造他们的产品，实际上是逆向工作，但留下了一些面包屑，回到他们最初设想的未来状态。去年，当 Dynatrace 再次剥离成为一家独立公司时，Ruxit 团队准备将其提交给 Dynatrace 的新管理层。格里芬尼德被重新纳入麾下，“由鲁西特提供动力”的想法由此诞生。

## 优质数据

![Alex Williams speaks with Dynatrace CTO Bernd Greifeneder](img/91d30fd398eb4053c4835242ed95d628.png)

Alex Williams 采访了 Dynatrace 首席技术官 Bernd Greifeneder

为什么统一是必要的？为什么该公司不能根据自己的条件提供这两个平台？

“我们已经看到了动态环境的增长。我们看到了对更好的分析和分析的需求，”CTO 回应道。“我们还了解到，为了进行正确的分析，您必须将数据集中到一个单独的存储中，不仅如此，还要自己捕获数据，因为您需要一流的数据。”

Greifeneder 通过提供一个通用数据提要的统计相关性的例子来解释这个术语。在这种情况下，来自服务器的典型数据流将包括服务器端指标，如 CPU 利用率和响应时间，每五分钟以聚合形式发送一次。如果将通用算法应用于这些数据批次，观察者最多只能推测*CPU 峰值与响应时间变化相关。*

 *Greifeneder 说，这种通用的方法是失败的，因此数据流必须变得更细粒度，更少聚合，从而达到“第一质量”

“只有这样，我们才能在正确的位置上进行分析，超越任何其他通用方法，”Greifeneder 说。

Dynatrace 还生产一款名为[数据中心真实用户监控](http://www.dynatrace.com/en/products/data-center-real-user-monitoring.html)或 DC 朗姆酒的[网络监控工具](https://thenewstack.io/category/monitoring/)。它也将被纳入 Dynatrace 统一中。

“这是统一的一部分。这不会疏远我们现在的客户，因为我们将他们的用例向前推进…当然，这是一个旅程。并不是每件事都[马上]完美地统一起来，但这是我们的方法，”格里芬尼德说。

Dynatrace 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*