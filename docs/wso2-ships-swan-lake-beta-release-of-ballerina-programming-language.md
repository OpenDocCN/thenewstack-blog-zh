# WSO2 发布芭蕾舞演员编程语言“天鹅湖”测试版

> 原文：<https://thenewstack.io/wso2-ships-swan-lake-beta-release-of-ballerina-programming-language/>

集成软件提供商 [WSO2](https://wso2.com/?utm_content=inline-mention) 对云原生编程非常认真，以至于该公司创建了 Ballerina，这是一种专门为云原生计算构建的编程语言。今天，WSO2 推出了芭蕾舞演员最新版本的测试版，天鹅湖版本。

[Ballerina](https://ballerina.io/) 是一种开源语言，用于云原生编程以及与序列图和代码的双向映射的集成。WSO2 的首席技术官 [Eric 新人](https://www.linkedin.com/in/enewcomer/)在接受采访时告诉新堆栈，天鹅湖版本有助于简化开发人员如何构建和部署云原生应用程序，其语法用于开发服务和 API，JSON 支持和内置并发。

他说:《芭蕾舞曲》是图表就是代码的唯一语言，而代码就是图表。

“我们认为这是唯一的语言，你可以从它那里得到一个序列图，与代码完全一致和同步，”新人说。“如果您更改代码，它会重新绘制图表，因为创建该语言的目的是为了能够从该语言绘制序列图。”

该语言包括用于并发和网络交互的抽象和语法，并与序列图紧密对应，这使得任何芭蕾舞演员源代码能够在其文本表示和作为序列图的图形表示之间进行双向映射。

### 低代码方法

这意味着专业开发人员可以在文本或图表编码之间移动，而较少的技术人员可以在低代码方法中使用 Ballerina 进行应用程序开发，同时保持代码的完全保真。

“芭蕾舞演员的低代码方面是 VS 代码插件(用于该语言)，它从代码中绘制序列图，”新人说。“每次保存到 GitHub 的代码发生变化时，图表都会刷新，因此它总是最新的。代码的可视化视图总是可供参考。在未来的版本中，图表还将能够生成代码，将低级代码概念扩展到从代码的可视化表示开始。”

芭蕾舞者项目的领导者、WSO2 的创始人兼首席执行官 Sanjiva Weerawarana 说:[现代应用程序不是孤岛，构建它们的团队也不是孤岛。](https://www.linkedin.com/in/sanjivaweerawarana/)

Weerawarana 在一份声明中说:“芭蕾舞语言使开发人员能够创建云原生应用程序，这些应用程序本质上是服务、数据、交易和流程的集成。”“新的天鹅湖测试版扩展了这一功能，使企业能够进一步消除应用开发和集成之间的障碍，以及高技能开发人员和临时开发人员之间的障碍，以加快创新的新数字产品和服务的交付。”

## 云原生应用和微服务

Ballerina 专为云原生应用和微服务而设计。它基于这样一个概念，即现代应用程序编程围绕着创建和使用 API。该公司表示，虽然它可以用作通用编程语言，但它提供了语言抽象，使开发者能够更容易地使用、组合和创建网络服务。

芭蕾舞演员也有一个结构类型系统，允许比传统的静态类型语言更松散的耦合。当组合来自多个独立设计的系统的数据时，这很方便。类型系统可以用作模式来定义通过网络传输和接收的数据，包括 JSON 和 XML 的本地数据类型。

整个 Ballerina 平台包括一个用于包和模块管理的框架，包括依赖性和版本控制。它还拥有芭蕾舞演员中心，这是一个开发者共享模块的公共网络服务。该平台还带有一个 Visual Studio 代码插件，支持芭蕾舞演员程序的文本和图形开发和调试。

此外，Ballerina 平台拥有用于 [OpenAPI](https://thenewstack.io/why-bloombergs-openapi-participation-is-important-for-the-financial-industry/) 和 [gRPC](https://thenewstack.io/grpc-lean-mean-communication-protocol-microservices/) 的工具，并且它具有对 [GraphQL](https://thenewstack.io/why-shopify-favors-graphql-over-rest-for-its-apis/) 的原生支持。它有一个交互式命令行工具来帮助开发人员原型芭蕾舞演员代码，还有一个新的更新工具来保持芭蕾舞演员安装的最新状态。该平台具有一个组件库，支持许多网络协议、数据源和数据格式，以简化语言的采用。

此外，Ballerina 支持独立于任何处理数据的代码来使用普通数据。新人说，它的特点是简单数据与 [JSON](https://thenewstack.io/vintage-computer-festival-2017-giant-floppy-disks-json-vanquished-xml/) 之间的直接映射，具有类似 SQL 的语法、表和十进制数据类型的集成查询，以及类似 XQuery 的 [XML](https://thenewstack.io/marklogic-expands-xml-roots-embrace-json/) 支持。

“我认为最有趣的部分是芭蕾舞演员如何处理数据，”WSO2 首席技术宣传员 Asanka Abeysinghe 说。“我大部分时间都在整理和理解新的数据类型。因此，作为后端开发人员，Ballerina 中表示 XML 和 JSON 的内置数据类型对我来说非常重要。”

Ballerina 还支持为 Kubernetes 和 Docker 自动创建部署，以简化 Ballerina 代码到云的开发和部署。

“在部署层面，一旦你编译并构建了应用程序，你就可以把它放入 CI/CD 管道，你需要的一切都可以部署到 Kubernetes，”新人说。“我们帮助开发人员处理部署到 Kubernetes 的复杂性，允许他们从语言中提取内容，从而在 Kubernetes 配置中创建正确的 Docker 文件配置。”

## 比 Java 更适合云计算

新人还吹捧 Ballerina 比 Java 更适合云计算，他对让 Java 更适合云计算的努力不屑一顾。然而，芭蕾舞演员是一种 [JVM 语言](https://en.wikipedia.org/wiki/List_of_JVM_languages)。

“因此，尽管我们已经获得了在 JVM 生态系统中工作以及与 Java 代码交互操作的好处，但 Ballerina 仍然没有我们希望它在云原生部署中实现的轻量级和敏捷。因此，我们正在使用 [LLVM](https://llvm.org/) 对其进行本机实现，以创建直接到操作系统的二进制映射，并能够通过 C 接口调用来操纵操作系统资源。这项工作计划在今年年底前完成。”

但他说，Java 还没有准备好迎接云原生世界的黄金时代，他引用了 [Micronaut](https://micronaut.io/) 、 [Microprofile](https://microprofile.io/) 、 [Spring Boot](https://thenewstack.io/azure-spring-cloud-offers-managed-deployment-of-spring-boot-applications/) 和 [Quarkus](https://thenewstack.io/red-hats-quarkus-brings-natively-compiled-java-to-kubernetes/) 作为试图让 Java 更适合云原生应用的项目的例子。

“我在想，这是怎么回事，”他说。“为什么要投资尝试将所有这些云原生的东西改造成 Java 呢？这就好比[面向对象的 COBOL](https://www.microfocus.com/documentation/visual-cobol/vc50pu10/VS2019/GUID-A80CA9E8-7B68-4637-91E9-42078C8C9275.html) 。为什么不首先学习一门专为云原生计算设计的语言？”

芭蕾舞演员天鹅湖测试版今天推出。作为在 Apache License 2.0 下发布的开源实现，它不收取任何许可费，可以在[https://ballerina.io/downloads](https://ballerina.io/downloads)免费下载。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>