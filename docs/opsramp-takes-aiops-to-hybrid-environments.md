# OpsRamp 将 AIOps 带到混合环境中

> 原文：<https://thenewstack.io/opsramp-takes-aiops-to-hybrid-environments/>

AIOps，即采用人工智能来管理 IT 运营的实践，最近已经成为一个相当流行的词，Gartner [将此归因于运营团队因其系统生成的数据的数量、种类和速度而不堪重负。](https://tekwurx.com/wp-content/uploads/2019/05/Gartner-Market-Guide-for-AIOps-Platforms-Nov-18.pdf)

它描述了面向 It 运营的机器学习的四个阶段:描述性、诊断性、前瞻性能力和根本原因分析。

虽然迄今为止很少有供应商提供全面、集成的 AIOps 平台，但它预测，在五年内，大范围的 AIOps 平台将成为规范，而不是将 AIOps 功能嵌入应用性能管理、网络性能管理或 it 基础设施管理工具等监控工具中。

在那些对 AIOps 持更广泛观点的人中，要数[ops amp](https://www.opsramp.com/)了。

本周，该公司发布了对其 OpsQ 事件管理和智能关联机器学习模型的增强，以及针对亚马逊网络服务和谷歌云平台的新的多云基础设施监控功能。

OpsRamp 工程和 DevOps 高级副总裁[巴努·辛格](https://www.linkedin.com/in/bhanu-singh-ab888810/)说:“你可以将它视为运营管理的大数据平台。

一些供应商专注于 IT 运营的一个方面，即发现问题或监控问题，而 OpsRamp 则采取更全面的观点，涵盖云和本地基础架构运营。

Singh 告诉新的 Stack [之前的](/what-is-aiops-and-why-you-should-care/):“ai ops 提供对工具的访问，这些工具可以将数据、数据分析和机器智能结合在一起，通过收集和分析数据来做出高级决策并执行自动化操作。”

他说，OpsRamp 提供了对您所拥有的资源(路由器、交换机、存储)的可发现性和可观察性，或者如果您在云上运行东西，您的 EC2 实例、RDS 数据库、Azure 上的 IaaS，并确保您有一个单一的视图。

### 在噪音中跋涉

这家总部位于圣何塞的公司由服务管理背景的 [Raju Chekuri](https://www.linkedin.com/in/raju-chekuri-66431b1/) 和 [Varma Kunaparaju](https://www.linkedin.com/in/varmak/) 于 2014 年创立。2017 年，它从 Sapphire Ventures 获得了 2017 年 2000 万美元的资金。其客户包括云服务供应商 GreenPages、广告和营销公司 Epsilon 以及托管服务提供商 Carousel Industries 和 CloudBrix。

辛格说，OpsRamp 鼓吹本地发现和本地监控，尽管客户不必使用这些 SaaS 功能，如果他们更愿意坚持使用他们现有的工具。

在通过内部和云操作接收、聚合、分析数据并向客户提供建议的同时，该公司自己也在通过 AWS 和 Azure 以及自己的数据中心进行操作。

他说，它对 AiOps 采取了不同的方法。

“[其他供应商说]‘我们收集你的数据，并把它放在一个神奇的盒子里。我们摇动它，在另一端给你一个输出。我们有所有的算法来解决这个问题。

“我们不会采取那种方式，”他说。“我们相信 AiOps 并不是孤立的。…总是需要更多的集成。

“我们做本地监控。机器学习的算法应该是内置的，并解决问题…你如何做事件警报？您如何进行事件分类？警报关联？异常检测？根本原因分析？…您拥有所有数据。”

它提供了一个可定制的控制面板，客户可以按服务器、虚拟机管理程序、网络、业务部门、业务线、位置、云区域、数据中心、分支机构等过滤视图。

“我们正在密切关注一小群供应商，他们推出的平台可以提供一系列监控和事件管理功能。这些供应商，包括 OpsRamp、 [FixStream](https://fixstream.com/) 和 [Centerity](https://www.centerity.com/) ，代表了新一代的 IT 运营管理(ITOM)供应商，既服务于事件响应者，也服务于高级管理人员，” [451 Research](https://451research.com/) 高级分析师 [Nancy Gohring](https://info.opsramp.com/application-and-infrastructure-performance-market-map) 写道。

她认为未来是运营的混合，并且自 2018 年底以来，Kubernetes 监控是 AiOps 供应商的必备产品。OpsRamp 在其夏季版本中增加了这一功能。

她将 OpsRamp 分为两类:基础设施监控和事件关联。

Fellow 451 Research 分析师 [William Fellows](https://www.opsramp.com/wp-content/uploads/2019/03/451_Reprint_OpsRamp_25MAR2019.pdf) 指出，OpsRamp 面临着在监控、事件分析和事件管理方面提供单点产品的竞争对手，以及提供某种组合的供应商。它们包括 [Datadog](https://www.datadoghq.com/) 和 [SignalFX](https://techcrunch.com/2019/08/21/splunk-acquires-cloud-monitoring-service-signalfx-for-1-05b/) ，最近[被 Splunk](https://thenewstack.io/splunk-buys-signalfx-how-cloud-native-observability-accelerates-digital-transformation/)收购， [ScienceLogic](https://sciencelogic.com/) 以及更多来自 [Moogsoft](https://www.moogsoft.com/) 和 [Big Panda](https://www.bigpanda.io/) 的全功能产品。

辛格说，OpsRamp 的与众不同之处在于它专注于混合环境，以及从警报噪音中筛选意义的能力。

新堆栈最近推出了一个[演示](/opsramp-demo-an-aiops-platform-for-hybrid-infrastructure-management/)，其中 OnRamp 的 AI 处理了来自混合基础设施的近 200 万个原始事件，并将其归结为 10，000 个需要解决的问题。

其对 200 名 IT 决策者的[调查](https://www.opsramp.com/wp-content/uploads/2019/04/The-OpsRamp-State-of-AIOps-Report.pdf)发现，对 AiOps 客户来说，四个最重要的特性是推理模型、事件可视化、数据无关摄取和集成生态系统。

OpsRamp 拥有 100 多个与 AWS、Azure 和谷歌云平台的集成。其秋季版本增加了与 AWS IoT 的集成；AWS 开发工具，如 CodeCommit、CodeBuild、CodeDeploy 和 CodePipelineGCP 平台资源的实时发现。它简化了使用 webhook 身份验证来构建客户集成。

新版本还增强了其智能事件管理、警报关联和补救解决方案 [OpsQ](https://www.globenewswire.com/Tracker?data=qU2iw_MZZb8u-yaJ_gR4q19f9Fy7mV_GoGyPlLVdyjSwLn47qXXm2DcItp1aqTYrtABX4Sf0sxJzeyTZfheNvlG8TEpZWXftdY9-wlkPKB7w3OSv2TMuDPTJtEruur3t) 。它们包括新的推理模型，使用基于相似性的模式识别来更快地发现相关警报以进行故障排除；细粒度的观察模式小部件；以及通过来自其他 IT 运营管理工具的警报改进资源上下文获取。

此外，增强的综合监控功能让客户能够将网站中断定位到特定的网络路由。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>