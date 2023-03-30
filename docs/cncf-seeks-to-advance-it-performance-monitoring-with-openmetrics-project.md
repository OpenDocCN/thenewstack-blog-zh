# CNCF 寻求通过 OpenMetrics 规范推进 IT 性能监控

> 原文：<https://thenewstack.io/cncf-seeks-to-advance-it-performance-monitoring-with-openmetrics-project/>

[云原生计算基金会](http://cncf.io/) (CNCF)已经承担了一个项目，以标准化和推进云原生应用的性能指标报告方式。

基于来自 CNCF[普罗米修斯监控工具](https://thenewstack.io/microservices-monitor-prometheus-emerges-from-cncf-incubation/)的[数据模型](https://github.com/prometheus/docs/blob/master/content/docs/instrumenting/exposition_formats.md),[open metrics](http://openmetrics.io/)开源规范试图提供一种以文本表示或二进制协议缓冲区的形式格式化和大规模传输性能指标的方法。它将提供一种中立的指标展示格式，一种不依赖于当今 It 性能监控工具中使用的现有分层数据模型的格式，云原生用户声称，这些工具通常是专有的和/或难以实施的。

SpaceNet 的技术架构师、普罗米修斯团队成员、OpenMetrics 的创始人理查德·哈特曼(Richard Hartmann)说:“监控[工具]正在传输的数据模型的基本假设与他们以前的做法完全不同。“我们正在摆脱这种分层模型，在这种模型中，数据是如何移动的，我们正在转向一种完全 n 维的矩阵，”他说，这种矩阵将更容易对数据进行切片和切块，以供进一步分析。

哈特曼说，这些变化是必要的，以体现微服务给性能监控带来的新的复杂水平。“我们从追逐复杂性(其他监控工具也是如此)转向真正拥抱和控制复杂性。”

Prometheus 将迁移到这个 OpenMetrics 模型，InfluxData、Sysdig、Weave 和 OpenCensus 的面向微服务的监控软件也将迁移到这个模型。

除了来自 Prometheus 团队的输入，该项目还包括来自谷歌公司 Stackdriver 和 Bogmon 内部监控软件的输入。该项目的贡献者包括来自 AppOptics、Cortex、Datadog、Google、InfluxData、OpenCensus、Prometheus、Sysdig 和优步的工程师。

“OpenMetrics 是对当前混合格式的巨大改进，将使系统之间更具互操作性。优步度量和系统监控负责人 Rob Skillington 在 CNCF 的博客文章[中宣布了该项目](https://www.cncf.io/blog/2018/08/10/cncf-to-host-openmetrics-in-the-sandbox/)。“使用这一标准，复杂的软件和数据中心将变得更容易观察、监控和运行，这使得工具更容易协同工作，中小型组织将需要投入更少的时间来进行一流的监控。”

OpenMetrics 在沙盒级别加入了 [CNCF 稳定团队](https://www.cncf.io/projects/)，这是早期项目[的家园](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc)。该项目由 CNCF 技术监督委员会成员 [Alexis Richardson](https://twitter.com/monadic?lang=en) 和 [Bryan Cantrill](https://twitter.com/bcantrill?lang=en) 发起。

CNCF 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>