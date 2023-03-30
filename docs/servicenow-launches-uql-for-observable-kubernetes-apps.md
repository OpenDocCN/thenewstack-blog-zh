# ServiceNow 为可观察的 Kubernetes 应用程序推出 UQL

> 原文：<https://thenewstack.io/servicenow-launches-uql-for-observable-kubernetes-apps/>

ServiceNow 已经将其 [Lightstep](https://lightstep.com/) [UQL(统一查询语言)](https://lightstep.com/blog/announcing-the-lightstep-unified-query-language)普遍提供给组织使用 Observability 作为代码来创建从一开始就可以观察到的 Kubernetes 应用程序。

UQL 将帮助公司扩展在 [Kubernetes](https://thenewstack.io/category/kubernetes/) 应用中的可见性。ServiceNow 本周在底特律举行的 [KubeCon + CloudNativeCon 北美](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)活动上介绍了完整的 UQL。

Lightstep(去年 [ServiceNow 收购了](https://thenewstack.io/servicenows-lightstep-buy-moves-observability-up-the-stack/))总经理兼联合创始人 [Ben Sigelman](https://www.linkedin.com/in/bensigelman/) 在一份声明中说:“今天的工程师可以利用[可观察性作为代码](https://thenewstack.io/category/monitoring/)来更加强大和灵活地洞察他们的云原生应用的健康和性能。“当想到像 Kubernetes 这样高度复杂和动态的现代建筑时，这一点尤其重要。Lightstep UQL 致力于确保每一个部署的 Kubernetes 应用程序在默认情况下都是完全可检测的。”

![](img/6a1794ea36df4b072cc869c021093774.png)

本·西格曼

## 烘烤而成

Lightstep UQL 通过提供“作为代码的可观测性”，使得 DevOps 团队集成可观测性变得更加容易，星座研究公司的分析师安迪·图雷说。

“其他供应商也提供了其他变体，所以这不是惊天动地的创新，”他说。“然而，这使得 DevOps 团队更容易从设计/代码级别实现可观察性，而不是事后才想到。”

Lightstep 一直是追踪数据的领导者。

“但是由于 UQL 同时涉及度量和跟踪，它允许跟踪数据在这些管道中向左移动，”Sigelman 告诉新堆栈。“因此，您现在可以像自动化从报警和警报到 C I/CD 的所有工作一样，编写相同的脚本。这种编写脚本的方式，以前只适用于度量标准，现在可以用一种语言来编写所有这些不同类型的数据。”

此外，UQL 允许自动化发生，而不管跟踪数据的基数，也不管总体的数据类型。Sigelman 指出，这打开了一整套用例，这些用例由于今天存在的语言的基本限制而被封闭。

## 模糊的线条

“UQL 实际上只是我们试图有意模糊这些不同遥测发射井之间的界限的另一种表现，以便你可以有一次体验，但我们已经以类似于我们以前对 [OpenTelemetry](https://opentelemetry.io/) 和 [OpenTracing](https://thenewstack.io/opentracing-open-standard-distributed-tracing/) 所做的方式做到了这一点，”西格曼说。他是这两个项目的共同创始人。

UQL 已经酝酿了一段时间。几位曾在谷歌与西格曼合作开发 [Dapper](https://research.google/pubs/pub36356/) 和 [Monarch](https://research.google/pubs/pub50652/) 的工程师现在都在 Lightstep 工作，这两款软件分别是谷歌的追踪系统和公制系统。但 Lightstep 已经专注于 UQL 一年多了——这主要得益于收购 ServiceNow 的资源和好处。

## ServiceNow 的影响

“ServiceNow 对我们非常有利，仅从 R&D 的角度来看，我们的增长速度比独立运营时要快得多。这无疑加速了这类事情的发展，”西格曼说。

对于 ServiceNow 为 Lightstep 带来的好处，Sigelman 说:“我认为它允许我们在管理链的上下对齐的情况下进行这样的项目，我们需要追求长期愿景，并以一种创业公司难以做到的方式真正实现它。所以这是有帮助的，无论是让我们以那种方式有更大的梦想。从资源的角度来看，执行速度也会更快。”

IDC 分析师[史蒂芬·艾略特](https://www.linkedin.com/in/stephen-elliot-2125a8/)表示，总的来说，UQL 使基于 Kubernetes 的应用程序具有更深更广的可见性，从而推动开发人员、 [SRE](https://thenewstack.io/devops-institute-checks-the-pulse-of-sre/) 和开发团队的代码策略的可观察性。

“它为收集和管理度量日志和跟踪提供了一致的语言，”他说。“对于 Lightstep/ServiceNow 来说，这延续了他们的可观察性策略，并推动了云原生功能的深入发展。对于客户来说，可观察性正在成为一种必备策略，因为系统可靠性现在跨越了 IT、安全以及越来越多的业务组织中的许多利益相关方。”

## 不要用“S”字

尽管 Sigelman 将 UQL 称为一种厂商中立的方法，他希望行业能够采用，但他对使用“标准”这个词犹豫不决。

“我们很难理解标准这个词，因为‘标准’可能意味着类似 [IEEE【电气和电子工程师协会】](https://www.ieee.org/)的标准，也可能意味着事实上的标准，就像人们正在使用的标准一样。我想我现在越来越喜欢第二种标准了，”他说。“我们试图创造一种既有广度又有深度的产品，以满足各种各样的使用案例，同时又不会把人们局限在其中。你可以做到所有这些，而不用试图说你是一个标准。”

尽管 Lightstep 没有宣布开源 UQL 的计划，“这是我们希望长期看到的事情，”Sigelman 告诉 New Stack。“因为我觉得我们从 OpenTracing 和 OpenTelemetry 开始的开源运动非常有效。”

Thurai 指出，UQL 的出现意味着可观测性可以从一开始就进入云原生的 Kubernetes 应用程序。

“此外，UQL 允许在 Lightstep 平台内轻松搜索日志、指标和跟踪。ServiceNow 希望它能加速大型企业全部迁移到他们的 LightStep 平台，而不是使用许多其他竞争工具，”他说。“虽然这很容易实现，但在现实中，将企业的工具从开源工具和其他已建立的可观察性工具中移走并不是一件容易的事情。只有时间才能证明这是否是 ServiceNow 的制胜策略。"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>