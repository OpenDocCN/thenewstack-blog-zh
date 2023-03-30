# API 在容器时代的重要性

> 原文：<https://thenewstack.io/importance-apis-container-age/>

编者按:这篇文章是由 TNS 撰稿人马克·博伊德撰写的，他是本月晚些时候在奥斯汀举行的今年 API 战略和实践会议项目的项目主席。我们请 Boyd 解释 API 的价值，以及为什么它们构成了新一代互联 IT 系统的基础。

即将于 11 月 18 日至 20 日在奥斯汀举行的 API 战略与实践(通常称为 API Strat)会议将分享故事，并推动日益成熟的 API 经济面临的挑战。

今年，企业和初创公司部署 API 的方式发生了几个重大转变。就在几年前，大部分 API 讨论发生在初创公司和渴望将竞争引入传统市场的自愿颠覆者之间，而 2015 年已经出现了更多企业采用的趋势，即使是像银行业这样发展最慢的行业也开始参与进来。

应用程序编程接口(API)是一种代码格式，使企业能够以一种可以集成到其他内部或外部 IT 系统架构中的方式，提供其 IT 基础架构组件(如数据集或服务功能)的简单表示。

对于颠覆性的初创公司，这意味着他们可以通过 API 公开数据和功能，快速构建新的用户友好界面和移动应用。对于速度较慢、规模较大的企业来说，API 使不同的 IT 基础设施能够共享数据、创建新的概念验证产品模型或连接到外部服务，而不必共享他们自己的遗留代码库的复杂性。

因此，企业对 API 的接受是今年一个关键的成熟信号。但是它是在需要一个新的隐喻来描述 API 的好处(一个还没有完全确定的任务)，后“可组合企业”框架的时候出现的。

## API 是/不是微服务

在某种程度上，今年已经看到一些评论家将 API 描述为微服务架构的一部分。更新“可组合企业”行话，API 被描述为微服务，就像它们曾经被描述为“可组合单元”——甚至是乐高积木——一样，它们可以被重构为新的价值链，以产生工作流效率，加快产品开发，或创建与目标市场连接的新渠道。

但是微服务潮流并不完全合适。

就在几年前，希望快速进入市场并颠覆现状的初创公司还在开发 API。现在，这些初创公司已经处于增长阶段，在他们的创造速度中，他们最终复制了具有复杂代码库的遗留系统，其中源代码将功能与底层通常构建较差的数据模型相结合。这些初创公司快速迭代，并构建新功能来响应付费客户的需求，但现在他们已经是成熟的企业，并意识到他们需要退一步，对他们的 API 有一个长期的看法，这通常意味着他们自己采用更多的微服务方法。

到去年为止，初创公司和企业内部的 API 设计讨论通常从单个用例以及端点契约的创建开始。随着 API 的优势被越来越多的全球企业所认可和采用，当多个 API 引用相同的数据集或功能时，复杂性被重新引入。

