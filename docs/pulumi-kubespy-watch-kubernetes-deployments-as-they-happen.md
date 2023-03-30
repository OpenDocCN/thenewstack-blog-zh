# Pulumi Kubespy:观察 Kubernetes 的部署

> 原文：<https://thenewstack.io/pulumi-kubespy-watch-kubernetes-deployments-as-they-happen/>

西雅图初创公司 [Pulumi](https://www.pulumi.com/) 发布了一款名为 kubespy 的工具，可以实时显示对 Kubernetes 对象所做的更改。它基于 Pulumi 的工作来支持 Kubernetes，这是它几周前宣布的。

在[的博客文章](https://blog.pulumi.com/kubespy-and-the-lifecycle-of-a-kubernetes-pod-in-four-images)中，您可以看到 nginx 使用裸 pod 部署时的变化。

“客户很难知道 Kubernetes 集群内部发生了什么。…人们倾向于拿起他们的 YAML 文件，扔向集群，并希望一切顺利。这意味着他们手动轮询日志和浏览事件，试图找出发生了什么，”联合创始人兼首席执行官[乔·达菲](https://github.com/joeduffy)说。

Kubespy 在 [GitHub](https://github.com/pulumi/kubespy) 上可用，即使您没有使用 Pulumi 进行部署，也可以使用它来检查集群并为您提供交互式信息，如故障、网络连接问题等。

达菲说:“你可以把它想象成卷曲，但它是针对库伯内特星团的。”"它为您提供了丰富的状态信息，您可以使用这些信息进行调试并获得洞察力."

到目前为止，kubespy 有三个命令:

*   **状态** —实时跟踪发出对所做的所有更改。任意 Kubernetes 资源的状态字段，作为 JSON diff。
*   **变更** —以 JSON diff 的形式跟踪 Kubernetes 资源中任何字段的变更。
*   **trace** —跟踪复杂的 Kubernetes 资源在整个集群中所做的更改，并将它们汇总到一个高级摘要中，该摘要会实时更新。

它允许用户查询 API 服务器知道的任何资源，包括[CustomResourceDefinitions(CRDs)](https://kubernetes.io/docs/tasks/access-kubernetes-api/custom-resources/custom-resource-definitions/)。第二篇博文[关注的是 trace 命令，展示了如何观察一个服务被删除，或者一个不健康的 pod 在推出新版本时变得健康。](https://blog.pulumi.com/kubespy-trace-a-real-time-view-into-the-heart-of-a-kubernetes-service)

基于“基础设施即代码的[理念，Pulumi 专注于使开发者和 DevOps 团队能够使用他们已经喜欢的语言和工具部署到任何公共或私有基础设施上——以及跨基础设施。](https://thenewstack.io/pulumi-using-languages-to-program-across-clouds/)

联合创始人乔·达菲和 T2·埃里克·鲁德来自微软，首席技术官 T4·卢克·霍班来自亚马逊。

该公司最近发布了一套名为 Cloud Native SDK 的软件库和工具，允许开发人员用 JavaScript、TypeScript、Python 和 Go 编写应用程序，在多个云或私有数据中心的 Kubernetes 部署中工作。它引起了相当大的轰动。Duffy 说，它还为 OpenStack 和 VMware 提供了在线支持，并与客户合作进行内部部署。

Duffy 说:“Kubernetes 今天面临着许多我们在 AWS Manager 开发中看到的同样的挑战——许多 YAML，许多 Bash 脚本，因为人们正在构建应用程序，管理应用程序。“随着越来越多的人使用多云技术，人们需要掌握很多不同的 YAML 方言和工具。这就是 bash 的东西越来越不受控制的地方，因为人们使用的工具，坦率地说，从来没有打算一起工作。

“使用这种新方法，您可以在同一个程序中调配 GKE Kubernetes 集群、AKS Manager 和 AKS 数据库，然后在亚马逊中调配服务。你知道，像 S3 桶或托管的 MySQL 数据库，然后使用你的 Kubernetes 应用程序。今天真的很难，”他说。“使用 Pulumi，您只需编写一些类型脚本—[只需几]行代码，而以前需要数千行 YAML，无论云部署如何，我们都能管理所有的配置和管理。”

他说，这为进行更高级的部署协调奠定了基础。

“客户对此非常兴奋，他们让他们的 DevOps 团队使用不同的工具来调配 Kubernetes 集群，开发人员使用完全不同的工具，这有点像西部大开发。决策者很难对策略或管理进行任何控制，这让 DevOps 团队感到沮丧，因为配置蔓延，文件到处都是。我们将基础设施视为代码，以此来驯服它和所有那些 YAML 文件。”

联合创始人致力于。Duffy 说:[公共语言运行时](https://docs.microsoft.com/en-us/dotnet/standard/clr)中的. NET，所以他们知道如何做多语言运行时。

该平台是可扩展的。引擎是用 Go 编写的，使用插件模型，可以插入自己的语言。它不会对 IDE 中的语言发表意见。

他们正在与一位客户合作。Duffy 说，NET 支持和 Java 是未来的发展方向。

“我们有办法让您现有的应用程序使用 Pulumi 进行部署。如果您只是想要 GitOps 体验或 CLI 体验，您可以获取现有的 YAML 文件，并按原样部署它们，而不做任何更改。也许你想一次转换一个 YAML 文件，或者边转换边转换，这种混合环境——我们称之为棕地——对于在 Kubernetes 有大量投资的客户来说非常重要。类似地，我们可以拿着舵轮图，然后部署它们。如果我想在 Kubernetes 应用程序中提供一个 S3 存储桶，通常我必须使用两个不同的工具链。

“让我感到惊讶的是，人们会不惜一切代价来获得并非为协同工作而设计的工具。有了 Pulumi，您只需订购存储桶和部署，一切都以统一的方式进行。”

他说，展望未来，该公司正在努力使其成为一个团队环境，并在未来几周内将发布围绕部署协调、服务网格等的工具。

Pulumi 是新堆栈的赞助商。

特征图片:[美国陆军](https://www.flickr.com/photos/soldiersmediacenter/)的“060726-F-7564C-325”。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>