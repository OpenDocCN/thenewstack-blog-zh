# Choreo:构建云原生应用的无服务器平台

> 原文：<https://thenewstack.io/choreo-a-serverless-platform-for-building-cloud-native-apps/>

[](https://www.linkedin.com/in/charleshumble/)

 [查尔斯·亨布尔

查尔斯·亨布尔是云本地咨询公司 Container Solutions 的主编。作为一名前软件工程师、架构师和首席技术官，他曾担任过技术和内容团队的高级领导和执行官，最近又与离岸团队、在岸团队和远程团队合作，从小型初创公司到大中型公司。](https://www.linkedin.com/in/charleshumble/) [](https://www.linkedin.com/in/charleshumble/)

云从根本上改变了几乎每个层面的编程本质。我们已经从 API 通常位于语言库中的情况发展到通过 HTTP/JSON 在网络上使用 API。在前云时代，很少有企业开发人员需要处理并发性，而现在几乎每个程序员都需要处理并发性。越来越多通常在网络层处理的问题已经转移到软件中，成为程序员的问题。作为一个行业，我们仍然在寻找我们的语言、工具和编程模型来赶上。

我们看到诸如 [Go](https://golang.org) 和 [Rust](https://www.rust-lang.org) 等语言，以及最近 WSO2 的 [Ballerina](https://ballerina.io) 等语言，都诞生在这个新时代，每一种语言都有一个特定的甜蜜点。就云原生世界中的编程模型而言，无服务器可能是唯一接近 Kubernetes 的炒作和关注水平的技术。然而，这是一个模糊不清的术语，指的是一组完全不同的技术，从开发者的角度来看，底层计算机无关紧要。这个术语似乎是由肯·弗洛姆在 2012 年创造的，他 [写道](http://readwrite.com/2012/10/15/why-the-future-of-software-and-apps-is-serverless/) :

短语“无服务器”并不意味着不再涉及服务器。这仅仅意味着开发人员不再需要考虑那么多。计算资源被用作服务，而不必围绕物理容量或限制进行管理。服务提供商越来越多地承担起管理服务器、数据存储和其他基础设施资源的责任。开发人员可以建立自己的开源解决方案，但这意味着他们必须管理服务器、队列和负载。

“功能即服务”( Function as a Service，或称 FaaS)已经与术语“无服务器”纠缠在一起，以至于两者几乎可以互换，但应该注意的是，还有其他无服务器产品覆盖特定领域，如队列、数据库和一些低代码系统，如 Choreo 或 Zapier。

围绕 FaaS 的这种兴奋始于 2014 年的[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)'[λ](https://aws.amazon.com/lambda/)。Lambda 的运行方式很像 20 世纪 90 年代末或 21 世纪初的典型消息队列系统。您部署了一些代码，这些代码在被某个事件触发之前一直处于休眠状态，比如到达队列的消息、HTTP 调用或到达特定位置的文件。当被触发时，代码运行，当完成时，它关闭。底层平台处理这一点，包括函数的并发执行，因此您可以在适当的时候运行多个副本。

这有许多优点:开发人员相对容易编写和推理；它为您提供了一个隐含级别的健壮性和高可用性，并且在处理不可预测的负载时特别适合；不运行的代码不会让你花钱——你只需为你使用的代码付费。

当然，软件架构中的一切都是一种交换，FaaS 也不例外。有一些重要的限制需要注意:您对给予每个运行时调用的资源的控制是有限的，比如 CPU 或 I/O；函数对于长时间运行的流程来说并不理想，事实上，它们的运行时间通常是有限的；如果基础设施的其他部分不能很好地扩展，FaaS 的动态扩展特性会带来问题。

此外，大多数函数调用被认为是无状态的，这意味着一个函数不能访问前一个函数的状态，除非该状态已经被保存在外部的某个地方，如数据库。如果你需要这样做，有几个选项——AWS 提供了 [步函数](https://aws.amazon.com/step-functions/) ，允许开发人员使用 JSON 将多个函数捆绑在一起，Azure 提供了 [持久函数](https://docs.microsoft.com/en-us/azure/azure-functions/durable/durable-functions-overview?tabs=csharp) ，支持暂停函数状态并允许它在函数停止的地方重新启动——但这两个选项都不理想。

这些围绕状态管理的挑战使得使用 FaaS 进行集成编程存在问题，而这正是 WSO2 的 Choreo 的目标领域。

## 构建基于 API 的应用程序

[Choreo](https://wso2.com/choreo/) ，目前处于测试阶段，是一个 iPaaS，构建在 [Ballerina](https://ballerina.io) 之上，WSO2 的语言是为编写中小型网络分布式应用程序而设计的。它可以被认为是自以为是的软件，因为它提供了您需要的所有核心功能，以支持构建基于 API 的应用程序的完整软件开发生命周期——从编码到可观察性——开箱即用。WSO2 负责 API 管理和集成的副总裁兼副首席技术官 Nuwan Dias 告诉我，他认为 Choreo 是一个无服务器的 API 平台。

“Choreo 为您提供了一个平台，您可以在这个平台上使用无服务器来构建实际的 API。所以你得到一个无服务器的体验，你不用考虑服务器，你实现你的 API 逻辑，然后你运行它。”

像 FaaS 一样，Choreo 可以增加或减少运行实例的数量，作为未来 GA 版本的一部分，用户将能够限制平台允许并发运行的给定 Choreo 程序的实例总数。

Choreo 内置了对许多可公开访问的 API 的支持，如世界银行开放 API、开放天气地图、新冠肺炎统计等，以及对 GitHub、Slack、SalesForce、谷歌的 Workplace(以前的 G Suite)、Spotify、SendGrid 和 Medium 等工具的 API 访问，并且一直在添加更多的集成。

然而，该平台真正闪光的地方是对于那些希望使用第三方 API 或者开发和发布自己的 API 的用户。除了使用预建的 [连接器](https://wso2.com/choreo/docs/references/connectors/) 之外，开发人员还可以将 Choreo 的 HTTP 连接器用于任何合适的第三方 API。然后，Choreo 为通过系统公开的 HTTP 服务提供了一套全面的 API 管理特性，包括内置的断路器。底层芭蕾舞语言包括对 JSON/XML 数据类型的内置支持，正如詹姆斯·克拉克 [最近在 InfoQ 播客上与我讨论的](https://www.infoq.com/podcasts/james-clark-ballerina-language-network-data-concurrency/?itm_source=infoq&itm_medium=videos_homepage&itm_campaign=videos_row1) 一样，它使处理普通数据变得简单明了。

要了解这一点，请看 Choreo 文档中的这个 [快速示例](https://wso2.com/choreo/docs/apis/create-and-publish-your-first-api/) ，它演示了如何从头开始创建、测试和发布一个简单的 REST API。

Choreo 中的 API 管理由五个关键组件推动:

*   **Choreo 控制台**:允许 API 创建者开发、记录、保护、测试和版本化 API。它还为 API 发布者提供了部署和发布 API 以及应用速率限制策略的机制。
*   **API 开发者门户**:允许 API 发布者托管和宣传他们的 API，API 消费者安全地发现、评估、订阅和使用 API。
*   **API 密钥管理器**:Choreo 的默认身份提供者(IdP)，充当安全令牌服务(STS)。拥有管理员权限的用户还可以通过 Choreo 控制台将外部授权服务器(如 Okta)配置为 IdP。
*   **流量管理器**:帮助管理 API 流量，为不同服务级别的用户提供 API 和应用，保护 API 免受恶意攻击，并应用速率限制策略。
*   **Choreo Connect** :专门为微服务设计的 API 网关。

在引擎盖下， [OpenAPI 规范](https://swagger.io/specification/) (也称为 Swagger)用于一个 API 的表示。您可以在 Choreo 控制台中使用 Swagger 定义导入 API，Choreo 用户也可以用同样的方式在 Swagger 中查看、编辑、导入或下载 API 定义。

一旦部署了 API 或其他 Choreo 应用程序，该平台就内置了对可观察性的支持，允许团队可视化和监控正在运行的应用程序，包括查看状态、延迟、吞吐量数据、诊断数据和日志。

Choreo 的一个关键方面是使用 Ballerina 为其开发应用程序，这与脚本语言有一些相似之处，并且非常实用。由于 Ballerina 旨在用于工业而非学术界，因此它强调可靠性和可维护性。它相对较小的尺寸和简单性也给了它一个温和的学习曲线，使得个人程序员学习起来很简单。

Ballerina 中的几个设计选择使其特别适合这个云原生时代的 API 编程。一个例子是，类型系统被设计成网络友好的，具有一组基本的数据类型，它们一对一地映射到 JSON。[Dakshitha Ratnayake 在为 InfoQ](https://www.infoq.com/articles/ballerina-cloud-native-programming/) 撰稿时指出，“这使得来自网络的 JSON 有效负载可以立即进入语言，并且无需转换或序列化就可以运行。”

Ballerina 还对并发性提供了强大的支持，其工作方式与 Go 类似，并且包括对轻量级线程的支持，即 Ballerina 中的 strands。这些类似于 Go 中的纤程或 Java 中即将推出的 [项目 Loom](https://www.infoq.com/podcasts/java-project-loom/) 中的虚拟线程。从编程的角度来看，线程看起来像操作系统线程，但实际上是一个运行时构造，并不直接映射到操作系统线程。运行时虚拟机可能会将数百万个线程映射到一个非常小的操作系统线程集。因为它们是轻量级的，所以您可以使用更多的线程，并且因为创建虚拟线程的成本很低，所以您不再需要共享它们，这大大简化了多线程代码的编写。

在集成编码中，允许开发人员观察端点之间的流程和交互的可视化表示非常有用。芭蕾舞演员能够提供这一点。为了实现它，低代码编辑器是芭蕾舞演员语法树的直接表示，而不是抽象层。这意味着，与前几代低代码工具不同，开发人员可以直接编辑芭蕾舞演员的源代码，并将这些更改反映在低代码编辑器的可视化表示中，而不会有一个无法表示另一个的风险；在低级代码环境中生成的代码仅仅是代码——不涉及其他抽象。正如我在一篇关于新堆栈 的 [文章中提到的:](https://thenewstack.io/exploring-choreo-wso2s-new-ipaas-built-on-top-of-ballerina/)

Choreo 平台将生成的源文件存储在与用户帐户相关联的私有 Git repo 中。用户可以克隆 repo，使用 Microsoft VS 代码编辑 Ballerina 代码，提交他们的更改，并合并到同一个 repo。Choreo 将获取更新的代码，在图形和文本编辑器中显示，并将其用于构建管道。”

另外， [芭蕾舞女 VSCode 插件](https://marketplace.visualstudio.com/items?itemName=WSO2.Ballerina) 可以从源代码动态生成序列图。

Choreo 和 Ballerina 是雄心勃勃的项目。这四个关键主题——网络交互、数据、并发和代码的可视化——使 Choreo 成为云原生业务的一个独特而有趣的选择。你已经可以开始免费试用 Choreo 了，预计明年年初会有 GA 发布。

定价模型基于用户数量和顺序中的步骤，从运行简单流程的单个开发人员免费到运行更复杂工作流程的团队每月 995 英镑不等。与许多[无服务器环境](https://thenewstack.io/category/serverless/)不同，Choreo 程序在运行时间方面没有限制，尽管更复杂的工作流会更昂贵。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>