# 使用 Apache Kafka 和 TriggerMesh 增强事件驱动的集成

> 原文：<https://thenewstack.io/supercharging-event-driven-integrations-using-apache-kafka-and-triggermesh/>

事件驱动的集成为企业提供了所需的灵活性，以适应和调整快速的市场和客户偏好变化。Apache Kafka 已经成为整个企业中代理消息的领先系统。将 TriggerMesh 添加到 Kafka 提供了一种跨系统以原生方式路由和转换消息的方式。DevOps 团队，如 PNC Bank 的团队，使用 TriggerMesh 声明式 API 来定义这些事件驱动的集成，并将其作为 CI/CD 管道的一部分进行管理。

## 事件驱动架构基础

 [塞巴斯蒂安·戈阿斯根

Sebastien 是 TriggerMesh 的联合创始人兼首席产品官。](https://www.linkedin.com/in/sebastiengoasguen/) 

许多现代应用正在迅速采用事件驱动架构(EDA)。EDA 用于松散耦合独立的微服务，并提供接近实时的行为。当结合云原生思维以及容器和无服务器功能的使用时，EDA 使整个企业应用前景现代化。

在过去的 10 年里，从 DevOps 运动开始，我们就非常重视提高灵活性和缩短新应用的上市时间。从开发到生产的竞赛被视为真正的竞争优势。考虑到这一点，将单片应用程序分解为微服务被视为一种更快部署独立服务的方法，为每个微服务提供了自己的生命周期。将每个微服务打包并在生产中进行管理，这导致了容器和 Kubernetes 时代的到来。然而，耦合每个微服务仍然是一个未解决的问题，这也是 EDA 卷土重来的原因。当你采用事件驱动的架构时，你可以通过像 Kafka 这样的消息传递底层将你的独立微服务耦合在一起；从而获得您一直在寻找的敏捷性和规模。

### 解耦您的应用

将应用的组件解耦到微服务中，使它们能够彼此独立地部署，这意味着它们现在具有独立的生命周期-它们可以通过独立的 CI/CD 管道进行开发、打包、测试和部署。这样做的好处是，开发人员可以修改他们自己的系统，而不需要改变组成整个云原生应用程序的任何其他微服务中的任何逻辑。本质上，松散耦合的微服务是云应用程序的库，其好处是不必重新编译成一个整体应用程序。

### EDA 和容器

事件驱动架构由三个主要组件组成:生产者、消费者和代理。当事件发生时(例如，数据库更新)，生产者向代理发送消息。消费者从代理接收一个事件，并采取一些行动(例如，运行一个无服务器功能，在数据库上执行某种类型的 ETL 操作)。

起初，消息和事件之间的区别可能会令人困惑。事件是状态发生变化的通知。但是，消息包含的附加信息不仅仅代表通知。存在与消息相关联的附加数据。事件就像一个电话，但是它不会告诉你谁在线或者他们的信息是什么。一条消息提供了通话的详细信息，例如谁打来的电话以及所讨论内容的记录。

生产者不受他们生产的事件将如何被消费的影响(因此可以添加额外的消费者而不影响生产者)。消费者不需要关心事件是如何产生的。由于这种松散耦合，微服务可以用不同的语言实现，或者使用不同的适合特定工作的技术。这意味着容器是微服务的完美包装机制；在我们的 EDA 环境中，容器是事件和/或消息的生产者和消费者的完美包装。我们将越来越多地看到，在 Kubernetes 中管理的云原生应用程序将是一组带有 Kafka 消息传递底层的事件的生产者和消费者，运行在 Kubernetes 或 AWS MSK 或 Confluent 等云服务中。

### 来自 CNCF 的云事件规范

现在想象一下，这些消息是由不同的服务提供的，无论它们是云服务还是本地应用程序。这使得系统很难理解从一个系统到另一个系统的消息。您不仅需要消息的转换，还需要对消息的元数据有一个共同的理解。

这就是标准，或者至少是规范发挥作用的地方。由[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)支持的规范 CloudEvents 1.0 为云提供商提供了一种表达事件的通用方式。该规范指出，事件以特定的格式表示，数据需要有特定的字段。因此，它需要有时间戳、主题、来源和类型。

越来越多的系统正在实现事件驱动架构。云提供商看到了这一趋势，他们都提供了具有自己特定功能的消息传递基础。[例如，亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)提供了 [Kinesis](https://aws.amazon.com/kinesis/) 用于实时处理事件消息。其他解决方案，如开源分布式事件平台 [Apache Kafka](https://kafka.apache.org/) ，可以与几乎任何系统集成，并部署在任何云或本地。Kafka(及其商业版本，由 Confluent 提供)的受欢迎程度自其在 LinkedIn 上发展以来迅速增长。随着它开始取代 Tibco 或 Mulesoft 等企业服务总线，大多数财富 100 强企业现在都在使用它。这种增长的原因是因为 Kafka 提供了一种方法来提供高度可伸缩的实时消息流，以共享可用于在云和企业中支持事件驱动的应用程序的事件。

## 增压卡夫卡

Kafka 是一个非常好的代理消息和支持 EDA 的系统，但这只是等式的第一部分。在 TriggerMesh，我们发现提供一种方法来路由这些消息并将其转换为更有意义的事件(可以在云上进行交换)是非常有价值的。随着卡夫卡越来越受欢迎，用这些实时事件流做更复杂事情的能力也在上升。消费、路由事件流并将其转化为有用消息的能力(不只是来自 Kakfa，而是来自所有云提供商)是长期成功的关键。我们所说的以本机方式处理事件云是指应用程序中发生的事件流需要用强大的声明式 API 来描述。Kubernetes 向我们展示了如何用声明式思维来管理大规模应用程序；而为埃达做，就是为卡夫卡“增压”的方式。

### GitOps 遇见 EDA

想象一下，能够用一个声明性的 API 定义您的事件生产者、消费者、您的转换、您的事件存储和您的路由表。您将能够在您自己的事件驱动应用程序中使用相同的 DevOps 思维模式，您采用这种思维模式来分离您的整体应用程序。这意味着在您的版本控制系统中，您将拥有您的事件流的表示；并且 EDA 声明状态的任何改变都将在您的实时系统中自动协调。

一个例子是我们的客户 PNC 银行，它正在使用 Apache Kafka。银行的项目团队事件或消息来自各种不同的来源，如 Jenkins 和 Bitbucket。他们把每一条信息都推给卡夫卡。他们发现需要像 TriggerMesh 这样的云原生集成平台来增加事件的意义，同时利用 Apache Kafka 的事件流功能。原因是，他们有一组需要在特定事件发生时按需触发的微服务。TriggerMesh 为他们提供了一种声明性的方式来定义他们的事件流，而不必深入 Kafka 配置:没有 Java 编码，没有 Kafka connect 配置，没有特定的语言 SDK 来产生或消费消息。他们采用了 CloudEvent 规范，他们的微服务只是消费和产生云事件，TriggerMesh 提供了带有声明性 API 的连接，允许他们继续使用他们的 GitOps 管道。

PNC Bank 了解这种 API 驱动的集成模式非常适合他们的 DevOps 团队的优势，因为他们可以像管理微服务应用程序一样管理集成。TriggerMesh 声明式 API 很容易被 DevOps 团队集成到他们的管道中。

## 结论

TriggerMesh 抽象事件代理、事件源和事件接收器。对于代理，您可以交换您想要的任何消息流技术。你可以使用 Kinesis，卡夫卡，谷歌 PubSub，NATS，和/或其他。

TriggerMesh 利用底层代理上的事件流并扩展它们，以便它们可以用于新的场景(例如，来自云提供商、Apache Kafka 或企业服务总线的实时流)。我们最常遇到的用例是 TriggerMesh 提供了一种扩展开源 Apache Kafka 的方法。有了 Kafka Connect，就有了更多的低级系统管理员工作和安装配置。而使用 TriggerMesh，由于它完全是 API 驱动的，开发人员退后一步，直接与 API 交互，并定义所需的状态。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>