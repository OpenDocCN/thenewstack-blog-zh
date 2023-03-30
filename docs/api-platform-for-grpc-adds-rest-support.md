# API 平台 Kreya 为以 gRPC 为中心的解决方案增加了 REST 支持

> 原文：<https://thenewstack.io/api-platform-for-grpc-adds-rest-support/>

API 平台 [Kreya](https://kreya.app/) 现在支持 REST，并在 7 月 11 日发布的 1.8 版本中推出了新的 pro 和 enterprise 产品。该工具最初是为了支持 [gRPC](https://grpc.io/) 而开发的。

“我们出于需要开发了 Kreya。两年多前，我们一直在寻找一种类似于 Postman 但支持 gRPC 的工具，”住在瑞士的 Kreya 开发者 [Manual Allenspach](https://www.linkedin.com/in/manuel-allenspach/) 通过电子邮件告诉新堆栈。“随着时间的推移，我们不得不切换到其他工具来与[REST API](https://thenewstack.io/how-to-automate-and-scale-your-rest-api-tests/)交互，这让我们很不高兴。”

Kreya 团队模块化地构建了它的架构，这使得添加对 REST 的支持变得容易，“即使这意味着大量的工作，”Allenspach 补充道。与此同时，竞争对手 Postman 和失眠症增加了对 gRPC 的支持。

据发布新版本的博客文章[称，其余操作包括目录设置、环境和模板，以及对认证的支持。](https://kreya.app/blog/kreya-1.8-whats-new/)

除了推出对 REST 的支持，Kreya 团队还引入了第一个付费功能:脚本和测试。

“有了这个特性，您可以定义在操作被调用时运行的 [JavaScript 代码](https://thenewstack.io/learning-javascript-gordon-zhu-founder-watch-code/)。除了其他功能之外，它还允许你创建测试并查看测试结果。例如，您可以检查响应内容是否包含预期值

面向个人的 Pro 订阅提供了脚本和测试功能，其中还包括每月 5 美元的 Windows 身份验证。Enterprise 以每个用户每月 10 美元的价格构建了具有集中许可证管理和优先级支持的产品包。

新版本还包括一些小功能，例如:

*   系统凭据身份验证提供程序(Windows 身份验证)
*   MacOS ARM (M1)构建
*   gRPC 截止日期支持

## API 平台竞争对手

有许多 API 平台支持 REST 和'[HTTP API](https://www.educative.io/blog/what-are-rest-apis)'根据 IT 研究公司 Gartner 的 2021 年全生命周期 API 管理魔力象限，邮递员[被列为其中有远见的](https://www.postman.com/product/gartner-magic-quadrant/)。谷歌的 [Apigee](https://thenewstack.io/building-adaptive-apps-like-google-now-with-apis-and-analytics-with-apigee-insights/) 、 [Mulesoft](https://thenewstack.io/mulesoft-concession-openapi-adopts-raml-different-approach-api-documentation-descriptions/) 、 [IBM](https://thenewstack.io/creating-api-easy-part-ibm-now-offers-full-api-lifecycle-management/) 、Axway、Software AG、[孔](https://thenewstack.io/neosec-ties-its-api-security-platform-to-kongs-api-gateway/)和[微软](https://thenewstack.io/microsofts-net-core-2-0-brings-apis-cross-platform-standardization/)都是那个市场的领导者。

然而，根据乌克兰软件测试工程师[奥莱克桑德尔·罗马诺夫](https://alexromanov.github.io/about/)的说法，Kreya 是仅有的四个支持 gRPC 的 API 测试工具之一，他补充说 [BloomRPC](https://github.com/bloomrpc/bloomrpc) 与 [Postman](https://www.postman.com/) 、[失眠症](https://insomnia.rest/)和 Kreya 在同一个领域竞争。Postman 对 gRPC 的支持实际上处于测试阶段，尽管公司发言人告诉新堆栈，预计它将在今年晚些时候全面推出。

在克雷亚加入对 REST 的支持之前，罗马诺夫在二月份对四人进行了比较。“对于邮差和失眠来说，gRPC 只是众多功能中的一个，”他写道。“HTTP API 测试是这两个工具的主要功能。此外，它们还有许多额外的特性，便于编写 API 测试。”

最终，他在对那些只需要测试 gRPC APIs 的人的评论中倾向于 Kreya，尽管他指出，那些需要一体化组合的人可能希望“采用一些专门的东西，如 Kreya 或 BloomRPC，并等到 Postman 完成 gRPC。”

如果你需要一个“联合收割机——多合一”，那么你可以暂时使用一些专门的东西——比如 Kreya 或 bloom RPC——然后等到 Postman 完成 gRPC。Postman 已经为 HTTP 准备了一堆不同的好东西(外加一堆教程和社区)。

Allenspach 认为，Kreya 还有其他一些与众不同的特点。

“例如，在 Kreya 中配置多个操作的认证比在其他工具中容易得多，”他告诉我们。因为 Kreya 项目是以文件形式存储的，所以它们也可以被签入到版本控制系统中，这使得它们更容易共享

Allenspach 说，Kreya 仍在开发新的功能，这将使构建和测试 API 在未来的迭代中“更加容易”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>