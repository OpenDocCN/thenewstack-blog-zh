# 红帽为 OpenShift 创建服务网格

> 原文：<https://thenewstack.io/red-hat-creates-service-mesh-for-openshift/>

红帽正在为其混合云企业 Kubernetes 平台 [OpenShift 版本 4](https://www.openshift.com/) 推出自己的服务网格。

商业产品包 [Istio](https://thenewstack.io/googles-eric-brewer-on-why-envoy-and-istio-are-the-future-of-networking/) ，该领域的新兴领导者，以及用于追踪的 [Jaeger](https://www.jaegertracing.io/) 项目，以及用于监测和管理 Istio 的 [Kiali](https://www.kiali.io/) 。

一个[服务网格](https://nam02.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.redhat.com%2Fen%2Ftopics%2Fmicroservices%2Fwhat-is-a-service-mesh&data=02%7C01%7C%7C716f3900123d4a55205208d724edd057%7C84df9e7fe9f640afb435aaaaaaaaaaaa%7C1%7C0%7C637018476125550701&sdata=eLfOmdYCI%2BEvI8XNOSz4qPdzBDGV77y1oHQwW5Qaefw%3D&reserved=0)通常作为基于微服务的应用架构的服务之间的通信层作为边车运行。它处理流量管理、策略执行以及服务身份和安全性。

“我们采用了上游的 Istio，并编写了一个操作符来处理 Istio 本身的部署和管理。Red Hat 的首席产品经理 Brian "Redbeard" Harrington 解释道:“对于上游版本，你必须以更高的特权级别运行所有的 sidecar 容器，这相当于以根用户的身份运行程序。

“open shift Service Mesh[，通过操作员和我们编写的 CNI(集装箱网络接口)插件，您可以运行 Istio 并调出那些边车组件，而无需为 Istio 本身的应用程序组件提供额外的权限，”他补充道。](https://www.openshift.com/learn/topics/service-mesh)

其特点包括:

*   **跟踪和测量:**使用 Jaeger，开发人员可以从头到尾跟踪服务之间的请求。
*   **可视化和可观察性:** Kiali 使用户能够查看服务网格的拓扑结构，并观察服务如何交互。
*   **集成 API 网关:**与 Red Hat 3Scale 一起部署时，简化应用程序端点和服务后端之间的南北流量。
*   **“一键式”服务网格安装和配置**通过服务网格运营商和运营商生命周期管理框架。

哈灵顿说，该公司创建了自己的版本，主要是为了使部署更容易，但它也比上游组件提供了更多的见解(即，对典型的配置设置做出更多的假设)。

“我们在早期测试中发现，对于将要安装 Istio 的用户来说，一旦他们开始将应用程序部署到 Istio，由于 sidecars 和应用程序组件可以部署在几十个不同的节点上，习惯于使用传统 Java 堆栈和内置调试工具的用户能够查看单个应用程序服务器，当它运行在 Kubernetes 或服务网格上时，就具有相同的可见性，”他说。

“因此，这就是为什么我们固执地选择将 Jaeger 与 Istio 集成，这样用户就不必在部署服务网格的两周内了解到他们需要更多组件，然后不得不将其拆除并重做，”他说。

他说，因为它协调所有这些组件的安装，所以它可以同时将它们设置在一起，并知道它们将被正确配置。

他说:“我们希望确保用户在安装软件后就可以随时使用，而不是像开始使用软件一样，必须了解每个开源项目的所有细微差别。”。

Red Hat 在过去的一年里一直致力于服务网格。它与运营商的合作包括将更新作为服务自动下推到所有组件的能力。

“我们希望确保这一点，因为 OpenShift 可以在任何云平台上运行，当你部署服务网格时，它可以跨计算环境移植，所以你可以决定你想在内部运行它，或者你可以决定你想在 AWS 上运行它，”他说。

他发现 Kiali 是更有趣的组成部分之一。

“特别是对于那些不知道自己不知道什么的用户来说，给他们一个图形用户界面，他们可以可视化他们在 Service Mesh 中运行的所有应用程序，看到这些应用程序之间的连接，知道哪些部分试图相互通信，因此他们可以更好地控制这些应用程序之间的通信，”他说，并补充说，Kiali 推动了许多围绕设计的决策。

针对 OpenShift 带来一切和厨房水槽的批评，OpenShift 第 4 版的工作包括对其进行一点分解，使用户能够只引入他们想要的组件。他说，提供更大的灵活性是 OpenShift 的发展方向。

红帽是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>