# 我们的 2023 年现场可靠性工程愿望清单

> 原文：<https://thenewstack.io/our-2023-site-reliability-engineering-wish-list/>

是我们，还是我们不仅仅是新年的钟声？现在我们已经结束了 2023 年 1 月？Wuuuuutttt？时间去了哪里？

2022 年底，我们(即阿德里亚娜和安娜)制定了 2023 年 SRE 的愿望清单。我们在斯蒂芬·汤森的[轻微可靠性](https://youtube.com/@SlightReliability)播客的[“SRE 的未来”](https://www.youtube.com/watch?v=WNOnq5Mc8CI)以及我们在 DevOpsTV 的网络研讨会[“2022 教会我们 SRE 的未来”上的出现，激发了我们创建这个愿望清单的灵感](https://youtu.be/o0Pgo2fWIUc)您可能已经注意到，SRE 工厂可靠性工程的未来是最受关注的！

这几集只是冰山一角，我们想探索一下我们在播客和网络研讨会中提到的一些项目，并添加一些我们没有机会谈论的项目，因为，老实说，我们可以谈论这些东西几个小时！所以，事不宜迟，让我们来展示 2023 年 SRE 的愿望清单吧！

## SRE 可观测性的普遍存在

当你不在凌晨 4 点昏昏沉沉地坐在电脑前挠头，想知道为什么你的系统表现得如此怪异时，随叫随到就没那么糟糕了。可观察性对此有所帮助。

可观察性是一个系统发出足够信息的能力，让你可以跟踪面包屑，这样你就可以最终回答这个问题:“为什么会发生这种情况？”它有能力给 SREs 一些真正的超能力，因为如果做得好，它可以让 SRE 更容易解决棘手的生产问题。

但是我们还没到那一步。我们相信可观察性仍然被视为 SRE 的一个独立部分，而事实上，它应该是每一个 SRE 实践的基础。我们希望生活在这样一个世界里，当我们说“SRE”的时候，可观察性是隐含的。通过把可观察性作为 SRE 的基础，我们在添加任何混乱之前建立了对我们系统的理解。当我们这样做时，我们以身作则。理想情况下，这将成为在库和工具中构建更多工具——发送到可观测性后端的数据——的动力。

## 团队运动的可观察性

虽然可观察性是对 SRE 工具带的一个很好的补充，但它也应该被看作是开发人员和 QA 的一个有用的工具。怎么会？

**开发人员**编写代码(使用 [OpenTelemetry](https://opentelemetry.io) )以便它向给定的可观察性后端发出足够的信息，后者又以有意义的方式呈现这些信息，帮助他们在产品中对代码进行故障排除。你知道，当他们需要自己的代码时。

然后，QAs 可以使用 observability 后端来帮助他们在测试时解决代码问题，使他们能够提交更详细的错误报告。他们还可以利用工具(更具体地说，是跟踪)来创建基于跟踪的测试(TBT)，使用的工具有 [Tracetest](https://tracetest.io) 、 [Malabi](https://github.com/aspecto-io/malabi) 和 [Helios](https://gethelios.dev) 。关于这方面的更多信息，请点击这里查看 Adriana 关于这个话题的博客文章。

**SREs** 利用开发人员设置的应用遥测技术，以及从各种基础设施收集的遥测技术，帮助他们从外部了解系统以及该系统如何在内部交流。这让他们对自己负责的系统有了一个大致的了解。这些信号提供的可观察性允许他们排除生产问题，测量系统性能和检查整个系统的健康状况。

## OpenTelemetry 的采用增加

可观测性取决于它背后的遥测技术。当然，这意味着要确保你的系统正在发射和收集遥测数据。然而，围绕所述遥测技术有一个标准也是有帮助的。这就是 [OpenTelemetry](https://opentelemetry.io) (OTel)发挥作用的地方。OTel 是一个开源的、厂商中立的框架，用于测量、生成、收集和导出遥测数据。

[始于 2019 年](https://www.cncf.io/blog/2021/08/26/opentelemetry-becomes-a-cncf-incubating-project/#:~:text=The%20OpenTelemetry%20project%20was%20created,CNCF%20Sandbox%20project%20shortly%20thereafter.)，OpenTelemetry 自 Adriana 第一次[开始使用它](https://medium.com/tucows/unpacking-observability-the-observability-stack-93d4733e2a72)以来已经走过了漫长的道路。2021 年，[成为云原生计算基金会(CNCF)孵化项目](https://www.cncf.io/blog/2021/08/26/opentelemetry-becomes-a-cncf-incubating-project/)。OTel 的特点是[支持多种流行语言](https://opentelemetry.io/status/)。跟踪和度量的[规范现在是稳定的](https://opentelemetry.io/docs/reference/specification/status/)，并且许多组织正在生产中使用它。

在所有主要可观察性供应商的支持下，它是检测应用程序的事实上的标准。这是什么意思？随着越来越多的组织开始意识到可观测性的重要性，期待看到他们使用 OpenTelemetry 来装备他们的系统，以提升他们的可观测性(以及随后的 SRE)游戏。

## 越来越多地采用基于痕迹的检测(TBT)

基于跟踪的测试背后的想法很简单。既然您已经在应用程序代码中创建了分布式跟踪，为什么不使用跟踪数据创建测试断言来验证您的端到端系统流呢？这个想法最初是由 Ted Young 在 KubeCon North America 2018 上提出的[，现在它成为了现实，这要归功于 trace 标准化和](https://www.youtube.com/watch?v=NU-fTr-udZg) [OpenTelemetry](https://opentelemetry.io) 以及基于 trace 的测试工具，如 [Tracetest](https://tracetest.io) 、 [Malabi](https://github.com/aspecto-io/malabi) 和 [Helios](https://gethelios.dev) 。

随着越来越多的公司开始看到可观察性的价值，这意味着我们将看到更多的系统发出跟踪，那么为什么不使用那些已经存在的跟踪，并用它们做测试用例呢？

## 开发人员获得更多代码所有权

当 Adriana 第一次进入 DevOps 工作时，她对其承诺融化 dev 和 Ops 之间的障碍感到兴奋，使整个“将代码扔过墙”的心态成为过去。相反，许多组织滥用了 DevOps 的名称，在开发和运营之间插入了一个全新的层，称之为 DevOps，但这并不是 DevOps 的真正含义。

可悲的是，在许多情况下，开发人员仍然把他们的代码扔在墙外(现在是几堵墙)，sre(在许多情况下更名为 ops)经常陷入对他们没有编写的生产代码进行故障诊断的困境。正如 Adriana 在[之前的一篇文章](https://leaddev.com/personal-development/how-be-ethical-engineering-leader)中所说:

“软件工程师需要拥有自己的代码。把你的代码扔到墙上就完事了，这已经不再是好的了。拥有自己的代码鼓励责任感，并鼓励开发人员用他们的代码提升质量。

[“Honeycomb 的 Liz Fong-Jones](https://leaddev.com/community/liz-fong-jones) 在“On-Call Me Maybe”播客的第一集[中说得很好，当时她敦促工程师们编写自己的测试、自己的注释和自己的仪器。](https://oncallmemaybe.com/episodes/how-to-rock-at-sre-with-liz-fong-jones-of-honeycomb)

当你知道你已经被自己的代码缠住了，你就更有可能对你的代码多加小心，因为你猜怎么着？如果可以避免的话，你可能不想在半夜被叫醒去处理生产问题？

## 选择你自己的 SRE 冒险

我们在《[On-Call Me Maybe](https://oncallmemaybe.com)》(OCMM)第一季中看到的一个反复出现的主题是，[谷歌 SRE 的书](https://sre.google/sre-book/table-of-contents/)应该被视为一个指南，而不是做 SRE 的方式。(参见 OCMM [第 1 集](https://oncallmemaybe.com/episodes/how-to-rock-at-sre-with-liz-fong-jones-of-honeycomb)和[第 9 集](https://oncallmemaybe.com/episodes/kube-cuddles-with-rich-burroughs-of-loft-labs)。)如果你应该从谷歌 SRE 的书中吸取什么，那就是这个:

1.  通过编纂所有的东西来尊重 DevOps 原则(不管怎样，谁有时间手工做事情？)
2.  通过服务级别目标提高系统可靠性(SLO——稍后将详细介绍)
3.  尽可能减少工作——与运行生产服务相关的工作，这些工作往往是手动的、重复的、可自动化的、战术性的

如何到达那里取决于你自己。仅仅因为“这是谷歌做事的方式”就去做某件事肯定会导致灾难，应该不惜一切代价避免。拥有一个运转良好的 SRE 团队的最佳方式是拥有一个目标和工作方式一致的团队。

## SLO、SLO、SLO

服务水平目标(SLO)是 SRE 最好的朋友。SLOs 让你回答这个问题，“这个服务的可靠性目标是什么？”SLO 的示例包括:总请求中成功请求的数量、延迟<1,000 milliseconds and availability.

It’s not easy to come up with SLOs. Maybe your initial set of SLOs might not even be that great. But one thing we can say for sure is that the more you SLO, the better you and your team will be at it.

SREs should use SLOs to drive system alerts. This ensures that your alerts are meaningful, and it means that your on-call SREs don’t jump at every little system hiccup that occurs.

And in keeping with the SRE principle of “codifying all the things,” there is a movement to codify SLOs, thanks to projects like [OpenSLO](https://openslo.com) 。我们希望看到更多的人采用 OpenSLO 作为定义和编码 SLO 的标准，并希望 SRE 团队将其集成到他们的工作流程中。

有关定义 SLO 的更多信息，我们强烈建议您阅读 [Alex Hidalgo](https://www.alex-hidalgo.com) 的书《[实现服务水平目标](https://www.alex-hidalgo.com/the-slo-book)》

## 更多地采用策略即代码

“编纂所有的东西”是 SRE 的一个重要原则。它确保一致性、可维护性、再现性和可靠性。我们已经将我们的构建和部署管道、我们的基础设施甚至[可观察性](https://medium.com/dev-genius/observability-landscape-as-code-in-practice-732743e201b2)整理成文。因此，自然地，将我们的政策编成法典是有意义的。

鉴于我们的生活有多少已经转移到数字领域，邪恶的角色有越来越多的方式来进行破坏。知道策略是标准化的(通过代码)难道不会让您安心吗？)，并且有真实的来源(版本控制！)而且它不是通过 InfoSec 团队的 Google Drive 上的共享文档完成的？

幸运的是，由于像[开放政策代理](https://www.openpolicyagent.org/) (OPA)这样的机构，政策的编纂成为可能。我们希望在 2023 年，我们将看到更多的策略即代码在起作用，并且更进一步，通过自助工具实现这些策略(稍后将详细介绍)。

## 共享共同的任务和流程

现代开发人员共享代码的最佳方式之一是通过共享库和框架。这很好，因为你不必重新发明轮子，因为别人已经为你解决了那个问题。为什么我们不能在 SRE 王国做更多这样的事情呢？

尽管跨公司的 SRE 角色有其独特的风格，但许多组织确实有许多共同的 SRE 任务和流程。这些可能包括:Kubernetes 集群管理和维护任务、带有 [Argo CD](https://argoproj.github.io/cd/) 或 [Flux CD](https://fluxcd.io/) 或<insert _ your _ favorite _ GitOps _ tool>的 GitOps 流、基础设施自动化、定义 SLO 和 SLO 触发的工作流。

如果有一种方法可以在团队之间共享共同的编码任务和/或工作流，那不是很好吗？或者，更好的是，我们可以跨组织共享通用脚本和工作流？

市场上已经有一些工具解决这个问题的不同方面，包括 [RunWhen](https://www.runwhen.com) 、 [Kratix](https://kratix.io) (打包/共享 API 即服务) [Temporal.io](https://temporal.io) 和 [RunDeck](https://www.rundeck.com) 。我们希望看到像这样的工具被组织更广泛地使用。

## 自助供应的兴起

我们绝对讨厌的一件事是不得不依赖一个团队来为我们提供东西。这就是为什么我们非常高兴看到平台团队朝着自助式资源调配的方向发展。同样，这符合我们的 SRE 主题，即编纂所有的东西，真的很有意义。想想看:SRE 团队已经实现了自动配置任务，但他们仍然必须手动触发这些配置任务来满足用户请求。呃。老实说，这是浪费 SRE 团队的时间。他们可以利用时间做其他更酷的事情，比如提高系统可靠性。

自助供应的额外好处是:通过将它与策略即代码一起实施，它有助于确保团队不会做他们不应该做的事情。

帮助实现这一目标的一些技术包括 [Kratix](https://kratix.io/) (打包/共享 API 即服务) [Loft Labs 的 Kubernetes 名称空间自助服务](https://loft.sh/features/self-service-kubernetes-namespaces)和 [RunWhen](https://runwhen.com) (工作流共享和自动化)。

## 拥抱失败并从中吸取教训

不管我们喜欢与否，事情都会失败。真正重要的是我们如何从失败中恢复过来。作为开发人员，尽管尝试了各种不同的方法来让代码工作，但当我们看到相同的令人讨厌的错误一次又一次地出现时，我们的心都会下沉。

虽然这很令人沮丧，但重要的是强迫自己后退一步，把这整件事视为一次实验。没错，尝试 X 失败了，但是看看结果学到的其他东西！例如，我们现在知道 X 不是解决方案的一部分。

在一天结束的时候，我们最终会对我们正在努力做的事情了解更多，在这个过程中，我们也学会了如何更好地解决问题。这反过来使我们成为更好的开发者。

系统故障也是如此。是的，他们很烂。很多。但是失败给了我们丰富的信息。他们可以告诉我们，我们的流程、设计、代码甚至硬件存在问题。所有这些都是改进的机会。但是我们不能让自己停留在失败的事实上。相反，我们必须关注他们失败的原因，这样我们才能使我们的系统更好，更有弹性。

通过将我们对失败的看法从消极的转变为积极的，这有助于改善那些受失败影响的人的心理安全。我们确信，如果许多人知道他们可以谈论失败而没有任何反响，他们会更愿意就失败以及如何从失败中恢复进行开放和诚实的对话。

我们不应该逃避失败。我们应该寻求失败，拥抱失败，实践失败。只有这样，我们才会擅长处理失败。

让我们把围绕失败的积极对话正常化。关于这方面的更多信息，请查看我们与 Jeli.io 首席执行官诺拉·琼斯的精彩对话。

## 最后的想法

SRE 自早期以来已经走过了漫长的道路，在 2023 年还有一些令人兴奋的事情等着我们！

随着越来越多的组织将 OpenTelemetry 仪器标准化，我们很高兴看到可观测性的持续增长。测量数据被输入到可观测性后端，这有助于 SREs 解决那些棘手的系统问题。随着越来越多的组织开始使用 OpenTelemetry，基于跟踪的测试将是 2023 年的一大亮点，因为它通过弥合开发、质量保证和 SRE 之间的差距来提高我们系统的质量和可靠性。

我们也很高兴看到 SRE 通过策略即代码、已编码的 SLO、自助供应以及工作流共享和自动化，真正遵守了其编码所有内容的核心原则。

最后，我们很高兴看到我们的行业继续在优先考虑心理健康和健康方面取得进展，以确保我们的 SREs 处于最佳状态。

随着我们步入 2023 年，may SREs 将继续通过协作、思考和换位思考来推动技术创新。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>