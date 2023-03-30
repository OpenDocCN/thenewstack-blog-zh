# OpenTelemetry 协议如何与 Lightstep 和 Prometheus 一起工作

> 原文：<https://thenewstack.io/how-the-opentelemetry-protocol-works-with-lightstep-and-prometheus/>

[](https://www.linkedin.com/in/ted-young/)

 [Ted Young

Ted 是 OpenTelemetry 项目的联合创始人，目前在 Lightstep 担任开发者教育总监。他住在俄勒冈州波特兰的一个小农场里。](https://www.linkedin.com/in/ted-young/) [](https://www.linkedin.com/in/ted-young/)

我们一直在努力使[指标](https://lightstep.com/metrics)遥测成为 Lightstep 不可或缺的一部分。作为这项工作的一部分，我们一直在研究数据接收的问题。与分布式跟踪不同，分布式跟踪是许多可观测性栈中相对较新的成员，自恐龙时代以来，度量一直是主干。

我们对“一次仪器化，把你的数据送到任何地方”这个问题很感兴趣但是，如果您已经进行了检测，并希望将数据发送到 Lightstep，该怎么办呢？

现实是现代系统是异构的。从一个度量系统转换到另一个度量系统并不总是容易的，遗留系统可能会以您不再希望使用的格式产生度量。这对操作人员来说是一个很大的难题，他们最终要管理一堆杂乱的遥测系统。

虽然 Lightstep 支持其他常见格式，但我们相信，当我们能够就标准协议和 API 达成一致时，我们的客户以及整个行业都会受益。这就是为什么 [Lightstep](https://lightstep.com/?utm_content=inline-mention) 是 [OpenTelemetry](http://otel.lightstep.com/) 项目的核心贡献者，我们相信遥测技术可以被简化。应该有可能有一个标准系统来优雅地处理所有类型的可观测性数据，而不管数据是在哪里和如何产生的。

## OTLP FTW

因为早期的系统倾向于只处理单一类型的数据，我们需要一个新的协议。因此 OpenTelemetry 创建了 [OpenTelemetry 协议](https://github.com/open-telemetry/opentelemetry-specification/blob/main/specification/protocol/otlp.md) (OTLP)，它支持单个数据流中的跟踪、度量和日志。Lightstep 原生支持 OTLP，目前正在与社区的其他成员一起完成 OTLP 的指标部分。

这意味着如果你能把你的数据翻译成 OTLP，你就能把它发送到 Lightstep。

下一步是编写翻译器，它将现有格式转换成 OTLP。在 OpenTelemetry 中，这种转换发生在收集器中。收集器是一个独立的服务，处理所有主要可观察性格式的接收、处理和导出。像这样的翻译和处理服务可以在现代系统中提供一些急需的粘合剂。

目前，我们正努力与 OTel 社区的其他成员合作，从 Prometheus 开始，让收集者熟悉所有的通用度量协议。

## 普罗米修斯支援

以下是 Prometheus support 目前的工作方式以及未来的路线图。

为了将普罗米修斯数据翻译成 OTLP，Lightstep 设计了[open telemetry Prometheus Sidecar](https://github.com/lightstep/opentelemetry-prometheus-sidecar)，它与普罗米修斯服务器一起运行。sidecar 读取 Prometheus WAL(预写日志)，将其转换为 OTLP，同时添加其他 OTLP 支持的元数据，例如识别仪器是计数器还是计量器。

因此，从现有的 Prometheus 部署向 Lightstep 发送数据只需将这个 sidecar 添加到您的 Prometheus 服务器部署中。这是有帮助的，但是它仍然涉及运行额外的服务。

下一步是将翻译工作转移到收集器中。我们正在将普罗米修斯边车捐赠给 OpenTelemetry，并将其转换为收集器组件。

通过将收集器作为边车运行，您的 Prometheus 服务器池可以兼作收集器池，从而获得收集器提供的所有功能。

在添加 Prometheus WAL 支持之后，收集器将转而支持 OpenMetrics 摄取，以及 Prometheus 远程写入。这种支持将允许运营商完全替换他们的 Prometheus 服务器，将其遥测系统减少到单一类型的服务。这将节省开销和复杂性，同时保持收集器提供的灵活性。

这项工作预计在 5 月底完成。想跟着去吗？所有这些工作都发生在[open telemetry Prometheus SIG](https://github.com/open-telemetry/wg-prometheus/projects/1)中，作为两个项目之间的合作成果。如果你想今天就开始使用普罗米修斯和 Lightstep，你可以在这里找到设置说明。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>