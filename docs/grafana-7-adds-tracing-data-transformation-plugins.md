# Grafana 7 增加了跟踪，数据转换，插件

> 原文：<https://thenewstack.io/grafana-7-adds-tracing-data-transformation-plugins/>

本周发布的 Grafana 7.0 将跟踪引入了可观察性平台，完善了对可观察性三大支柱的支持。该更新还允许用户动态转换数据，并为任何语言的新数据源创建插件。

Grafana Labs 的联合创始人兼首席执行官 [Raj Dutt](https://www.linkedin.com/in/radutt) 说[的发布](https://grafana.com/blog/2020/05/18/grafana-v7.0-released-new-plugin-architecture-visualizations-transformations-native-trace-support-and-more/?isource=hp)是“公司历史上最具纪念意义的发布”。

Dutt 在一次采访中说，这些根本性的变化中的第一个是增加了跟踪数据，这是在 Grafana 6 通过 Loki，Elastic Search 和 Splunk 增加了日志数据之后。Grafana 7.0 将为 [Jaeger](https://www.jaegertracing.io/) 和 [Zipkin](https://zipkin.io/) 开源跟踪工具提供开箱即用的支持，Dutt 表示，该公司预计将“为各种其他供应商和项目添加跟踪支持，如 New Relic、Dynatrace、AppDynamics 等。”

Dutt 解释说，通过将所有这三种可观察能力放在一个平台上，这“允许人们创建一种将三者联系在一起的体验，我们认为这种体验非常强大。如果有人在凌晨三点收到警报，他们可以在 Grafana 内部无缝地从指标切换到日志，从日志切换到跟踪，而不必切换上下文，也不必转置不同的查询或从一个系统登录到另一个系统。”

[https://www.youtube.com/embed/oE56TTqpcQU?feature=oembed](https://www.youtube.com/embed/oE56TTqpcQU?feature=oembed)

视频

Grafana 7 的三个主要更新中的第二个涉及 observability platform 自己转换数据的能力，而不是依赖于它所连接的数据库或数据源的能力。Dutt 表示，这有助于为用户提供数据操作，否则可能会缺乏数据操作。

“传统上，Grafana 一直致力于可视化数据，但我们利用我们连接的数据库来调整和微调我们随后可视化的查询。现在，你实际上可以在数据在 Grafana 内部可视化之前对其进行处理，”Dutt 说。“这是 Grafana 的一项基本功能改进，使其更加强大，特别是当人们从可能没有非常复杂的查询语言或分析能力的地方引入数据时。”

最后，Grafana 7 希望通过引入新的插件框架，大幅增加可以导入数据的数据源数量，Dutt 表示，该框架允许用户用任何他们想要的语言创建插件——从 C 到 Java 到 JavaScript React。

“Grafana 有大约 50 种不同的数据源，我们支持这些数据源，所以如果你的数据存在于这 50 种不同类型的数据库或供应商中，那么我们可以非常容易地将其引入，”Dutt 解释道。“我们有一个全新的插件框架，让社区开发自己的数据源和可视化插件变得非常非常容易。这意味着已经相当大的格拉法纳生态系统将会爆炸。从任何地方获取数据都要容易得多，因为如果一个插件还不存在，那么创建一个插件就变得几乎微不足道了。”

[https://www.youtube.com/embed/p-UWg_A41j0?feature=oembed](https://www.youtube.com/embed/p-UWg_A41j0?feature=oembed)

视频

AppDynamics、Dynatrace 和 New Relic 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>