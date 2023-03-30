# cloud flow:Kubernetes 上的流数据管道框架

> 原文：<https://thenewstack.io/cloudflow-a-framework-for-streaming-data-pipelines-on-kubernetes/>

Portworx 赞助了 New Stack 在圣地亚哥的 KubeCon + CloudNativeCon 的报道。

创造 Scala 编程语言和 Akka 中间件的公司 [Lightbend](https://www.lightbend.com/) 已经发布了 [Cloudflow](https://cloudflow.io/) ，这是一个开源框架，使得在 Kubernetes 上开发和部署流媒体数据管道更加容易。

此次发布是本周 [KubeCon + CloudNativeCon 北美 2019](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 发布的一系列 Kubernetes 新闻的一部分。

[Cloudflow](https://github.com/lightbend/cloudflow) 提供了一个特定于流数据的框架，该框架简化了流技术的安装和集成，提供了一个用于在微服务架构中创建流数据管道的编程模型，并针对 Kubernetes 堆栈上的部署进行了优化。

[light bend](https://twitter.com/mabrewer7)的首席执行官马克·布鲁尔表示:“围绕人工智能和训练机器学习模型的最有趣的新机会给开发人员带来了很大的压力，他们需要将流数据纳入新的应用程序，并在生产后对这些数据的不间断流动进行预测。

他说，当用户使用多个流媒体引擎，如 Spark、Akka Streams 和 Apache Flink 时，复杂性就出现了。

“你知道，这些技术被广泛采用，开发人员很容易上手。但一旦你开始把它们连在一起，事情就会变得复杂得多，”他说。

“Cloudflow 就是要实现这一点，也就是设置这些东西、让它们彼此互操作并处理持续不断的数据流的挑战。”

他列举了使用 Spark 和 Akka 等技术的客户:Capitol One 使用数据流来确定提供汽车贷款的风险；挪威邮轮公司在其船上乘客应用程序上提供个性化服务；和迪士尼，为其新的流媒体服务做推荐。

“所有这一切最困难的部分不仅仅是设置它并让它运行，而是让它在大小可变的集群上保持运行。…只要有新内容，你就会看到需求激增。这个系统需要适当地扩大规模。然后，当然，缩小规模。这是 Cloudflow 为运营商和开发者节省大量时间的一部分，”他说。

### 模式优先

Cloudflow 帮助开发者为每个处理阶段选择合适的流媒体引擎，如 Akka、Spark 和 Flink 只关注核心业务逻辑；并消除构建样板文件的负担。Cloudflow 处理数据持久性、序列化和阶段之间的连接。

[NetApp](https://www.linkedin.com/in/merzdba/)的首席技术专家 Chris Merz 之前指出，管理云原生应用状态的[最近已经落到了开发人员的肩上，而不是运营团队。](/the-state-of-state-in-cloud-native-applications/)

在部署中，Cloudflow 使运营商能够通过简单的蓝图文件管理数据流，并通过一个命令部署多级管道。它为您配置阶段之间的所有连接，并可以自动显示 HTTP 服务端点。

使用 Cloudflow，您可以轻松地将您的流应用程序分解成小的可组合组件，并用基于模式的契约将它们连接在一起。

小的流处理单元称为细流，每个细流代表应用程序逻辑的一个独立阶段。数据流被划分以允许并行处理。可以使用蓝图将细流合并到更大的系统中，蓝图指定细流如何形成拓扑。

Cloudflow 采用模式优先的方法来构建流数据管道，以一个 [Avro](http://avro.apache.org/docs/current/spec.html) 模式作为起点。

通过在 [sbt](https://www.scala-sbt.org/index.html) 项目中定义设置，您可以选择用什么编程语言来生成它们的模式。

细流暴露一个或多个入口和出口，所有这些都由模式驱动，以确保数据流始终一致，并且连接是兼容的。细流之间发送的数据保存在底层发布-订阅系统中，允许对不同组件进行独立的生命周期管理。

应用程序是作为一个整体部署的。Cloudflow 负责部署单个细流，并且数据在连接之间适当地流动。细流可以放大和缩小，以满足应用程序的负载要求。

Cloudflow 应用开发工具包提供:

*   小数据流的 API 定义。
*   流行的流运行时的一组可扩展的运行时实现，如 Spark 的结构化流、Flink 和 Akka。
*   蓝图定义驱动的细流合成模型。
*   用于测试应用程序的沙盒执行模式。
*   一组 sbt 插件，用于将应用程序打包到可部署的容器中。
*   Cloudflow operator，一个管理 Kubernetes 上的应用程序生命周期的 Kubernetes 操作员。
*   一个命令行界面——一个用于手动和脚本化管理应用程序的 kubectl 插件。

今年早些时候，新的 Stack 和 Lightbend】合作进行了一项调查，旨在了解实时数据的驱动因素，以及在流数据基础设施上开发和管理应用程序的障碍。你可以在这里找到完整的 [2019 年流媒体数据调查](https://www.lightbend.com/white-papers-and-reports/survey-streaming-data-future-tech-stack)结果。新堆栈分析师 Lawrence Hecht 在[新堆栈环境](https://thenewstack.io/context-the-future-of-data-is-in-streaming/)播客中讨论了结果。

[数据的未来在于流式传输](https://thenewstack.simplecast.com/episodes/the-future-of-data-is-in-streaming)

[KubeCon + CloudNativeCon 北美 2019](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 和 NetApp 是新堆栈的赞助商。

图片由来自 Pixabay 的 Johannes Plenio 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>