# MuleSoft 特许权？RAML 创建者加入 OpenAPI 计划以统一 API 描述

> 原文：<https://thenewstack.io/mulesoft-concession-openapi-adopts-raml-different-approach-api-documentation-descriptions/>

4 月 20 日， [Open API Initiative](https://www.openapis.org/) (OAI)增加了一名新成员。MuleSoft 是 T2 RESTful API 建模语言 T3(RAML)背后的主要关注点，现在是 OAI 的一部分，并将为 T4 open API 规范 T5(OAS)做出贡献。在过去的四年里， [MuleSoft](https://www.mulesoft.com/) ，一家 API 管理和应用程序网络公司，开发并支持一种不同的 API 文档和描述方法。加入 OAI 是将 MuleSoft 的方式和方法引入 OAI 发展委员会的一条途径。

RAML 规范的共同创建者和 MuleSoft 的 CTO Uri Sarid 说，他已经与 OAS 委员会讨论了技术细节，他希望这次合作富有成效。他说，到目前为止，他们的讨论能够集中在 RAML 支持的事情上，但 OAS 3.0 没有，因此，Sarid 说 RAML 做出的一些决定可能会影响 OAI 的未来。

“对我们所有人来说，更大的任务是让人们在一个互联的 API 驱动的环境中将 API 规范作为契约，我们都在一起打这场仗。OpenAPI 规范是一种被广泛采用的描述 API 的机制。我们自己支持这个规范，我们也鼓励其他人支持它。这是通用语。我们使用这些词汇和语法来描述适用于所有人的 API 规范。它可能不能做所有的事情，但至少你能理解这一点，”萨里德说。

他说，加入 OAI“以一种公开的方式表明，它不是关于在作为 API 建模语言的 RAML 和作为 API 描述语言的 OAS 之间站队。我们应该着眼于双方的利益。“RAML 旨在帮助您对 API 进行建模、设计，并允许您拥有显式可重用的组件。它促进了一致性，所以这些 API 的行为是相似的。”

https://www.youtube.com/watch?v=5o_nExedezw

从外部来看，MuleSoft 加入 OAI 可以被视为 RAML 输掉了一场想象中的 API 规范战争的让步。然而，Sarid 认为任何这样的描述都不利于每个项目背后的技术目标。

RAML 被设计用来对 API 建模，并通过类型和注释提供 Sarid 所说的元-元数据层。这些更高层次的构造允许企业用户更可持续地对待大量 API，更好地描述每个 API 到底做什么。

然而，OpenAPI 规范描述了 API，并围绕它们自动生成文档。这使得开发人员能够更快地行动，而不是每次 API 改变时都必须不断地返回并更新他们的规范和文档。

OpenAPI 规范起源于 Swagger 3.0 规范，但在 2015 年，OAI 在 Linux 基金会下形成。Swagger 规范的实际技术管理被接管，并被重命名为 OpenAPI 规范。Swagger 的名字现在由 Swagger 的创建者 Tony Tam 监管的一套工具所拥有。

Sarid 说，最重要的是，RAML 仍然可以共存。RAML 社区甚至开发了一套在 OAS 和 RAML 之间来回移动的工具。Sarid 说:“通过我们成为双方的一部分，并创建开源工具来连接这两个世界，确实为每个人带来了两个世界的最佳效果。

他补充说，RAML 世界的精华植根于企业用例。RAML 的建立是为了给企业 API 实现带来可重用性和一致性。与 Swagger 类似，RAML 出现在一个 API 激增的时代。2013 年，企业刚刚开始理解托管大量[微服务](https://thenewstack.io/reality-microservices-enterprise/)意味着什么，因此，RAML 规范诞生了，以帮助他们理解他们正在构建什么。

[https://www.youtube.com/embed/_RI5iZgOtis?feature=oembed](https://www.youtube.com/embed/_RI5iZgOtis?feature=oembed)

视频

2016 年 9 月，RAML 规范迎来了 1.0 版本。更新增加了注释、数据类型和改进的示例。Sarid 说，RAML 实现多个示例的方法引起了 OAI 团队的兴趣，当时他们正在集体讨论如何在 OAS 中实现这种行为。Sarid 说，希望这是 OAI 团队如何与 RAML 团队合作的一个例子。

RAML 1.0 的实际好处肯定是集中在企业的需求上。数据类型的增加允许围绕 API 数据源积累元数据，确保它可以正确地插入到接收应用程序中而不会混淆。

另一个强大的附加功能是注释。Sarid 说，用户开始看到，“在规范之上输入注释的力量:覆盖规范。覆盖允许您注释规范，而不改变规范。我们现在有注解库，”Sarid 说。

他谈到了一位开发人员，他创建了由注释驱动的用户界面控件库。“他采用了热传感器的标准 API 规范。[开放连接基金会](https://openconnectivity.org/)已经[发布了物联网设备的标准 RAML 规范](https://github.com/OpenInterConnect/IoTDataModels)。其中一个是温度传感器，可以读取和设置，”Sarid 说。

Sarid 说，使用这个通用的 RAML 规范，开发人员能够创建一个 UI 组件库，直接绑定到传感器上。“有了这个库，您就可以利用热传感器创建一个用户界面，它会自动与该规范同步。然后，用户可以与用户界面进行交互，测量或改变温度，”Sarid 说。

这就是 Sarid 说 RAML 能够以标准 OAS 无法做到的方式帮助企业的原因。Sarid 说，在一个微服务激增、注册中心成为应用网络中心的世界里，RAML 可以帮助开发人员更轻松地使用所有这些不同的服务。

“我认为这是解决方案的一部分，而且是重要的一部分。它不能完全解决这个问题，最终你需要重要的智能软件来处理整个服务生态系统。这个难题的一部分是获取 API 规范。到目前为止，我们都将该规范捕获为文档。很自然地，我们会把契约看作是应该放在源代码控制中的东西。面向文档是非常自然的，”Sarid 说。

然而，API 规范实际上编码了一个对象树，以及它所公开的业务对象图。它说这是发票，这是使用它的业务组，等等。这个对象树，这些树之间的关系，以及你可以对它进行的操作，形成了一个内存结构。行业的发展方向，也是我们的发展方向，是围绕这些 API 的结构来真正捕获、构建和保持业务逻辑。它在 API 里面，”Sarid 说。

“API 建模捕获了 API 规范中的所有对象。这是拼图的一部分。它没有给你注册表和软件来存储所有这些模型和图表，而是在这些之上建立价值，”Sarid 说。

Sarid 说，这也允许在规范范围内正确处理测试和故障排除之类的事情。“API 规范为您提供了大量关于 API 功能方面的信息。调用这个方法，得到这个响应。但是有更多层次的元数据是相关的。我如何实际测试这个 API？如果我做一个例子，我能得到一个例子吗？必须有额外的语义信息覆盖在上面来帮助你测试它。您可能还想在其他地方放置额外的信息。RAML 有可重用的组件和它们之间的双向跳闸。你的对象表示应该记得。如果你能记住指向更高级代码的指针，堆栈跟踪就能再次变得有意义，”Sarid 说。

现在，拉姆哪儿也不会去。虽然 MuleSoft 将积极参与 OAI，但 Sarid 表示，支持特定的计划或框架不如传播正确、标准化的 API 描述重要。当所有 API 的行为都相似时，所有开发人员都会节省时间。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>