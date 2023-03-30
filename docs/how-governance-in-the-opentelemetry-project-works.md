# OpenTelemetry 项目中的治理如何工作

> 原文：<https://thenewstack.io/how-governance-in-the-opentelemetry-project-works/>

在这篇文章中，我将讨论当我们开始 [OpenTelemetry](https://opentelemetry.io/) 项目时，我们是如何处理资金和联盟的。我很高兴我们如何构建项目的治理和设计来支持那些贡献者，以及如何成功地创建了一个大型、健康的社区。

## 定义明确的民主

 [泰德·杨

Ted 是 OpenTelemetry 项目的联合创始人，目前在 Lightstep 担任开发人员教育总监。他住在俄勒冈州波特兰的一个小农场里。](https://www.linkedin.com/in/ted-young/) 

首先，我们来谈谈治理。OpenTelemetry 没有仁慈的独裁者。在我看来，对于一个希望成为开放标准的项目来说，这不是一个合适的模型。

相反，我们有一个治理委员会。该委员会最初由创始成员组成，但所有职位都由项目贡献者选举产生。根据我的经验，有贡献的工程师倾向于投票给其他有贡献的工程师。这通过确保项目由受尊敬的、积极的参与者来管理，从而保持项目的健康。

治理委员会的职责在我们的[章程](https://github.com/open-telemetry/community/blob/main/governance-charter.md)中有明确的规定，这是出色的[莎拉·瓦特尼](https://twitter.com/sarahnovotny?lang=en)指导我们起草的。合同是用来处理冲突的，所以写合同并不有趣。但是把所有的东西都写清楚可以防止一些潜在的问题。

你希望在事情看起来像是问题之前，而不是之后，把这些规则写下来。例如，章程确保没有一家公司在委员会中有过多的代表。这确保了没有一家公司可以雇佣它的方式进入项目接管。

事实上，OpenTelemetry 中的每一种决策形式都是由角色定义的[。每个角色都有获得它的要求，以及随之而来的责任。再说一次，写起来有点无聊。我们真的需要定义什么是维护者吗？是的。是的，我们有。当转移这些角色时，这考虑到了客观性和指导性，这将发生在一个大的和长期的项目中。](https://github.com/open-telemetry/community/blob/main/community-membership.md)

决策本身也遵循类似的模式。为了保持项目正常进行，使用[规范](https://github.com/open-telemetry/opentelemetry-specification)。对该规范的更改通过一个 [RFC 过程](https://github.com/open-telemetry/oteps/)来处理。这也是一个开放的过程:任何人都可以提交 OTEP(open telemetry Enhancement Proposal)。

拥有一个官方流程真的很有帮助，因为它确保了所有的决策都是公开进行的，并被记录在 GitHub 上。当我们在 Zoom 上见面时，这是很常见的，这些会面也是在公共场合进行的——录音[被上传到 YouTube](https://www.youtube.com/channel/UCHZDBZTIfdy94xMjMKz-_MA/videos) 。

提前做所有这些工作需要一些时间。但是我相信，当项目发展到成百上千的贡献者分布在大量的工作组中时，有这样的结构作为依靠是很重要的。对于大型项目来说，定义角色和过程与定义一个[行为准则](https://github.com/cncf/foundation/blob/master/code-of-conduct.md)一样重要。

## 清晰的项目边界

这种明确的指导也扩展到作为软件的 OpenTelemetry 的架构。系统设计和社区设计相互作用，相互影响。对于 OpenTelemetry，有两个重要的设计决策有助于建立信任。这可能比治理结构更微妙，但是在您设计自己的项目时也值得考虑。

OpenTelemetry 项目的一个主要目标是创建一个通用遥测系统，它可以描述任何计算机系统，然后将这些观察结果传输到任何可观测性后端，而无需重新安装应用程序或库。

通过可观察性后端，我们指的是一个数据存储和分析工具。普罗米修斯，耶格，齐普金，Lightstep，DataDog，XRay，Stackdriver 等。各位！我们希望所有这些系统都考虑采用 OpenTelemetry 作为其仪器系统，并为该项目做出贡献。通过合作建立一个共享的遥测系统，类似于描述计算机系统操作的标准语言成为一个可行的目标。

为项目定义一个清晰的边界帮助我们实现了这个目标。早期，OpenTelemetry 项目宣称它永远不会开发自己的后端。这避免了项目可能在某个时候变成一个封闭系统的风险，并且不再关心其他系统的需求。清楚地表明这一界限让潜在的贡献者和邻近的项目清楚地知道，我们不是某种寻求取代他们的可怕威胁。这使得这些项目中的许多都取得了飞跃，并开始对项目做出重大贡献。

这条规则也清楚地表明了你应该如何利用这个项目来赚钱——建立一个真正令人敬畏和新颖的分析工具，然后把它卖给人们！由于您不需要构建整个遥测管道，您可以将精力集中在改进您提供的分析种类上。我相信在接下来的几年里，我们会在这个领域看到很多创新，基于用 OpenTelemetry 数据做新奇的事情。

## 共享所有权，共享信用

在一个大型项目中，一个巨大的紧张来源可能来自一个出资公司“拥有”项目的一部分，并试图将他们的公司品牌与项目本身的品牌相融合。又名，猪所有的信贷。如果你是集装箱战争的一部分，你可能会记得其中的一些，以及它可能造成的尴尬局面。

我们创建了一个规则，即任何被认为是 OpenTelemetry 一部分的代码必须存在于 OpenTelemetry GitHub 组织中，并且将版权转移给 OpenTelemetry 作者。这一点，加上一些基本的[营销方针](https://github.com/open-telemetry/community/blob/main/marketing-guidelines.md)，帮助我们作为一个团体保持一致，这从整体上促进了 OpenTelemetry 项目。

## 关注点的清晰分离

另一个主要目标是为共享库提供一种本地自我检测的方式。这将允许 web 框架、HTTP 客户端和其他 OSS 项目的作者提供他们自己的可观察性数据。这些项目的作者是专家；他们知道在调优或调试他们提供的库和服务时什么信息是重要的。

为了确保本地插装是可行的，我们实现了 API 与实现的严格分离。使用 OpenTelemetry 测试的任何代码都只拉入 API，它具有很少的依赖性和严格的向后兼容性保证。这确保了当使用 OpenTelemetry 的 OSS 库被组合在一起形成应用程序时，open telemetry 不会产生依赖冲突。

这种 API 分离意味着使用 API 的任何人都不需要使用我们提供的实现——可以插入替代实现。或者根本不使用实现。如果没有安装实现，API 调用将变成空操作。

我们还确保收集器虽然很棒，但在运行 OpenTelemetry 时不会成为必需的组件。同样，我们也不想强迫任何人采用 OTLP。

这种“照单全收”的方法提供了一个普遍采用的项目所需要的灵活性。我们希望用户感觉他们运行每个 OpenTelemetry 组件是因为他们想要，而不是因为他们必须。

## 快乐设计

上述设计选择，无论是代码还是项目治理，都带来了额外的工作。一开始，避免上述承诺肯定会更容易。但是，尽管企业兴趣的规模和数量很大，所有这些结构的到位已经导致了顺利的采用和一个愉快的、低政治的社区。

我不认为每个项目都有一个通用的解决方案，但是我希望当你自己的项目启动时，这里的指导对你有所帮助。

*要了解有关 OpenTelemetry 和其他云原生技术的更多信息，请考虑参加 5 月 4 日至 7 日在[kube con+CloudNativeCon Europe 2021–Virtual](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>