# gRPC:深入研究沟通模式

> 原文：<https://thenewstack.io/grpc-a-deep-dive-into-the-communication-pattern/>

[](https://www.linkedin.com/in/dknkuruppu/)

 [Danesh Kuruppu 是 WSO2 的技术负责人，在微服务、消息协议和服务治理方面拥有丰富的专业知识。Danesh 率先开发芭蕾舞演员的标准库，包括 gRPC、数据和微服务框架。他与人合著了由 O'Reilly media 出版的《gRPC 启动和运行》。](https://www.linkedin.com/in/dknkuruppu/) [](https://www.linkedin.com/in/dknkuruppu/)

如果您已经构建了 gRPC 应用程序并了解通信基础，您可能已经知道在基于 gRPC 的应用程序中使用了四种基本的通信模式:简单 RPC、服务器端流、客户端流和双向流。在本文中，我将深入探讨这些通信模式，并讨论每种模式的重要性，以及如何根据用例选择正确的模式。

在讨论每个模式之前，我将讨论它们的共同点，比如 gRPC 如何通过网络在客户机和服务器之间发送消息，以及请求/响应消息是如何构造的。

## 基于 HTTP/2 的 gRPC

根据官方文档，gRPC 核心支持不同的传输协议；然而，HTTP/2 是其中最常见的。在 HTTP/2 中，客户机和服务器之间的通信通过一个 TCP 连接进行。在连接中，可以有多个双向字节流，称为流。在 gRPC 术语中，一个 RPC 调用被映射到 HTTP/2 中的一个流。如下图所示，在客户端和服务器之间传递的消息被分解成多个帧，每个帧都标记有流 ID。这允许在单个连接中多路复用多个消息。

您可以看到附加到流的两种不同类型的帧(即报头和数据帧)。这类似于 HTTP 协议，在 HTTP 协议中，请求/响应以头部开始，后面跟着数据内容。

## 请求/响应消息

在 gRPC 中，客户端触发通信，通信由请求头、二进制消息(称为带长度前缀的消息)和流结束标志组成，通知服务器客户端已发送完内容。作为响应，服务器发送一个响应消息，该消息也由头部、二进制消息和尾部组成。

我们知道 gRPC 消息如何在 HTTP/2 连接上流动，让我们用编码示例来讨论通信模式。在本文中，我将使用[芭蕾舞语言](https://ballerina.io/)作为代码示例。

> Ballerina 是一种开源语言，主要专注于云原生编程。如果你还没有安装芭蕾舞演员，你可以从这里下载。

## 简单 RPC

这是 gRPC 最简单的通信模式。这里，客户端向服务器发送一条消息，并接收一条消息。如下图所示，在流内部，只有一个二进制消息同时进入请求和响应。

让我们看看服务器端和客户端的代码是什么样子的。这里，我们要以 gRPC 官网上著名的‘路线指南’为例。

下面摘录了简单的 RPC 方法定义；您可以在芭蕾舞演员 gRPC 资源库中找到完整的[服务定义](https://github.com/ballerina-platform/module-ballerina-grpc/blob/master/examples/routeguide/proto-file/route_guide.proto)。

这里的“GetFeature”方法用于获取给定点位置的特征。客户端发送位置细节并接收特征的名称。如果给定位置没有要素，则返回名称为空的要素。

使用服务定义，我们可以生成服务存根并实现 GetFeature 方法的逻辑。

在 Ballerina 中，有一个内置工具可以生成服务和客户端存根文件。您可以参考芭蕾舞者网站上的 [gRPC 工具指南](https://ballerina.io/learn/tooling-guide/cli-tools/grpc/)。

在下面的代码片段中，我们向您展示了 RouteGuide 服务中的`GetFeature`方法的 Ballerina 实现。

在这里你可以看到，我们得到一个单一的“点”信息作为输入，在服务器端，我们得到相应的“功能”和响应。

现在，让我们实现客户端逻辑来远程调用“GetFeature”方法。在 gRPC 中，您可以使用任何首选语言来实现客户端。

如上面的代码片段所示，第一步是建立到服务器的连接并启动客户机。然后，我们可以调用客户端的“GetFeature”方法来调用远程方法。作为回报，我们从服务器得到一条“特征”消息。

在 Ballerina 中，网络呼叫由'→'符号表示，这很容易区分网络呼叫和本地呼叫。(参见[消费服务](https://ballerina.io/learn/by-example/consuming-services)的网络交互示例。)

check 表达式立即返回函数，而不专门处理它。(参考[检查表达式](https://ballerina.io/learn/by-example/check-expression)的语言样本。)

简单的 RPC 模式实现起来很简单，所以让我们转到服务器流 RPC，这是一种更高级的模式。

## 服务器流 RPC

与简单 RPC 模式不同，在服务器流 RPC 中，当从客户端收到请求时，服务器发送回一系列响应。这个响应消息序列是在客户端发起的同一个 HTTP 流中发送的。如下图所示，服务器会一直等待，直到收到来自客户端的消息，并以成帧消息的形式发送多个响应消息。最后，服务器通过发送带有呼叫状态细节的尾部元数据来结束流。

让我们以同一个`Route Guide`例子来说明使用 Ballerina 的服务器端和客户端实现。

下面摘录了在`Route Guide` [服务定义](https://github.com/ballerina-platform/module-ballerina-grpc/blob/master/examples/routeguide/proto-file/route_guide.proto)中定义的服务器流 RPC 方法。我们将使用下面的 RPC 方法演示服务器和客户机的实现。

这里使用“ListFeature”方法来获取给定矩形区域内的可用特征。客户端发送矩形的点细节，并以流的形式接收可用特征的列表。

正如我们前面所做的，我们可以从服务定义中生成服务器和客户端代码，并构建“ListFeature”方法的逻辑。下面的代码片段显示了如何使用 Ballerina 在服务器端实现“ListFeature”方法。

我们得到一个单一的“矩形”消息作为输入，在服务器端，我们过滤掉“矩形”中的“特征”,并以“特征”消息流作为响应。

Ballerina 支持集成查询表达式，它以类似 SQL 的语法指定逻辑来处理数据。更多详情请参考芭蕾舞者网站上的[综合查询指南](https://ballerina.io/learn/user-guide/data-and-events-processing/using-language-integrated-queries/)。

现在，让我们实现客户端逻辑来远程调用“ListFeature”方法。

像简单的 RPC 调用一样，我们首先初始化客户机并建立与服务器的连接。然后，我们可以调用客户端的“ListFeature”方法来调用远程方法。返回的是一串特征消息。在 Ballerina 中，这个消息序列由 Ballerina Stream 对象表示。我们可以遍历流对象并逐个读取响应。

Ballerina 支持流类型，它携带一系列生成的值。(参考[流类型](https://ballerina.io/learn/by-example/querying-with-streams.html?is_ref_by_example=true)的语言示例。)

现在，我们学习了简单和服务器流 RPC 模式。在这两种情况下，客户端通过只发送一条消息并等待响应来启动流。服务器使用同一个流发送一条或多条消息。让我们看看客户机流 RPC 模式，它与服务器流模式相反。

## 客户端流 RPC

在客户端流 RPC 模式中，客户端向服务器发送多条消息，而服务器只返回一条消息。与上面讨论的模式类似，所有这些消息都在客户机发起的一个 HTTP 流中传递。下图说明了多个消息如何在流中流动。这个流可以持续到 RPC 结束。

让我们以同一个“路线指南”为例来说明服务器端和客户端的实现。

“路线指南”[服务定义](https://github.com/ballerina-platform/module-ballerina-grpc/blob/master/examples/routeguide/proto-file/route_guide.proto)中定义的客户端流 RPC 方法摘录如下。我们将使用下面的 RPC 方法演示服务器和客户机的实现。

这里,“RecordRoute”方法接受正在遍历的路线上的点流，并在遍历完成时返回 RouteSummary。客户端发送路线上的点细节，并在完成时接收路线摘要。

下面的代码片段显示了如何使用芭蕾舞语言在服务器端实现“RecordRoute”方法。

如代码片段所示，服务器以流的形式接收客户端消息，并遍历该流，计算路由摘要。最后，服务器返回摘要报告作为响应。

在 Ballerina 中，通过`ballerina/time`模块支持与时间相关的操作。更多细节请参考[时间模块](https://lib.ballerina.io/ballerina/time/2.0.0-beta.2)的 API 文档。

现在，让我们实现客户端逻辑来远程调用`RecordRoute`方法。

与其他两种 RPC 模式不同，当调用客户端的`RecordRoute()`方法时，客户端流返回一个流客户端。使用流客户端，我们可以向/从服务器发送和接收消息。一旦所有的消息都被发送，客户端通知服务器完成。

让我们看看最后一种通信模式:双向流 RPC。这是我们之前讨论过的风格的组合。

## 双向流 RPC

在双向流 RPC 中，客户端和服务器互相发送消息流。客户端通过发送报头帧来建立 HTTP 流。一旦建立了连接，客户机和服务器就可以同时发送消息，而不必等待对方完成。通信基于 gRPC 客户端和服务器的逻辑进行。

让我们以同一个“路线指南”为例来说明服务器端和客户端的实现。

路由指南[服务定义](https://github.com/ballerina-platform/module-ballerina-grpc/blob/master/examples/routeguide/proto-file/route_guide.proto)中定义的双向流 RPC 方法摘录如下。

这里,“RouteChat”方法用于接受正在遍历的路由上的 route note 流，同时从其他用户返回 route note。客户端发送路线上的点细节，并从其他用户接收相同点的细节。

以下代码片段显示了如何在 Ballerina 中实现“RouteChat”方法。

如代码片段所示，服务器以流的形式接收客户端消息，并遍历该流，发送从其他用户收集的 RouteNode 消息。这里，服务器使用 caller 对象向客户端发送消息，而不是从远程方法返回值。这是因为服务器需要同时发送消息，而不是等待客户端请求完成。

在 Ballerina gRPC 模块中，有两个选项可以向客户端发送响应:一个是从远程函数返回值，第二个是使用传入远程函数的 caller 对象。我们只能使用其中一个选项。

现在，让我们实现客户端逻辑来远程调用`RouteChat`方法。

当调用客户端的“RouteChat()”方法时，这类似于客户端流模式。它返回一个流客户端。使用流客户端，我们可以向/从服务器发送和接收消息。在客户端流中，在客户端发送所有消息后，只有一条响应消息来自服务器。但是，在双向流中，服务器响应消息可以同时出现。因此，您可以启动一个新的 worker 来读取响应，同时向服务器发送消息。

芭蕾舞演员有一个独特的并发模型使用股。更多详情请参考芭蕾舞女演员并发指南。

至此，我们涵盖了 gRPC 支持的所有通信模式。当您构建基于 gRPC 的应用程序时，分析业务需求并选择正确的模式是非常重要的。我希望您从本文中收集的信息能够帮助您选择最适合您需要完成的任务的模式。

## 结论

gRPC 是一种进程间通信技术，使微服务之间的通信更快、更高效。它支持四种基本的通信模式:简单 RPC、服务器流 RPC、客户端流 RPC 和双向 RPC。当连接多个服务以构建真实世界的应用程序时，每种通信模式都解决独特的实际问题。

您可以参考我们在[芭蕾舞演员 gRPC Github 库](https://github.com/ballerina-platform/module-ballerina-grpc)中讨论的示例的完整实现。

这里有一些额外的资源可以帮助你。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>