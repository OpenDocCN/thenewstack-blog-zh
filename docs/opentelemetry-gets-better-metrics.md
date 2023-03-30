# OpenTelemetry 获得更好的指标

> 原文：<https://thenewstack.io/opentelemetry-gets-better-metrics/>

西班牙巴伦西亚——open telemetry 被它的创造者定义为一个 API 集合，用于测量、生成、收集和导出遥测数据以实现可观测性。这些数据以度量、日志和跟踪的形式出现，并且已经成为一个流行的 CNCF 项目。在本次采访中，我们将深入探讨 OpenTelemetry 及其刚刚全面推出的指标支持。

为 metrics 协议提供的规范旨在将 metrics 连接到其他信号，并提供一条通向 OpenCensus 的路径，使客户能够迁移到 OpenTelemetry，并使用现有的 metrics-instrumentation 协议和标准，当然包括 Prometheus。

在这一集的 [新栈制造者播客](/tag/the-new-stack-makers) 中，录自秀场上的[kube con+CloudNativeCon Europe 2022](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)[摩根麦克林](https://ca.linkedin.com/in/morganmclean) 产品管理总监[Splunk](https://www.splunk.com/fr_fr)， [light step](https://lightstep.com/)和[Daniel Dyla](https://www.linkedin.com/in/danieldyla)，高级开源架构师， [Dynatrace](https://www.dynatrace.com/) 讨论了 OpenTelemetry 是如何发展的，以及 DevOps 的可观测性的魔力。

[OpenTelemetry 获得更好的指标](https://thenewstack.simplecast.com/episodes/opentelemetry-gets-better-metrics)

OpenTelemetry 可以被描述为用户需要从基础设施中提取的工件、数据和信息的标准。“它通常集中在后端基础设施上，现在的状况是分布式跟踪已经成熟并普遍可用了一年多，”McLean 说。随着度量标准的全面推出，日志支持将于今年晚些时候推出

杨说，OpenTelemetry 的想法也是“可观测性-工具不可知的”。“从第一天开始，我们的一大重点就是不要试图选择赢家或类似的事情，”杨说。“任何想要提供任何开源工具的供应商都可以在 OpenTelemetry collector 中实现一个接收器或插件，并开始处理数据。”

[https://www.youtube.com/embed/Qczve1sGaBc](https://www.youtube.com/embed/Qczve1sGaBc)

视频

归根结底，人们普遍认为，没有准确可靠的可观测性数据，很难进行任何深度分析。Dyla 说:“不同的 DevOps 和 CI/CD 技术和工具“很好”，但良好、可靠和准确的数据是所有这些技术和工具的先决条件。在数据出来之前，你什么也做不了。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>