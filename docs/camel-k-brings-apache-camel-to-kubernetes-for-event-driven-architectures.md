# Camel K 将 Apache Camel 引入 Kubernetes，用于事件驱动的架构

> 原文：<https://thenewstack.io/camel-k-brings-apache-camel-to-kubernetes-for-event-driven-architectures/>

近年来，应用程序[越来越依赖](https://thenewstack.io/event-driven-architecture-wave-future/)事件驱动架构(EDA ),尤其是随着无服务器和微服务的出现。EDAs 将一个事件从随后可能发生的动作中分离出来，这与传统的线性架构相反，在传统的线性架构中，一个事件可能在同一代码中处理。这种分离使得 EDA 流程能够独立扩展，虽然 EDA 并不严格要求微服务或无服务器，但各自的松散耦合和按需特性是完美的契合。

在云原生世界中，焦点可能通常在事物的无服务器端，Knative 或 Lambda 成为焦点，但是，正如名称所暗示的，事件驱动的架构没有事件就什么都不是。 [Apache Camel K](https://camel.apache.org/camel-k/latest/) 采用了 [Apache Camel](https://camel.apache.org/) ，这是企业集成软件的基础部分，最初是作为 2003 年的书籍[Enterprise Integration Patterns](https://en.wikipedia.org/wiki/Enterprise_Integration_Patterns)的一种编码出现的，并将其引入 Kubernetes，为 EDA 提供了大量的事件源， [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 的产品管理总监[基思·那个傻瓜](https://www.linkedin.com/in/babo)解释道。

那个傻瓜说:“当他们创作这本书时，阿帕奇社区的几个人走过来，创建了这个开源项目，叫做阿帕奇骆驼”。“Apache Camel 所做的是，它采用了书中的模式，并基于这些模式创建了自己的特定领域语言(DSL)。这使得实现这些基本的集成变得简单多了。”

那个傻瓜所说的模式包括基于内容的路由、转换、连接、索赔检查等等。虽然 Camel 可以为 EDA 提供所有的功能，但它不是为本地 Kubernetes 部署而构建的，那个傻瓜说这已经足够了。他说，Camel K 是 Camel for Kubernetes 的改编版，通过 Kubernetes 运营商安装和管理 Camel 的生命周期。

“我们想‘我们如何利用这个伟大的集成框架，从本质上来说，围绕它进行构建，并以本机方式与 Kubernetes 集成，以便您获得 Kubernetes 在扩展、管理、监控、生命周期独立交付方面的最佳方面，就像 Kubernetes 擅长的所有这些方面一样？“我们如何为骆驼本身制作这些土特产，”“骆驼王就是从那里来的，”那个傻瓜说 Camel K 本身并没有改变 Camel，它引入了 Camel K 操作符，它的工作是监视部署在平台上的定制资源，然后控制生命周期管理的所有元素。"

EDA 的许多常见实现都使用 HTTP 和 TCP 作为事件源，但是 Apache Camel K 将这个列表扩展到 300 多个组件。

“在一般情况下，这些无服务器架构的很大一部分是由 HTTP 请求驱动的。随着我们开始扩大使用规模，我们立即转向其他一些技术，如 Kafka、消息传递和事件驱动的接口，这些技术实际上会将生产者事件从该事件的下游处理中分离出来，”那个傻瓜解释道。“我们有能力部署 Camel K 连接器，并将其作为 Knative 和无服务器的入口点。Knative 可以使用的事件源，Camel K 可以与它进行本机集成，以将 Knative 或无服务器架构连接到您想要生成或从中提取事件的任何上游系统。”

除了作为 Knative 的入口，那个傻瓜说骆驼 K 还超越了 Knative 的规格，作为一个出口。Camel K 可以执行他所谓的“事件同步”，即在接受来自外部系统的一些数据并使用无服务器架构处理这些数据之后，可以将这些数据路由到其他地方。

“这是一个独特的方面，”他说。“骆驼 K 有助于这一点。您不仅可以将这些连接器用于传入或传入数据和事件，还可以将它们用于传出和传出数据。”

那个傻瓜进一步解释说，虽然 EDA 的核心概念没有随着微服务的引入而改变，但 EDA 模式的应用已经基于新的架构方法而发展。

“一个主要的变化是，许多事件驱动的结构，如 Java 或。Net 事件、触发器或消息驱动 beans 存在于一个进程空间中，因此您不能从其他微服务订阅它们。这确实是像阿帕奇卡夫卡这样的技术帮助填补的空白，”那个傻瓜说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>