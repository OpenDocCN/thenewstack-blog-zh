# 微软巴克展示了 CNAB 捆绑如何为云应用部署服务

> 原文：<https://thenewstack.io/microsoft-buck-shows-how-cnab-bundling-could-work-for-cloud-app-deployment/>

容器的便利性很快使其成为简单部署的 ZIP 文件的现代等价物，但随着基于云原生堆栈构建的应用程序变得更加复杂，容器不再是部署的单元，而是应用程序。

Helm trench 等工具为 Kubernetes 安装应用程序，但许多应用程序不仅仅涉及 Kubernetes，还需要定义无服务器功能和托管云服务，并与容器一起打包成一个可以共享的包。云原生应用不一定运行在公共云中；它们可以在任何地方运行，从云设备到间歇连接的工业网站上的 Raspberry Pi，在那里资源不能按需下载，但你仍然需要能够安装应用程序并更新它们(甚至删除它们)。

分发和部署云原生应用是最近成立的云原生计算基金会[应用交付特别兴趣小组](https://github.com/cncf/sig-app-delivery) (SIG)的主要关注点，而不仅仅是构建或运营它们。即使是同名的容器公司 Docker 也试图从容器转向更广泛的视角，看看开发人员如何发布应用程序。

这里的一个关键举措是针对云原生应用捆绑包的 [CNAB 规范](https://thenewstack.io/what-is-cnab-and-why-it-is-important-for-cloud-native-computing/)，该规范将分布式应用打包成单个可安装文件，该文件可以签名并存储在注册表中或复制到 u 盘，使用[工具](https://cnab.io/community-projects/#tools)，如 [Duffle](https://github.com/cnabio/duffle) 、 [Porter](https://github.com/deislabs/porter) 和 Docker 应用。

“我们有喜欢 Helm 的客户，但他们不仅仅在 Kubernetes 上，”Azure container compute 团队的 Lachlan Evenson 告诉 New Stack。“现代分布式应用程序由许多不同的运行时组成，您永远不会只关注其中一个。所以 CNAB 想知道，世界上谁想运行不仅仅由 Kubernetes 组成的分布式应用程序；我们如何给他们分布式应用程序体验，我们都知道并喜欢 Docker 用容器给我们的体验”

Azure Compute 总监 Gabe Monroy 告诉我们:“没有任何其他公司能做到 CNAB 所做的，当然也没有任何公司能做到我们能够通过完全密封的加密包提供的安全性和合规性保证。”。

新的[开放应用模型](https://openappmodel.io/)规范将应用的定义与部署的操作细节分离开来(作为两个工具为 Kubernetes 实现，Dapr 用于开发人员，Rudr 用于操作人员),可以使用掌舵图将 OAM 定义和依赖项部署到 Kubernetes 集群。或者，如果您需要在 Kubernetes 集群上安装相同的应用程序，而该集群无法访问 Helm 需要提取的容器图像，您可以将图像和 Helm 图表放在 CNAB 包中。与掌舵图不同，CNAB 捆绑包还可以包括操作细节，如在一组服务的运行状况受到升级影响时触发自动回滚。OAM 还将能够瞄准 Kubernetes 以外的平台，CNAB 在这方面提供了帮助。

Monroy 说，总体目标是“我们如何让开发人员编写健壮、有弹性、高度可用的分布式应用程序成为可能？”OAM 和 Dapr 是实现这一目标的一种方法，无服务器也是如此。 [Buck](https://github.com/brigadecore/buck) ，微软为了简化 Kubernetes 控制器的开发[而为 Kubernetes 开发的通用控制器](https://cloudblogs.microsoft.com/opensource/2019/11/15/in-cluster-cnab-management-brigade/)就是这种趋势的一部分，他认为。“我们如何使这项技术民主化，我们如何使它对更多的开发人员更有吸引力，更容易接近？”

### 逆势而上

Monroy 说，Kubernetes 操作器是一种自动化的应用程序，可以自己操作，通常通过监听自定义资源定义创建的用户定义资源来操作，是云原生开发中一种令人兴奋的模式。“但是编写一个操作符很难，它需要对 Kubernetes API 语义有深入的了解:如何做观察，如何做再同步循环。里面有很多硬东西。”

“人们希望定义他们的特定工作负载控制器，”Evenson 解释说，“但是进入的障碍非常大。你必须去库伯 builder。如果你以前从未与 Kubernetes 合作过，这是一个非常大的飞跃。您希望定义一个非常轻量级的控制器，与 Kubernetes 进行对话，而不必处理所有的细节，那么我们是否可以利用 Brigade 和我们构建的工具来接收来自 Kubernetes 的事件，然后实现一个控制器”

Buck 使用了用于事件驱动的工作流自动化的云原生计算基础项目 Brigade，使编写 Kubernetes 控制器变得更加容易；它是一个旅网关，充当 Kubernetes 控制器前端，接受一个自定义资源名，然后监听 Kubernetes 事件流中与该自定义资源相关的事件。当网关为它的定制资源接收到一个事件时，它通知 Brigade，Brigade 创建一个新的 worker 并将事件细节传递给它；然后，该工人运行您定义的工作流程。

Buck 本身是用 Rust 编写的，但是因为它是 Brigade 的网关，控制器可以用 JavaScript 编写。甚至有一个[舵图](https://helm.sh/)用于定义一个定制的资源并使用它部署 Buck gateway。

Evenson 指出:“全世界的开发者都在使用 JavaScript，当他们来到 Kubernetes 时，你会要求他们去做一名 go 开发者。”“Brigade 总是在问，我们能否创建一个框架来与这些开发人员交流，这样他们就可以拥有 Kubernetes 的体验，而不必成为围棋专家。”

## 托管像容器这样的包

微软还使用 Buck 创建了一个[示例操作器，用于将 CNAB 包安装到集群上，并使用 Porter 管理它们的生命周期。“我们想和巴克一起做的事情之一就是模拟 CNAB 的可能性，”Evenson 解释道。](https://github.com/technosophos/buck-cnab)

它将 Porter 动作定义为 Kubernetes 自定义资源。它还允许您使用包含 CNAB 安装详细信息的 YAML 文件，从集群管理 CNAB 软件包；创建 YAML 来安装软件包，修改它来更新 CNAB 安装，删除它来卸载 CNAB。

如果 CNAB 捆绑包变得普遍，你将不会想要站起来保护另一个回购协议——或者在另一个云注册表上管理账户——只是为了存储它们。容器注册中心已经被加固、保护，并变得可扩展和可用。那么，为什么不将它们用于其他构件，如 CNAB 捆绑包、舵图和地形、ARM 和云形成模板以及云部署所需的所有其他构件呢？

开放容器倡议的分发规范定义了注册中心 API 该软件的第二版仍在审批中，但多亏了 [OCI 人工制品项目](https://github.com/opencontainers/artifacts)和 [ORAS(作为存储的 OCI 注册库)](https://github.com/deislabs/oras)库，它将支持不同的媒体类型，如掌舵图、CNAB 包，甚至 [WebAssembly 模块](https://radu-matei.com/blog/wasm-to-oci)。这已经在 Docker 注册中心和 Azure Cloud 注册中心的实验旗帜下实现了。

“当你登录 Docker 时，你现在可以在同一个空间存储你的舵轮图和你的捆绑包，”Evenson 解释道。“这只是一种很好的综合体验。”

将 OCI 注册中心用于像 CNAB 捆绑包这样的新工件，可以更好地将它们与现有工具集成在一起，这使得在您开始构建需要它们的更复杂的云应用时，更容易迁移到捆绑包。

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>