# DevOps 团队的云原生可观察性:简介

> 原文：<https://thenewstack.io/cloud-native-observability-for-devops-teams-an-introduction/>

Editor’s note: This is the introduction to The New Stack’s latest ebook, Cloud Native Observability for DevOps Teams. You can download the entire ebook [here](https://thenewstack.io/ebooks/observability/cloud-native-observability-for-devops-teams/).

如果您正在阅读本文，您可能已经在使用云原生应用程序和架构，或者您的组织正在踏上云之旅。如果是这样，您已经熟悉了云原生环境提供的大量选择。这么多的工具和这么多做出错误决定的机会。

一句话，这么多复杂。

即使您的团队只监管一个或几个微服务集群，这些集群也可能部署在多个公共云或云和本地服务器的组合上。更加复杂。

当出现异常时——延迟、应用程序编程接口(API)调用高峰、重要服务突然中断——您如何知道是什么原因导致的呢？你怎么知道这是一个孤立的事件还是一个小故障，会让一切都崩溃？

问题是，除非你的整个团队具有完全的可观察性，否则你无法知道。

对于一个组织的能力来说，没有什么比可观察性更重要的了，它不仅能发挥作用，还能服务于客户。也许没有什么比这更容易被误解了。

可观察性意味着从外部输出推断系统的内部状态。但这不仅仅是看到系统中发生了什么的能力。这是一种能力，能够理解所有的事情，收集和分析防止事故发生所需的信息，并在事故发生时追踪其路径，尽管有各种保护措施，以确保它们不会再次发生。

## 不再仅仅是运营部门的工作

传统上，可观测性是操作工程师的责任。但是随着 DevOps 团队的出现，更多的责任“左移”给了开发人员，这变成了每个团队成员的工作。如果您正在构建一个应用程序，那么在应用程序生命周期的后期，可观察性不能被归入“附加”状态。不这样想就像制造一辆汽车，把速度计、里程表和仪表灯留给经销商去安装。

在 2021 年 1 月由 [VMware Tanzu](https://tanzu.vmware.com?utm_content=inline-mention) 对 300 多名 IT 专业人员进行的[调查](https://hello-tanzu.vmware.com/state-of-observability-2021/?utm_source=google&utm_medium=cpc&utm_campaign=amer_c4_a2&utm_content=g1_t045&utm_term=application%20observability&_bt=513356028639&_bk=application%20observability&_bm=b&_bn=g&_bg=114812554943&gclid=Cj0KCQjwxJqHBhC4ARIsAChq4asuepy7PSG-CrfxsCqmH3bkDqcHu5hy7sEZ0YIkwQN3VKg359S39UoaAsyxEALw_wcB)中，84%的参与者表示，如果包括开发人员在内的更多利益相关方能够了解他们系统的整体基础架构和性能指标，他们的云应用程序将具有更好的可用性和性能。

当前关于可观测性的讨论始于改变游戏规则的云原生技术(如 Kubernetes)的引入之前。在被大量引用的[科里·沃森](https://www.linkedin.com/in/gphat/)2013 年[的博客文章](https://blog.twitter.com/engineering/en_us/a/2013/observability-at-twitter)中，科技界了解了 [Twitter](https://about.twitter.com/) 的工程师如何在公司从整体架构转向分布式架构的过程中寻找跟踪他们系统的方法。

此时，正如 Watson 所描述的，Twitter 将其可观察性工作集中在收集和监控指标，以及从其收集的数据点生成的可视化上:

图表通常是临时创建的，以便在部署或事故期间在团队内部快速共享信息，但也可以在仪表板中创建和保存。工程师可以使用用于创建仪表板的命令行工具、用于通用指标的可重用组件库以及用于自动化的 API。

日志记录和跟踪在标题为“相关系统”的一个段落中进行了介绍

沃森写道，Twitter 创建了一个命令行工具，帮助其工程师创建自己的仪表板，以跟踪他们的指标生成的图表:

Twitter 上的仪表盘平均包含 47 个图表。如果你漫步在办公室，在大屏幕或工程师的显示器上看到这些仪表板是很常见的。Twitter 的工程师就住在这些仪表盘里！

## 超越“可观察性的三大支柱”

随着云计算时代的到来，越来越多的工程师开始“生活在他们的仪表盘中”他们认识到，仅仅监控数据点是不够的。因此，可观察性并不仅仅意味着监控，而是基于三个支柱，这就是众所周知的:

1.  **度量**:系统中各种活动的度量。
2.  **跟踪**:请求在分布式系统中移动时所采用的路径。
3.  **日志**:系统内活动的记录。

越来越多的，关于可观察性的讨论超越了这三个支柱，采取了一种更加微妙的观点。人们对这三大支柱是如何结合在一起的有了更多的认识，也更加重视分析。开发运维团队越来越认识到衡量满足服务级别目标(SLO)的真正重要因素的重要性。

经理们在高流动率和相对较少的人才储备中苦苦挣扎，试图找出如何减轻“寻呼机疲劳”的人力成本——要求运营工程师在白天或晚上的所有时间响应警报，这些警报可能是也可能不是业务关键事件的信号。

SLOs，一个由谷歌网站可靠性工程团队在 T2 SRE 书籍 T3 中记录的概念，可以根据每个组织甚至团队的目的而有很大的不同，例如为一定数量的请求实现特定的延迟，或者确定多少客户可以在一个在线购物车应用程序中同时购买。服务水平指示器(sli)是照亮一个健壮的可观察性过程的信号，并且可以显示一个团队是否正在实现它的 SLO，或者一个问题是否正在酝酿。

如前所述，分布式系统和云原生技术增加了可观察性的复杂性。毕竟，Kubernetes 无处不在，而且“无处不在”很难追踪。

在 VMware Tanzu 调查中，90%参与调查的 IT 专业人员表示，分布式应用程序带来的监控挑战比其他应用程序大一个数量级。

超过 80%的调查参与者表示，传统监控工具不足以跟踪现代云应用。只有 8%的受访者表示他们对其组织当前的监控工具和流程“非常满意”。

## 增加商业价值

云技术本身并不总是容易被观察到。例如，普通的 Kubernetes 只提供非常基本的功能，通过 kubectl 来检查集群中对象的状态，而没有成熟的本地日志解决方案，正如[Francis Espenido](https://www.linkedin.com/in/franciss-espenido-1bb84725)、 [LogDNA](https://logdna.com/?utm_content=inline-mention) 的高级技术合作伙伴项目经理在我们的新电子书的章节中所写的那样。

但是克服这些挑战可以为企业带来回报。

在 VMware Tanzu 调查中，92%的受访者表示可观察性推动了更好的业务决策。运动服装零售商阿迪达斯(Adidas)就是一个例子，说明可观察性正融入企业经营方式。

阿迪达斯的解决方案架构总监 Rastko Vukasinovic 表示，随着公司规模的扩大，它需要让可观察性变得更加容易。因此，它[建立了自己的整体监控系统](https://thenewstack.io/how-adidas-manages-for-scale/)，不仅可以收集和观察技术指标，还可以收集和观察业务数据。

其全球 DevOps 团队现在每天编译代码超过 10，000 次。阿迪达斯的整体数字化转型帮助其电子商务收入从 2012 年的 4700 万美元飙升至 2020 年的 47 亿美元。

对于开发人员来说，拥有更多关于可观察性的知识——并构建安全的、可观察的、容易满足 SLO 的应用程序——意味着对整体业务目标做出更多贡献。根据[451 Research](https://www.sumologic.com/brief/observability-evolution/)2019 年的一项调查，开发人员 55%的时间花在维护和管理服务于当前业务需求的定制应用上；只有 45%的时间用于构建新的应用程序，以帮助企业在竞争中脱颖而出。

根据由 Sumo Logic 委托的 [451 Research](https://451research.com/) 的 [2020 关于可观察性的报告](https://www.sumologic.com/brief/observability-evolution/)，对 SLO 的更多关注可以帮助开发者将更多时间花在推动新业务的应用上:

通过了解描述对最终用户至关重要的性能的关键目标，开发人员可以针对最重要的性能问题优先处理现有应用，而不是对用户没有负面影响的基础架构或应用异常。

云原生可观测性的故事还在增加新的篇章。科技界正在关注[open telemetry](https://opentelemetry.io/)——一个旨在创建一套标准化工具、API 和软件开发工具包(SDK)的开源项目——它现在正在[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)孵化。

在其新的电子书中，新的堆栈收集了一些关于可观测性现状的最佳文章，这些文章由来自 [LogDNA](https://www.logdna.com/?utm_content=logo-sponsorpage&utm_source=thenewstack&utm_medium=website&utm_campaign=platform) 、[浮力](https://buoyant.io/)、 [Dynatrace](https://www.dynatrace.com/?utm_content=inline-mention) 和[蜂巢](https://www.honeycomb.io/?utm_content=inline-mention)的专家撰写。它面向 DevOps 团队的每一名成员，让全栈参与确保云原生应用和系统平稳运行并让客户满意。将应用程序代码“扔过墙”并让操作工程师处理后果的日子已经过去了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>