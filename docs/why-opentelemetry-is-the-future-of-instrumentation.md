# 为什么 OpenTelemetry 是仪器仪表的未来

> 原文：<https://thenewstack.io/why-opentelemetry-is-the-future-of-instrumentation/>

[云原生计算基金会](http://cncf.io/)和[新遗迹](https://newrelic.com/)赞助了这篇文章，期待虚拟 [KubeCon + CloudNativeCon 北美 2020–虚拟](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)，11 月 17-20 日。

 [拉旺亚·乔卡林加姆

Lavanya 是 New Relic APM 产品的高级产品营销经理。她开始职业生涯时是一名工程师，然后转到销售和产品营销岗位。](https://www.linkedin.com/in/lavanya-chockalingam-6a21b738/) 

今天，公司在软件开发的各个方面都在快速地拥抱开源；而监控空间也没有什么不同。工程师可以使用许多工具来测量他们的堆栈的性能，开源是这个工具爆炸的核心。

除了工具之外，标准正在出现并改变团队实现工具的方式。开发 OpenTracing 和 [OpenCensus](https://opencensus.io/) 是为了标准化团队如何获取踪迹和指标。虽然这两个标准都实现了让许多人容易观察的目标，但一个基本问题仍然存在:它们是两个独立的标准。对于分布式追踪来说，拥有一个标准尤为重要，因为如果因果链中的一个点被破坏，追踪就不再完整。

[OpenTelemetry](https://blog.newrelic.com/product-news/what-is-opentelemetry/) 是一个开源项目，是服务工具的统一标准。由[云本地计算基金会(CNCF)](https://www.cncf.io/) 赞助，它取代了 OpenTracing 和 OpenCensus。OpenTelemetry 项目由各种语言(如 Java、Go 和 Python)的规范、API 和 SDK 组成。它还定义了一个集中的收集器和导出器，将数据发送到各个后端。这一标准得到了许多领先监控公司的支持，他们都认为这是仪器仪表的未来。

[https://www.youtube.com/embed/yY6hHhiDths?feature=oembed](https://www.youtube.com/embed/yY6hHhiDths?feature=oembed)

视频

以下是 OpenTelemetry 改变仪器仪表的四个原因:

### **1。无处不在的仪器仪表**

随着技术的发展，一个供应商很难构建集成来提供获得完整的端到端可见性所需的深度和广度。开源解决方案周围有蓬勃发展的社区，它们被支持和改进解决方案的共同动力所束缚。这种社区驱动的方法可以更快地引入新概念和新功能；这种方法通常比专有解决方案更有效。作为一种开放标准，OpenTelemetry 鼓励广泛的合作，并促进更好的覆盖范围、灵活性和普遍性，因为来自世界各地的工程师都为仪器做出了贡献。

### **2。互操作**

现代环境是分布式的，也更加复杂，在这样的环境中有效地管理性能是一个巨大的挑战。为了理解服务和应用程序的集体行为，您需要跨所有编程语言对所有框架和库进行检测。如果应用程序中的所有服务都没有标准工具，您将会有影响故障排除的盲点或数据孤岛，从而降低您快速检测和解决问题的能力。OpenTelemetry 通过提供跨所有服务的标准形式的仪器，弥补了可见性的差距，具有完全的互操作性。

### **3。供应商中立**

大多数专有监控解决方案要求您安装各自的仪器代理来收集遥测数据。如果您切换到不同的供应商，您的工程师必须花费更多的时间和资源来安装不同的专有代理或重新检测代码。您经常被供应商配置和路线图优先级所束缚。OpenTelemetry 提供了一种厂商中立的工具，因此您可以全面了解源代码，并了解社区是如何开发功能和解决 bug 的。拥有改变后端的灵活性而不必改变你的工具是很重要的。

### **4。未来证明**

随着新技术的出现，它们各有利弊。这些技术带来的灵活性、规模和效率的提高是以监控复杂性的增加为代价的。这意味着，要监控新兴技术，您要么必须定制仪器，要么等待专有供应商来构建集成。OpenTelemetry 旨在通过将仪器构建到库和框架中来解决这个问题，以便当新技术出现时，您可以轻松地监控它们，而不必等待供应商添加支持。

## **今天就开始探索 OpenTelemetry】**

OpenTelemetry 将于 11 月全面上市，所以现在是在您自己的应用程序和服务上开始试验它的最佳时机。对您已经熟悉的服务进行试验将会给您信心，让您的仪器经得起未来的考验。如果您想尝试，请查看我们的在线精品云原生微服务演示应用[,它有两个使用 OpenTelemetry SDKs 的服务:FrontEnd(在 Go 中)和 AdService(在 Java 中)。](https://github.com/newrelic-forks/microservices-demo)

*要了解更多关于 Kubernetes 和其他云原生技术的信息，请考虑参加 11 月 17 日至 20 日在 T4 举行的 [KubeCon + CloudNativeCon 北美 2020 大会。](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)*

云计算原生计算基金会和亚马逊网络服务是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>