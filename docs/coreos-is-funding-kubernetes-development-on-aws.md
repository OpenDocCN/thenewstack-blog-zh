# CoreOS 正在资助 Kubernetes 在 AWS 上的开发

> 原文：<https://thenewstack.io/coreos-is-funding-kubernetes-development-on-aws/>

Amazon EC2 客户可以安装 Kubernetes orchestrator，使用 CoreOS 和 containers 来管理容器工作负载。这个事实碰巧在去年的这个时候被公之于众，就在亚马逊的 re:Invent 大会召开之前。该方法的一个经过测试和确认的版本现在出现在 Kubernetes 的官方文档中。

现在，在[亚马逊 2015 版于周二](https://reinvent.awsevents.com/index.html)在拉斯维加斯开放的前一周，CoreOS 宣布其包括 Kubernetes 在内的构造容器平台将包括与亚马逊 AWS 的“官方”集成。当被 New Stack 问及 CoreOS 所说的“官方”是什么意思时，公司首席执行官亚历克斯·波尔维(Alex Polvi)回应道，“两个主要区别是:1)我们，CoreOS，Inc .正在资助该项目的开发；2)我们通过“构造”为整个堆栈提供商业支持和测试。”

这是如何展开的？关于 Docker、容器生态系统以及使用底层可编程基础设施构建微服务所需的新平台的对话有了新的层面。AWS 在过去几年中为市场定义了这种可编程的基础设施。但是谷歌和微软一样有自己的基础设施。问题变成了如何编织这些不同的基础设施，以实现容器应该提供的可移植性。

与此同时，有 Mesos 的用途，有 Kubernetes 的用途，还有新的平台，如 Hashicorp 的 Nomad，它们都有自己可行的方式。但这种支持是一个问号。能从 AWS 得到 Kubernetes 的支持吗？现在不行，你不能。这在 AWS re:Invent 会成为现实吗？这是一个我们无法回答的问题，但是正在展现的可能性有可能提供一种更通用的能力，在更广泛的基础设施中使用 Kubernetes。

CoreOS 称其官方工具为“ [AWS CloudFormation](https://coreos.com/kubernetes/docs/latest/kubernetes-on-aws.html) ”，并于周五发布了关于其工作原理的文档。[在周五](https://coreos.com/blog/kubernetes-on-aws-cloudformation.html)的一篇博客文章中，该公司表示，其特定于 AWS 的设置将支持弹性负载平衡器集成，用于将流量导向选定的微服务。

亚马逊自己的 EC2 容器服务(ECS)是一个平台，包括亚马逊自己的调度和编排工具，尽管它为第三方编排器提供 API。尽管如此，当亚马逊去年 4 月推出 ECS 时，技术媒体在很大程度上将其视为针对谷歌容器引擎的竞争行为，谷歌容器引擎本质上是 Kubernetes 提供的“即服务”。(微软 [Azure 仅在本周早些时候发布了其基于 DCOS 中间层的容器服务](https://thenewstack.io/microsoft-launches-azure-container-service-mesosphere-dcos-drawing-distinction-google/)。)

ECS 最初是由亚马逊在去年的 re:Invent 上宣布的。当亚马逊首席技术官沃纳·威格尔博士去年 7 月在公司博客的[中首次描述 ECS 的全部细节时，他引用了一个 AWS 客户的用例，该客户需要一个 Heroku 兼容的能够横向扩展的 PaaS。当客户的工程团队检查 CoreOS 和 Kubernetes 的组合时，沃格尔斯说，“工程团队很小，所以他们没有时间管理集群基础架构并保持集群的高可用性。”当然，客户最终选择了 ECS。](http://www.allthingsdistributed.com/2015/07/under-the-hood-of-the-amazon-ec2-container-service.html)

沃格尔斯继续对比 Kubernetes 的 ECS，吹捧亚马逊如何向用户掩盖底层系统的复杂性。“Amazon ECS 得到了全面管理，并提供了运营效率，允许工程资源专注于开发和部署应用程序；没有集群需要管理或扩展，”他写道。

这位首席技术官讲述了去年 7 月教育出版商 Coursera 的另一个故事，他描述说 Coursera 带着一个单片出版应用程序来到亚马逊，并要求该公司帮助它转向微服务。

“当然，当你有一个包含许多不同功能的单片应用程序时，”他解释道，“很难估计你实际上需要什么样的资源来让每个线程工作——是 CPU，还是内存，所有这些。所以他们决定采用微服务架构。首先，当然，他们开始使用 Docker，但运行自己的调度程序。

“事实证明，这太难了，”他争辩道。“因此，将 EC2 容器服务与新的调度程序结合使用，使他们能够专注于构建他们想要构建的应用程序，而不是关注您实际上必须如何将它们分布到各个集群上。而且效果真的很好。”

这一声明表明了 AWS 对其竞争对手调度服务的立场。

我们问 CoreOS CEO Polvi，Kubernetes 和 CoreOS 会给 AWS 用户提供哪些 EC2 不会提供的东西。

“最大的区别是，negative 可以在许多不同的环境中运行:云、数据中心或你自己的带虚拟机的笔记本电脑，”他回应道。“ECS 仅在 AWS 上提供。此外，构造是基于 KubernetesECS 基于他们自己特定的 AWS 工具。”

Polvi 补充说，虽然这个新文档是公开的，而且显然已经完成，但 structural 本身仍处于预览模式。“我们正接近全面上市，”他说。“敬请期待。”

新的 Stack 将在整个星期内报道亚马逊在拉斯维加斯举行的 re:Invent 2015，其中包括来自 Alex Williams 的播客和来自新 Stack 团队的报道。

CoreOS 和 Docker 是新堆栈的赞助商。

专题图片: [cea +](https://www.flickr.com/photos/centralasian/) 的《[【C】马克·夏迦尔——马戏团场景(1958)](https://www.flickr.com/photos/centralasian/5471338661/in/photolist-9ku3nc-bEQX5b-g3XDw6-cu3MRQ-9rTMj1-bfJfiD-iymky6-9sgfe9-qAcSaU-rTNEca-dQrTU4-9AysWk-9sdexn-ciTnXf-dugcss-6XbYNQ-6gTUUv-8YjfoK-cu3Mkm-cu3MZd-saU8P3-qxZ7PL-agwq2e-6qTroa-rt5ADA-5BjJgv-agzhkf-9sa2pR-ffYQWs-e7RBV5-h6VQPJ-qjdEZu-6gY6nh-cu3Mbj-rT4wq8-5BjJ4Z-5BjJjK-sbTdRg-8N9p3w-rryrqn-uyCZjn-gnFaoP-o2YAZn-q7KQTS-9vkBjH-5P4Jwj-dZPsfS-9voGRq-8Wz9R2-cACiYS) 》由 2.0 授权于 [CC 下。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>