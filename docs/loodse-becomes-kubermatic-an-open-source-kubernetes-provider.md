# Loodse 变成了 Kubermatic，一个开源的 Kubernetes 提供商

> 原文：<https://thenewstack.io/loodse-becomes-kubermatic-an-open-source-kubernetes-provider/>

虽然“loodse”是一个荷兰语单词，意思是在船上驾驶，但德国公司 Loodse 决定放弃原来的名字，转而采用其旗舰产品的名称， [Kubermatic](https://github.com/kubermatic) 。在更名的同时，多云和 edge Kubernetes 自动化提供商今天发布了其旗舰 Kubermatic 平台的 2.14 版本，作为在 [Apache 2.0 许可](https://www.apache.org/licenses/LICENSE-2.0)下的开源版本，该公司预计将提供一个企业版。

Kubermatic 首席执行官 [Sebastian Scheele](https://www.linkedin.com/in/sebastian-scheele/) 在一次采访中说:“这或多或少完全是 Kubermatic，现在是这样，在企业版中有一些小的附加功能。”。“使用开源版本，你可以从任何云提供商的单点运行它，但你只能在一个中央提供商上运行主服务器。如果你想在不同的提供商上运行它——就像你想在 Google 上拥有 worker nodes 和 masters，在 Amazon Web Services 上拥有相同的 worker nodes 和 masters 你要么需要安装两个 Kubermatic，要么需要企业版。企业版确实具有这种高度联合的功能，因此您还可以跨所有不同的安装进行联合监控。”

Scheele 解释说，企业版将作为订阅提供，但不是作为软件即服务提供。他说，相反，这是一种基于工人节点消耗的订阅。

Kubermatic 于 2016 年首次建立，基于使用 Kubernetes 运行 Kubernetes 的想法[，这与 Scheele 现在描述该项目的方式非常相似，尽管多云功能似乎从那时起就占据了更多的中心舞台。](https://thenewstack.io/running-kubernetes-kubernetes/)

“我们的想法是，将 Kubernetes 的管理真正抽象化，并在任何提供商上运行。最后，对我们来说，供应商应该像一个能源供应商。不管你是在 AWS 还是谷歌上。应该很容易旋转集群。他们为您提供基础架构，您获得基础架构，如果您出于任何原因(法律原因、合规性原因、性能原因)需要，您可以选择另一家云提供商。这应该很容易，你不需要长途跋涉来建立一个完整的新基础设施，因为你现在要去一个不同的提供商，”Scheele 解释说。

Kubermatic 从经典的[宠物与牛的类比](https://thenewstack.io/container-orchestration-scheduling-herding-computational-cattle/)开始，其中你想要将容器视为非特殊的和可丢弃的，而不是珍贵的和独特的。舍勒发现，库伯内特星团通常被当作宠物，而不是牛，Kubermatic 试图打破这种动态。

一路走来，Kubermatic 团队[一直是 Kubernetes 项目的主要贡献者](https://k8s.devstats.cncf.io/d/9/companies-table?orgId=1&var-period_name=Last%20year&var-metric=commits)，并在 Kubermatic 中构建了许多功能，包括支持所有主要的公共云提供商、自动化生命周期管理、使用 Prometheus 和 Grafana 进行日志记录和监控，以及添加一个中央自助服务门户来提供 Kubernetes 即服务。根据该公司的一份声明，Kubermatic 的最新版本增加了 Kubermatic 虚拟化，这是一种“本地 [KubeVirt](https://kubevirt.io/) 集成，用于通过 Kubernetes 同时管理容器化和虚拟化应用程序”。

至于 Kubermatic 的下一步发展方向，现在它是开源的，Scheele 说“现在，第一步是真正让 Kubermatic 开源，然后获得贡献者并围绕它建立一个社区。当我们看到它有意义，并且我们正在 Kubermatic 周围采用它时，我们肯定会考虑将其放入一个基金会，但这真的取决于一切的发展方向。”

关于 Kubermatic 2.14 的更多信息，该公司在一篇[博客文章](https://www.loodse.com//blog/kubermatic-open-source)中提供了细节，该项目可在 GitHub 上[获得。](https://github.com/kubermatic)

亚马逊网络服务是新堆栈的赞助商。

维基百科图片来自 Pixabay。

*目前新栈不允许直接在本网站评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>