这使得埃森哲技术实验室的高级经理 Teresa Tung 致力于[工业 API 成熟度模型](https://www.accenture.com/us-en/blogs/blogs-getting-to-industrialization-introducing-an-api-maturity-model)，该模型展示了一种更加面向生命周期的 API 开发方法，其中单个用例被一种更加基于系统的思想所跨越，这种思想认为 API 应该是一个相关功能的捆绑包。

虽然埃森哲的模型于 2014 年发布，但来自总部位于奥斯汀的 API 设计公司 [LaunchAny](http://www.launchany.com) (下周将在奥斯汀举办 API 战略和实践)的詹姆斯·希金波坦(James Higginbotham)表示，超越端点的思维才刚刚开始出现在商业对话中:

> 对于 API 来说，这是激动人心的一年。无论 API 是私有的、合作伙伴的还是面向公众的，企业都开始从考虑端点转移到 API 产品和解决方案。随着企业转向基于产品的思维，他们寻找设计可重用 API 的技术，这些 API 可以处理各种用例，其中许多在设计时是未知的。

“因此，”Higginbotham 继续说道，“我一直在与团队合作，在基于 HTTP 的端点集合之外查看他们的 API。团队需要理解 API 是一种架构关注点，它向底层系统公开了一个接口。应用系统设计和领域驱动的设计有助于创建清晰的界面边界，可以结合起来解决无数的用例。”

希金波坦所指的是 API 的微服务隐喻的缺点。事实上，API 更像是捆绑在一起的微服务的集合。以此类推，单个端点可能是微服务更好的比较点。

和 Teresa Tung 一样，Higginbotham 也将在 API Strategy and Practice 上发表演讲，他说，今年，他看到了对领域驱动设计(DDD)的回归的更大兴趣，就像基于容器的分布式架构系统一样。

“对于产品经理来说，灯泡时刻是他们开始看到产品边界的时候，”希金波坦说。“随着产品架构的出现和 DDD 的应用，可以发现以前没有发现的新产品和产品机会。它还防止不完整的产品被发布，这些产品需要被充实以确保它们为目标市场提供价值。

团队面临的最大困难是识别和设计 API 资源。DDD 通过帮助团队找到 API 资源和这些资源的协作来实现目标用例，从而解决了这个问题。它还使用 webhooks 识别出站事件的机会，这可以为一个全新的可能性领域打开一个 API，如果没有类似的设计方法，这些可能性可能会被错过。"

## 作为企业效率引擎的 API

大约两年前，当“可组合企业”一词流行起来时，来自美国电话电报公司的 Laura Merling 在旧金山的 API Strategy and Practice 上分享了她的团队在将单一电信公司重新定位为支持 API 的公司方面取得的成功。当时，她的团队的策略之一是会见每个业务部门，确定主题专家，并帮助他们定义可以打包成独立 API 的数据集和功能。

今年，API Strat 将听取来自 Maps Credit Union 的 Loren Paulsen 的发言，他在[采取了类似的方法来建立内部支持](https://medium.com/p/6-sure-fire-signs-that-2015-is-the-year-to-talk-about-banking-apis-f816c7f8e0c6)，与各个部门会面并讨论 API 的力量。为了展示 API 的价值，他的团队绘制了业务工作流程图，例如通知客户何时可以领取借记卡的工作流程，并确定了使用 API 来自动化流程中各个阶段的机会。Paulsen 已经能够向组织介绍使用第三方 API，如 SendGrid 的电子邮件 API，以加快生产并降低当前流程的成本。(现在，Maps CU 使用 SendGrid API 首先尝试提醒客户借记卡的可用性，从而降低每月的邮政成本)。

虽然这可以通过简单的电子表格或白板来完成，但一套新的流程自动化工具——如[build . io Flow](https://thenewstack.io/built-io-and-its-automated-pipeline-for-connecting-apps-with-custom-logic/)——正在发布，以使企业能够将 API 菊花链在一起，并通过消除剪切、粘贴和重新输入数据等数据处理中的人为错误来提高效率。(Built.io 的 CEO Neha Sampat 也是 API Strat keynote。)

## 作为平台价值单位的 API

Paulsen 在构建对内部 API 的支持时使用的另一个策略是使用 API 描述格式来鼓励业务产品负责人和技术负责人在设计 API 时保持一致，并取得了一些成功。

API 定义格式可能是今年 API 成熟的最大证明，并且允许 API 部门复制类似于容器技术的讲述能力。

Codenvy 的容器技术信息图[发表在新的 Stack](https://thenewstack.io/containers-disrupting-devops-infographic/) 上，描述了容器如何成为平台生态系统的核心价值单元。像 [Sangeet Choudary](http://platformthinkinglabs.com/about/sangeet-choudary/) 这样的平台商业模式思想家长期以来一直在鼓吹，科技企业要想转型为一个平台游戏，他们必须首先确定将生产者和消费者带到平台上的单一价值单位。例如，对于 Docker 和 Kubernetes 生态系统，容器是价值的单位，它允许整个生态系统为工具组件开花结果，从编排、日志和可发现性，到监控、测试等等。

在 API 圈子里，今年我们已经看到 API 定义格式成为 API 平台的单一价值单位。API Strat 联合组织者(以及 [3scale](http://www.3scale.net/) )和 API 布道者 Kin Lane[描述了一个包含大约 17 个阶段的生命周期](http://apievangelist.com/2015/02/23/my-brain-dump-on-an-api-definition-fueled-life-cycle/)。今年，API 工具——主要在测试领域，但也在其他生命周期阶段——已经成熟，并越来越多地利用 API 定义格式来自动化工具的投入使用，就像持续集成帮助容器技术沿着开发到生产的管道推动应用程序一样。

API 工具初创公司 API Changelog 的创始人布鲁诺·佩德罗(Bruno Pedro)表示，作为核心价值单位的 API 描述格式是一种“有趣的类比”。API 工具初创公司 API Changelog 通过自动通知和量化 API 文档和使用条款政策的变化规模，帮助 API 提供商与最活跃的用户建立联系。

“这非常符合 API 游戏目前所处的环境，”Pedro 说。“回到几年前，我们经历了与 SOAP 类似的事情，我们有遵循正确标准的机器可读系统和自动化系统。但它没有起飞，因为它太企业化，没有得到全球观众的接受。尤其是在最近几天，随着 Swagger 发展成为开放 API 计划，IBM 和其他大公司也加入进来。”

他补充道:“随着 API 工具生态系统的成熟，以及 API 描述格式使用的增加，人们将会更好、更容易地构建更多的自动化解决方案。”

随着我们进入 2015 年的最后一个季度，这种生命周期工具已经发展成为一系列新的 API 生态系统工具，试图模仿 Docker 平台。它始于今年早些时候 apary 为企业开发的[蜂房，基于 API 蓝图描述格式。现在 SwaggerHub 已经由 SmartBear 发布，MuleSoft 发布 API Workbench，Postman 发布 Postman 客户端，跃跃欲试的新人 API Garage，RepreZen 和 RESTLET Studio 都在提供替代方案。](https://thenewstack.io/apiary-releases-world-first-automated-api-ci-testing-service/)

每一个都使用 API 定义格式来推动 API，类似于 Lane 的 17 阶段 API 生命周期模型或 Tung 的工业 API 成熟度模型。

## 作为看不见的手的 API

因此，虽然 API 正在成熟，企业也在继续采用，但似乎没有一个常见的隐喻或讲故事的设备来描述 API，就像 Docker 和其他人能够如此成功地使用容器以及最近的“微服务架构”术语一样。

也许这根本不是问题。当然，保尔森已经能够通过正面展示效率收益来培养企业吸引力，而不是用微服务、可组合企业或其他类型的解释来构建 API。

佩德罗认为其中一个原因可能是 API 注定会变得几乎不可见:“我的观点是，这可能需要几个月，甚至一两年的时间，但最终我们会看到各种 API 之间的所有集成都将完全自动完成。您将不必编写一行代码。您只需将您的应用程序需要的东西与其他系统集成，它就会为您集成。”

已经有迹象表明，佩德罗可能是对的。迪翁·欣奇克利夫(另一位 API Strat 主题演讲人)所描述的“公民开发者”的崛起预示着最终用户可能甚至不需要知道 API 是推动他们工作的动力。像 [Blockspring](http://www.blockspring.com) 这样的服务——使任何人都可以通过谷歌电子表格使用 API——以及 Slackbot 集成的兴起都表明 API 变得更容易访问，同时也更不可见。

今年，API 领域发生了一些重大变化。如何描述这些将影响 2016 年企业、政府和社会的接受程度。像 API 战略和实践这样的会议使领导者能够分享故事，并测试有效描述 API 给企业和社会带来的好处和挑战的隐喻。

包括 Teresa Tung(埃森哲)、Neha Sampat(build . io)、Rion Dooley(德克萨斯高级计算中心)、Lori MacVittie (F5 Networks)和 Dion 欣奇克利夫(企业思想领袖)在内的 API 领导者将在一个多元化的计划中分享主题演讲，该计划包括研讨会、关于关键 API 主题的会议跟踪、炉边聊天和 mainstage 面板，所有这些都旨在进一步推动 API 议程。

新书库的读者被邀请以 20%的折扣率参加，通过[使用代码 APISTRATTHENEWSTACK 在线注册](https://www.eventbrite.com/e/api-strategy-and-practice-conference-austin-tickets-18084100030?discount=APISTRATTHENEWSTACK)。

Docker 和 IBM 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>