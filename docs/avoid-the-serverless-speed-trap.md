# 避免无服务器速度陷阱

> 原文：<https://thenewstack.io/avoid-the-serverless-speed-trap/>

[](https://www.linkedin.com/in/markrhinkle/)

 [马克·辛克尔

Mark 在新兴技术和开源领域有着悠久的历史。在共同创立 TriggerMesh 之前，他是 Node.js 基金会的执行董事，也是 Citrix、Cloud.com 和 Zenoss 的高管，在那里他领导了他们的开源工作。](https://www.linkedin.com/in/markrhinkle/) [](https://www.linkedin.com/in/markrhinkle/)

不到五年前，无服务器计算已经成熟，并以惊人的速度被采用。亚马逊网络服务公司(AWS)最初提供单一的无服务器服务，现在已经覆盖了几十个竞争平台和两种主要方法:功能即服务(FaaS)和基于容器。可以肯定的是，无服务器现在已经超越了功能，并且已经成熟为云原生架构模式。出于这个原因，我们更喜欢用有服务的*而不是无服务的*。

越来越多的选择——就提供者和方法而言——与无服务器固有的抽象性相结合，为企业架构师带来了希望和风险。

众所周知，随着企业使用无服务器将事件驱动架构(EDA)扩展到更多系统，这一承诺将带来更低的成本、更高的敏捷性和更强的客户响应能力。

虽然每个人都喜欢谈论承诺，但很少有人讨论风险。随着现代化和向云迁移的压力越来越大，一个有时被忽视的风险是将非标准和/或理解不充分的云技术置于企业架构的中心，我们可以称之为速度陷阱。我们认为像 Kubernetes 这样的开源方法，以及它的无服务器分支 Knative，可以成为企业架构师管理这种风险的关键盟友。

了解支持多云 EDAs(事件驱动架构)的公共基础的架构师可以做出更明智、更灵活的选择。为了说明这一点，让我们看看来自两个非常不同的平台公司的基于 Knative 的托管无服务器产品:Google 和 SAP。

## 用于 Anthos 的谷歌云运行

[Google Anthos](https://cloud.google.com/anthos/) 是一个应用管理平台，为云和内部环境提供一致的开发和运营体验。

Google Cloud Run for Anthos 是其无服务器产品，允许您在完全托管的无服务器平台上开发和部署高度可扩展的容器化应用程序。Cloud Run 基于 Knative，这意味着 API 规范是一个标准的 Kubernetes 定制资源。这一点很重要，因为这意味着您为构建系统所做的设计工作可以高度移植到任何其他基于 Kubernetes 的平台上。

Anthos 的云运行为事件驱动架构(EDA)奠定了坚实的基础。Cloud Run for Anthos 提供了对许多 Google sources、Pub/Sub、Cloud Scheduler 和自定义事件的支持。当与 [TriggerMesh](https://triggermesh.com/?utm_content=inline-mention) 结合使用时，您可以从任何地方的事件中触发云运行无服务器工作负载，甚至是本地传统应用。

## SAP 云平台，Kyma 运行时

SAP 进入无服务器游戏的地方与谷歌截然不同，但却拥有相似的技术。谷歌首先吸引的是新应用程序的开发者，而 SAP 当然拥有大量复杂的内部企业应用程序。SAP 的主要目标是确保这些客户能够通过无服务器和事件驱动的功能经济高效地更新这些应用。

[Kyma](https://kyma-project.io/) 允许您通过使用微服务和无服务器功能来构建扩展，因此开发人员可以扩展 SAP 解决方案，也可以结合现有的 IT 解决方案来创建新的功能。像 Cloud Run for Anthos 一样，Knative 锚定了 Kyma 的无服务器功能。Knative 支持这两种用例的无服务器需求的能力证明了它的多功能性。

## 采用 Knative 101 的多云 EDA

开源和开放标准消除了平台选择的风险，这不仅是因为它们为您提供了更好的应用程序可移植性。它们还降低了重新学习的需求，因此不仅是应用程序变得可移植，而且团队的知识也变得可移植。

考虑到这一点，[我们在 1 月 12 日](https://www.triggermesh.com/resources/webinar-recording-event-driven-architecture-with-knative-google-anthos-and-triggermesh)举办了一场免费的网络研讨会，让架构师们实际动手看看 Kubernetes 和 Knative 如何提供一个通用的底层来连接运行在任何地方的应用。名为“Knative、Google Cloud Run for Anthos 和 TriggerMesh 的事件驱动架构”的网络研讨会通过查看 Knative 事件在 Google Cloud Run for Anthos 中的工作方式，介绍了 Knative 事件。[在录制的](https://www.triggermesh.com/resources/webinar-recording-event-driven-architecture-with-knative-google-anthos-and-triggermesh)中，你将发现你和你的团队如何在多个基于 Kubernetes 的环境中使用相同的技术、模型，甚至在很多情况下使用完全相同的 YAML。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>