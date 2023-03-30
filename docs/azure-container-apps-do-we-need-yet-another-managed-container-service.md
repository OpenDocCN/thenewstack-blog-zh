# Azure 容器应用:我们还需要另一个托管容器服务吗？

> 原文：<https://thenewstack.io/azure-container-apps-do-we-need-yet-another-managed-container-service/>

在本月早些时候的 [Ignite 2021](https://myignite.microsoft.com/home) 大会上，微软[宣布了](https://techcommunity.microsoft.com/t5/apps-on-azure/introducing-azure-container-apps-a-serverless-container-service/ba-p/2867265)一个名为 [Azure Container Apps](https://aka.ms/containerapps) 的新[无服务器](https://thenewstack.io/category/serverless/)容器平台的公开预览。Azure compute service 的最新成员加入了其他基于容器的产品，如 [Azure App Services](https://azure.microsoft.com/en-gb/services/app-service/containers/) 、 [Azure Kubernetes Service](https://azure.microsoft.com/en-gb/services/kubernetes-service/) 、 [Azure functions](https://azure.microsoft.com/en-gb/services/functions/) 和[Azure Container Instances](https://azure.microsoft.com/en-gb/services/container-instances/)。

微软将 Azure Container Apps 定位为 AKS 的平台即服务(PaaS)层。它带来了熟悉的工作流，即部署一个或多个容器图像，然后带着 URL 或端点离开。在幕后，容器应用运行在一个隐藏的、抽象的基于 AKS 的 Kubernetes 集群之上。

今年早些时候，亚马逊推出了[App Runner](https://aws.amazon.com/apprunner/)——一种在 AWS 上运行容器化应用的托管服务。正如鸭嘴集团首席云经济学家科里·奎因指出的那样，App Runner 成为第 18 个在亚马逊网络服务上运行容器的服务。从[弹性豆茎](https://aws.amazon.com/elasticbeanstalk/)到 [AWS Fargate](https://aws.amazon.com/fargate/) ，亚马逊的云拥有压倒性的容器服务选择。

和谷歌云没什么区别。要部署容器化的工作负载，可以瞄准 [App Engine Flex](https://cloud.google.com/appengine/docs/the-appengine-environments) 、 [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine) 、 [GKE Autopilot](https://cloud.google.com/kubernetes-engine/docs/concepts/autopilot-overview) 和 [Cloud Run](https://cloud.google.com/run) 。

虽然 Kubernetes 的架构和 API 已经标准化和成熟，但是开发者的体验仍然缺失。事实上，云提供商无法满足于 Kubernetes 的 PaaS 层就是一个很好的证明。

去年，在 New Stack 的创始人兼主编 Alex Williams 的播客中，我强调了 Kubernetes 生态系统中缺乏开发者经验。

[https://www.youtube.com/embed/pH352KoeX4I](https://www.youtube.com/embed/pH352KoeX4I)

视频

是什么促使云提供商几乎每个季度都向产品组合中添加新的容器服务？

## Kubernetes 的复杂性继续增长

Kubernetes 是一个元平台——一个旨在构建其他平台的平台。但即使在推出 7 年后，该行业仍在努力获得正确的开发者体验。

在 Kubernetes 之上缺乏一个开源的、可移植的 PaaS/应用层是开发者发现很难与 Kubernetes 打交道的关键原因之一。

在过去几年中，云原生生态系统取得了重大进展。存储、网络、服务网格、可观察性和安全领域的进步推动了这一发展。他们正在帮助 Kubernetes 和云原生堆栈成为真正的企业级产品。另一方面，它们也增加了堆栈的复杂性。

虽然可以保证 Kubernetes APIs 是相同的，而不管托管服务产品如何，但是在不同的云环境上运行的平台层并没有融合。你可能会说，像 AWS App Runner、Google Cloud Run 和新推出的 Azure Container 应用程序这样的服务提供了开发者体验。虽然对于处理少量容器的简单工作负载来说这可能是正确的，但是部署、扩展和管理复杂的多容器应用程序是困难的。

## 对可移植的云原生平台层的需求

Knative 和 Dapr 等项目试图减少在 Kubernetes 上运行复杂工作负载所需的管道。但是，他们仍然需要一个抽象层来交付无缝的开发人员体验。

Knative 是一个基于 Istio 服务网格的平台，致力于为 Kubernetes 带来无服务器功能。服务和事件功能被公开为一组 API，供开发人员在 Kubernetes 上部署和扩展容器。但是，Knative 本身并不是一个 PaaS 层。它通过一个简化和聚合的 API 层抽象出底层的 Kubernetes 和 Istio APIs。

[分布式应用运行时(Dapr)](https://dapr.io) 也通过提供开发微服务的核心构建模块来采用平台方法。它向对象存储、缓存、消息传递和数据库等服务公开了一个可插拔的模型，而无需更改代码。最近，Dapr 已作为孵化器项目提交给 CNCF。

[KEDA](https://keda.sh) ，基于 Kubernetes 的事件驱动自动缩放器，是另一个开源项目，也是 CNCF 的孵化器项目。这是一个事件驱动的自动扩展引擎，可根据外部因素(如队列中的消息数量或来自 Prometheus 的自定义指标)来扩大和扩大工作负载。KEDA 和 Knative 服务的最终目标是相同的，即提供零扩展基础架构来优化资源利用率并降低计算成本。

Dapr 和 KEDA 的共同点是这些项目都是由微软和红帽支持和维护的。

Knative 的主要贡献者谷歌已经基于 Knative 建立了 GKE 的专有层 Cloud Run。Cloud Run 是公共云中可用的简单而强大的无服务器容器平台之一。

Cloud Run 是 Knative 和类似 PaaS 的开发者体验之间缺失的一环。与 Knative 不同，Cloud Run 不是一个开源项目。谷歌正利用这一点在其公共云(GKE)和混合云(Anthos)平台上提供差异化的体验。

借鉴谷歌的做法，微软现在将 Dapr 和 KEDA 联合起来，以 Azure 容器应用的形式提供新的容器服务。它是一个多租户隔离层，运行在预先配置了 Dapr 和 KEDA 的 AKS 集群之上。像 Cloud Run 一样，您不必提供托管的 AKS 集群并在其上安装 Dapr 和 KEDA。容器应用程序带有基于 Dapr、KEDA 和 Envoy 代理的预配置环境。

所以，Azure Container Apps 之于 Dapr+KEDA，就像 Google Cloud Run 之于 Knative 一样。

很明显，谷歌和微软等平台提供商正在利用他们的开源投资在其云平台上提供不透明的托管服务。这并没有错，但这凸显了 Kubernetes 缺乏一个开源的、基于标准的、可移植的应用平台。

## Kubernetes 上应用平台的碎片化是不健康的

从长远来看，云原生应用层和专有实现之间不断扩大的差距将损害生态系统。即使容器映像是堆栈的最小公分母，运行在这些黑盒服务上的应用程序的打包和配置也是互不相同的。

在 Kubernetes 的上下文中，一个有效的部署/pod 定义必然会在任何集群中运行——无论是托管的还是自托管的。托管应用程序服务则不同。针对 AWS Fargate 的微服务工作负载无法轻松迁移到 Azure 容器实例或容器应用程序。此外，将多个容器缝合在一起作为单个基于微服务的工作负载很难在这些托管服务中运行和扩展。

我们需要的是一个可移植的、透明的、开源的应用层，它将在开发人员笔记本电脑中部署的 Minikube 集群或公共云中提供的大规模多节点集群中持续运行。我们正在等待一个平台层，将 Knative、Dapr 和 KEDA 的精华带到 Kubernetes，而不被锁定。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>