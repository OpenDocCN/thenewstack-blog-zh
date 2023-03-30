# 微软和红帽公司的 KEDA 为 Kubernetes 带来了事件驱动的自动缩放

> 原文：<https://thenewstack.io/microsoft-and-red-hats-keda-brings-event-driven-autoscaling-to-kubernetes/>

随着事件驱动架构变得越来越普遍，出现了许多旨在将无服务器引入 Kubernetes 的项目。Azure Functions 已经在 Kubernetes 上运行，但像其他函数运行时一样，它一直在使用容器的标准水平伸缩，基于容器的 CPU 和内存消耗。这不符合无服务器的事件驱动特性。

“当 Kubernetes 试图决定每台机器上运行多少 pods 时，它只是查看消耗了多少 CPU 和内存，”Azure Functions 的高级项目经理 Jeff Hollan 解释道。“很无功；它试图猜测需要多少个实例。”

这对于扩展无服务器功能来说太慢了，因为无服务器功能需要对来自事件源的信号做出反应，而不是等到系统资源耗尽时才做出反应，而且它也没有反映出您可能选择如何进行负载平衡。例如，Azure Functions 通过观察事件队列来扩展，如果一个队列有 100 条消息在等待，那么不管 CPU 负载看起来如何，它都会旋转 4 或 10 个实例，而不是一个。

