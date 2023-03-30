# 微软与 DCOS 中间层合作推出 Azure 容器服务，与谷歌拉开差距

> 原文：<https://thenewstack.io/microsoft-launches-azure-container-service-mesosphere-dcos-drawing-distinction-google/>

如果谷歌的容器引擎的特点是 Kubernetes 编排平台的存在，微软的容器引擎的特点是中间层 DCOS 的存在。周二，在一个名为 AzureCon 的全新 Azure 聚焦大会上，微软和 Mesosphere 发表联合声明称，他们正在以这样一种方式扩展他们的合作伙伴关系，即基于 Apache Mesos 构建的令人眼花缭乱的 orchestrator DCOS 将成为新 Azure Container 服务上提供的首选 orchestrator。

微软的 Azure 首席技术官 Mark Russinovich 在谈到新的堆栈时表示:“这是客户将容器化的应用程序部署到 Azure 的能力，只需几次点击就可以设置他们的集群。”

> “我们与 Mesosphere 合作，在 Mesos 和 DCOS 开源部分的基础上构建容器服务……我们觉得这是一个很棒的合作伙伴关系，我们可以通过将容器服务扩展到开放的东西上，而不是建立在专有技术上。”

## 多世界假说

DCOS 不会成为 Azure 新服务上管理容器工作负载的默认选项。但是正如 Russinovich 告诉新的堆栈，将不会有这样的默认选项。(只是提醒我们的读者，我们正在与微软对话。)

Azure 首席技术官说:“在容器服务的这个初始版本中，我们不知道那些应用程序在集群上的部署管理是如何发生的。“不同的人会构建不同的解决方案，其中一种可能性是他们会在基础上使用像 DCOS 这样的东西。另一个是他们将通过 Visual Studio 使用一些持续集成/持续部署管道来将应用程序部署到集群，在一个更加面向 DevOps 的世界中。然后，您可能仍然会有锁定的、活跃的 IT 场景，其中一些 IT 管理员决定部署什么和管理什么，与开发人员无关。

> “我认为你会看到完整的光谱，”他继续说道。“我们建立在 Mesos 之上的好处之一是，生态系统正在建立起来，以支持所有这些不同的情况。”

这是一种不可知论，开发者，尤其是来自 Linux 的开发者，不会马上联想到微软。在面向容器的会议上，每当供应商或开源贡献者展示开发人员将容器部署到生产环境中的轻松程度时，通常都会有欢呼。但是在大型企业中，尤其是那些保持严格的遵从性指导方针的企业，是 it 部门决定什么从开发转移到生产，以及如何完成。

当 Windows Server 仍然被认为至少在数据中心的基础设施上有一个立足点时，微软帮助巩固了 IT 驱动的部署作为最佳实践。它专门为管理员开发应用程序部署系统，并将这些系统硬连接到其主要管理工具包 System Center 中。开发人员和管理员之间的适当工作流被融入到公司的团队集成工具中，这些工具的名字暗示了他们之间关系的难度:例如，[微软 Visual Studio Team Foundation Server 2010 工作项同步的系统中心管理包](http://blogs.msdn.com/b/visualstudioalm/archive/2013/04/19/system-center-and-intellitrace.aspx)。

在现代世界中，有竞争力的云服务提供商别无选择，只能提供容器部署。这意味着解决开发人员的问题，至少给他们部署控制的希望。

微软将暂时置身事外，拥抱并扩展其新的企业哲学。但是已经证明自己是以开发者为中心的部署的冠军[的 Mesosphere 又如何呢？](https://mesosphere.github.io/marathon/docs/deployments.html)

“这真的取决于组织真正想要如何运行他们的容器，”Mesosphere 的创始人和 Apache Mesos 的创建者 Ben Hindman 说，他也谈到了新的堆栈。“可能有一个管理员接收人们的容器，并使用 DCOS 的接口来启动这些容器；或者它可以是类似 Jenkins 的东西，或者其他类型的持续集成设置，可能直接从 Visual Studio 连接。DCOS 不会固执己见，强迫一个组织以这样或那样的方式部署它。它将尽可能简化这些部署策略。”

## 重新组合

现在，向公共云快速部署可扩展的容器化系统的选择比以往任何时候都多，我们是否有可能看到容器化工作负载的设计方式发生变化？Hindman 认为需要发生的主要建筑变化已经发生了。

“在 Linux 世界中，如果你正在编写一个 LAMP stack 应用程序，期望你在完全相同的机器上有 Apache 和 MySQL，并且你已经用那种方式编码了它们，你最好分解应用程序。即使在 Twitter，这个应用也是一个单一的应用，但它是针对 Linux 的，我们仍然需要花费大量时间将它分解成微服务。所以这种心态适用于两种视角[Windows 和 Linux]；这实际上是关于你如何考虑应用程序的架构。

“有了微服务架构，将会有不同的组件，有些是为 Linux 编写的，有些是为 Windows 编写的，它们仍将一起通信和交谈，”Hindman 继续说道。

> “这就是微服务架构的整个前提:你可以将碎片分解成这些通信组件，并且可以专注于正确的技术来解决工作，但然后你需要一种方法来部署所有这些应用程序，并使它们能够一起通信。”

“我认为，教育在于定义这些接口，并理解如何分解组件。我们的工作是，一旦你编写了一个组件，[确保]你可以尽可能高效地运行这些东西。这就是 Azure Container Service 和 Apache Mesos 和 Mesosphere 真正走到一起的地方。”

专题图片: [Christopher Michel](https://www.flickr.com/photos/cmichel67/) 的《[继续走，你就快到了](https://www.flickr.com/photos/cmichel67/11826271726/in/photolist-j23JyE-f2cwht-qHcnEC-fpwA5a-kgjrVy-mYNXHu-f398LY-jvfbfE-qGHPrr-oQeoLz-vqtWTG-dMfviP-pJDvg3-hH88dq-hkG9bR-nKFXz4-gPJEKq-nNQ8uL-p2Yk5f-s5rjV4-qXe8HE-gSt7EL-qDpL5t-qFU1yL-tEJCrS-uXRHEJ-jRg1WW-uyKV6y-tHRE2h-fvQhJu-dykFj9-hhnAjj-oiaQ79-vCYFzs-dD6tgh-eZzPsE-e9K51c-efZBk4-prAb8Z-tHyMFA-mkJNJh-e7ZspX-tKTRmw-xxkJkU-oJ3Tu2-rC9bp3-u5pXc7-fFS38A-p8QCH2-toMpYA)由 2.0 的 [CC 授权。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>