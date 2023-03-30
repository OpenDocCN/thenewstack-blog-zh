# Knative 如何联合 Kubernetes 和 Serverless

> 原文：<https://thenewstack.io/how-knative-can-unite-kubernetes-and-serverless/>

[](https://cloudplatformonline.com/TNS-CI-CD-with-Kubernetes.html?utm_source=google&utm_medium=email&utm_campaign=FY18-Q3-americas-nurture-email-wd-icb_tns&utm_content=cicd&utm_term=tns)

 [吐温泰勒

吐温是 Twistlock 的客座博主和 Fixate IO 撰稿人。他在谷歌开始了他的职业生涯，在那里，他参与了 AdWords 团队的技术支持。他的工作包括审查堆栈跟踪和解决影响客户和支持团队的问题，以及处理升级。后来，他建立了品牌社交媒体应用程序和自动化脚本，以帮助初创公司更好地管理他们的营销业务。如今，作为一名科技记者，他帮助 IT 杂志和初创公司改变团队构建和发布应用程序的方式。](https://cloudplatformonline.com/TNS-CI-CD-with-Kubernetes.html?utm_source=google&utm_medium=email&utm_campaign=FY18-Q3-americas-nurture-email-wd-icb_tns&utm_content=cicd&utm_term=tns) [](https://cloudplatformonline.com/TNS-CI-CD-with-Kubernetes.html?utm_source=google&utm_medium=email&utm_campaign=FY18-Q3-americas-nurture-email-wd-icb_tns&utm_content=cicd&utm_term=tns)

Kubernetes 和[无服务器](https://www.twistlock.com/serverless-security/)是当今科技领域最热门的两个词汇——然而它们并不经常出现在同一个对话中。通常，Kubernetes 用于编排容器化的应用程序，而无服务器计算提供了一种不同类型的部署模型。当大多数人想到无服务器时，他们首先想到的仍然是 AWS Lambda、Azure Functions 和其他基于云的无服务器框架，这些框架在几年前将无服务器带入了主流。

但是由于依赖 Kubernetes 的无服务器框架的发布，围绕 Kubernetes 和无服务器的生态系统越来越交叉。如今，希望构建无服务器环境的开发运维团队不必再局限于公共云供应商的托管无服务器框架。

在这篇文章中，我们来看看目前可用的基于 Kubernetes 的无服务器框架。我们涵盖了所有主要产品，但最重要的是，我们特别关注 Knative。

事实上，Knative 在吸引 DevOps 团队离开 Lambda 等公司，转向基于 Kubernetes 的无服务器环境方面最引人注目，发挥了最大的作用。

## 一无所有

Kubeless 是一个开源的 Kubernetes-native 框架，它允许你部署一些代码，而不用担心底层的基础设施。它在幕后使用 Kubernetes 来提供 API 路由、自动伸缩、监控、故障排除等。创建 Kubeless 只是为了让人们初步了解在 Kubernetes 上运行无服务器工作负载的情况。一旦发布，Kubeless 将不会是唯一一个基于 Kubernetes 的无服务器框架。

## 分裂

[Platform9](https://platform9.com/) ，一家主要提供托管 Kubernetes 服务的公司，发现除了 Lambda 之外，还需要一个无服务器解决方案。它发布了[裂变](https://platform9.com/fission/)，一个开源的无服务器框架。它的目标是为用户提供一种简单的方法来开始和管理他们的应用程序，而不必做任何与容器相关的工作。裂变是基于本地库伯内特人。

Pete Johnson 在思科博客上做的这个有帮助的[比较表明，裂变介于 Lambda 和 Kubernetes 之间。然而，当务之急是要有一个更接近 Kubernetes 而不是 Lambda 的解决方案——无论是在没有供应商限制的情况下，还是基于 Kubernetes，这是当今所有云平台正在整合的平台。Platform9 正在提供商业化的裂变技术，但它还没有像 Kubernetes 那样被整个行业采用。然而，现在这个位置有了一个竞争者:Knative。](https://blogs.cisco.com/cloud/examining-the-faas-on-k8s-market)

## Knative

Knative 本身并不是一个完整的无服务器解决方案。相反，它是一个构建无服务器解决方案的平台。从这个意义上说，Knative 更有可能被供应商或运营商用来在 Kubernetes 上构建无服务器解决方案。Google Cloud 的软件工程经理、Knative 项目的贡献者 Dan Lorenc 解释说,“Knative 充当了 Kubernetes 和无服务器框架之间的中间层。因此，如果你编写的应用程序以 Knative APIs 为目标，你可以在 Kubernetes 运行的任何地方运行它。”

## 供应商协作方法

Knative 的主要动机是为无服务器计算定义独立于供应商的标准。

第一个迹象是 Knative 是由领先的云组织如 Google、Pivotal 等组成的财团创建的。Google Cloud 的产品经理 Jason Polites 在评论创建 Knative 的协作方法时表示:“我们相信客户从跨提供商的一致性中受益最多，开源和社区协作是实现这一点的最佳方式。我们已经在 Kubernetes 上看到了这种情况，Knative 也采取了类似的方法。根据 Jason 的说法，最终目标是“不仅在容器级别，而且在无服务器平台级别获得可移植性。"

例如，当您准备好的时候，您可以将整个无服务器平台及其上运行的所有应用从数据中心迁移到云平台。

### 无服务器作为形容词

Polites 提出了一个有趣的观点，将“无服务器”作为一个形容词而不是名词。对于语法上有挑战的人来说，这仅仅意味着你不想成为无服务器——相反，你意识到要运行你的应用，你需要无服务器计算、无服务器内存等等。一旦你从这个角度看问题，Polites 解释说，“你现在可以选择最适合你的抽象，而不必被迫接受或放弃无服务器的好处。”有了 Knative，您可以灵活地构建理想的无服务器平台，完美满足您组织的需求。您可以挑选整个堆栈中您希望无服务器管理的部分，其他部分保持不变。

### 建造、服务、活动

Knative 包含三个主要组件:构建、服务和事件。

*   构建:一旦编写了一段代码，就需要将其打包到一个容器中。这是管道的构建部分，通常由像 Jenkins 这样的 CI 工具处理。一旦构建了容器映像，它就被上传到容器注册中心。从那里，可以使用 YAML 文件进行部署，以创建简单或复杂的部署。Knative 将所有这些步骤抽象成一个清单文件。Knative 的构建部分处理所有容器编排任务；
*   Serve:这是 Knative 的一部分，它处理底层实例从零到大规模的伸缩，以及当服务不再使用时返回到零。它还利用 Istio 来处理多个修订或快照之间的请求路由。
*   事件:Knative 的这一部分允许您为您的函数设置和定义触发器。它有助于在任何单个步骤或使用管道的复杂流程中构建自动化。项目的这一部分仍在进行中。

### 易用性

从运营效率的角度来看，Knative 也很有意义，因为它使用起来非常简单。Dan 评论道:“如果你想在谷歌云平台上尝试 Knative，今天你可以非常容易地做到。只需一个命令，你就可以让 Kubernetes 在其中运行 Knative。”他说，“如果你想在 Kubernetes 集群中运行你自己的无服务器框架，Knative 是最好的选择。”最棒的是，你可以在你的数据中心使用同样的易用性——简而言之，在任何你可以运行 Kubernetes 的地方，你也可以运行 Knative 和你所有的无服务器应用。

无服务器运行容器是整个 Kubernetes 生态系统的发展方向。正如 Lorenc 调侃的那样:“我们将很快发布一些公告，说明这两项工作(容器和无服务器)在 Knative 的上下文中是如何关联的。”第一次看到这个是 Knative GKE 附加，这是有史以来第一次商业 Knative 提供。我们会看到类似 AWS Fargate 的东西，或者完全新的东西吗？我们只能等着瞧了。

除了谷歌的努力，还有 [Pivotal Function Service](https://pivotal.io/platform/pivotal-function-service) ，也是基于 Knative。另一个有趣的初创公司是 [TriggerMesh](https://triggermesh.com/) ，它是由《无库》的创作者[塞巴斯蒂安·戈阿斯根](https://twitter.com/sebgoa)创办的。

## 基于 Kubernetes 的无服务器还是 Lambda？

大约一年前，如果你想决定是使用基于云的无服务器框架，比如 Lambda 还是基于 Kubernetes 的框架，这个问题的答案肯定是前者。

然而今天，Knative 改变了现状，为我们提供了一个有能力的，甚至比 Lambda 更好的选择。如果你刚刚开始使用无服务器，我会推荐你选择一个有创意的解决方案，比如 GKE 插件、Pivotal Function Service 或者 TriggerMesh。如果你已经在 Lambda 这样的无服务器平台上运行应用程序，我建议等待几个月，直到 Knative 解决方案发布，经过初始客户的审查，评论蜂拥而至。我猜评论会一致认为 Knative 是未来之路 Kubernetes 和 serverless 的交叉点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>