# 通过分阶段方法为微服务做好准备

> 原文：<https://thenewstack.io/get-ready-for-microservices-with-a-phased-approach/>

在线数字调查和市场研究公司 [Questback](https://www.questback.com/) 在其 18 岁的整体应用架构转型过程中，现在正在完成为期一年的容器化计划，并准备开始相应的微服务部署。

该公司正在重新设计其平台，以使其现代化，更容易为客户添加创新，并使其更具成本效益。

一些 It 分析师告诉 The New Stack，这种策略在越来越多的企业中越来越受欢迎。他们说，像 Questback 这样的分阶段方法是实现这一转变的好方法。

随着公司朝着其现代化目标努力，它将继续运行和维护其现有系统，以尽可能实现无缝转换。

“我们生活在一个平行的世界里，”Questback 首席执行官弗兰克·穆勒普告诉《新堆栈》。“我们在准备新东西的同时，也在处理旧东西。所有这些都可以更快地完成，但我们决定在我们这一端稍微慢一点，以确保我们不会像往常一样对我们的业务造成太大影响。”

## 两阶段方法

从零开始是不可能的，因为现有的系统已经投入了太多的资金，而且它在大多数方面仍然在发挥作用。

“我们在 2000 年进入云，当时它被称为托管，”他说，远在公共云的扩散和成功之前。“这是我们技术的摇篮。”

问题是旧的架构需要现代化和其他改进，因为该公司希望通过公共云提供其产品和服务。过去，Questback 仅通过私有云提供服务。

ml lerop 说，这些需求变得更加明显，因为公共云在过去六年中开始获得巨大的牵引力和速度，亚马逊网络服务、谷歌和微软 Azure 等公司允许企业轻松部署可供客户使用的应用程序。

在研究其选项后，Questback 的 it 和领导团队在 2016 年年中开始实施一项计划，通过添加容器和微服务来重振其 IT 架构，以便它可以更好地服务客户和扩展业务，同时坚持其久经考验的 IT 系统。该计划要求采用两个阶段的方法，首先是集装箱化，然后以微服务结束，微服务将与其现有的整体架构集成。

“这就是问题的关键，”莫勒普说。“我们不想取代它，因为我们的东西可以工作，而且可以永远运行。”

## 集装箱化完成，对微服务

到 2018 年 4 月，容器化部署已经完成，自 2017 年夏末以来，在详细的项目计划的帮助下，包括创建内部云支持团队、治理程序以及来自 IT 员工和第三方技术合作伙伴的帮助。集装箱化的测试正在继续。集装箱化阶段使用 Docker、Kubernetes 和 Kublr 管理组件，按时按预算完成。

muller op 表示，第二阶段，即引入微服务，将于 4 月开始，将包括决定使用哪些微服务技术，以及公司希望通过微服务向客户提供哪些单独的服务组件。

他说，微服务的吸引力在于，它们将有助于简化试图在庞大、笨拙的整体系统中做出改变的复杂问题。现有的 IT 架构中包含大约 200 种技术和标准，以及超过 100 万行代码，做出更改会产生许多技术问题，因为每个更改都会影响其他系统。

他说:“这会产生另一个问题，或者其他东西不起作用，然后你会有一个需要测试的项目的完整列表。”使用这样的程序,“你需要很长时间才能将新的创新引入市场”。“这是我们希望重新设计平台的原因之一。

他说，通过使用容器和微服务将单块系统内的服务和流程分割开来，选择的客户功能将独立运行，自给自足，允许客户在需要时通过公共云使用它们。通过使用微服务，Questback 将不必担心因其现有架构的变化而产生的问题，因为其现代化和效率计划将继续进行，因为变化只会发生在容器的子系统内部。

“有了集装箱化，我们可以移动东西，这更容易，你可以控制它，并有一个完整的概览，”他说。“它增强了你的机动性。”

客户将能够通过 Questback 的 API 访问这些服务，从而使公司获得收入，同时简化创新和服务交付，并为其提供新的上市模式。

“这将开辟一个新的商业模式，因此我们可以对使用我们的服务收取不同于我们在单一设置中所做的费用，例如，我们可以对每个 API 调用收取 0.01 美元的费用，”llerop 说。

同时，即使现有系统继续支持公司的日常业务工作，也可以进行技术添加。

## 绘制微服务路线图

为了准备微服务阶段，Questback 将依靠其 100 人的 IT 工程团队以及第三方 EastBanc Technologies，后者提供其 Kublr 容器管理系统。

他说，对于微服务战略，计划还处于非常早期的阶段。“我们需要首先决定我们将提供哪些单独的服务组件。如果我们不打算让这种服务元素可用，那么做一个巨大的微服务架构项目就没有任何意义。我们需要很好地记录 API，以便客户可以利用它们，并了解每个服务组件将如何单独工作。”

穆勒普说，到目前为止，这一过程面临着一些挑战，包括一些员工对变革的抵制，以及如何利用新技术推动公司未来目标的实现。此外，由于欧洲的一般数据保护条例隐私规则(GDPR)将于 5 月生效，Questback 必须确保这些变化符合那些更严格的规则，他说。

“这是一个非常周到和精心安排的过程，”穆勒普谈到迄今为止的集装箱化和微服务项目。“这不容易。在你前进的过程中，有很多艰苦的工作，很多加班，还有一些挫折。但我们现在正处于最后阶段，所以看起来非常好。”

他说，实现这一切的一个关键是让 Kublr 和 EastBanc 来协助这项工作，并“给我们一个新的视角，让我们知道我们应该如何从技术上解决这个问题”。“这就是我们所做的，也是我们能够在预算内按时完成的关键原因之一。”

## 分析师参与进来

Pund-IT 的首席 IT 分析师查尔斯·金告诉 New Stack，Questback 决定将容器和微服务引入其现有的整体架构，这也是他从其他公司听到的战略。

“迁移与从头开始的问题提供了一个比较微服务开发技术和程序与您已经拥有的技术和程序的好机会，”King 说。通过这样做，它还可以允许“对过程如何进行以及最终应用程序如何执行的尝试和真实的期望”。在已经走上应用程序现代化之路的组织中，从零开始似乎更常见。”

金说，Questback 承认员工在项目中抵制变革的举动是明智的，可以在保持员工工作满意度的同时保持努力的正轨。他说，该公司决定引入一家值得信赖的第三方供应商来帮助这项工作，这也是一个明智的举动，以及其调整现有 IT 基础设施以配合微服务工作和项目的新方法。

“你可以指出包括 Docker 在内的核心技术的流行和持续快速增长，作为它变得多么普遍的证据，”King 说。

另一位分析师，加布里埃尔咨询集团的丹·奥尔兹说，Questback 的方法是有道理的。最终，“实现微服务架构的最佳方式是首先将应用构建为一个整体，然后将其拆分为多个微服务，”他说。

与此同时，根据他在市场上的讨论，他说，其他已经在使用各种内部技术和架构的公司可能很难批量迁移到微服务。

“我所知道的许多公司都在新项目中启动他们的微服务架构，并在获得更多经验和更好的转换工具之前放弃旧的东西，”Olds 说。“这是一个进化过程，而不是大爆炸过程。”

阅读微服务系列下一篇:[分析这个:了解微服务监控](https://thenewstack.io/analyze-this-understand-microservices-monitoring/)

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>