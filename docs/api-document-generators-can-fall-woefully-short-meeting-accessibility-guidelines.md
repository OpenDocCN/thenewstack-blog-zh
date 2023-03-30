# API 文档生成器在满足可访问性准则方面可能会严重不足

> 原文：<https://thenewstack.io/api-document-generators-can-fall-woefully-short-meeting-accessibility-guidelines/>

由于标准化，API 规范文件越来越多地用于自动化构建系统，甚至可以用于自动生成文档。然而，这种自动化是有成本的，因为这些系统的产品往往不符合无障碍指南，可能会妨碍残疾人获得这些信息和服务。

SwaggerUI 可能是最受欢迎的选择之一，并且是 API 提供者快速创建交互式 API 文档的一种简单方法，但是社区成员要求 SwaggerUI 符合可访问性标准已经有一年多了，到目前为止，SwaggerUI 团队几乎没有什么回应。根据联邦法律，许多组织希望甚至可能被要求满足[Section 508 Accessibility standards](https://www.section508.gov/)，该标准是仿照 W3C 的[Web Accessibility Guidelines 2.0](https://www.w3.org/TR/WCAG20/)制定的。

自 2016 年 1 月以来，Swagger 在 [SmartBear](https://smartbear.com/) 的管理层已经意识到合规性的缺失。“我们知道 508，但没有做任何特殊的工作来符合它，”Swagger 开发者福音传道者 [Ron Ratovsky 写道](http://grokbase.com/t/gg/swagger-swaggersocket/1615q1dj0f/508-compliance-in-swagger-ui) 。相反，Ratovsky 建议个人用户可以自己定制 SwaggerUI。根据 2016 年 6 月 14 日公开的一期 [、仍未公开、仍未分配的期刊](https://github.com/swagger-api/swagger-ui/issues/2216) ，一些人已经继续这样做了。

这是一个恶性循环:SwaggerUI 的项目团队可能不会特别在意让残疾人也能使用他们的文档工具，因为他们可能没有把这看作是他们用户社区的一大部分。

今年的 [Stack Overflow 开发者调查](https://insights.stackoverflow.com/survey/2017) 发现，3.4%的受访者乐于承认自己有残疾。如果在 SwaggerUI 社区中有相同的比例，基于他们在 GitHub 上的 8，076 个明星粉丝，那将代表 275 个用户。项目团队可能不认为 275 个用户是一个足够大的群体来优先考虑他们的文档需求。

SwaggerUI 是 API 行业中自动生成文档的主要方法之一。这通常是新的 API 提供者为他们的社区快速创建文档的第一种方式。SwaggerUI 获取一个 API 规范文件，如开放 API 倡议格式(OAS ),并自动生成文档，然后作为交互式沙箱嵌入到 API 提供商的开发人员门户中。因此，无法访问可读的 API 文档可能会将残疾开发人员挡在潜在的就业和参与机会之外。

“在试图将 Swagger UI 整合到政府 API 项目中时，我发现 Swagger UI 需要做大量的工作才能达到 508 合规性，”创意制作集团 The Misery Brothers 的创始人、工程师 Joe Adkins 说，他之前在 SwaggerUI GitHub repo 中发现了这一问题。

Adkins 说，SwaggerUI 不符合残疾人无障碍标准“有些令人惊讶，因为它被用于许多政府项目。在这方面，人们可以做一些装饰性和表面性的事情(如对比、标记等)来帮助解决问题，一些其他社区成员也在这方面做出了改进。但这仍然需要相当多的前端开发，以使 Swagger UI 成为一个符合 T2/508 的应用程序。据我回忆，所需的工作并非微不足道，但却是可行的。令人惊讶的是，几乎没有政府开发承包商关注可访问性和可用性，只是使用这样的工具，而没有定制的计划。”

## API 规范在未来自动化中的重要性

API 规范文件越来越多地被用于实现自动化持续集成/持续交付(CI/CD)管道，这使得产品构建更快、更稳定。但是 API 规范文件也被用来自动生成文档和参考指南。

像 [开放 API 倡议](https://www.openapis.org/) 这样的 API 规范格式对于希望管理其 CI/CD 工作流的企业来说变得越来越重要。集成构建、自动生成文档和资源(如 SDK)已经成为 API 规范的主要优势。

Open API 版本目前还没有全面发布，GitHub 上发布了一个 RC 2 供评论。然而，工具制造商已经开始采用这一标准。最近， [RepreZen](https://www.reprezen.com/) 更新了其 API 设计工具 API Studio，以及其针对 Eclipse IDE 的开源 [KaiZen](https://github.com/RepreZen/KaiZen-OpenAPI-Editor) 编辑器，这两个工具现在都支持开放 API 3.0 版本。

RepreZen 首席执行官 Ted Epstein 表示，他希望在未来 18 个月内，随着越来越多的 API 生命周期工具将新的 OAS 版本整合到他们的产品中，在不可避免的混乱到来之前，在公司的产品中提供新的规范。

最初，在规范中记录 API 元数据的想法可能是为了使它在搜索中更容易被发现，或者为开发人员提供一种简单的方法，以便在使用前快速了解 API 的功能，但是自动化用例引领了人们对实际使用规范文件的兴趣。但是就像黑盒算法从开发者创造者的实现决策中重建系统障碍一样，自动化过程的 API 规范也可能有类似的潜在不良影响。

“这是 API 设计的一个总主题:确保像 OAS 这样的机器可读 API 描述被认为是一流的源代码。您从 API 描述中创建的代码生成成为您的自动化构建过程的一部分，并且您希望能够将其作为源代码的一部分来管理。它在某种程度上就像一个编译器，”爱泼斯坦说。

RepreZen 的 API Studio 被一系列非营利教育初创公司和越来越多的中型公司和企业使用，如瑞士金融科技公司 Finnova，而 PayPal 和房利美等企业也在使用该工具。Epstein 说，特别是在这些用户中，API 规范文件被用于 CI/CD 支持。

“他们正在 API Studio 中编写 API 描述，或者当他们开始使用 API Studio 时，他们可能会一次性导入他们的工作，”Epstein 说。“那么我们的工具就是编写和编辑描述以及进行特别沙盒测试的主要环境。

当 API 处于组织的稳定点时，API Studio 会生成 API 支架或支架代码，这是基于 API 描述自动生成的代码块。这些存储在生成的代码文件夹中。用户还将创建手工制作的实现代码，这些代码将记录所需的业务逻辑、数据访问和任何数据操作。

通过将 API 描述与 API Studio 等工具结合使用，用户可以混合和匹配自动化工具。Epstein 说，对于新的 API 提供者来说，一个相当典型的进展是将 OAS 文件输入到 [SwaggerUI](https://swagger.io/swagger-ui/) 中，以自动创建 API 参考文档。然后，随着时间的推移，API 提供者可能会添加自己编写的 API 文档。

其他文档生成器工具如 [ReDoc](https://github.com/Rebilly/ReDoc) 和 [Slate](https://github.com/lord/slate) 也使用 API 规范文件 a 来自动生成它们的文档。

专题图片:由[马修·汉密尔顿](https://unsplash.com/search/industrial?photo=KtI5aQU9Pzo)对[Unsplash.com](http://Unsplash.com)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>