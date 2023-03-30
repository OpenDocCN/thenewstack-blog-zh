# Knative 在基金会之外的独立未来

> 原文：<https://thenewstack.io/knatives-independent-future-outside-a-foundation/>

Knative 是一个基于 Kubernetes 的开源平台，用于部署和管理现代无服务器工作负载，最初由谷歌开发，现在[拥有来自 50 多家不同公司的](https://cloud.google.com/knative/)贡献。鉴于它与 Kubernetes 的接近和依赖，云原生世界中的许多人都期望它会被捐赠给一个基金会，如[云原生计算基金会](https://www.cncf.io/) (CNCF)，但这一希望在去年 10 月被粉碎，当时 Knative 指导委员会成员 [Donna Malayeri](https://www.linkedin.com/in/donnamalayeri) 在 [Knative 开发者论坛](https://groups.google.com/forum/m/#!forum/knative-dev)上发布了一篇“Knative 基金会状态的[更新”， 称谷歌领导层考虑了“Knative 是否会捐赠给 CNCF 等基金会的问题”，并“决定在可预见的未来不会向任何基金会捐赠 Knative”](https://groups.google.com/forum/m/#!topic/knative-dev/YmL2vgMC4rc)

对这封电子邮件的[立即回应](/this-week-in-programming-no-foundation-necessary-google-retains-knative-istio/)迅速，许多业内人士称这一决定“令人失望”，一个月后，指导委员会跟进澄清了其立场，在 2019 年 [KubeCon+CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 前几天[发布了官方更新](https://groups.google.com/forum/#!msg/knative-dev/KbrYbiF4XCs/j76PsjPNDAAJ)(交叉发布到[谷歌开源博客](https://opensource.googleblog.com/2019/11/knative-governance-update-from-steering.html))。在更新中，该委员会写道，“信任是开源的核心”，并引用清晰的治理作为“建立和维护信任的一种手段。”

委员会承认“仅有愿望是不够的”，并提出了四个要点来定义项目治理的总体目标，其中包括一个清晰且有文档记录的贡献者阶梯，指导委员会监督 Knative 商标的使用和实施的能力，扩大贡献者群体以防止任何一个供应商在项目的任何部分占多数，以及制定治理文档和反馈协议来实施上述变更。

然而，这封信并没有让社区中的许多人满意，在接下来的一周的会议上，关于 Knative 未来地位的讨论是一个常见的话题。在一条提供会议想法的 Twitter 帖子中，[特使代理](https://www.envoyproxy.io/)创建者[马特·克莱恩](https://www.linkedin.com/in/mattklein123)称谷歌既不向 CNCF 捐赠 Istio(与 Kubernetes 密切合作的服务网格实施特使)也不捐赠 Knative 的决定是“短视的”，称这比他想象的“制造了更多的焦虑”。

当时，我们联系了谷歌，一位发言人提供了以下声明。

“谷歌云和社区正在积极投资于持续的项目增长、可持续性以及 Knative 和 Istio 的采用，”他们说。“这两个项目都实施了透明度、治理和包容性，以尽可能确保分布式决策。我们欢迎新的社区成员，任何投资于这两个项目成功的人都可以帮助影响方向，就像我们在 Go、Tensorflow 和我们的其他项目中鼓励的那样。”

> “如果你想为整个行业创建一个类似于万维网的平台，那么你需要你的技术在一个中立的家中”——Alexis Richardson。

在接受新堆栈采访时，CNCF 技术监督委员会成员 Alexis Richardson 回应了这一声明，指出 Knative 和 Go 或 Tensorflow 之间的比较有点不匹配，因为它们都不是企业平台。相反，理查森专注于谷歌捐赠 Kubernetes 的先例，这在许多方面引发了当前的云原生景观。

“的确，其他开源项目可以从基金会之外受益，在基金会之外也很好，但是，如果你想为整个行业创建一个类似于万维网的平台，那么你需要你的技术在一个中立的家中。我们希望 Kubernetes 和栈中所有在它上面的东西成为一个中性家庭的一部分，这样我们就可以把它当作互联网的基础设施。如果谷歌不把它放在那里，那么他们将创造一个分叉的互联网，没有人愿意支持，”理查森说。

这次对 Richardson 的采访是在 12 月初，几乎在同一时间，Knative 指导委员会与社区成员举行了一次“问我任何事”(AMA)，您可以[完整地查看它](https://zoom.us/recording/play/uDvU9mX28ptNHW_IhFRP2h5_dxHSiGUpdV3nStVvJPd_YsqT_Swfl0GfXj9FotKk?continueMode=true)。绝大多数讨论都集中在这个话题上，即谷歌决定不捐赠 Knative，指导委员会成员[杰斯·辛格·杜马斯](https://github.com/jdumars)和[保罗·莫里](https://www.linkedin.com/in/pmorie)回答了大多数问题。在 AMA 进行了大约 10 分钟后，谷歌员工杜马斯给出了一个回应，这似乎是谷歌应对这种情况的核心——将该项目捐赠给 CNCF 不会在本质上改变任何事情，也不会确保超越其自身治理能力的任何进一步成功。

“关于 CNCF 做什么和不做什么，有一大堆假设，我认为做出这些假设有点危险，因为如果你认为通过捐赠你可以得到这些东西，那不是真的。如果我们明天捐赠这个项目，治理方面不会有任何改变，”杜马斯说。“CNCF 不会做出任何改变。唯一不同的是，他们将持有 Knative 这个名字的版权。”

虽然有些人批评 Knative 指导委员会让谷歌提供了大多数成员，七分之四的成员是谷歌的现任员工，但杜马斯指出，浮力创建的 Linkerd 是开源项目的一个例子，也是完全由浮力员工管理的 CNCF 的成员。与此同时，DuMars 承认 SAP“开源爱好者” [Krasimir Semerdzhiev](https://www.linkedin.com/in/krasimir-semerdzhiev-84044a/?originalSubdomain=de) 在之前的问题中提出的观点是正确的，即“CNCF 基本上是作为 CNCF 其他项目的利益相关者的一种方式，因为显然 CNCF 关心其项目之间的互操作。”

“我认为 Krasimir 关于 CNCF 生态系统和互操作性的评论是有道理的，但这并不是因为 CNCF 在强制执行，”DuMars 承认。“这是因为 TOC 和 CNCF 倾向于此，因为他们想提供一些跨项目的保证，我认为这可能会改变，也可能不会改变，但这肯定不是 CNCF 所做的核心部分。这只是 TOC 运作项目的一部分。”

尽管如此，对于谷歌是否以及为什么不将 Knative 捐赠给 CNCF 或任何其他基金会这一长期存在的问题，答案仍然是一样的——决定是由谷歌做出的，它不在指导委员会的手中，他们将继续努力在任何基金会之外提供一个清晰、开放的治理。

然而，对于 CNCF TOC 成员 Richardson 来说，这一点是谈话的关键。在审视这种情况时，理查森以 Istio 为例，谷歌也决定在基金会之外保留该公司。

“厂商中立的家是最重要的事情，因为这是不能通过花钱来提供的，”理查森说。“除此之外，我认为还有一个与其他项目合作的动机，这些项目也在同一个供应商中立的家中。因此，Prometheus、Kubernetes、Envoy 和 Flux 以及 Argo 都将尝试与 Google Istio 集成，如果它在供应商中立的家中的话。如果不是，那么人们就会忽略它。”

在 AMA 和随后的“一整天的工作会议，以实现我们重组项目治理的承诺”之后，Knative 指导委员会再次提供了 Knative 治理的更新，提供了第一封信中列出的要点的更多细节。这一最新更新解决了对谷歌主导的指导委员会的担忧，称将为更广泛的包容性开放额外的席位，并提出了一些方法，计划创建“一个全面的贡献阶梯，定义贡献者如何有资格担任项目中的每个角色。”最后，委员会承诺了一个常见问题解答和对 AMA 遗留问题的回答，以及一个可能的“为社区和我们的用户举办一天的活动”

由于所有这些承诺都是在假期前做出的，这封信仍然是 Knative governance 未来的最后更新，但我们希望我们很快会听到更多消息。

理查森说:“我认为这将是未来 12 个月的一个主要话题，所以我希望你能习惯这一点。”

云原生计算基金会和 KubeCon+CloudNativeCon 是新堆栈的赞助商。

来自 Pixabay 的 Cicero7 特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>