[KEDA](https://github.com/kedacore/keda)——基于 Kubernetes 的事件驱动自动伸缩——是微软和 Red Hat 的一个新的开源项目，旨在将这种伸缩引入 Kubernetes，使容器能够根据事件指标(如流延迟或队列长度)从零扩展到一千个实例。

KEDA 充当激活和停用部署的代理，并且充当 Kubernetes 度量服务器，向水平 Pod 自动缩放器公开事件数据。“这是一个额外的组件，用于监控您的活动源并将数据反馈给 Kubernetes 系统，以便 Kubernetes 了解您的队列和活动中心，”Hollan 解释道。“您只需在集群上一次性安装 KEDA，KEDA 就会监控支持 KEDA 的新容器，并像功能一样扩展它们。”

您可以设置 KEDA 轮询新消息的频率以及它应该如何扩展和冷却，然后部署直接处理事件，这样事件就不必转换为 HTTP 请求，HTTP 请求会丢失内容并阻止与事件源的直接通信。类似地，使用 KEDA 不需要对已部署的代码进行任何更改(尽管代码需要包装在 Docker 容器中)。

KEDA 已经与 Kafka、Azure Queues、Azure Service Bus、RabbitMQ、Azure Event Grid 和其他云事件合作(这将它连接到更多的服务)。微软将为 Azure 事件中心、存储、Cosmos DB 和持久功能添加触发器，事件源也可由社区扩展。

KEDA 可以扩展任何容器或部署，其他无服务器项目也可以利用它，但开源的 Azure Functions runtime 已经与它集成了。

红帽和微软都在为上游的 KEDA 项目做贡献，红帽也在使用 KEDA 来扩展 OpenShift 容器平台上的 Azure 功能作为开发者预览版。这种集成是用 Red Hat 的 Operator Framework toolkit 构建的，将于今年晚些时候在 OperatorHub.io gallery 中提供。Red Hat 的 [William Markito Oliveira](https://www.linkedin.com/in/markito/) 解释说:“它的设计目的是以托管服务的方式在 Azure 上运行，但现在可以在 OpenShift 运行的任何地方运行，这意味着在混合云和本地运行。“Azure 服务和其他云提供商的用户可以通过他们的服务发送事件，并以可移植的方式使用 Azure 功能处理这些事件，从而减少锁定问题。”

“实际上，KEDA 通过轮询来自云上事件源(如 Azure Queues)或本地事件源(如 Kafka)的队列或主题，使应用程序能够根据需求进行扩展，”奥利维拉在一封后续电子邮件中指出。“举个例子，当用户向购物车添加一件物品时，KEDA 会主动监控购物车并触发一个容器。这是一个非常简单的例子，但是对于具有突发和不可预测特征的系统来说，它变得非常有趣。当一个购物车系统的需求增加，1000 人向其中添加多项商品时，KEDA 将自动扩展您的应用程序，以满足这样的需求。当处理完这些事件后空闲时，它会缩小规模，甚至回到零个容器，这是无服务器解决方案的一个主要优势。”

“我们知道很多人对锁定感到焦虑，并考虑如何在不同的环境中运行，”Hollan 指出。“KEDA 是关于采用函数编程模型和它带来的所有生产力，你可以在任何最有意义的地方运行它——这可能是 Kubernetes。如果你想带着你的玩具在不同的云中运行，你可以这样做，我们会为你提供工具。”

## 超越 HTTP

微软云计算团队负责人 [Gabe Monroy](https://github.com/gabrtv) 告诉 the New Stack，“很多时候我们认为自动扩展和扩展到零的功能是以 HTTP 为中心的。“事实证明，在 Azure 函数中，60%到 70%的执行是事件驱动的，而不是 HTTP 驱动的。像事件网格、服务总线和那些提供事件的不同排队系统；这是一种非常常见的模式。”

对于像 HTTP 这样被推到容器中的事件——这构成了其他 30%的工作负载函数——你可以使用 [Knative serving](https://github.com/knative/serving) 或者微软去年在 Kubecon、 [Osiris](https://github.com/deislabs/Osiris) 和 [KEDA](https://github.com/kedacore/keda/wiki/Using-Azure-Functions-with-Keda-and-Osiris) 宣布的开源项目。“KEDA 是函数的事件驱动伸缩，Osiris 是函数的 HTTP 驱动伸缩。Osiris 是 HTTP 版本的 scale-to-zero，KEDA 是事件驱动、队列驱动、自定义指标驱动的版本，”Monroy 解释道。

这是一个精心设计的策略，构建“小、有范围、做好一件事”的开源组件，为 Kubernetes 社区提供混合和匹配的选项，以获得他们需要的东西；他建议的一种方法可以追溯到 Docker 的“包含电池但可拆卸”的承诺。

“允许这些东西分别组装和组合是确保我们让开源生态系统最大限度地利用这一机会的关键，因为如果你构建的东西太大，最终就很难将其视为一个库，”他指出。

## 无服务器 Kubernetes:一个跨行业项目

Monroy 告诉我们，Red Hat 希望将 Azure Functions 的体验带到 OpenShift 上。“RedHat 正在关注押注于 Kubernetes 的所有客户，这些客户希望构建功能型应用。Knative 和其他一些技术在这方面有一定的优势，但这些东西都没有功能带来的完善程度和生产使用水平。几乎从第一天起，函数就已经是容器原生的了。”
KEDA、Open Shift 和功能的组合为您提供了在云中运行无服务器托管服务的选择，作为 Open Shift 中的一个集成选项，或者在任何 Kubernetes 集群上 DIY，无论它在哪里。

去年，Kubernetes 联合创始人[布伦丹·伯恩斯](https://www.linkedin.com/in/brendan-burns-487aa590/)说[Kubernetes 的未来是无服务器的](https://thenewstack.io/the-future-of-kubernetes-is-serverless/)。蒙罗伊说，企业客户已经在要求这样做了。“他们想要没有虚拟机开销、按秒付费、具有快速扩展能力的 Kubernetes 服务。”

微软开发部门主管 John Montgomery 建议，如果这是大多数 Kubernetes 采用者想要的，那么基于一个涉及多个组织的项目是很重要的。“不可能只有一家供应商在做这件事。”

“无服务器在很深很深的方面改变了游戏规则，”Montgomery 告诉 New Stack。“无服务器能够在一个容器中运行，我们在过去 5 年中一直致力于开发人员体验，通过无服务器的强大功能为您提供开发人员生产力。然后你在 Kubernetes 上运行，突然间你就获得了这种云规模的能力来旋转和摧毁容器。KEDA 还可以利用我们用 AKS 做的所有其他事情，比如无服务器容器工作。你得到了可移植性，你得到了容器的加速-减速，加上函数的加速-减速，再加上开发人员的生产力。将所有这些放在一起，该技术将改变一类应用程序的游戏规则，但我认为我们才刚刚开始弄清楚这类应用程序是什么。”

红帽是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>