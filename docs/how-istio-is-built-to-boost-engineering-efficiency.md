# Istio 如何提高工程效率

> 原文：<https://thenewstack.io/how-istio-is-built-to-boost-engineering-efficiency/>

*This is the first part of a three-part series. See the second part [here](https://thenewstack.io/when-you-need-or-dont-need-service-mesh/).*

Kubernetes 管理中出现的一个亮点是 Istio 服务网格的核心功能如何帮助工程团队更高效地运行多集群应用。在本期 [The New Stack Makers](/podcasts/makers) 播客中，我们采访了杰出工程师[丹·伯格](https://www.linkedin.com/in/daniel-berg-18b2bb3)、IBM Cloud Kubernetes Services 和 Istio 以及 F5 Networks 联合创始人兼首席架构师[尼拉杰·波德达尔](https://www.linkedin.com/in/nrjpoddar)、Aspen Mesh 。他们讨论了 Istio 在 Kubernetes 管理层的广泛影响力以及我们未来可以期待的事情。《新书库》的创始人兼发行人亚历克斯·威廉姆斯主持了这一集。

[ASPEN MESH:如何构建 Istio 以提高工程效率](https://thenewstack.simplecast.com/episodes/aspen-mesh-how-istio-is-built-to-boost-engineering-efficiency)

与过去的虚拟机(VM)相比，微服务无疑给基础架构带来了复杂性。Berg 说，Istio 已经成为一种通过 API 编程网络策略的方式。“这是一个自然的演变，以适应我们今天基于容器的云原生应用程序，”Berg 说。

Istio 也是一种非常适合编写通用的、可重用的软件来管理内部通信的方法。作为一个简化微服务通信的开源服务网格平台，Istio 处理“许多围绕微服务相互通信的复杂问题，”Poddar 说。它的使用范围包括执行策略、管理证书和遥测，“以便您可以了解您的集群中正在发生什么，”波德达尔说。“随着微服务的增加，这些问题会变得越来越复杂。”

波德达尔说，一旦部署投入使用，还存在其他挑战。“在第二天，你想强化你的集群环境，你不想让未加密的数据流过可维护性，”波德达尔说。“他们需要在整个系统中有一致的指标，否则他们不知道发生了什么。”

类似地，开发团队必须保持警惕，如果他们的应用程序在第二阶段失败的话。Poddar 说，开发人员“需要在失败发生时参与进来，并需要在正确的时间和正确的背景下接受咨询”。

波德达尔说，Istio 的遥测能力是“了解集群中发生了什么”的关键组成部分。“随着你添加更多的微服务，这些问题变得越来越复杂，”波德达尔说。“因此，Istio 中的服务网格只是将开发人员的负担转移到基础设施层。这基本上是将两个团队分离开来，使他们能够同时取得成功。”

Berg 说，Aspen Mesh 还在帮助 DevOps 团队利用 Istio 的流量管理、安全和一般网络功能方面发挥了作用。“一般来说，开发人员会使用流量管理功能和类似的功能，因为你正在定义特定于你的应用程序的路线和特征，以及你的部署的推出，”Berg 说。

但是对于设置阶段，涉及到对集群的入站或出站访问控制的策略，“这可能是一个安全顾问，负责定义这些级别的策略，而不一定是开发人员，因为你不会希望开发人员定义那个级别的安全策略，”Berg 说。“应该是一名安全官员来做这件事。有多个不同角色的空间。”

Poddar 说，Istio 在如何在 Kubernetes 上运行多集群应用程序方面的未来应该包括进化到“与应用程序的语言对话”。“这是真正价值发挥的地方，服务网络仍将是其中的一个关键角色，但它将是生态系统的一部分，其中其他部分也很重要，所有这些部分都在提供信息，我们正在关联这些信息，”波德达尔说。“我们仍然很早，因为人们刚刚习惯于理解服务网格。因此，告诉他们我们需要以自动化的方式协调所有这些信息是很可怕的，但我们会实现这一点。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>