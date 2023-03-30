# 您的平台工程门户需要哪些功能？

> 原文：<https://thenewstack.io/which-features-does-your-platform-engineering-portal-need/>

[平台工程](https://thenewstack.io/platform-engineering-the-ultimate-guide/)已经成为一种社会技术解决方案，填补了 [DevOps 中缺失的许多空白。](https://thenewstack.io/the-what-why-and-how-of-devops/)特别是，平台工程的主要优势在于它如何提高大规模灵活性和消除孤岛，尽管这是 DevOps 一直以来的目标。

改善开发人员的体验是关键，因为这是提高敏捷性的主要方法。实际上，这意味着开发人员——通过优化的平台工程，提供自动化基础架构运营的自助服务功能——可以开展工作，而不必承担与管理运营相关的更繁琐的任务。

这对于在云原生环境中工作特别有用，因此开发人员可以创建应用程序或完成 pull 请求，而无需参与管理 Kubernetes 的巨大复杂性和其他相关任务，例如安全性。

[Gartner 预计，到 2026 年，80%的软件工程组织将建立平台团队](https://www.gartner.com/en/articles/what-is-platform-engineering)，作为应用交付的可重用服务、组件和工具的内部提供商。分析师预测，平台工程最终将解决软件开发商和运营商之间合作的核心问题。

然而，经常被忽视的平台工程的一个关键元素仍然是实际的开发者体验。这就是所谓的[内部开发者门户](https://thenewstack.io/do-you-need-an-internal-developer-platform/)发挥作用的地方，作为工程平台之上的接口，它将确保开发者能够完成他们的工作，学习曲线类似于使用无代码替代方案。

有了合适的门户，开发人员必须先花一年多时间学习如何在 Kubernetes 上创建和部署应用程序的日子一去不复返了。相反，开发人员可以立即开始应用他们的才能来开发软件，以反映敏捷开发实践的节奏实现直接的业务目标。

事实上，在过去的几年中，许多组织在尝试采用平台工程时，都把重点放在了平台本身上。他们通常会设计 CI/CD 管道、云基础设施，实现 TerraForm 并设计 Kubernetes 基础设施。

然而，在许多情况下，试图让开发人员能够访问该平台的努力可能会被遗忘。

“开发人员需要能够以他们能够理解的方式消费不同的平台元素，提供类似产品的体验，因为他们不需要知道幕后的一切，”[港、](https://www.getport.io/?utm_content=inline-mention)的联合创始人兼首席执行官[佐哈尔·艾尼说，该公司提供内部开发人员门户，为开发人员提供自助服务体验。](https://il.linkedin.com/in/zohar-einy-b6219612a)

“但是通过实施适当的平台工程，你可以减少开发者的认知负荷，帮助他们获得他们需要的一切，”Einy 说。“这可以通过现成的内部开发人员门户产品来实现。”

## 为什么开源可能不是解决方案

成功设计一个能够提供开发人员真正需要的门户平台是一项重大的工程壮举。虽然存在开源产品，但它们需要大量的内部资源来设置和管理。

领先的开源开发者门户是[后台，](https://github.com/backstage/backstage)根据 [Eran Stiller 的说法，](https://stiller.blog/)他是旅游服务提供商 Luxury Escapes 的首席软件架构师。Stiller 说, [Spotify 的工程师开发的 back stage,](https://thenewstack.io/how-spotlify-adopted-platform-engineering-culture/)具有高度的可定制性和可伸缩性，但它需要开发者花费大量的时间来适应，而且“你还必须自己托管它，这[需要额外的时间和精力。](https://thenewstack.io/the-hidden-costs-of-free-internal-developer-portals/)

最近几个月，后台也暴露了一些[重大漏洞，](https://thenewstack.io/oxeye-finds-bad-spotify-backstage-javascript-vulnerability/)可[引入安全风险。](https://thenewstack.io/xss-vulnerability-discovered-in-backstage-software-catalog/)

Stiller 说，另一方面，商业产品通常在功能和可扩展性方面受到限制。

“如果产品能满足您的需求，并能与您当前的技术体系和平台兼容，那就太好了。但如果没有，它给你带来的好处可能是有限的，”他说。“一个提供高度定制和可扩展性的现成商业平台有着巨大的潜力，可以帮助那些不想或不能花时间调整和托管自己的后台实现的开发团队。”

## 开发人员门户清单

根据 Einy 的说法，开发者门户应该提供的特性:

**自助服务为开发人员提供了灵活性，同时保持了政策合规性。**门户的自助服务功能应超越微服务搭建，允许开发人员对软件目录中公开的任何资产进行供应和执行第 2 天操作。同时，门户应该确保任何操作都符合策略，并允许对某些操作进行手动审批。

“Port 是第一个在开发人员自助服务行动方面采取这种雄心勃勃的方法的公司，超越了脚手架，脚手架也是后台方法，”Einy 说。“作为对我们愿景的验证，我们看到市场上的其他参与者也开始采用这种方法。”

**门户和平台的松散耦合。**通过这种方式，平台工程团队可以自由构建符合其规范的底层平台，并让开发人员通过开发人员门户以他们理解的方式使用平台数据。

平台工程团队可以选择他们想要的 CI/CD、IaC、软件架构和所有 DevOps 流程。

这种分离允许对底层平台进行更改，同时保持开发人员体验的一致性。

“我们不会给你一个什么都有的预制房子，并告诉你如何进行开发或平台工程，”Einy 说。“但是我们给你无代码元素来创造你梦想中的房子。这是我们与其他解决方案的主要区别。”

**整合组织自身数据模型的能力。**数据模型被引入到软件目录中，软件目录是组织内开发和管理的基础设施和软件的可见性层。

一个理想的软件目录应该展示围绕软件开发生命周期的整个生态系统。这些包括 CI/CD 流、开发者环境、管道、部署和任何云，“跨所有[研发]部署，”Einy 说，“从应用程序开发甚至数据、安全、产品和研究——基本上每个团队都与软件有关。”

**开发者门户中的工作流自动化支柱，允许机器与之交互。**在开发者门户中，机器可以通过 Port 的实时软件目录访问单个 API。这为机器提供了它们在上下文中所需的信息，以作为其工作流的一部分:使 CI 作业失败、自动终止资源或基于软件目录数据运行 CD 流。

此外，机器可以订阅触发器，例如:资源生存时间达到零，Cron 作业计时器超时，或者实体的创建、修改或删除。您可以使用订阅来触发自动化工作流或任务。

“这也是因为软件目录作为一个通用的软件目录，而不仅仅是为开发者提供抽象的信息，”Einy 说。

Stiller 说，这样的门户特性“对于现代软件开发团队来说是必不可少的”，并补充道，“对于那些大型团队或为多个部署单元(如微服务)构建软件的团队来说尤其如此。”

## 建筑师的经历

Stiller 说，在后 monolith 时代，软件设计需求变得更加复杂，“开发团队也随之成长”。“我们开始分发自己编写的软件。”

“这种分布导致了一个问题，即多个团队不断地互相踩着对方的脚趾，所以我们转向了[面向服务的架构](https://thenewstack.io/primer-understanding-software-and-system-architecture/)，后来又转向了[微服务。](https://thenewstack.io/microservices-101/)问题是分布式架构比单体架构更难掌握和维护，这带来了新的挑战。”

Stiller 说，在基于微服务的应用程序开发中，监督开发过程的架构师通常需要理解系统如何工作，并提出以下问题:

*   应用程序部署在哪里？
*   当前运行的是哪个版本？
*   哪个服务依赖于哪个服务？
*   哪种服务对大多数客户错误负责？

斯蒂勒说:“他们需要工具来帮助理解分布式复杂性，并引导他们专注于何处。”“一个好的内部开发人员门户让我能够做到这一点，它允许我建立一个包含我的应用程序的所有软件的目录，无论是服务、部署管道、基础架构组件、云环境等。”

他说，一个好的门户网站允许架构师在他们的目录上叠加额外的信息，这些信息通常可以在其他系统中获得，但需要在一个位置进行连贯的组织。

“例如，我可以添加一个信息层，根据我的可观察性平台中可用的数据，说明每个服务的错误率，”Stiller 说。“或者我可以添加一个信息层，根据我的源代码控制系统或 CI/CD 管道中的信息显示特定横切依赖项的版本。”

一旦添加了信息，架构师就可以添加规则并创建仪表板。

“例如，我可以根据错误率对服务进行排名，并对不符合[服务级别协议]的服务发出警报，我还可以对没有将依赖关系更新到最低要求版本的服务发出警报，”Stiller 说。“能够做到这一点并以一种易于理解的方式向团队中的所有开发人员展示所有这些信息是无价的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>