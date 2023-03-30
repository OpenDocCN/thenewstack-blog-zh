# 为什么数据库需要 API

> 原文：<https://thenewstack.io/why-databases-need-apis/>

一个应用程序在投入生产之前没有多大价值。对于开发人员来说，快速到达这一点意味着轻松访问他们需要构建的数据，而不必担心启动、管理和维护数据库的细节。

API 已经成为将应用程序连接到数据库的事实上的标准，但它并不总是那样。在这里，我们将讨论软件世界中发生了什么变化，以提升将数据库公开为 API 的重要性。我们还将讨论 Stargate，这个开源项目简化了开发人员如何使用这些 API。最新版本的星际之门，包括可扩展性和灵活性的改进，[今天发布。](https://dtsx.io/3gBPz6Q)

## 我们如何构建使用数据库的软件

数据库管理员(DBA)过去负责查询，因为它需要数据库专家来设计开发人员与数据交互的方式。但直到最近，开发人员还被期望知道很多关于与数据库交互的知识，即使他们不是 SQL、查询或数据模型方面的专家。

在 20 世纪 90 年代，我是一名熟练的开发人员，但是数据库让我感到害怕。我花了几年时间才适应使用 SQL。简单地提供一个“SQL 相似物”也是不够的。以 CQL (Cassandra 查询语言)为例，开发它是为了提供一种类似于 SQL 的查询语言，用于与 Apache Cassandra 进行通信。这个想法是为与 Cassandra 的通信提供一个抽象，让那些熟悉关系数据库的人更容易做到这一点。

但是在网络世界中，我们有了身份、权限和[安全性](https://thenewstack.io/category/security/)的新概念，它们完全独立于查询语言。驱动程序简单地在二进制协议上通信的概念在云中并不适用。HTTP 是云的基础应用层协议，但是大多数基于 HTTP 的 API 都很慢。gRPC 等低延迟选项对于分布式系统中的实时通信至关重要。

## 软件如何与软件对话

客户端或应用服务器与数据库对话的标准方式涉及在数据中心内运行的驱动程序。现在一切都在云中运行，但是开发者用各种各样的语言编写。可能会使用 JavaScript 、Python 或任何一种不同的框架，因此软件访问数据的方式需要以不同于传统数据库驱动程序的方式进行抽象——使用开发人员熟悉的 API(JSON、gRPC、 [GraphQL](https://thenewstack.io/distributed-graph-with-graphql/) 或 Document)。

软件与软件对话的现代方式是 API 正是抽象层隐藏了数据库的复杂性。

## 数据的本质

数据过去要统一得多；它可以整齐地放入数据库表的行和列中。但是数据的动态已经改变了。数据以无缝的方式从内存中的表示形式移回数据库，无需太多软件介入。我们正在处理新类型的数据格式，它们比人们过去处理的数据原语(或者 SQL 可以处理的六种左右的数据类型)更加健壮。

## 数据库 API

API 是当今开发人员处理数据库的方式。以下是对原因的总结:

*   HTTP 是云的网络协议。许多开发人员已经熟悉了 web APIs，使用 HTTP 使云应用程序部署变得容易得多。

*   没有必要在本地安装和运行数据库。在本地安装数据库需要付出努力，并且还会产生另一个必须调试问题的环境。

## 通向简单性、可伸缩性和可扩展性的大门

一个[数据 API 网关](https://www.infoq.com/articles/serverless-data-api/)是一个软件基础设施，它通过各种风格的 API 提供对数据的访问，包括 REST、gRPC 等。网关使用一个或多个持久性存储来抽象存储和检索数据的细节。这使得应用程序开发人员能够专注于编写通过易于使用的 API 访问数据的业务服务，而不必学习错综复杂的数据库查询语言。

[Stargate](https://stargate.io/) 是一个开源数据 API 网关，位于应用程序和它需要查询的数据库之间。它于 2020 年 9 月首次推出， [Apache Cassandra](https://dtsx.io/3D95iTS) 被选为第一个数据库，部分原因是它解决了世界上最难的可扩展性和可用性挑战。

数据 API 网关是一种强大的方式，使您的开发人员能够在他们熟悉的框架和结构中工作，提供了生产力和性能之间的一系列权衡。Stargate 通过将 REST、Document 和 GraphQL 作为简单的 API 来提供 Cassandra 的功能。它还提供了一组 gRPC 库，用于在 gRPC 上进行 CQL，作为 CQL 本地驱动程序的一种更简单、轻量级和更云友好的替代方案，而不会牺牲性能。

今年，data tax 的 Stargate 工程团队一直致力于 Stargate 的架构升级。我们称之为星际之门 v2，今天在 T2 发布。基于来自 [Stargate 开发者社区](https://stargate.io/community.html?utm_source=datastaxmedium&utm_medium=blog&utm_campaign=stargate-amplification&utm_term=cloud-native-devplay&utm_content=announcing-stargate-v2-M96&utm_source=blog&utm_medium=stargate-amplification&utm_campaign=cloud-native-devplay&utm_term=announcing-stargate-v2-M96&utm_content=https://stargate.io/community.html)的反馈，在 Stargate v2 中，我们做了一些重要的更新，使得开发者更容易使用，社区也更容易为项目做出贡献。最重要的是，Stargate v2 的高性能 gRPC API 可以提供相当于本地数据库驱动程序的速度。这使得开发人员能够使用 HTTP 等云友好的网络协议来连接应用程序和数据库，而不会损失网络性能。

### 可扩展且适应性强

没有一种自顶向下的策略或 API 风格能够在与大量开发人员的接触中幸存下来。Stargate v2 的一个关键目标是通过使实现本身更容易理解、调试、增强和扩展，使社区能够快速和容易地添加新的 API 服务。

添加一个新的 API 服务现在简单多了，其余的、GraphQL 和 Document API 服务的源代码为开发人员提供了指导性的示例代码，展示了一个完成的 API 服务应该是什么样子。

API 层应该是多模型的；开发人员希望找到他们喜欢的现成 API，而不是被迫调整他们的开发工作以适应不同的 API。如果 API 不可用，API 层应该能够适应。

### 云原生

在数据库前扔代码已经做了很多年了。但是实际上构建一个可以随数据库扩展的平台——适应性强且可靠——是一件新鲜事。如果你正在使用 Cassandra，你可能已经是一个高速增长的应用程序——或者渴望成为一个。因此，摆在它面前的一切都必须有利于一个高增长的环境。Stargate 作为 Cassandra 协调器代码的一个分支而诞生，因此它继承了 Cassandra 众所周知的可靠性和可用性。

API 层必须完全能够大规模运行，所以 Stargate v2 的另一个目标是使它对云更加友好。促进星际之门可扩展性的几个变化包括:

*   Stargate 现在完全集装箱化，并在 Kubernetes pods 中运行，这使运营商能够更好地控制工作负载的规模。

*   API 服务已经从单片星际之门节点转移到独立的微服务中，这将使每个 API 能够独立扩展。

*   存储节点和协调器节点可独立部署和扩展，这也让运营商能够更好地控制工作负载的扩展方式。

如果工作负载是查询密集型或存储密集型的，则无需将整个集群作为一个整体来扩展，就可以对其进行调优。

## 用熟悉的东西发展

云数据服务已经成为技术世界的主导主题，因此毫不奇怪，开发人员倾向于按照 JSON 这样的数据抽象而不是特定数据库特有的习惯用法来思考。Stargate 是大量艰苦工作的高潮，以满足开发人员的需求，使他们能够在他们熟悉的框架和结构中工作。

在这里了解更多关于星际之门的信息。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>