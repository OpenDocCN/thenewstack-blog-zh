# Splunk:开放式遥测技术和可观测性的未来

> 原文：<https://thenewstack.io/splunk-opentelemetry-and-the-future-of-observability/>

[](https://www.linkedin.com/in/spiros/)

 [斯皮罗斯·桑多斯

斯皮罗斯·桑多斯是 Splunk 的可观察性和 IT 运营产品管理副总裁，负责监督 Splunk 的可观察性和 IT 产品组合。此前，他是 Omnition 的首席执行官和创始人，Omnition 是一个面向云原生应用的可观测性平台，开创了无样本跟踪，并共同创建了 OpenTelemetry。Omnition 于 2019 年 9 月被 Splunk 收购。在 Omnition 之前，Spiros 启动并运行了 Pattern Insight，该公司构建了 Log Insight(一个日志分析平台)，直到 2012 年将其出售给 VMware，并运行了 ezhome，直到 2017 年 9 月。](https://www.linkedin.com/in/spiros/) [](https://www.linkedin.com/in/spiros/)

**我们都听说过“可观察性”这个术语，即通过捕获和分析数据来了解复杂的应用程序和环境。可观测性是一个热门话题，OpenTelemetry 很快成为其中的明星。OpenTelemetry 是一个于 2019 年推出的[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)项目[，它正在迅速发展，成为最受欢迎和支持的从应用程序和基础设施中捕获性能遥测的方式。这反过来允许开发者和站点可靠性工程师(SREs)获得对系统结构、状态和行为的可观察性。](https://www.cncf.io/blog/2019/05/21/a-brief-history-of-opentelemetry-so-far/)**

 **OpenTelemetry 提供了一组 SDK、代理和协议定义，可从应用和基础架构堆栈的每一层捕获元数据、指标、分布式跟踪、日志(目前处于实验阶段，但正在快速开发)以及最终的其他类型的数据。OpenTelemetry 的显著优势显而易见，包括更低的总拥有成本、专有数据锁定的终结以及由开源社区引导的创新驱动和功能的快速扩展。让我们来看看为什么 OpenTelemetry 相信他们的[遥测解决方案是可观测性](https://thenewstack.io/monitoring-vs-observability-whats-the-difference/)的未来，以及为什么它正在迅速接管开源世界。

## 对可观察性的需求

虽然向云服务和 Kubernetes 的转变让数百万开发者和组织能够推出大规模的 web 服务，但由此产生的应用程序非常复杂，难以理解、监控、调试和开发。这一点，以及随叫随到的责任从运营团队转移到开发和 SRE 角色，使得可观测性成为软件开发速度和可靠性的关键输入——以及依赖于它的业务。

一个人观察系统内部工作的能力取决于从系统中获得的遥测数据，这意味着遥测数据需要通过每个平台、操作系统、语言、存储和 RPC 客户端、web 框架以及开发人员想要深入了解的其他库来捕获和传播。从这些来源生成的信号也需要相互关联，以便对服务采取的操作可以链接到底层基础设施和对属于同一请求链的其他服务采取的操作。

这是一个重大的挑战，多年来，开发人员一直在努力收集这些数据的一个子集进行分析。不同信号类型或应用堆栈层之间的结果通常不相关，整个设置需要持续维护。即使拥有人员充足的团队，该领域的供应商也很难从客户要求的平台、语言和框架中获取数据。

## 用 OpenTelemetry 征服复杂性

从基础设施和应用中提取高质量信号的问题正是将 OpenCensus 和 OpenTracing 项目结合在一起形成 OpenTelemetry 的原因，也是 OpenTelemetry 如此受欢迎的原因——事实上，它是 CNCF 仅次于 Kubernetes 的第二大活跃项目。这证明了它给开发者和 sre 带来的价值。

通常，开发人员将通过以下方式在应用程序中使用 OpenTelemetry:

*   使用自动工具语言包或将 SDK 和适当的工具链接到它们的代码库
*   将收集器部署到相同的主机或 Kubernetes pod
*   将 SDK /自动检测包跟踪和指标导出到收集器
*   将这些指标和系统指标从收集器导出到它们选择的处理目的地

OpenTelemetry 的长期目标是开发人员希望从中捕获数据的遥测源、库、框架和其他代码，以使用特定于语言的 OpenTelemetry APIs 本地生成遥测。已经有这样的例子了:最新版本的。Net 框架和 ASP.Net 直接调用 OpenTelemetry 兼容的 API，谷歌的几个数据库客户端也是如此。从短期来看，OpenTelemetry 项目提供了从这些来源本地捕获遥测数据并将其转换为 OpenTelemetry APIs 的工具。这使得 API、SDK、收集器和语言自动检测包能够为每个人提供即时的价值。

## 全力以赴开发遥测技术

作为 OpenTelemetry 项目的[创始成员](https://www.splunk.com/en_us/blog/devops/opentelemetry-open-collaboration.html)和[顶级贡献者](https://www.splunk.com/en_us/blog/leadership/splunk-now-top-contributor-to-opentelemetry.html)之一，我们在 [Splunk](https://www.splunk.com/) 相信 OpenTelemetry 现在比以往任何时候都更重要。在移动和网络应用的数字体验比以往任何时候都更加重要的时代，它有能力加快稳健可观测性的实施，并通过云原生应用提供惊人的结果。

OpenTelemetry 也很容易上手，一旦部署，它会提供许多好处。OpenTelemetry 内置了对许多框架和客户端库的支持，并有一个大型的仪器注册表，为大多数 web 框架、RPC 系统、存储客户端、数据库、web 服务器、操作系统和 Kubernetes 提供了开箱即用的支持。

此外，其本地有线协议和导出器接口允许 OpenTelemetry 用户完全避免供应商锁定。如果信号在导出前被发送到采集器，改变导出目标就像编辑 YAML 文件一样简单。OpenTelemetry 可以同时将数据发送到多个目的地，这意味着组织中的不同团队可以评估、使用不同工具并在不同工具之间顺利迁移，同时仍然可以在整个堆栈中获得无障碍的可观察性。

因为它使用一组 SDK 和语义约定，OpenTelemetry 还提供了相关性，并为每个信号附加一致的元数据。自定义应用程序指标与服务和主机相关联，分布式跟踪与日志和指标样本相关联，等等。

最后，OpenTelemetry 由一个庞大、健康的开源社区支持，它的每个部分都在积极开发中。OpenTelemetry 项目的重点是遥测数据收集，而不是存储、分析等。—保持供应商、云平台和最终用户贡献者的激励一致，该项目每天都欢迎新成员和贡献。

## 产生影响

OpenTelemetry 已经被广泛采用，这与过去的应用程序性能管理领域的大多数产品都依赖专有代理的情况有很大的不同，这些代理使用字节码注入和 monkey 修补的某种组合来从大多数语言运行时捕获分布式跟踪和指标。这些代理的开发成本很高，只能使用特定的语言并支持少量的源，它们对字节码签名检测的依赖意味着它们必须在遥测源收到少量更新时进行更新，并且通常会消耗很大一部分 CPU 周期。OpenTelemetry 的功能和支持的来源、对 API 和标准而不是字节码模式的依赖、灵活性和最小的性能影响使它成为供应商和最终用户的必备工具。

## OpenTelemetry 的下一步是什么？

我们确信，OpenTelemetry 将成为可观测性的行业标准，并受益于未来几年前所未有的增长。随着 OpenTelemetry 的跟踪功能在 2021 年 2 月全面上市，我们已经看到了这一点，大多数 OpenTelemetry 组件已经发布了具有生产就绪跟踪功能的 1.0 版本。从那里开始，OpenTelemetry 的度量能力将在今年晚些时候达到 1.0，尽管许多最终用户和供应商已经依赖于收集器捕获系统和预打包应用度量的能力。

日志记录仍处于试验阶段，但是由于 ObservIq 捐赠了 Stanza 日志记录代理，收集器中的本地日志记录功能的开发已经在进行中。此外，随着时间的推移，还会有更多的增强功能和信号类型出现。例如，Splunk 正在将 eBPF 捕获添加到收集器中，这将允许直接从操作系统内核收集指标和其他信号类型。

总的来说，OpenTelemetry 的好处和影响不言自明。开源社区内的高速增长是前所未有的，以至于我们预测到 2022 年底，OpenTelemetry 将成为世界上最常用的数据仪器和收集技术。对于其他公司，我们说是时候致力于 OpenTelemetry 的标准化了，这样每个人都可以从主导 DevOps 社区的开源项目中获益。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**