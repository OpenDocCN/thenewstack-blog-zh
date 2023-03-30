# 在争议中，无服务器软件保持增长

> 原文：<https://thenewstack.io/amidst-controversy-the-knative-serverless-software-keeps-growing/>

上周，Knative 宣布短期内不会捐赠给基金会，这让很多人感到失望。

[Google Cloud Run 的产品经理、](https://www.linkedin.com/in/donnamalayeri) [Knative](https://github.com/knative) 指导委员会的成员唐娜·马拉耶里写道，它的未来将由指导委员会决定，它将发布项目成员如何在团队中获得领导职位的信息。

几周前，分析师兼 TNS 定期撰稿人[贾纳基拉姆·MSV](https://twitter.com/janakiramm/status/1177209662103404544)提出“Knative 有潜力成为 k8s 首选的无服务器平台”，并询问它应该如何发展。

对他的推文的回应显然倾向于一个有[云本地计算基金会](https://www.cncf.io/)的家，也是 Kubernetes 的家。

### 无服务器标准

谷歌[于 2018 年 7 月发布了 Knative](https://thenewstack.io/with-knative-google-brings-multicloud-serverless-to-the-enterprise/) ，作为组织和服务提供商建立无服务器基础设施的一种方式，该基础设施可以跨多个公共云或内部运行相同的容器化代码，只需最少的定制。

谷歌云产品管理总监柳文欢·泰奇当时说:“Knative 的整个要点是将无服务器的构建模块整合在一起，并为您提供这种工作负载可移植性。”。

Pivotal、IBM、Red Hat 和 SAP 也为该项目做出了贡献。

客博主 Twain Taylor 在最近的一篇帖子中写道，Knative 的主要动机是为无服务器计算定义[供应商无关的标准](https://thenewstack.io/how-knative-can-unite-kubernetes-and-serverless/)。

它建立在 Kubernetes 编排引擎和 Istio T21 服务网之上。Knative 和 Istio 都是在 Apache License 2.0 下开源的。

[T2 Pivotal 的技术营销总监 Dan Baskette](https://twitter.com/dbbaskette?lang=en) 发了一篇帖子解释 Knative 的技术细节。

在一次采访中，Teich 将 Knative 描述为一组在 Kubernetes 上运行应用程序的组件。

“[有]一批客户拥有 Kubernetes 集群，原因有很多……但他们想要无服务器平台提供的开发者体验，”他说。“如果我有一个响应 HTTP 的无状态容器，我如何启动并运行它？

我如何衡量它？我如何向 it 部门交付事件？我该如何构建它？我怎样才能让开发人员从第一天开始就体验到尽可能简单？"

Knative 由两个松散耦合的组件组成:

*   **服务**提供了轻松运行应用/功能并对其进行扩展的能力。它负责让您的容器运行，并处理从入口、流量分割、部署修订等所有事情。

“它还引入了一些不错的零标度组件。我并不是说 Kubernetes 集群本身的规模为零。如果你正在运行一个响应 HTTP 的服务，在 Kubernetes 的土地上，传统上你必须让它一直运行。你可以缩放到 1。这可以一直扩展到零…它使您能够运行非常大量的轻量级无服务器工作负载，而不会在 Kubernetes 上造成资源紧张，并提供出色的开发人员体验，”他说。

Knative 的服务部分很快就会升级到 1.0 版本。

*   **事件**允许应用程序/功能发布和订阅事件流，如 Google Cloud Pub/Sub 和 Apache Kafka。它提供了处理事件的所有基础设施——与第三方系统集成，将事件交付到您的应用程序中，并连接控制平面 API。

Teich 说，这是两者中不太成熟的，将是未来工作的重点。

最初，第三个组件，称为 **Build** ，是项目的一部分，但是现在已经“毕业”了，现在是持续集成/持续交付(CI/CD)项目 [Tekton](https://www.ibm.com/cloud/blog/knative-v07-tekton-and-ibm-cloud-kubernetes-service-oh-my) 的一部分，称为 [Tasks](https://github.com/tektoncd/pipeline/blob/master/docs/tasks.md) 。它为从源代码构建容器提供了一个可插拔的模型。

### SAP 的扩展框架

当谷歌在构建 Knative 时，许多其他项目也在解决同样的问题，包括 [OpenFAAS](https://github.com/openfaas/faas) 、 [riff](https://projectriff.io/) 等等。

“当我们在这个领域起步时，有很多不同的项目。我们数了一下，有十几个。当我们与客户交谈时，他们想要便携性，他们不想被束缚，他们想要功能，其中一些是非常特殊的用途，”他说。

在建造 Knative 的过程中，这个空间中的一些玩家在 Knative 之上重新搭建了平台。

SAP 就是其中之一。

2017 年底，由于需要在其商业云领域提供快速创新，它开始建立一个新的并行扩展框架，该框架将在所有产品线中运行。

“我们 100%确定我们需要一个无服务器架构作为它的基础，而 Kubernetes 和 Istio 的结合在当时似乎是这个的逻辑基础。SAP C/4HANA Core 首席架构师 [Krasimir Semerdzhiev](https://twitter.com/evilyeti?lang=en) 说:“我们不知道与此同时，Knative 也在谷歌闭门造车。

“在我们的开发过程中，一个又一个 sprint，我们不断增强构建无服务器功能的体验。我们从 Kubernetes 上围绕容器网络的复杂性中抽象出来，通过利用 Istio 来处理所有需要的传输加密和安全性。事件是我们故事的核心部分，因为我们设想业务事件是我们许多扩展场景中的触发器。”

它在 2018 年早春推出了 alpha 产品，以选择合作伙伴，获得积极评价。该团队在哥本哈根 KubeCon Europe 之前第一次了解到 Knative，在一次介绍电话后，很快意识到未来合作的潜力。

“在双方看来，我们已经确定并解决了一个非常相似的问题领域。Google 从构建和运行应用程序的角度着手，特别关注生命周期管理(构建、部署、流量管理)。在 SAP 方面，我们自然更加重视与业务应用的连接、来自多家供应商的标准化服务消费，以及重用已经定义的功能来构建更高级别的执行流程，”Semerdzhiev 说。

他们发现这两个项目是互补的，SAP 决定重新调整其 [Kyma](https://kyma-project.io/) 开源计划，在 Knative 上运行。在 Google Cloud Next 上，两者都被宣布为无服务器会议的一部分。

“一年半之后，我们已经取得了长足的进步。我们已经为 Knative 以及其他几个相关项目(AsyncAPI、Istio 等)做出了一些贡献(NATS 流媒体频道实现、小的修复)。)”他说。

“我们相信 Knative 对于无服务器来说就像 Kubernetes 对于容器部署和编排一样。…展望未来，我们看到 Kyma 的成功与 Knative 的成功密切相关。两者都在许多公司的并行可扩展性战略中发挥着至关重要的作用，超越了 SAP 本身。”

### 成长中的生态系统

Project Kyma 是一个并行扩展框架，SAP 设想将它放在云和内部部署的企业应用程序旁边。它使开发人员能够跨多个企业应用程序对事件做出反应，并开发轻量级 lambda 函数。

40 多年来，SAP 一直在企业软件市场开发产品，其中许多产品都是为客户量身定制的。

Semerdzhiev 说:“在多个产品中存在大量定制代码，这对于商业应用的升级、补丁和进一步发展来说是一个相当大的障碍。“这就是我们将 project Kyma 作为并行可扩展性框架的原因，它可以放在任何产品旁边，使客户和合作伙伴能够按照自己的速度和时间表进行创新，规划他们的数字化和向云产品的扩展。”

谷歌也在 Knative 上建立了自己的云运行服务。它是一个托管平台，采用 Docker 容器映像，并将其作为无状态、自动扩展的 HTTP 服务运行。它允许您运行服务于多个端点的任意应用程序，而不是具有特定接口的小功能。

生态系统继续增长。IBM [在二月份启动了对 Knative 的支持，作为其托管的 Kubernetes 服务的一部分。](https://www.ibm.com/blogs/bluemix/2019/02/announcing-managed-knative-on-ibm-cloud-kubernetes-service-experimental/)[其新的开源项目之一](https://devclass.com/2019/07/16/ibm-unveils-trio-of-open-source-kubernetes-projects-and-not-a-red-hat-trick-in-sight/)[Appsody](https://appsody.dev/)，使用针对 Kubernetes 和 Knative 部署的预配置堆栈和模板，帮助开发人员快速创建符合其组织标准和要求的微服务。

今年 5 月，红帽发布了 Knative 的[开发者预览版](https://thenewstack.io/red-hats-openshift-4-adds-knative-key-coreos-features/)，作为 OpenShift 4 的一部分。

云计算原生计算基金会、Pivotal 和 Red Hat 是新堆栈的赞助商。

专题图片:[安德鲁·古斯特](https://www.flickr.com/photos/andrewgustar/)的《多米诺骨牌》。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>