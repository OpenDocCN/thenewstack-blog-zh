# 揭穿顶级单片应用程序的神话

> 原文：<https://thenewstack.io/debunking-the-top-monolithic-application-myths/>

顾名思义，巨石柱是神秘的实体。在数以千计的全球组织中，单体应用程序通常是独立的，并排的，就像它们的巨石阵兄弟一样——过去的建筑杰作唤起了敬畏和神秘。但与它们的史前对等物不同，单片应用程序是当今现代业务结构的组成部分，是每个业务关键流程的关键贡献者，从后台办公室到供应链到客户服务到商业参与等等。

虽然这些巨大的系统继续为业务做出巨大贡献，但这些应用程序的现代化是一个持续的挫折和痛苦的来源。许多组织简单地放弃了，而其他组织则通过重新托管或重新平台将整个整体迁移到云中作为权宜之计，这是旧的“提升和转移”但现在是 2022 年，新的希望、新的技术和新的方法正在打破围绕单片应用的神话。

## 神话#1:整体现代化是一个失败的事业

 [鲍勃·奎尔林

Bob 是 vFunction 的首席生态系统官，负责开发者宣传、营销和云生态系统参与。Bob 之前是甲骨文云基础设施(OCI)开发人员关系副总裁。他是 StackEngine 的联合创始人兼首席执行官，并在 2015 年 12 月甲骨文收购 StackEngine 时加入甲骨文。Bob 住在德克萨斯州奥斯汀，是一名连续创业者，之前曾在多家科技公司担任高管职务。他的职业生涯专注于应用自动化来简化复杂的云、IT 和开发人员挑战。你可以在推特@bobquillin 上找到他。](https://twitter.com/bobquillin) 

每个云提供商、云原生平台和系统集成商都有一个模型，该模型包含了现代化词典中几乎所有的“R”。最初，这个行业只从现代化的五个 R 开始:主机更换、重构、重新架构、重建或替换。随着现代化的成熟，越来越多的顾问参与进来，R 的数量也在增加，包括重新平台、重写、保留和淘汰。这令人困惑，因为现代化的实践更多的是艺术而不是科学。几乎没有数据、数学和自动化应用于整块巨石的现代化过程。有[本书](https://martinfowler.com/books/refactoring.html)和最佳实践，加上许多愿意提供建议和交付的顾问和解决方案架构师。这些都是很好的开端，但通常要么侧重于 DIY(自己动手)方法，要么侧重于昂贵、高风险的外包服务。

并非一切都没了。有一个新的工具，应用人工智能和自动化的浪潮正在被应用于弥合所有 DIY 或所有外包选项之间的差距。这些方法的基础是基于整体的实际架构分析，不仅仅是需要迁移到新版本的底层平台组件，还有实际的业务逻辑本身。业务逻辑是应用程序的核心，架构师可以从这里开始确定能够带来更清晰的微服务领域驱动设计的领域。至少，这些代表了更独立的迷你服务或者仅仅是以更高程度的排他性运作的普通服务。缺乏基础数据驱动的方法导致应用程序团队放弃现代化，并选择迁移策略作为权宜之计，这导致了误解 2。

## 神话 2:将独石迁移到云=现代化

将您的应用程序迁移到云是一个令人信服的目标，也是一个“moonshot”愿景，它将 IT 和应用程序团队聚集到一个更大的目标上。但要明确的是，移民不等于现代化。在整体迁移到云的过程中，可以获得巨大的开发运维及数据中心缩减优势。几乎所有组织都实现了这些短期收益，并反过来为寻求加速和简化企业工作负载向云迁移的云提供商提供了意外之财。许多技术领导者犯的错误是相信他们的工作已经完成了——我们现在已经现代化了！

这个神话很快就被打破了:现在，大多数组织都清楚地知道，云中的一个庞然大物存在着它在内部存在的大部分棘手问题——缓慢的工程速度、缺乏可扩展性、难以维护性和低可持续性。随着成本开始上升，云的好处仍然遥不可及，许多人将这一阶段称为“搬起又搬的遗憾”或“迁移懊悔”。为了打破这个神话，必须在一个更大、更具战略性的现代化战略的背景下看待和规划移民——移民是好的，只要它是完全现代化的一块基石。monolith 的现代化使其能够充分利用云原生架构的价值，从容器和微服务到 Kubernetes 和无服务器。再加上利用通用 CI/CD、安全性和 DevSecOps 策略和平台的优势，您的业务案例很快就会水落石出，这就引出了第三个误区。

## 误区 3:构建准确的应用程序现代化业务案例是不可能的

对于大多数组织来说，应用程序现代化最困难的部分是为现代化项目建立准确的业务案例。我们已经探索了解决神话#1 中这个问题的缺失元素之一:预测时间和工作量的架构师与批准预算和资源的业务领导之间的讨论缺乏数据驱动的基础。缺乏共同语言和衡量基础导致了领导层和管理层之间信任的双向破裂。打破这种循环需要数据和测量开始。

从分析测量整体结构的复杂性和改变整体结构的风险开始。为了理解复杂性，这需要首先识别依赖关系的社区或集群，这表明哪里域是明显的，因此哪里可以提取微服务。[然后可以通过类依赖关系之间的纠缠程度来计算复杂度](https://vfunction.com/solutions/formulate-your-modernization-strategy/)，从而降低代码的模块化程度。风险可以通过依赖链的长度来衡量，依赖链的长度决定了应用程序中某个部分的变化对应用程序下游不相关部分的影响程度。这些都可以汇总成一个[总体技术债务得分](https://vfunction.com/wp-content/uploads/2022/04/vFunction-AssessmentHub-Datasheet-2022-final.427.pdf)，它揭示了当前在债务和创新上花费了多少，从而揭示了现代化项目的 ROI 和 TCO 业务案例优势。从这个强有力的量化立场来看，业务优先级更容易达成一致，这导致我们打破了神话#4。

## 神话 4:所有的巨石都是平等的

独石有各种形状和大小，有不同的商业价值和非常不同的复杂性。事实上，整体架构可以成为各种用例的相关现代设计模型。一个简单的第一步是根据它们的商业价值对你的独石进行排序。评估他们的业务效用和工程负载、功能积压和维护成本。通常，这些应该是一致的，因为团队的规模、待定特性的数量和维护成本应该与企业整体的商业价值一致。事实上，这些巨石抵制“遗产”的标签，因为他们仍然是企业和支持他们的工程团队的一等公民。业务价值下降的老化的整体是简单的平台改造或最终淘汰的绝佳选择。

对于仍然是可行的业务贡献者的应用程序，有必要[全面评估它们的复杂性](https://vfunction.com/assessment-hub-free-trial/)以及与它们的现代化相关的风险(参见误区 3 ),以制定最佳计划，从而制定更准确的业务案例。通过计算这些业务关键型整体的复杂性、风险和由此产生的技术债务，您可以使用基于人工智能的自动化工具来加速过程，将不太复杂的项目转移到更快的应用程序现代化项目中。更复杂的整体——通常被称为“巨石”——将花费更多的时间，并且应该遵循更迭代的重构方法，使用[扼杀者模式](https://vfunction.com/blog/simplify-refactoring-monoliths-to-microservices-with-aws-and-vfunction/)一次选择性地提取一个或两个微服务，以将控制从整体切换到新服务。这些单一的应用程序可以存在于任何地方，甚至是云中，这就是神话 5。

## 神话 5:巨石柱是一个内部问题

诚然，今天的大部分巨石柱仍然存在，牢牢地固定在它们原来的基础设施上。但是越来越多的单体已经成功迁移到了云，它们现在运行在云提供商的 IaaS 基础设施中，使用提供商的电力、CPU 和内存，但不幸的是仍然作为单体运行。云中的这些单体可能会成功运行一段时间，但当可扩展性问题出现时，唯一的解决方案是以越来越多的费用购买越来越大的映像——更多的 CPU 和更多的内存。这些可能需要更昂贵的保留实例，云工程师必须始终在红线级别运行，没有弹性，没有水平可扩展性。

上述相同的数据驱动的评估方法和优先化方法与云中的这些巨石完全相关，甚至可能更相关。为什么？数据驱动的评估、人工智能支持的现代化和迁移后重构[是所有解决方案和软件架构师需要的关键能力](https://thenewstack.io/3-must-have-modernization-competencies-for-application-teams/)。云中的一块巨石如此接近完全实现其现代化的命运。一旦 monolith 重构过程完成，容器、Kubernetes、DevOps、无服务器和服务网格服务就可以在云提供商上启动了。只要解开那块巨石；参见误解 6。

## 神话 6:独石依赖是不可能解开的

负责维护的建筑师面临着一个令人生畏的挑战，更不用说让他们负责的巨型建筑现代化了。大多数时候，他们不是最初的架构师或开发人员，即使他们是，这个整体也会随着时间的推移而发展，承担越来越多的技术债务，这些债务可能会掩盖最初的意图。这些纠结而密集的巨石有很多相似之处:泥球、意大利面条代码、鸟巢和纠结的线团。如果你曾经花了几个小时解开你的节日灯或钓鱼线缠绕的灾难，你知道这个挑战。

人工智能实际上可以在这方面提供帮助。当[系统可以将一个整体的深度依赖关系](https://vfunction.com/product/)表示为图形时，图形机器学习可以检测形成潜在领域活动社区的集群和联系——这可以带来一系列好处，从理解复杂性和变化风险到实际检测潜在的微服务和社区之间的边界。构建支持它的图表和模型需要混合动态和静态分析，但最终结果是更加高效和有效的现代化工作。不可能的整体现代化变得可能，它们变得更加可预测和更快，导致我们最后的神话。

## 神话 7:整体现代化需要永远

在打破了上面的六个神话之后，应该很清楚，如果你遵循建议，时间和预算在你的现代化中应该不是一个很重要的因素。现在，讨论的应该是您应该实现哪些现代化，从而带来业务优势和成果。清晰的评估和数据驱动的规划也应该塑造您实现现代化的方式。具有较高复杂性分数的应用程序应该遵循一种迭代的、选择性的重构策略，在这种策略下，不太复杂的关键业务模块可以更快地完成整个过程。

在过去的十年中，应用程序现代化一直是一种人力密集型的最佳实践，需要广泛的培训以及文化和组织的转变。这些实践是关键的技能，但是由于技能差距和失败疲劳，自动化和支持工具的缺乏已经将过程减缓到停滞状态。新工具在这里拥抱这些方法，并通过人工智能和自动化将它们提升到新的水平。下一步是部署一个[持续现代化方法](https://thenewstack.io/vfunction-guides-enterprises-toward-continuous-modernization/)，它插入 CI/CD 管道，在应用程序的整个生命周期中检测并修复技术债务。 [vFunction platform](https://vfunction.com/) 是专为帮助建筑师进行评估和现代化项目而打造的，旨在打破最大的神话。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>