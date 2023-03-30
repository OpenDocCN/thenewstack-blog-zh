# AsyncAPI 希望在 Linux 基础下统一 API 工作流

> 原文：<https://thenewstack.io/asyncapi-looks-to-unify-api-workflow-under-linux-foundation/>

AsyncAPI 倡议最近加入了 [Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)，带来了其围绕异步应用编程接口(API)的规范，以及其帮助异步 API 开发者创建文档、编码等的开源工具集。随着这一举措，AsyncAPI 计划与 Linux 基金会的 OpenAPI 计划一起加入，将一枚硬币的两面带入了基金会，Linux 基金会的首席技术官兼开发者关系副总裁[克里斯·阿尼斯奇克](https://www.linkedin.com/in/caniszczyk)表示，他预计合作将会增加。

“我们已经是 GraphQL、OpenAPI 和 gRPC 等产品的主要宿主。AsyncAPI 有一些雄心勃勃的目标，为许多不同的系统提供抽象，所以对我们来说，我们很高兴为这个社区服务，并把 API 社区集中在一个中立的地方，他们将在那里合作和学习，”Aniszczyk 说。"一旦你让一群聪明的人在一个房间里，合作往往会发生."

说到 API，有很多种可供选择，比如 Aniszczyk 提到的那些。但是有一个关键特征将所有 API 分成两个阵营:应用程序是否在继续之前等待 API 响应。对于同步 API，有一个请求/响应模式，其中发出一个请求，应用程序在继续之前等待响应。相比之下，异步 API 通常使用发布/订阅(通常称为发布/订阅)模型，其中应用程序订阅一个主题，然后每当有任何消息发布到该主题时，API 就向所有订阅者提供更新。对于异步 API，关键因素是应用程序继续向前移动，而不是等待响应，这些类型的 API 已经成为无服务器和微服务架构的主干。

AsyncAPI 创建者 Fran Méndez 将 AsyncAPI 倡议描述为可与 OpenAPI 相媲美，但是是针对 API 的另一个领域。

该规范为定义这些类型的接口提供了一种通用语言。异步 API 中协议和消息传递的前景非常广阔。有很多协议，不像 HTTP APIs 那样只有 HTTP，”Méndez 说。“AsyncAPI 提供了这种每个人都可以同意的语言，如果你想的话，这种契约，然后工具可以有利于生成文档，生成代码，做几乎任何你现在可以用 OpenAPI 做的事情，但对于异步 API 来说。”

在一份新闻稿中，AsyncAPI 被描述为 OpenAPI 计划的“姐妹项目”, async API 计划具有许多与 OpenAPI 相同的功能，但 Méndez 表示，该项目的最终目标是更进一步。

“从用户的角度来看，我们在过去几年中看到的问题是，每当你想使用 API 时，这是一个非常分散的世界。假设您必须为用户定义数据模型。Méndez 说:“这种数据模型很可能会在许多系统中使用，而不仅仅是在 REST APIs、GraphQL API 或 Kafka API 上。“这就像是，我一遍又一遍地做着同样的事情。作为用户，我必须适应工具，而不是工具适应我的工作流程。基本上，我们想要完成的是统一工作流程。”

为此，Méndez 和 Aniszczyk 都提到了一些未来的计划，他们希望这些计划能够在 Linux 基金会的指导下统一那些从事 API 工具和规范工作的人。首先，Aniszczyk 提到了“今年晚些时候的 API 相关会议”,该会议可能会跟踪不同的 API 协议和规范。Aniszczyk 指出，AsyncAPI 有更大的野心，要包括一些其他 API 系统，以便最终提供一个公共层，像这样的事件，以及 Linux 基金会本身的合作，将提供一种推进这一努力的方式。

与此同时，Mendez 解释说，AsyncAPI 加入 Linux 基金会不仅是为了让可能犹豫不决的企业相信 AsyncAPI 计划不仅仅是一个个人指导下的项目，也是为了再次与 API 社区的其他成员合作。

Mendez 说:“我们还希望让人们更容易合作，并在 AsyncAPI 中获得某些计划的所有权。“这是关于提供信任。”

除了加入该基金会，Méndez 还表示，他们还希望创建一个 API 工作组，不仅为 API 规范作者，也为开发人员和工具创作者提供一个场所，每月会面并讨论他们自己和用户面临的问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>