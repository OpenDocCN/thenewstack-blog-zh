# 2022 年可持续建筑实践状况

> 原文：<https://thenewstack.io/the-state-of-sustainable-architecture-practices-in-2022/>

明年，2022 年，将是地球的转折点。要么我们主动大幅减少碳排放，要么全球变暖导致的极端世界事件将继续造成破坏。

科技行业扮演着重要的角色。

计算和信息通信技术(ICT)的排放比之前认为的还要糟糕。技术的碳成本分为两类——硬件生命周期和数据中心用电。因为我们关注的是现代技术，所以这篇文章将关注后者。

在过去一年左右的时间里，[的个体技术工人](https://thenewstack.io/tech-ethics-can-developers-save-the-earth-one-container-at-a-time/)已经越来越意识到气候危机，在较小的程度上，他们的组织的碳足迹和[他们影响它的能力](https://thenewstack.io/what-does-it-mean-to-be-a-green-developer/)。今天，我们反思了绿色建筑实践的现状，并展望了下一个合理的步骤，包括可持续建筑、碳感知工具以及云提供商在做出或打破这一拯救世界的最后努力方面的巨大利益。

## 走向绿色从三巨头规避风险开始

云提供商走向绿色并不意味着利他。碳中和云计算完全是关于业务可持续性和免受监管的保护——通过变得更加环保，你天生就更加厌恶风险。

[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)，微软 Azure 和谷歌云平台[占据了国际数据中心市场](https://www.crn.com/news/data-center/aws-google-microsoft-are-taking-over-the-data-center)的一半以上。这使得它们成为任何可持续建筑策略中最重要的成分。这使得 AWS 成为最大的杠杆，AWS 是市场领导者，也是直到今年才在碳排放方面落后的云提供商。

Container Solutions 的 Anne Currie 表示，AWS 虽然起步较晚，但正在花费大量资金进行追赶。今年早些时候，AWS 上升为世界上最大的可再生能源企业消费者，从历史上更环保的谷歌云手中夺走了桂冠。AWS 还承诺在未来三年内 100%使用可再生能源。

然而，当 AWS 在本月早些时候在 re:Invent 上宣布 AWS 良好架构框架的新可持续发展支柱时，这是一个惊喜。临时首席技术官和前 AWS 雇员 [Paul Johnston](https://www.linkedin.com/in/padajo/) 告诉新的堆栈，这“可能是自 2014 年 AWS Lambda 以来 AWS 交付的最重要的项目——甚至可能比这更重要。”

这篇文章强调了 AWS 可持续发展团队和道德白皮书[2021 年绿色软件实践状况](https://docs.google.com/document/d/1Lym55mXRVO8pldUfrcpRqFKvE9biX93jhz-HLi_c99Y/edit#) *的建议，Currie 和 Johnston 分别是该白皮书的主要作者和撰稿人。

## 绿色建筑师的崛起

不仅仅是云提供商需要做这项工作。如果你想变得环保，团队也有很多工作要做。正如 AWS 定义的这种[共同责任](https://aws.amazon.com/compliance/shared-responsibility-model/)，它将负责云的可持续性，但 AWS 客户负责云中的可持续性。

“谈到可持续发展，AWS 负责云的可持续发展，这意味着我们在水资源管理方面做得很好。我们在能源管理方面做了很多创新。我们正在制造自己的芯片，因为我们真的可以提高成本效率。然而，作为我们的客户，你要对云中的可持续发展负责，以确保你选择那些对你最有影响的技术，”亚马逊首席技术官沃纳·威格尔博士告诉 re:Invent 观众。

根据 AWS，良好的可持续性设计包括:

*   理解(和衡量)你的影响。
*   建立可持续发展目标。
*   通过适当的规模调整最大限度地提高利用率。
*   预测和采用新的、更高效的硬件和软件产品。
*   使用托管服务。
*   降低云工作负载的下游影响。

科技行业需要接受不总是使用碳的架构考虑。所有的建筑师都必须成为绿色建筑师，因为当风能和太阳能变得更便宜，碳税变得更普遍时，“18 个月内你会发现你的托管账单会变得疯狂，”柯里预测。

“架构师只需要考虑如何更好地使用云服务，”她告诉 Zoom 上的新堆栈。

建筑师处于一个独特的位置，可以做出具有更持久影响的决策。正如柯里所说:建筑不只是为了圣诞节。

## 为可持续性而设计的技术

首先要明确的是，团队不能再使用按需实例和专用服务了。在公共云上进行管理总是比在客户云或数据中心上更高效、更具成本效益，除非您使用 100%的可再生能源。无论是谷歌，还是最近的亚马逊，都在 6 月份发布的关于数据中心碳感知计算的白皮书中表示，没有人——无论是公司还是地球——能够再垄断整个服务器。

一切永不停息的事情都要结束。绿色架构师必须设计系统，以便应用程序的一小部分必须连续运行，而大部分只是按需运行。

《绿色软件状况白皮书》中的一些建议是围绕操作工具和技术提出的，包括:

*   在 AWS 或 Azure 上使用 Spot 实例，在 GCP 上使用可抢占的实例。这些按使用付费的做法不仅比按需付费便宜了 90%[，而且让编排者可以自由决定何时运行作业。下一步将是应用碳感知算法来提高数据中心的运营效率。](https://www.cloudbolt.io/guide-to-aws-cost-optimization/ec2-spot-instances)
*   结束过度供应。这种将一切都放在[上的做法成本高昂的 2N 完全冗余](https://thenewstack.io/next-generation-sustainable-data-center-design/)，让许多组织将云存储过度配置了一倍。相反，使用 [AWS 成本浏览器](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)或 [Azure 的成本分析](https://docs.microsoft.com/en-us/azure/cost-management-billing/costs/quick-acm-cost-analysis)来识别[僵尸工作负载](https://thenewstack.io/the-new-stack-context-kubecon-eu-and-the-zombie-workloads/)以关闭。
*   自动扩展 CPU 或网络流量。自动扩展或缩小，甚至利用[预测自动扩展](https://thenewstack.io/kubernetes-autoscaling-keda-moves-into-cncf-incubation/)再次只使用您需要的，而不会影响正常运行时间。
*   让您的云提供商做得更多。完全按需的实例永远无法感知碳排放。通过允许云提供商进行更多管理，您可以提高机器利用率，从而降低碳排放和成本。 [AWS T3 实例](https://aws.amazon.com/ec2/instance-types/t3/)、 [Azure B 系列](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-b-series-burstable)和[谷歌共享核心机器类型](https://cloud.google.com/compute/docs/machine-types)都提供[云爆发](https://thenewstack.io/cloud-bursting-no-longer-a-myth/)，以便扩展您的公共云容量，无论您是在自己的私有数据中心还是在公共云上。

正如该论文所述:“值得注意的是，识别低优先级或可延迟任务的体系结构在高机器利用率下更容易操作。将来，同样的架构在碳意识方面会更好。其中包括无服务器、微服务和其他异步(事件驱动)架构。”

Currie 在过去写过关于 Google 愿意推迟不太紧急的任务来更有效地利用他们的硬件资源的文章。Gmail 确保你可以快速访问你的电子邮件，但 YouTube 可能需要几分钟或几小时来对视频进行代码转换——这是一个从一种文件格式转换成另一种文件格式的 CPU 密集型过程。像所有事情一样[事件驱动架构](https://thenewstack.io/gwen-shapira-on-the-power-of-event-driven-architecture/)，考虑用户体验的架构决策会带来其他好处，比如减少碳排放。

柯里还写道，谷歌的目标是在没有多少零碳电力可用的时候，积极减少使用。现在，他们更能够知道可再生能源支持的数据中心的时间和地点，这是云提供商未来发布的重要内容。

[AWS 的可持续发展团队](https://aws.amazon.com/blogs/aws/sustainability-pillar-well-architected-framework/)还建议:

*   为用户位置优化工作负载的地理位置。
*   优化对客户设备的影响。
*   最大限度地减少跨网络的数据移动。
*   实施数据分类策略。

当然，你可以采取一些策略，但首先要寻找对你的碳足迹影响最大的策略，同时保持甚至改善客户体验。例如，改善任何需要大量加工的东西都会导致更快的响应时间和更少的碳影响。任何减少 CPU 或 GPU 的工作通常都是一个好的起点。

## 不能改善你无法衡量的东西

科技的科学方面最强有力的原则是，你不能改进你不能测量的东西。测量一行代码的碳影响已经够难了，但是测量整个组织的碳影响几乎是不可能的。

“有趣的是，关于碳足迹报告有一场激烈的争论，”柯里说。“谷歌和 Azure 在过去三个月中都强调了他们的碳足迹报告工具，而 AWS 在 re:Invent 上宣布，它将在 2022 年初推出碳报告工具。”除此之外，这些仍然主要是目标——值得注意的第一步，但它们仍然缺乏如何以及何时实现的明确计划。

在过去，fin ops——仍处于萌芽状态的云财务管理实践——是碳报告的合理代理。是的[削减云成本](https://thenewstack.io/want-to-save-the-world-start-by-cutting-your-cloud-costs/)是削减环境成本的最短路径，但随着气温仍在危险地上升，这还不够。此外，我们知道财务部门无论如何都倾向于行动缓慢，所以他们很难跟上连续的交付周期。现在，公司正致力于减少碳影响，财务和云管理再次脱钩。

挑战的一部分在于，这一切都非常依赖于主办地区。有些地区的碳产量远远低于成本。Curries 解释说:“假设我在一个可再生能源发电的地区运行一个应用程序，这个地区是 [AWS 新斯堪的纳维亚](https://blog.aboutamazon.eu/sustainability/amazons-first-operational-wind-farm-in-europe-delivers-clean-energy-to-sweden)【91 兆瓦风能】或者是[法国一个使用核能的地区](https://aws.amazon.com/blogs/industries/tag/aws-nuclear/)——那么我的成本是一样的，但我的足迹更少。”在美国的一些地区，云是由太阳能和风能驱动的，但当天黑时，它是由天然气驱动的。当然，弗吉尼亚州的数据中心巷被认为是最脏的地区之一。

考虑到我们对三家主要云提供商的碳计数计划仍然知之甚少，Currie 继续说道，“希望这些碳足迹生成器将考虑当地电网的电力组合，因为如果他们不这样做，他们就真的没有意义。”但目前，只有云提供商知道他们从当地电网获取电力时当地电网的组成。

“只有他们知道，所以你要依靠他们来告诉你。”Currie 对此表示怀疑，他说“我怀疑他们的第一个版本并没有那么复杂，但是从长远来看，如果我们继续要求的话，它会的。”

[AWS 可持续发展白皮书](https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/wellarchitected-sustainability-pillar.pdf#sustainability-pillar)概述了组织衡量和改进的具体目标:

*   代理指标。计算、存储和网络有助于评估调配了哪些资源。
*   业务指标。工作负载提供的任何可量化的值，如活动用户或事务的数量。
*   KPI。代理指标除以业务指标。

对于任何有针对性的改进，有必要评估潜力、成本和风险，因为总会有权衡，如结果质量、响应时间和可用性。无论您做出什么决定，建议所有组织将可持续性设置为非功能性业务需求。正如该论文所述:“专注于从您使用的资源中获得更多价值，并减少使用这些资源，直接转化为 AWS 的成本节约，因为您只需为您使用的资源付费。”这适用于任何云服务。

## 星巴克如何为可持续发展而设计

星巴克的应用程序由围绕通过 Kubernetes pods 部署的事件驱动微服务的 API 提供支持，而[以关注绿色闻名的公司](https://sustainablereview.com/better-brands-is-starbucks-sustainable/)是有意绿色建筑设计的一个很好的案例研究。[德鲁·恩格尔森](https://www.linkedin.com/in/drewe/)，作为工程总监，与 re:Invent 的观众分享了他计算该应用程序碳足迹的旅程。他很快了解到，星巴克的可持续发展团队使用了“一个非常粗糙的、基于支出的模型来估算年度碳排放量。”虽然 20%的碳足迹来自乳制品，但不到 1%的碳足迹来自技术。

“虽然 1%似乎很低，但我们是一个非常大的企业，所以 1%仍然是一个相当大的数字，”恩格尔森说。他们想看看是否可以应用技术来减少技术之外的足迹。

“我还了解到，年度支出模型不够精细，也不够及时，我无法做出架构决策来进行更改、测试并了解它如何影响我们的碳足迹。”因此，他的团队花了整整一周时间来创建一个更绿色的云仪表板，用于测量碳足迹以及碳足迹与客户体验之间的潜在关系。

他们从 AWS 使用数据开始，应用标准化的成本和 CPU 时间。因为这些是代理指标，他们不一定要精确，但如果他们逐月朝着正确的方向前进，如果他们能够发现新的机会以提高效率，他们会更精确。

然后，他们联系 AWS 可持续发展团队，以获得他们托管的更硬的数字。他们从 AWS 即将推出的一些碳足迹工具的早期版本中获得数据，他们发现他们在 2019 年至 2020 年间实际上减少了约 32%的碳足迹，同年他们将订单功能从 50 家商店扩展到 15，000 多家商店。

星巴克工程团队意识到有机会将业务增长与碳减排分开。至少在这种情况下，针对计算的优化带来了业务增长和碳足迹的大幅减少。他们开始关注以下发展模式:

*   可观察性和服务水平目标(SLO)。
*   按设计高效，包括:cloud native 更干净，Kubernetes 允许将服务密集打包到它下面的基础设施上， [gRPC 二进制通信协议](https://grpc.io/)，他们有很多用 Scala 编写的服务。
*   调整规模–优化成本，关闭未充分利用的资源，匹配每个工作负载的 EC2 实例，以及[自动扩展调优](https://thenewstack.io/5-best-practices-for-configuring-kubernetes-pods-running-in-production/)。

恩格尔森还强调了他所谓的一些不太明显的教训:

*   他们将他们的一些[实例类型切换到 ARM](https://thenewstack.io/aws-graviton-marks-the-emergence-of-arm-for-cloud-native-workloads/) ，后者具有相同的成本和性能，但更节能。
*   他们使用 [AWS spot 实例](https://aws.amazon.com/ec2/spot/?cards.sort-by=item.additionalFields.startDateTime&cards.sort-order=asc)来优化成本，但他也表示，这允许云提供商“获得更高的基础设施利用率”
*   他们随机安排备份时间，因此他们不再是在每小时开始时运行备份的大多数人，这反过来又会推动 AWS 上的峰值。

![Digital Ecosystem with different bubbles of impact overlapping ](img/0d8e2e55976c0647c27fd4ef940108f5.png)

他还表示，星巴克希望有意进入低碳地区，但这当然仍有待决定。

Engelson 继续说，虽然他们将大部分可持续发展审计集中在云上，但他的工程团队是一个更大生态系统的一部分，该生态系统还包括数据中心、数据传输、供应商和最终用户设备。

Engelson 说:“无论您处于业务的哪个部分，如果您正在决定如何配置数据中心，如何构建应用程序，如何与供应商签订合同，您都可以做一些事情来帮助提高工作负载的可持续性。”

考虑到这一点，他强调了一些有助于减少碳足迹的唾手可得的水果:

*   转向云，AWS 宣称云的效率提高了近 80%。
*   启用应用内黑暗模式。
*   不要让机器人一直从你的网站上抓取信息。
*   减少 CPU。
*   减少页面重量。
*   停止视频自动播放。

他建议使用[网站碳计算器](https://www.websitecarbon.com/)来找出其他容易获胜的网站，并阅读汤姆·格林伍德的[可持续网页设计](https://sustainablewww.org/principles/sustainable-web-design-by-tom-greenwood)。

最后，Engelson 认为，我们不应该把重点放在有助于环境的成本优化上，而应该致力于与成本密切相关的碳优化。与此同时，开始在整个公司进行对话。

## 可持续建筑的下一步

除了更加关注开源中缺乏多样性和包容性之外，KubeCon-CloudNativeCon 时间表中的另一个明显漏洞是环境——2022 年所有技术活动都应该以某种方式包括这个主题。尤其是 Kubernetes，它是由等待它的额外容量实现的，这本身就造成了浪费。

因为 Kubernetes 编排如此复杂，您很可能需要一个[服务网格](https://thenewstack.io/category/service-mesh/)，添加一个代理 sidecar 容器，这是非常耗费资源的。像 Istio 和 Linkerd 这样的服务网格本质上是永远在线的、按需的，并且[非常节能](https://medium.com/@michael_87395/benchmarking-istio-linkerd-cpu-c36287e32781)。Istio 每个代理可以消耗大约 [1GB 的内存](https://medium.com/geekculture/watch-out-for-this-istio-proxy-sidecar-memory-pitfall-8dbd99ea7e9d)。

“即使在一个非常小的环境中，比如说，有 20 个服务，每个服务运行五个 pod，分布在三个节点上，您也有 100 个代理容器。无论代理实现有多小多高效，纯粹的重复都会耗费资源，”Liz Rice 写道， [Isovalent](https://isovalent.com/) 的首席开源官和 CNCF 技术监督委员会主席[在一篇关于新堆栈的博客文章](https://thenewstack.io/how-ebpf-streamlines-the-service-mesh/)中写道。然后，每个代理使用的内存随着它需要与之通信的服务数量的增加而增加。

赖斯在 eBPF 中提出了替代方案，她将其描述为“一种允许定制程序在内核中运行的内核技术”。这些程序响应事件而运行，eBPF 程序可以附加成千上万个可能的事件。”eBPF 的特点是每个节点一个内核，所以在同一个节点上运行的所有 pods 共享同一个内核。

甚至还有基于 eBPF 的联网、可观察性和安全性，通过 CNCF 沙盒项目 [Cilium](https://cilium.io/) 来实现，它允许服务网格没有边斗，这可以将代理实例的数量从大约 100 个减少到 3 个。

此外，Cilium 支持 eBPF 的网络已被基准测试为在 Kubernetes 网络中实现了显著的性能改进，它允许数据包走捷径，绕过内核的部分网络堆栈。

eBPF 是朝着正确方向迈出的充满希望的一步。当然，服务网格效率是碳感知预测分析可以显著帮助的另一个领域，此外，还允许云提供商进行自我管理。

2022 年另一件需要关注的事情是，托管服务提供商增加其在哪些地区更具可持续性的透明度。作为一个行业，我们必须继续推动这一点来得更快——如果我们只选择在可持续的服务器上托管，他们最终会让所有的服务器都是可持续的。绿色软件实践白皮书建议询问您的云提供商，哪些是他们可持续扩张的首选区域。提出问题是大组织提供答案的第一步。

最后提醒一下，接下来的 12 个月都是关于建筑师的。“弄清楚这对你所策划的服务意味着什么。如果你对你将要做的事情没有一个计划，你将会有麻烦。Currie 说:“监管将会出台，但可能会以数据中心碳定价的形式出现，无论是在本地还是在云中。”所以你不会想等的。

那么，你的建筑团队的游戏计划是什么？绿色建筑策略还应该包括什么？告诉我们 [@TheNewStack](https://twitter.com/thenewstack) 和 [@JKRiggins](https://twitter.com/jkriggins) 。

*请注意，这是第四年的[2021 年绿色软件实践状况](https://docs.google.com/document/d/1Lym55mXRVO8pldUfrcpRqFKvE9biX93jhz-HLi_c99Y/edit#)，这又是在谷歌文档中，一种更加绿色的发表论文的方式——并且欢迎互动评论和[持续反馈](https://twitter.com/anne_e_currie/status/1458821558709932036)。

*这篇文章的作者也为本文中提到的容器解决方案撰写文章。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>