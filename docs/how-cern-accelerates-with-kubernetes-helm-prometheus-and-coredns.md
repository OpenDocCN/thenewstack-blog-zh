# CERN 如何利用 Kubernetes、Helm、Prometheus 和 CoreDNS 加速

> 原文：<https://thenewstack.io/how-cern-accelerates-with-kubernetes-helm-prometheus-and-coredns/>

欧洲核子研究中心(CERN)是欧洲的核研究组织，以其粒子加速器以及亚原子粒子、反物质和其他粒子物理相关研究的实验和分析而闻名。欧洲核子研究中心(CERN)也是[万维网(WWW)](https://en.wikipedia.org/wiki/World_Wide_Web) 诞生的地方。

CERN 的研究员 [Ricardo Rocha](https://ch.linkedin.com/in/ricardo-rocha-739aa718) 说，CERN 现在总共管理着超过 500 Pb——超过 1 EB 的一半——随着一个新的加速器上线，预计十年后总数将达到 5000 Pb。

在这一集的[新堆栈分析师](/podcasts/analysts)中，我们从 Rocha 那里了解到 CERN 如何在未来几年内适应管理 10 倍于现在的数据。

[CERN 如何用 Kubernetes、Helm、Prometheus 和 CoreDNS](https://thenewstack.simplecast.com/episodes/how-cern-accelerates-with-kubernetes-helm-prometheus-and-coredns) 加速

[Alex Williams](/author/alex/) ，The New Stack 的创始人和发行人，与[Cloud Native Computing Foundation](https://uk.linkedin.com/in/cheryljhung)(CNCF)的生态系统副总裁 Cheryl Hung 和 [Spotify](https://www.spotify.com/us/) 的高级职员工程师 [Dave Zolotusky](https://www.linkedin.com/in/dzolotusky/) 共同主持了播客。

Kubernetes 在 CERN 的基础设施中扮演着重要角色。对于集群的管理，CERN 使用自己的私有云本地服务 [OpenStack](https://www.openstack.org/) 提供。Rocha 说，通过在 OpenStack 上部署 Kubernetes 集群，CERN 获得了“与公共云非常相似的体验”。这包括将其 Kubernetes 集群与云提供商集成，以实现自动扩展及其存储系统。OpenStack 还帮助 CERN 管理其遗留系统。

“我们为用户提供的是 Kubernetes 即服务的体验，”Rocha 说。

虽然允许用户按照自己的意愿使用工具和脚本迁移到 Kubernetes 可能很诱人，但 Helm 可以为这个过程增加纪律性和更严格的控制。Rocha 解释说，CERN 为板载用户提供内部培训，以在 Helm 上迁移他们的工作负载。

“当我们第一次向人们介绍 Kubernetes 时，让事情运转起来是非常诱人的，”Rocha 说。“但我们需要更多的东西来确保事情是可维护的…头盔是一个非常好的选择。”

罗查说，Helm 还在 CERN 采用 [GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 以及确保“在 git 中保存结构良好的定义”的能力中发挥了作用，同时消除了用户“直接接触集群”的需要。“这是我们掌舵之路的下一步，”罗查说。

采用正确的监控工具也很重要。对于监控，CERN 很大程度上依赖于[普罗米修斯](https://prometheus.io/)的集群度量，默认情况下与集群集成在一起。用户也可以添加他们自己喜欢的自定义指标。“这对于基于普罗米修斯的部署来说是相当标准的，”Rocha 说。

CERN 的基础设施是集中管理的，其网络层中只有几个孤立的租户和数据环境。它的 DNS 基础设施管理也由专门的团队集中管理。

有了 CoreDNS，CERN 的 DevOps 团队在初期经费上确实有些困难。“我们在根据集群内的请求数量进行扩展时遇到了一些问题。但是我们达到了一个点，它基本上可以自动缩放到我们需要的实例数量，”Rocha 说。“而且，[这些问题]基本上消失了。这不再是我们曾经触及的话题，这是一个好迹象。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>