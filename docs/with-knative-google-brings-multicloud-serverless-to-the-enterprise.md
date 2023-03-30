# 通过 Knative，Google 为企业带来了无服务器的多云

> 原文：<https://thenewstack.io/with-knative-google-brings-multicloud-serverless-to-the-enterprise/>

谷歌希望让无服务器计算变得足够简单，甚至连企业都可以使用。本周，该公司公开发布了一个名为 [Knative](https://cloud.google.com/knative/) 的新项目，旨在让组织和服务提供商建立一个无服务器的基础设施，可以在多个公共云和内部运行相同的容器化代码，只需开发者做最少的改动。

“Knative 的全部目的是将无服务器的构建模块整合在一起，并为您提供这种工作负载可移植性，”谷歌云产品管理总监[柳文欢·泰奇](https://twitter.com/teich)在本周于三藩市举行的 [Google Next 2018](https://cloud.withgoogle.com/next18/sf/) 上介绍这项技术时说。

Knative 建立在 Kubernetes 编排引擎和 Istio 服务网格的基础上，尽管开发人员不需要理解其中任何一个的复杂性就能享受到好处。“Knative 不是为最终用户设计的。它是为基础设施而设计的，使产品能够建立在它的基础上，”Teich 告诉观众。该软件抽象出了在云原生环境中准备和运行应用的所有步骤，包括容器构建流程、编排、路由和流量管理、负载平衡和自动扩展以及服务绑定。

Knative 有三个不同的组件处理以下任务:[自动化容器构建](https://github.com/knative/build)、[容器服务](https://github.com/knative/serving)和[事件绑定](https://github.com/knative/eventing)。构建服务利用 Kubernetes 原语从源代码运行集群上的容器构建。服务组件提供中间件来快速部署容器、根据需求扩展容器、路由和获取已部署代码和配置的时间点快照。

[![](img/2e8b2dedc1ac5d4603984379c6e67ce4.png)](https://github.com/knative/docs/)

"最终，我们的目标是让这个无服务器的世界团结起来."泰奇说。“我们希望以一种兼容、可移植的方式，推出一整套无服务器产品的生态系统。”

为此，SAP、IBM、Red Hat 和 Pivotal 等都为此项目做出了贡献。SAP [计划使用 Knative](https://blogs.sap.com/2018/07/24/sap-cloud-platform-an-open-enterprise-platform-with-a-cloud-native-core/) 来简化其开发者的开发过程，让他们只需担心他们正在制作的代码。使用 KNative 的早期私有测试版，SAP 构建了一个轻量级框架，名为 [Kyma](https://github.com/kyma-project) ，用于将 SAP 的商务组合扩展到云原生环境。

红帽[计划将](https://blog.openshift.com/state-of-serverless-in-kubernetes-knative-and-openshift-cloud-functions/) Knative 与其 OpenShift 商业 Kubernetes 发行版和[自有运营商框架](https://thenewstack.io/coreos-says-red-hat-will-help-introduce-openshift-to-operators/)相结合，提供一个具有自动化操作的多云容器平台。Pivotal 正在[将 Knative](https://content.pivotal.io/blog/knative-powerful-building-blocks-for-a-portable-function-platform) 整合到其即将推出的 [Pivotal 函数服务](https://pivotal.io/platform/pivotal-function-service)中，该公司的 Riff 软件为构建事件驱动函数提供了一些帮助。

“Knative 可能有一天会让开发人员使用 Apache OpenWhisk 以无服务器的方式编排云应用的所有部分，例如运行容器和功能即服务事件，所有这些都是按需和按需的，”IBM 研究员兼 IBM 云副总裁[Jason McGee](https://www.ibm.com/blogs/cloud-computing/2018/07/24/ibm-cloud-google-knative-serverless/)在一篇关于 Knative 如何与 IBM 自己的功能即服务软件[open whish](https://thenewstack.io/ibms-openwhisk-serverless/)对接的博客文章中写道。“这可能会极大地扩展 OpenWhisk 等无服务器工具的使用范围，超越功能，成为生产中全面应用的完整基础。”

谷歌最初开发这个想法是为了给谷歌应用引擎和谷歌云功能(GCF)提供无服务器容器服务。按照 Google 规范的定义，这些容器不写入本地磁盘，完全按照请求-响应模式工作。

该公司在 GCF 上预览了一个新的服务无服务器容器，它将运行任何符合规范的容器。现在，除了接收代码，GCF 还可以接收容器并执行它们。这项服务将于今年晚些时候推出，但对 alpha 测试者开放。

“我们意识到，容器不仅仅是包装格式，也是交换格式，”Teich 说。Teich 用开源 Blender 3D 渲染包的容器化版本向[演示了如何使用服务](https://youtu.be/iPQUdb0kssE)。

随着 [GKE 本地](https://cloud.google.com/gke-on-prem/)的发布，也是谷歌 Next 2018 的首映，是一个可以在内部运行的 GKE 分发版。它包括一个基于 Knative 的无服务器插件，允许一个为 GCF 封装的应用程序在内部运行，消除了消除重复代码的需要。

[https://www.youtube.com/embed/iPQUdb0kssE?feature=oembed](https://www.youtube.com/embed/iPQUdb0kssE?feature=oembed)

视频

谷歌、Pivotal 和 Red Hat 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>