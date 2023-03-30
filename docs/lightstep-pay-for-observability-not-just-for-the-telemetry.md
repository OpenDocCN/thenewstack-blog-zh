# Lightstep:为可观测性买单，而不仅仅是遥测

> 原文：<https://thenewstack.io/lightstep-pay-for-observability-not-just-for-the-telemetry/>

在 [Lightstep](https://lightstep.com/) 的首席执行官兼联合创始人[本·西格曼](https://www.linkedin.com/in/bensigelman/)看来，用户不应该为系统指标付费。对于监控微服务来说，遥测应该是一种商品。增值应该伴随着可观察性，或者说监控服务使最终用户快速识别和解决分布式系统中的问题变得更加容易。

“Lightstep 的意见是，你永远不应该为遥测技术支付利润，你应该继续控制这笔开支。它实际上只是一种你应该控制的商品，”西格曼说。“在现在的市场上，人们收到了非常非常大的遥测账单。它甚至不是为了可观测性，它真的只是为了遥测。”

[Lightstep](http://www.lightstep.com/) 声称，该公司正在将其核心平台从分布式跟踪扩展到更大的指标阵列，这是一套允许开发人员更快发现性能问题的功能。

“我们的目标是以最快的方式找出系统和系统内的服务发生了什么变化，”Sigelman 说。“长期以来，我们在分布式寻人方面一直处于领先地位。但单靠分布式追踪不足以让我们完全回答某些问题。”

分布式跟踪平台的新兴但不断增长的市场包括其他初创公司，如 [Honeycomb](/honeycomb-addresses-flawed-systems/) 和 [Datadog](/datadog-monitors-scalable-systems/) ，以及成熟的应用性能管理提供商，如 [New Relic](/why-new-relic-supports-w3cs-distributed-tracing-protocol/) 。

Lightstep 的更新是该公司将可观测性定义为一种服务的整体战略的一部分，这种服务超越了通过遥测技术简单收集指标的范围。

“人们在某种程度上被编程为相信遥测是可观测的，而实际上它只是原材料，”西格曼说。当谈到[遥测与可观测性](https://thenewstack.io/monitoring-vs-observability-whats-the-difference/)时，西格曼补充道，“我认为我们正试图改变人们对空间的看法，将遥测视为他们可以控制的商品，将可观测性视为他们建立在遥测基础上的价值工具。”

[https://www.youtube.com/embed/YQ7PH3EcQbU?feature=oembed](https://www.youtube.com/embed/YQ7PH3EcQbU?feature=oembed)

视频

Lightstep 已经建立了从 [OpenTelemetry](https://opentelemetry.io/) 项目收集的指标，尽管它认为它的价值在于它提供的工作流可以更好地查明问题，并使每月的监控账单保持合理。它允许用户设置约束条件，并为他们在遥测技术上实际花费设置预算。西格曼说，Lightstep 软件将“从遥测技术角度来看，在预算范围内大小合适”。

错误和延迟分析是一项新功能，它可以在问题通过调用堆栈传播时突出显示问题，并提供一个数据驱动的假设列表，说明问题出在哪里。该更新还提供了运行时指标，允许软件将指标与服务性能中的问题相关联。

通过在无需额外配置的情况下访问运行时指标，并提供并行的性能指标可见性，开发人员能够快速确定其运行时中的问题(例如，垃圾收集、CPU 或内存增加)是否会导致服务降级。回归分析可以自动显示导致错误和延迟增加的原因。

该公司的核心资产之一是关联引擎，它可以只过滤与特定回归相关的基础设施指标，如 CPU、内存、垃圾收集以及延迟等推断指标。“另一种方法是只显示一页又一页的图表，这是一个相当低的信噪比，”他说。

*想了解更多关于这种方法的信息，请收听 Lightstep 首席执行官兼首席技术官丹尼尔·斯普恩豪的播客[:](https://www.linkedin.com/in/spoons/)*

[light step CTO Daniel spoon hower——可观察性的三大支柱](https://thenewstack.simplecast.com/episodes/lightstep-cto-daniel-spoonhower-the-3-pillars-of-observability)

Lightstep 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>