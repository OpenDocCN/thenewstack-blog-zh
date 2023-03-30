# 在生产中在 Kubernetes 上部署 Jaeger 的最佳实践

> 原文：<https://thenewstack.io/best-practices-for-deploying-jaeger-on-kubernetes-in-production/>

[](https://www.linkedin.com/in/horovits/?originalSubdomain=il)

[Dotan horo vits](https://www.linkedin.com/in/horovits/?originalSubdomain=il)

[Dotan 生活在技术、产品和创新的交汇点。作为一名软件开发人员、解决方案架构师和产品经理，他在高科技行业工作了 20 多年，带来了云计算、大数据解决方案、DevOps 实践等方面的丰富知识。Dotan 是开源软件、开放标准和社区的狂热拥护者。Dotan 目前在 Logz.io 担任开发人员倡导者，在 Logz.io 宣传 IT 系统中的可观测性，使用流行的开源项目和标准，如 ELK stack、Grafana、Jaeger 和 OpenTelemetry。](https://www.linkedin.com/in/horovits/?originalSubdomain=il)

[](https://www.linkedin.com/in/horovits/?originalSubdomain=il)[](https://www.linkedin.com/in/horovits/?originalSubdomain=il)

日志、度量和踪迹是可观测性世界的三大支柱。特别是分布式追踪世界，最近几个月出现了很多创新，OpenTelemetry 标准化，Jaeger 开源项目从云本地计算基金会孵化中毕业。根据最近的 DevOps Pulse 报告，超过 30%的分布式追踪实践者使用 Jaeger。许多公司意识到需要分布式跟踪来获得对系统更好的可观察性，并解决性能问题，特别是在处理复杂的微服务架构时。

从 Jaeger 开始，第一步是编写代码向 Jaeger 发送跟踪信息。第二部分是设置 Jaeger 后端来收集、处理和可视化你的痕迹。在这篇文章中，我将回顾在生产中部署和管理 Jaeger 后端需要做些什么。我将介绍:

*   用于安装的耶格组件
*   Jaeger 使用的非 Jaeger 组件，如后端存储
*   Jaeger 部署策略，特别是围绕生产系统
*   代理与无代理
*   代理安装方法:sidecar vs. DaemonSet
*   安装工具:手册、操作员、舵图

## 耶格组件

部署 Jaeger 跟踪时，您需要处理以下组件:

*   代理是与您的应用程序位于同一位置的组件，用于在本地收集 Jaeger 跟踪数据。它处理收集器的连接和流量控制(见下文)以及数据丰富。
*   Collector 是一个集中的集线器，从环境中的各种代理收集跟踪信息，并发送给后端存储。收集器可以在跨度上运行验证和丰富。
*   Query 检索跟踪并通过 UI 提供它们。

关于每个组件和其他可选的 Jaeger 组件，显然有更多的细节，但为了讨论的方便，我将保持简单。让我们看看如何在各种设置和策略中部署代理、收集器和查询组件。

## Jaeger 使用的外部组件

根据您的部署策略(见下文)，Jaeger 可能会使用其他(非 Jaeger)组件，主要是持久性后端存储(Elasticsearch、Cassandra 或其他)和流式摄取队列(Kafka)。这些服务通常是独立部署的，你只需要将 Jaeger 指向相关的端点，尽管你也可以让 Jaeger 自行配置它们。这是一个广泛的话题，我计划在另一篇文章中讨论，所以请继续关注。

## 部署策略

您可能希望在许多不同的系统上部署 Jaeger，从您自己的用于开发目的的笔记本电脑到大规模、高负载的生产环境。以下是您可以使用的一些有用的部署策略:

*   **Jaegertracing All-in-One:** 这是一个易于部署的设置，适合试用产品、开发和演示使用。您可以将它作为预打包的二进制文件或 Docker 映像来运行。它将所有服务和内存存储打包并部署在一个副本中。
*   **生产:**关注生产环境对高可用性和可伸缩性的需求。它独立部署每个后端服务，并支持多个副本和扩展选项。它还使用持久的后端存储来保持跟踪数据的弹性。它目前支持 Elasticsearch 和 Cassandra 存储解决方案，Elasticsearch 是生产环境的推荐解决方案。
*   **流:**对于高负载环境，该设置将 Kafka 添加到生产部署策略中，以减轻后端存储的压力。如果需要对跟踪运行后处理逻辑，那么在写入存储之前执行会更容易。

一体式设置易于启动，并附带一个可执行包。如果你想开始尝试，看看这个教程如何与 Elasticsearch 后端以及 Kibana 结合使用，你可以用它来实现额外的可视化。

在这篇文章的其余部分，我将集中讨论生产部署以及这个过程中涉及的考虑事项和选项。

## 耶格可以无代理运行吗？

代理需要驻留在应用程序的任何实例中。如果您运行一个复杂的微服务架构，需要多个代理，您可能会想知道是否可以避开代理。简单的回答是——不要无代理。

更长的答案是，从技术上讲，您可以让 Jaeger 客户端库将跨度数据直接发送到收集器，但是您需要自己处理各个方面，例如收集器的查找、流量控制以及使用基于本地系统信息的附加元数据标记跨度。

虽然使用 Jaeger 代理是推荐的部署方式，但有些情况下您无法部署代理。例如，如果您的应用程序作为 AWS lambda 函数或类似的无服务器框架运行，而您无法控制 pod 部署和代理协同定位。如果使用 Zipkin instrumentation，代理也将无效。在这种情况下，跨度应直接提交给 Jaeger 收藏家。

## 耶格代理安装方法

代理需要与您的应用程序驻留在一起，以便 Jaeger 客户端库可以在本地主机上访问它，并通过 UDP 向它发送数据，而没有由于网络中断而丢失数据的风险(与 TCP 不同，UDP 传输协议不包括数据丢失保护，因此更快、更经济)。

在 Kubernetes 环境中实现协同定位的方法有两种，一种是作为 sidecar，另一种是作为 DaemonSet。让我们看看选项:

### 作为恶魔的耶格特工

将代理作为 DaemonSet 安装是最简单、最经济的选择。这将在节点上提供一个代理实例，为该节点上的所有单元提供服务。

然而，对于涉及多租户、安全隔离要求或针对不同应用程序的多个 Jaeger 实例的生产环境来说，这种策略可能过于简单。如果这是你的情况，考虑部署为边车(如下)。

### 耶格代理作为边车

sidecar 选项意味着代理将作为每个 pod 的附加容器运行。这种设置可以支持多租户环境，其中每个租户都有其各自的 Jaeger 收集器，并且每个代理都可以配置为发送到其相关的收集器。您还可以获得对内存分配的更多控制，这可以防止特定租户的蚕食。在同一个 pod 中运行时，安全配置也更简单。边车方法自然会带来额外集装箱的开销。一些安装工具可以自动注入代理 sidecar 和简化管理。

## Jaeger 的安装工具

现在我们已经知道了应该部署哪些组件以及策略，让我们看看哪些工具可以帮助我们将这个计划付诸实施:

*   **手动使用 kubectl:** 如果你需要快速入门，又不想麻烦自动化，那么这个可能适合你。对于生产部署，不建议这样做。这是 Jaeger 社区支持的官方方式，在[这个报告](https://github.com/jaegertracing/jaeger-kubernetes)中提供了策划的 YAML 模板。不过最近(2020 年 5 月)已经不赞成了。手动执行的另一个选项是使用 Jaeger Operator 生成一个静态清单文件:运行`jaeger-operator generate`生成 YAML，然后`kubectl apply`手动将其应用到您的环境中。这是目前 Jaeger Operator 的一个实验性功能，慎用。
*   **Kubernetes Operator:**Jaeger Operator 为 Kubernetes 实现了流行的 Operator 模式，因此您可以让一个指定的控制器将您的 Jaeger 后端作为定制资源进行管理。默认情况下，它会将 Jaeger 代理部署为边车。如果您在集群中运行控制器作为部署，那么 Jaeger 操作员也可以自动注入 Jaeger 代理程序，这样您就无需在规范中手动定义它。您还可以将代理策略设置为 DaemonSet。需要注意的一点是，在使用基于 gRPC 插件的外部持久存储时，Jaeger Operator 似乎有所欠缺。如果这是你的情况，你可能更喜欢使用头盔。查看 [Jaeger 操作员报告](https://github.com/jaegertracing/jaeger-operator)了解全部细节。
*   **Helm Chart:** 该选项具有完整软件包管理器的优势，如果您使用 Helm 来管理生产环境中的其他应用程序(如 Jaeger 使用的持久存储)，那么它将是您的自然选择。你可以在[这个回购](https://github.com/jaegertracing/helm-charts)中找到官方的 Jaeger 图表，但是注意，它仍然被声明为 beta。默认情况下，该图表将安装一个 Jaeger 代理作为 DaemonSet。注意，你也可以使用 Helm 来安装 Jaeger Operator(见图表[此处](https://github.com/jaegertracing/helm-charts/tree/master/charts/jaeger-operator))。

## 使用 Jaeger Tracing 摄取 Zipkin 痕迹

到目前为止，我们已经讨论了杰格跨度摄取。但是有相当多的系统使用了 Zipkin 工具，所以值得注意的是 Jaeger 也可以接受 Zipkin 格式的跨度，即 Thrift、JSON v1/v2 和 Protobuf。

如果您的 Jaeger 后端部署意味着接收 Zipkin 协议:

*   Jaeger 代理与收集 Zipkin 跨度无关。
*   您的 Zipkin 仪器应该将 Zipkin 跨度直接运送到 Jaeger 收集器。Zipkin spans 可以通过 POST 请求提交到以下 RESTful 端点:
    *   `/api/v1/spans`针对 Zipkin JSON v1 或 Zipkin Thrift 格式
    *   `/api/v2/spans`针对 Zipkin JSON v2
*   Jaeger Collector 应该配置为在指定的 HTTP 端口上接收 Zipkin spans，并带有标志`--collector.zipkin.http-port=9411`(端口 9411 由 Zipkin collectors 使用)。

## 尾注

Jaeger 是一个相当年轻的项目，诞生于 Kubernetes 领域，有一个强大的社区提供 Kubernetes 部署最佳实践和自动化。然而，作为一个年轻的项目，在生产中管理它的最佳实践仍在形成中，在赶上社区更新的同时，以适合您的组织的方式在生产中运行它需要一些仔细的考虑。我们在 [Logz.io](https://logz.io/tracing-request-beta/) 提供 Jaeger 作为 SaaS，就像我们使用 ELK Stack 作为日志并使用开源 Grafana 作为度量一样，因此您可以采用领先的开源可观测性项目，而不必亲自操作它。我们为 Jaeger 推出的 beta 服务即将推出，敬请期待。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>