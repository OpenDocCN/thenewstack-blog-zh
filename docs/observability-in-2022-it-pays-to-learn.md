# 2022 年的可观察性:学习是值得的

> 原文：<https://thenewstack.io/observability-in-2022-it-pays-to-learn/>

DevOps 团队不能不在 DevOps 中集成可观测性。鉴于网络蔓延和日益分散所带来的复杂性，组织面临着跟上发展步伐的挑战。不依赖于适当的可观测性过程这样做是不可想象的。Gartner 写道，到 2026 年，70%成功应用可观察性的组织将实现更短的决策延迟，从而为目标业务或 IT 流程带来竞争优势。

2022 年的例子是，随着势头的建立，组织正在*做*可观察性。随着 IT 团队陷入困境并开始实现可观察性，他们要求简单和自由地混合和匹配所选择的工具和平台。几个月前，当描述 Kubernetes 的学习过程时，他们正在通过做和建立“肌肉记忆”来学习，这是从 [Thomas Keenan、](https://www.linkedin.com/in/thomaskeenanmktg) [Kasten 的](https://www.kasten.io?utm_content=inline-mention)高级产品营销经理 Veeam 那里借用的术语。

“2022 年，工程师们意识到可观察性对他们企业的成功有多么重要——特别是当他们被赋予与更精简的团队合作的任务时，” [Chronosphere](https://chronosphere.io/) 的联合创始人兼首席执行官 [Martin Mao](https://www.linkedin.com/in/martinmao/) 告诉新堆栈。

通过 [OpenTelemetry](https://opentelemetry.io/) 协议，在单个面板下容纳更多的可观测性工具(通常是 [Grafana 的](https://grafana.com/))也取得了很大进展。要求易于使用的自动化，例如使用 [eBPF](https://ebpf.io/) 自动仪器。任何试图通过厂商锁定来获得市场份额的厂商都要小心了。

Honeycomb 首席产品经理兼 OpenTelemetry 布道者 [Phillip Carter 表示:“那些继续将自己的定制和专有仪器库和代理作为使用其产品的默认方式的供应商，很快就会发现自己站在了消费者需求的错误一边。](https://www.linkedin.com/in/phillip-carter-4714a135)

## 不像往常一样

在科技行业普遍大规模裁员的情况下，风险投资公司缩短了创业公司的跑道以获取利润，以及美国和世界经济状况的不确定性，2022 年肯定不是照常营业。“随着许多公司专注于他们的底线，并实施招聘冻结或更糟，DevOps 团队留下来承担客户的期望，”毛说。

事实上，根据最近的一项 Chronosphere 调查，工程师平均有 25%的时间花在解决低级任务上，而不是创新客户增强活动上，毛说。“为了实现这一点，并避免耗尽团队的精力，工程师们转向更有效的可观测性解决方案，以填补缺口，实现更高的效率，并最终满足客户，”毛说。

然而，组织在许多方面才刚刚开始意识到 obbservabilty 的潜力。根据 EMA 的网络管理大趋势研究，尽管采用了该方法，但成功完成总体任务的网络运营团队数量已从 2018 年的 47%下降到 2022 年的 27%。换句话说，还有许多工作要做。采用适当的可观察性策略需要适当的工具和平台选择，以及与之相适应的教育。组织还必须进行文化变革。组织在 2022 年取得了很大进展，但适当的可观察性(与安全性类似)仍然是一项长期的工作，因为挑战比比皆是。

[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉 The New Stack 说:“虽然我们喜欢关注那些已经消除了基础设施监控、日志管理、跟踪、云安全监控和 DevOps 管道监控之间的人为分离的组织，但我们需要记住，绝大多数组织仍然保持购买单独解决方案的单独预算，而不是一个可观察性套件。

Volk 说，即使是经验丰富的 DevOps 团队也在运营复杂性和将[全栈](https://thenewstack.io/webassembly-users-a-mix-of-backend-and-full-stack-developers/)遥测数据流与业务指标对齐的成本下挣扎。“要做到这一点，需要组织创建数据管道和数据模型，以便能够真正将网络或基础设施层面的资源争用与受影响的应用程序提供的用户体验联系起来，”Volk 说。

## 打开遥测保存

可以说，开放式遥测是 2022 年的可观测性故事。作为更重要的 [CNCF 项目](https://thenewstack.io/what-it-takes-to-go-from-cncf-sandbox-to-incubation/)之一，组织越来越意识到 [OpenTelemetry](https://thenewstack.io/opentelemetry-properly-explained-and-demoed/) 如何提供供应商中立的集成点，帮助组织以集成所需的相对最小的努力获得可观测性数据。它的厂商中立性是关键，因为用户可以混合、匹配和组合许多不同的[观察工具](https://thenewstack.io/serverless-needs-more-observability-tools/)。

Volk 说，通过 OpenTelemetry，开发人员可以利用简化的和大部分自动化的仪器，而操作员可以获得统一的可观测性后端，而不必担心丢失任何遥测数据。

“OpenTelemetry 是当今全 CNCF 最热门的项目。虽然我们仍处于这个故事的开始，但大多数可观测性平台供应商已经承诺支持 OpenTelemetry，将其作为跟踪、记录和收集健康和性能指标的未来标准，”Volk 说。“这是一个令人兴奋的前景，因为 OpenTelemetry 最终可以通过为两个角色提供一个统一的平台来解决他们各自的优先事项，从而将开发人员和操作员联系在一起。”

但是，OpenTelemetry 允许用户自由组合和删除工具选择的方式是一件大事。“今年我们从企业那里听到的关于他们的可观察性工具的最大抱怨之一是锁定。毛说:“OpenTelemetry 正在成为可观测世界的巨大希望，因为它为表达和接收信号以及防止锁定提供了一致的开源标准。“重要的是，我们不仅看到了采用，而且它还被大量的客户端和编程语言所使用。虽然 OpenTelemetry 已经成为分布式跟踪的标准，但考虑到这些数据类型的不同问题和动机，度量和日志记录的采用似乎还需要一点时间。”

事实上，OpenTelemetry 帮助 DevOps 团队实现了统一的可观测性，因为它帮助了需要将遥测和可观测性问题分开的团队:“你如何获得数据”与“你用数据做什么”，Lightstep 开发人员关系负责人奥斯汀·帕克说。“OpenTelemetry 通过提供一个独立于供应商的标准来创建、表示和收集适合可观测性用例的遥测数据，回答了第一部分，”Parker 说。

至于为什么 OpenTelemetry 今年受到如此多的关注，Splunk 产品管理总监 [Morgan McLean](https://ca.linkedin.com/in/morganmclean) 说,“最大的长期原因”是它的功能(自动捕获来自大量平台、语言和技术的痕迹和指标),一致的数据模型和语义，以及将数据发送到任何地方的能力。“OpenTelemetry 提供了组织知道他们需要但还没有的东西。今年发生的变化是，该项目获得了一种新的信号类型(度量)，该项目的工件(收集器代理、语言代理、语言库)普遍达到了成熟和市场意识的水平，人们乐于在大规模生产环境中使用它们，”McLean 说。

蜂巢的现场首席技术官 [Liz Fong-Jones 说，越来越多的大型企业组织的开发人员意识到，OpenTelemetry 是理解现代可观测性方法的好处的一部分。Fong-Jones 说，它涉及利用 OpenTelemetry 和利用分布式跟踪的能力，以便了解用户在生产中如何体验代码。“这证实了开发人员正在寻找超越日志和指标的方法来观察和理解他们日益复杂和分布式的系统，”Fong-Jones 说。此外，随着 eBPF 自动仪器的兴起、内置电池的易用性以及 OpenTelemetry 的标准合规性，企业在采用可观测性时比以往任何时候都更容易做出选择，以便获得他们对系统所需的洞察力。”](https://ca.linkedin.com/in/efong)

Grafana 实验室的技术副总裁 Tom Wilkie 说，OpenTelemetry 和 [eBPF](https://thenewstack.io/ebpf-finds-a-home-with-a-new-foundation/) 的自动仪器方面意味着“用户不必改变他们的代码来理解它的行为”。“今年，我们看到了自动化仪器仪表的开始，无论是通过 OpenTelemetry 还是 eBPF，都使开发人员更容易提取理解其应用所需的遥测数据。与此同时，用户要求有一个工具来存储所有数据，并允许你分析所有的数据，不管数据的格式如何。“今年，像 open telemetry auto instrumentation libraries 和 Grafana 米伊美这样的项目取得了很大的进步，允许您从 OTLP、Graphite、Datadog 和 influx db 中本机获取指标，并存储和分析这些指标。”

威尔基还对 2022 年进行了大胆预测。今年 1 月，他在新的 Stack 中引用了他的话:“到 2022 年底，担心你的指标基数将成为过去，”威尔基说。他的预测有多准确？

Wilkie 说:“高基数指标的存储成本一直很高，查询效率也很低，今年出现了这种变化，采用了预聚合等技术来降低存储成本，从而解决了这个问题。”。“但这并不是普遍有用的——相反，在一些领域，人们发现需要它们的高基数，例如多租户系统中的每用户 SLO 报告。今年，能够经济高效地扩展以支持此类用例，同时支持高性能分析的系统(如格拉法纳米伊美)越来越受欢迎。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>