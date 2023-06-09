# 首席执行官 Raj Dutt 采访:Grafana 的经验将会改变

> 原文：<https://thenewstack.io/ceo-raj-dutt-interview-the-grafana-experience-will-change/>

首先，有石墨。对于那些喜欢 metrics 工具但想要更好的用户界面的人来说，Grafana 构建了它的数据可视化面板。然后普罗米修斯在 2015 年 Grafana 增加对普罗米修斯的支持之前出现了。剩下的就是历史了，因为 Grafana 正在接近成为拥有近 1000 万用户的数据可视化事实上的面板。Grafana 继续保持对开源项目 Prometheus T1 的主要贡献者的支持，超过 44%的 Prometheus 维护者来自 T2 Grafana 实验室 T3。

“对我们来说，与普罗米修斯合作是一个相对明显的决定，即使普罗米修斯是一个非常小的度量数据空间，” [Grafana Labs](https://thenewstack.io/grafana-labs-invests-in-strengthening-enterprise-integrations-with-prometheus/) 的首席执行官兼联合创始人 [Raj Dutt](https://www.linkedin.com/in/radutt) 本月早些时候在纽约举行的[observibility con 2022](https://grafana.com/about/events/observabilitycon/2022/)期间告诉新的堆栈。“Prometheus 作为 Grafana 的跳板，与 Graphite 和 InfluxData 一起，为我们所谓的‘大帐篷哲学’奠定了基础:我们希望优先考虑下一个伟大的日志或度量数据库的互操作性，无论它是不是我们的。”

当然，Grafana 今天为 Prometheus 提供的不仅仅是一个好的 UI。它的可观察范围现在扩展到度量的米伊美，日志的洛基和轨迹的速度。Grafana 本月还推出了两个新的开源项目: [Grafana Phlare](https://go.grafana.com/MzU2LVlGRy0zODkAAAGIAT7RMxj4_xBkiwbzWZHMTsHOLos11o7raEaBmG_NkWkTYf3cwl-hfKTZMWIs4ANzQlhWgDc=) 用于持续剖析，以及 [Grafana Faro](https://go.grafana.com/MzU2LVlGRy0zODkAAAGIAT7RM7_7OVhm0vSzzC6416KuN1b2eA89MNiDx_mKZ-TtR1J-QG5j4FJARqtVlLvYdkb6q-U=) 用于前端应用程序可观察性。去年，k6 加入了它的投资组合。

但是这对于开发者社区意味着什么呢？我们与 Dutt 坐下来讨论 Grafana Labs 希望更直接地接触开发人员的原因和方式。这将包括在开发周期中进一步向左扩展其数据源，以使测试数据更易于观察和用户要求的其他功能。Dutt 还讨论了 Grafana 现在的可观测性计划，以及随着其用户群突破 1000 万大关，Grafana 的不同之处。

**米伊美现在是 Grafana 最近的开源项目之一，取代 Cortex 成为你所说的 Cortex 的“精神继承者”，现在米伊美可以提供 Cortex 的绝大多数企业功能。尽管如此，普罗米修斯仍然是度量的领先工具。你能把这个放在上下文中吗？**

Cortex 是 Prometheus 的扩展版本。但是米伊美的定位是公制数据库，普罗米修斯兼容是一个特点。它还具有与 Datadog、Graphite 和 OpenTelemetry 的兼容性。米伊美是普罗米修斯的替代者，但是它的兼容范围非常广。

**Grafana 仪表盘在 DevOps 社区非常受欢迎，因为它运行良好。但是开发人员和运营人员似乎真的不太关心流行工具或平台提供商的企业方面，而是关心特定供应商将做什么来帮助改善他们的生活和工作。为此，格拉夫纳实验室此时正在努力做什么？**

我们试图建立一个可观察的平台，它既是可组合的，又是完整的。你是对的:Grafana 只是前端，所以在过去的三年里，我们已经发布了度量(米伊美)、日志(Loki)和跟踪(Tempo)的开源项目，这确实帮助我们提出了一个完整的、有管理的开源堆栈实现，我们认为这是一个最佳的工具集。

人们不必使用整个系统。他们可以把格拉夫纳和米伊美或洛基一起用，也可以不用。你可以选择，按照你想要的方式构建它。当我们的客户把我们推向那个方向时，我们发布了新的开源项目。他们希望有一个坚持己见、完全受支持的堆栈，并保证完整的端到端体验，我们会在其中打上集成的印记。

当人们把自己的堆栈拼凑在一起时，这给了他们很大的灵活性。但是这很难做到。这需要很多工程师和专业知识。这对于我们的一部分客户来说很好。他们想要 DIY。但是我们发布开源项目，因为它们帮助我们完成我们的愿景，提供一个完整的可观察性平台，[而不仅仅是一个访问度量、日志和跟踪的仪表板]。

我知道你不想谈论公司的事情，但在这一点上，不到 50%的收入来自 Grafana frontend。

**Grafana 客户的比例只占 Grafana 用户的很小一部分。Grafana 是如何创收的？**

这是一个很好的问题。我们希望扩大用户群体。我们现在有将近一百万家公司在使用 Grafana。我们希望是 1000 万。然后，我们通过从这个巨大的蛋糕中获取一小块来赚钱。所以，我们有 2000 个付费客户。如果您是一家大型企业，并且有复杂的法规遵从性和安全性要求—在全球十大银行中，有一半是我们的客户—我们支持他们的法规遵从性、安全性和其他要求，并为他们提供我们的开源版本所不具备的功能。

您的云产品相对较新。接待怎么样？

除了我们的企业产品，我们还有云产品。云产品正在激增，它们显然是一个巨大的潜力，已经占据了超过 50%的收入。

**当一家大银行或另一家大客户选择将 Grafana 的企业版集成到其 IT 基础设施中时，该如何运作？例如，Grafana 为实施和支持提供了多少支持？**

这个想法是建立易于使用的软件。我们收入的很小一部分来自专业服务。我们绝大部分的收入都用于付费云消费，或者你想在企业版中增加多少用户席位。我们销售云服务和软件许可证。我们做的咨询服务很少，仅占我们收入的个位数。

我们将提供一个安全网。但是，我们会拿起电话，回复电子邮件或短信，回答客户的问题。如果他们有需要，我们会作出回应。如果存在安全问题，我们显然想知道并会解决它。支持是人们付钱给我们的一个原因，但它只是第二或第三个原因。

**我凭直觉猜测，使用 Grafana 开源项目和 Grafana 企业软件，如果你必须支付大量资金来实现和使用，那么通过 Grafana 仪表板的所有访问都不会很受欢迎。作为一个用户，Grafana 仪表板的简单性和对不同数据源和可观察性选项的访问是我使用它的原因。我还假设用户喜欢 Grafana 面板好看的图形。**

我不认为依靠提供支持的收入是建立企业的好方法。我们想降低开发者的摩擦。我们想让开发者更容易开始使用它，并信任这项技术，然后我们将讨论你还能做什么。有时我告诉我的工程师，你的工作是把支持挤出业务。理想情况下，该软件应该非常容易使用，你永远不需要支持。

随着软件整体复杂性的增加，我们希望缩短学习曲线。

我们的客户不从事运行可观测性堆栈的业务。无论从事什么行业，他们都是在为自己的客户服务。他们通常拥有工程人才和一个非常聪明的团队，他们知道开发和部署一个伟大的软件堆栈所需的所有知识，并使用他们选择的可观察性工具来帮助实现这一点。这正是我们的客户类型。

**您如何试图解决感知到的需求，开源是如何起作用的？**

除非我们解决了真正的问题，否则人们不会采用我们的软件，社区也不会成长。

开源代码不言自明。你没有像在商业世界那样的能力来推销你的产品，直到最初被采用。更艰难，是真实的。大家都不言而喻。我认为软件开发人员总体上对市场营销相当免疫。他们会说“我不想被告知为什么这个软件是好的”，他们想尝试一下，如果它是好的，他们会告诉你。

**对社区说，下一步是什么？你显然想扩大 Grafana 的用户，但是你真正想给开发者社区提供什么呢？**

我们有一个体面的故事，我们称之为 LGTM:洛基，格拉法纳，速度和米伊美。我们花了四年时间开发最初的核心堆栈。所以我们接下来要做的是在软件开发周期的早期，进行更多的测试，包括混沌测试，以及使用像 [k6](https://thenewstack.io/grafana-labs-purchase-of-k6-adds-load-testing-directly-to-observability-console/) 这样的工具进行可靠性工程。我们在软件生命周期的早期进行生产前测试，并继续投资于可观察性。

我们也在软件开发生命周期的早期和后期支持可观察性警报。这包括支持谁会收到提醒，谁会收到提醒，以及谁会被叫醒。例如，一旦那个人正在处理一个问题，你如何解决这个问题，如何与你的客户沟通？您如何在内部管理事故、确定停机原因并与客户沟通？对 SLA 和 SLO 有什么影响。事故发生后所发生的一切是我们正在深入研究的另一个领域，扩展我们已经拥有的工具，包括 [Grafana 警报、](https://grafana.com/docs/grafana/latest/alerting/)Grafana OnCall 和 [Grafana 事故。](https://grafana.com/blog/2022/02/02/announcing-grafana-incident-smart-incident-management-for-your-teams/)

我们的核心可观察性产品越来越强:Grafana 面板、日志、指标和跟踪，我们刚刚推出了持续剖析(Grafana Phlare)。因此，我们将在应用程序生命周期的早期和后期进行。

**你如何将 Grafana 的用户群划分为开发人员和运营人员？**

这个问题问得好。如果你看看使用我们软件的用户群，今天大约有 1000 万人在使用我们的软件。所以，如果你看看他们用它做什么，可观察性是核心用例——它大约是 Grafana 用途的 75%。因此，另外 25%用于商业智能、传感器数据、物联网过程控制或电厂数据等用例。SpaceX 使用 Grafana 来管理燃料流。因此，75%的社区将 Grafana 用于可观察性，其余的用于其他用例。

**告诉我们一些有趣的事情。**

是的，有趣的东西。因此，作为一家公司，我们专注于可观察性用例，但我们也有兴趣看看有趣的东西在发生什么。

第二，在那 75%的人群中，谁在使用 Grafana 进行观察？这是运营人员、开发人员和 sre 的组合。如果有一个角色脱颖而出，那可能是越来越多的 SRE 角色，可以说是开发者和操作者的混合体。所以，当你看到用户群时，它开始于你的技术领先的初创公司或愿意冒险的公司，较小的公司，爱好者用户:这就是社区的开始。但是如果你看看今天，在过去的五年里，世界上最大的公司已经开始把我们的软件投入生产。现在人们对品牌、质量和能力非常信任。当 Grafana 1.0 问世时，世界上一半最大的银行都不可能将其投入生产。

是关于开发者的摩擦。我敢肯定，在过去的 10 年中，您已经看到销售软件不再是带首席信息官去高尔夫球场。这是我们创办公司时的基本观察，可以追溯到开发人员的摩擦。我们正在进行优化，以给开发者和从业者留下深刻印象，因为与 10 年前相比，这个人在他们的组织中对购买什么有更大的影响力。10 年前他们被告知你会用这个。我们今天刚和 IBM 签约，有 10 年的合同。但现在如果发生这种情况，开发商就会退出。

**Grafana 仪表盘上有一千万只眼睛。我的观点是，对于可观察性，比如监控服务器性能或 SaaS 环境，我将负责引入我想使用的任何平台组合，以及 OpenTelemetry，可能包括也可能不包括 Loki、Grafana、Tempo 和米伊美。你同意这个评价吗？**

每个可观察性供应商都会说“是的，我们支持互操作性，但是你必须把你所有的数据发送给我们。”他们都会说我们会解决你的问题，但你的数据必须发送给我们，并存储在我们的平台内。他们的计费模式和赚钱方式仅仅是靠你发给他们的数据。因此，如果你不把数据发送给他们，他们不会采取行动，而我们有一个用户模型，我们坐在上面，你根据你拥有的用户数量向我们付费，你可以对你的数据做任何你想做的事情。这是让我们与众不同的一个非常重要的角度。

在 BI 领域，你会听说 SQL 数据库、雪花、数据块或类似的产品。因此，如果你正在销售一个 SaaS 解决方案，你会走进一家公司，说“我会帮助你可视化你的数据，但你必须将你的所有数据存储在我们这个 BI 供应商那里，”你会被笑出房间。但在可观察性领域，这种情况不会发生，因为任何可观察性供应商都会进来说，“我们可以解决您的问题，但您只需将数据保存在我们这里。”使用 Grafana，您可以使用任何您喜欢的数据源组合。当然，数据会保留在您希望的位置。当然，从我们正在竞争的意义上来说，洛基、米伊美和 Tempo 实际上必须与其他数据源竞争。

我们关于可组合性的故事是很大的:您可以自己选择想要使用的数据源。这对我们来说是一个很大的差异化因素。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>