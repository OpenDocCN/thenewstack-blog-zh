# OpenTelemetry 可观测性入门

> 原文：<https://thenewstack.io/getting-started-with-opentelemetry-for-observability/>

查尔斯·马勒

查尔斯是 InfluxData 网站的技术营销作家。Charles 的背景包括从事数字营销和全栈软件开发。

对于大多数开发人员来说，软件开发意味着几乎所有东西都有一个 API，硬件通过云提供，核心焦点是只构建对您的业务最重要的功能。

当然，所有这些集成和现代分布式架构都产生了自己的一系列问题。对您的应用程序有全面的了解变得更加重要，现在通常被称为可观察性。能够收集这种洞察力所需的数据本身就是一个挑战，因此，我们看到许多主要的技术公司共同努力，通过一个名为 [OpenTelemetry](https://opentelemetry.io/) 的项目来创建一个标准化的框架，以简化遥测数据的收集。

## 什么是 OpenTelemetry？

使用 [OpenTelemetry 规范](https://github.com/open-telemetry/opentelemetry-specification/)，OpenTelemetry 可以被描述为一组工具、API 和 SDK，用于生成和收集数据，包括指标、日志和跟踪，以帮助分析您的软件的性能和行为。OpenTelemetry 由 OpenCensus 和 OpenTracing 项目合并而成，是与[云本地计算基金会(CNCF)](https://www.cncf.io/) 的一个孵化项目。

OpenTelemetry 的目的是简化遥测数据的收集和管理，使开发人员能够采用可观测性最佳实践。OpenTelemetry 得到了科技行业一些大公司的支持，微软、谷歌、亚马逊、红帽、思科和许多其他公司也做出了积极贡献。

## OpenTelemetry 有什么好处？

那么，为什么会有这么多公司采用 OpenTelemetry 呢？根据您使用的是可观察性工具还是供应商，好处略有不同，但总的来说，结果是每个人都有一个更好的软件生态系统。

OpenTelemetry 的最大好处是它提供了一个标准的独立于供应商的接口。对于用户来说，这意味着你不必担心被一个可观察性工具所束缚，因为移植需要大量的代码修改。对于供应商来说，这意味着最好的服务将会胜出，因为新来者需要克服的障碍更少了。只要厂商支持 OTEL，他们就能获得新用户。这将推动可观测空间的创新和改进。OpenTelemetry 甚至会在开源生态系统中制造竞争。许多库和框架已经将 OTEL 支持嵌入到他们的项目中，因此开发人员可以开箱即用地获得遥测数据。

另一个好处是 OTEL 支持度量、跟踪和日志形式的三种主要遥测数据。这节省了开发人员的时间，因为他们不需要使用不同的工具或库来收集这些数据；他们可以用 OTEL。像自动仪器这样的特性也使得 OpenTelemetry 可以添加到应用程序中，在许多情况下甚至不需要修改代码库。

灵活性和易用性可能是 OpenTelemetry 的最大优势。该项目从头开始设计，旨在与云原生应用程序和现代架构协同工作。无论一个开发者在做什么，都有一个集成 OpenTelemetry 的方法。从长远来看，让遥测数据的收集变得更容易将会为每个人带来更高质量的软件。

## 打开遥测功能

### 多数据类型支持

OpenTelemetry 旨在支持三种主要类型的遥测数据:度量、日志和跟踪。度量和跟踪的规范目前是稳定的，尽管日志规范仍被认为是实验性的，但预计将在 2022 年的某个时候最终确定。

### API 和 SDK

OpenTelemetry APIs 和 SDK 是该项目的特定于编程语言的部分。API 用于检测您的应用程序代码并生成遥测数据。SDK 充当 API 和将遥测数据导出到目的地之间的桥梁。SDK 可用于在导出之前过滤或采样数据。SDK 还允许将数据导出到多个目的地，因此可以将不同的数据类型(如指标或跟踪)发送到更专业的工具。

### 打开遥测收集器

OpenTelemetry Collector 可以作为不同后端的直接进程内导出器的替代方案。OTEL 收集器是完全独立于供应商和语言的。这意味着您可以从任何语言 SDK 向收集器发送数据，并将数据导出到任何受支持的后端，而无需修改任何应用程序代码，并且您不必将额外的包导入到您的应用程序中。

OTEL 收集器由三个主要部分组成:接收器、处理器和输出器。这些组件可以被认为是一个管道，它们可以使用 YAML 文件进行配置。收集器有两个[部署](https://opentelemetry.io/docs/collector/deployment/)选项。它可以作为代理部署，作为 sidecar 代理或二进制文件在每个应用程序实例上运行，也可以作为网关部署，网关是从多个应用程序实例接收遥测数据的独立服务。

### 开放式遥测仪器

仪表化是连接应用程序的过程，因此它实际上是在生成遥测数据。OpenTelemetry 为 11 种流行的编程语言提供了特定于语言的实现。这些库可以导入到您的应用程序中，您可以编写代码来检测您的应用程序。

自动仪器是另一种选择。这些是社区或供应商提供的工具，允许您导出 OTEL 遥测数据，而不必进行任何手动代码更改。每种编程语言的许多最流行的框架和库已经支持自动插装。以 Python 为例，Flask 和 Django 都有可用的自动检测包，这里有完整的 repo。

## 如何使用您的 OpenTelemetry 数据

那么，一旦你收集了这些数据，你应该怎么做呢？让我们来看几个使用案例和工具，您可以使用 OpenTelemetry 从您的数据中获得价值。

### 存储您的数据

你需要考虑的第一件事是你将在哪里导出和存储你的遥测数据。您选择的[数据存储](https://www.influxdata.com/time-series-database/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06_spnsr-ctn_getting-started-opentelemetry_tns)将取决于您将要存储的[数据](https://www.influxdata.com/what-is-time-series-data/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06_spnsr-ctn_getting-started-opentelemetry_tns)的数量、存储时间以及查询数据的频率。如果您只存储相对少量的数据，您可以使用更通用的解决方案。另一方面，如果您要存储大量数据并对这些数据进行大量查询，那么使用更专业的解决方案可能更有意义。

存储遥测数据时可以考虑的一些选项:

*   **搜索数据库** —这些数据存储是为文本搜索而设计的，对于分析日志非常有用。Elasticsearch 或 Solr 将是一个[搜索数据库](https://www.influxdata.com/search-engine-database/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06_spnsr-ctn_getting-started-opentelemetry_tns)的开源例子。一个[内存数据库](https://www.influxdata.com/in-memory-database/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06_spnsr-ctn_getting-started-opentelemetry_tns)比如带有 Redis 搜索模块的 Redis 也是一个选择，如果它适合你的架构的话。
*   **时序数据库** —时序数据库旨在存储大量正在写入的数据，并跨时间范围查询数据，这是在处理其他数据库难以高效查询的指标时经常使用的查询类型。时序数据库也很适合[日志和跟踪数据](https://www.influxdata.com/blog/why-you-cant-afford-to-ignore-distributed-tracing-for-observability/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06_spnsr-ctn_getting-started-opentelemetry_tns)。
*   **多种数据库组合** —没有理由将自己局限于单个存储选项。使用[图形数据库](https://www.influxdata.com/graph-database/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06_spnsr-ctn_getting-started-opentelemetry_tns)可能不是您处理遥测数据的第一想法，但是您可以通过从主数据存储中提取数据，然后使用图形数据库提供的工具对其进行分析，来找到有价值的见解和关系。您也可以通过使用一个[键值数据库](https://www.influxdata.com/key-value-database/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06_spnsr-ctn_getting-started-opentelemetry_tns)与任意数量的上述存储选项相结合，为用户提供新的功能或更好地分析您的数据。

### 分析您的数据

一旦你决定了你将如何存储你的数据，你就可以开始考虑你将如何[分析你的数据](https://www.influxdata.com/time-series-analysis-methods/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06_spnsr-ctn_getting-started-opentelemetry_tns)以从中获得洞察力。第一步可能与[可视化您的数据](https://www.influxdata.com/how-to-visualize-time-series-data/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06_spnsr-ctn_getting-started-opentelemetry_tns)和创建仪表板有关。为此，您可以使用 Grafana 之类的工具，或者使用您喜欢的数据可视化库构建自定义 UI。

下一步通常是添加某种形式的监控和警报，以便在出现问题时通知工程师。通过创建警报和自动化操作，您可以开始减少中断和其他影响用户体验的事情。

最后一步不仅仅是对问题做出反应，而是真正开始充分理解您的应用程序，以便能够在出现问题之前采取行动。你也可以根据历史数据开始[预测](https://www.influxdata.com/time-series-forecasting-methods/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06_spnsr-ctn_getting-started-opentelemetry_tns)，并随着时间的推移尝试优化和变得更有效率。

## 可观测性和开放式遥测技术的稳步发展

可观察性继续获得开发人员的认同和采用。OpenTelemetry 可能是可观测性生态系统中的一个关键部分，有助于将所有不同的工具和供应商联系在一起。正因为如此，开发人员熟悉 OpenTelemetry 并开始试验它能做什么是值得的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>