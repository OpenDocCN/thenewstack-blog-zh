# Lightstep 的 OpenTelemetry 发射器简化了代码行的集成

> 原文：<https://thenewstack.io/lightsteps-opentelemetry-launchers-simplify-integration-to-line-of-code/>

[Lightstep](http://www.lightstep.com) 已经发布了前四款[open telemetry launcher](https://github.com/search?q=org%3Alightstep+launcher)，从 [Go](https://github.com/lightstep/otel-launcher-go) 、 [Python](https://github.com/lightstep/otel-launcher-python) 、 [Node](https://github.com/lightstep/otel-launcher-node) 和 [Java](https://github.com/lightstep/otel-launcher-java) 开始，该公司声称这些“使工程师能够在几分钟内理解复杂的系统，只需一行代码。”更具体地说，这些发射器使开发人员能够快速将 Lightstep 连接到 [OpenTelemetry 的](https://opentelemetry.io/)开源观测工具，Lightstep 首席技术官 [Daniel Spoonhower](https://www.linkedin.com/in/spoons/) 强调，这有助于用户在选择可观测性平台时避免供应商锁定。

“使用像 New Relic 或 AppDynamics 这样的工具，您可以运行一段与您的应用程序相耦合的专有代码，通常称为代理。那个东西实际上是供应商工具的一部分。购买这些工具的人投入了大量的工作，这在很多方面锁定了他们。当他们想要构建新的功能时，这就要求他们也对代理进行修改，所以他们最终会在 it 方面投入大量的工作。“OpenTelemetry 是这一过程的发展，在这一过程中，性能数据的提取成为一种开源工具，”Spoonhower 说。

Lightstep 始于 2015 年，此后[一直专注于微服务和分布式应用的可观察性、性能管理和分析](https://thenewstack.io/lightstep-brings-performance-management-microservices/)。Spoonhower 解释说，Lightstep 不仅仅是提供观察工具，而是帮助分析从度量、日志、跟踪和其他数据中收集的复杂信号，并找到可能发生的事情的原因。

“当应用程序是一个整体时，如果出现问题，很容易指出发生了什么，因为应用程序中的变化非常小。Spoonhower 解释说:“本周发布了一个版本，所以这可能是问题所在，但在一个更松散耦合、更分布式的应用程序中，有太多的东西一直在变化，这些东西相互依赖，人类很难搞清楚这一点。

OpenTelemetry 是一个[云本地计算基金会(CNCF)](https://www.cncf.io/) 沙盒项目，是一个 API、库、代理和收集器服务的开源集合，用于捕获分布式跟踪和指标，并将它们导出到观察工具。该项目于去年开始，由 Lightstep 在 2016 年最初创建的分布式追踪项目 [OpenTracing](https://opentracing.io/) 和谷歌在 2018 年创建的以度量为中心的便携式仪器项目 [OpenCensus](https://opencensus.io/) 合并而成。虽然 OpenTelemetry 提供了厂商中立的工具来将遥测数据从云原生应用程序中取出，并放入 Lightstep 等分析工具中，但该过程仍然需要一些专业知识。这就是 Lightstep 发射器的用武之地。

“OpenTelemetry 是这种通用格式，但它就像电源插座的规格。你仍然必须考虑如何将所有的电线与你的公用设施连接起来，”斯普豪说。“您可以将我们所做的视为即插即用，我们已经为您选择了一系列组件。反正他们都在你的墙后面，所以你不会真的想了解他们，但我们已经为你打包了这些东西。”

除了将 Lightstep 与 OpenTelemetry 的连接过程压缩到一行代码中，Spoonhower 还表示，还有“发生在引擎盖下的健全性检查”来帮助用户正确配置他们的连接。不仅 OpenTelemetry 需要一定水平的专业知识和熟悉程度，而且你可能与之连接的每个供应商也是如此，Lightstep 本质上是尽可能地为其用户简化这一过程，但 Spoonhower 表示，这些发射器是朝着使 OpenTelemetry 更容易访问的方向迈出的一步。

“转向开放式遥测技术在给人们带来灵活性方面很棒，只是随之而来的是一些成本。我们希望人们使用 OpenTelemetry，无论他们是否使用 Lightstep，”Spoonhower 说。“我们希望他们有一个良好的体验，这是我们帮助实现这一愿景的一种方式。我们认为我们是 OpenTelemetry 的最佳选择，但我们会让您选择。我们仍将帮助你思考开放式遥测技术以及如何实现，发射器是其中的一部分。”

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>