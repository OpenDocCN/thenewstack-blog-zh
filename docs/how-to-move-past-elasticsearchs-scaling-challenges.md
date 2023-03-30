# 如何克服 Elasticsearch 的规模挑战

> 原文：<https://thenewstack.io/how-to-move-past-elasticsearchs-scaling-challenges/>

[LogDNA](https://logdna.com/) 赞助本帖。

 [瑞安·斯塔茨

Ryan Staatz 是 LogDNA 的 DevOps 主管，他负责将公司的基础架构从虚拟机迁移到 Kubernetes。他的团队与 IBM 等大型企业合作，建立跨部署的稳定性，扩展 LogDNA 的合规性库，并提高大规模的可观察性。Ryan 经常介绍 Kubernetes 上的伸缩弹性搜索、利用多云基础架构应对挑战、在裸机上运行 Kubernetes 以及管理数十个独立的生产环境。在加入 LogDNA 之前，Ryan 曾在 WhatsApp 等企业公司工作，并一直热衷于为初创公司做出贡献。Ryan 拥有斯坦福大学的人类生物学学士学位。](https://www.linkedin.com/in/rcstaatz/) 

数据搜索和分析是现代应用的重要组成部分。

为什么？

企业需要能够实时存储和查询从用户、应用程序、基础架构和其他来源收集的数据。但是，这些来源生成的数据可能会达到相当大的数量，尤其是随着企业的发展。

Elasticsearch 是一个基于 Apache Lucene 的开源搜索和分析引擎，是解决这一数据问题的流行解决方案。它之所以受欢迎，部分是因为它能够接收非结构化数据，并且在发生故障时能够通过集群恢复。作为开源弹性堆栈的一部分，它已经成为许多企业的默认数据分析工具，包括 LogDNA。随着企业生成和使用的数据量不断增加，这些限制可能会很快成为增长的障碍。

在 LogDNA，我们开发了一个将 Elasticsearch 扩展到 Pb 级的解决方案。我们的解决方案利用 Kubernetes 在许多云和内部平台上自动部署、扩展和维护 Elasticsearch 节点。

在本帖中，我们将概述这种方法，并提供关于我们用来实现规模级别的配置、技术和优化的详细信息。

## 为什么是 K8s

Kubernetes 已经成为世界领先的容器编排平台。它允许团队自动化工作负载调度、部署和扩展。LogDNA 在许多不同的平台上广泛使用 Kubernetes。我们利用 Kubernetes 的所有特性和许多可用的工具来确保我们的环境尽可能地可复制。为了管理我们每天处理的大型数据集，并为我们的客户提供快速搜索选项，我们还运行了 Elasticsearch。作为 Elasticsearch 和 Kubernetes 的粉丝，我们希望通过将 Elasticsearch 打包和部署为一个容器化的应用程序来结合这两种解决方案。

然而，在 Kubernetes 上运行 Elasticsearch 并不容易。在任何大规模平台上运行 Elasticsearch 都很困难，因为存在一个临界点，在这个临界点上，传入数据会使节点过饱和，运营团队需要小心管理数量庞大的索引和碎片，而不会造成数据碎片。然而，在 Kubernetes 上，Elasticsearch 需要额外的配置和管理，这是由于容器的瞬时性质以及需要持久的、独立的卷来使集群有状态或者能够从重启到重启保持其历史的记忆。

如果您能够在 Kubernetes 上成功地启动和运行 Elasticsearch，您将获得几个好处。Kubernetes 在硬件上扩展工作负载和分配负载的固有能力使您能够快速高效地管理大得多的数据集。此外，您可以利用版本控制和代码审查来管理您的配置，从而确保轻松再现环境。最后，当您可以使用 Kubernetes 本身可用的工具时，这种大型集群的维护会容易得多。

## 如何部署

在 Kubernetes 上运行 Elasticsearch 时，您需要考虑许多因素。从了解硬件要求和本地存储与网络存储之间的差异，到确定您的容错能力和多站点数据访问设置，不一而足。

说到硬件，你真的有两个选择:虚拟机或裸机。虚拟机给你带来更多的灵活性和更低的维护成本，但是它们很贵。另一方面，裸机服务器要便宜得多，但是需要更多的维护，而且很难在短时间内部署。在这两种情况下，你都可以自己运行 Kubernetes。如果您选择虚拟机，您还可以获得一个托管的 Kubernetes 平台。

这两种硬件选项之间的另一个巨大差异与存储有关。虚拟机通常需要网络存储。网络存储通常在使用 Kubernetes 的主机提供商上“正常工作”,当您可能被系统维护工作压得喘不过气来时，这可能是一个很大的吸引力。此外，使用计划要容易得多，因为存储不会与特定节点纠缠在一起，这意味着如果某个节点发生故障并重新启动，存储不会受到影响。网络存储的性能受到其所连接的网络的速度和可用性的限制。由于网络连接的需要，并且由于它通常也由提供商管理，网络存储的成本也高于本地存储。

另一方面，裸机选项通常涉及本地存储。对于 Kubernetes 来说，本地存储大多数时候都不是即插即用的选项。它需要管理人员为 Kubernetes 集群启动并运行该存储。此外，根据定义，本地存储连接到特定的节点。如果该节点出现故障，存储也会出现故障。

另一方面，本地存储要快得多，因为它不依赖于网络的连接速度。这样一来，本地存储也便宜了很多。出于性能原因，我们选择了本地存储，并决定与一家专门为裸机上的 Kubernetes 集群提供动态本地存储的供应商合作。使用供应商还回避了基本 Kubernetes 本地存储的问题，如缺乏加密，以及 DIY 解决方案，如快速配置磁盘的困难。

## 如何管理

所有 Kubernetes 对象都是使用 YAML 文件定义的。在 LogDNA，我们使用 [ConfigMaps](https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/) 来管理集群范围的配置设置，使用 [StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) 来定义 Elasticsearch Pods。我们的配置图用于引导每个 pod 并配置所有必要的变量，以确保我们的集群保持正常运行。另一方面，StatefulSets 确保我们的 Elasticsearch pods 按照 Elasticsearch 的要求继续在主/节点关系中运行。我们实际上运行三个独立的状态集:主节点、热节点和冷节点。热节点处理活动索引，冷节点处理较旧的、资源不太密集的索引。

当计划如何管理系统时，配置图模板将是最有用的工具，尤其是当您要考虑多个环境时。我们系统的模板使用标准的 Go 模板语法来填充各种字段，以匹配每个环境或定制设置。模板化还具有允许我们使用语义版本控制的优势。这确保了当我们运行部署或管理我们的集群和版本控制时，每个人都在同一页面上，这允许我们像管理我们的部署一样管理我们的配置。

为了提高 Kubernetes 上的 Elasticsearch 系统的弹性，您应该考虑您的容错需求以及数据驻留和数据访问之间的平衡。我们的状态集帮助我们跨环境管理这些考虑事项。我们使用反相似性规则来平衡我们的 pod 在数据中心和相似性区域中的分布，以及我们运行的各种托管提供商，这提高了我们在这些提供商网络中的容错能力和可用性。

Kubernetes 上的 Elasticsearch 尤其需要一个具有高可用性的系统，因为它与存储和 Kubernetes 服务相集成。我们的 Elasticsearch 状态集经过优化，以确保 Elasticsearch pods 在服务器上获得优先权，这一点至关重要，因为 Elasticsearch 非常耗费资源。最后，我们通过默认采用滚动更新策略来确保始终有一个弹性搜索平台在运行，从而减少任何新部署对我们的基础架构和客户的影响。

将来，我们希望在 Kubernetes 上部署 Elasticsearch 会变得更加容易。最近，Elastic 在 Kubernetes (ECK)上发布了包含整个弹性堆栈的[弹性云。ECK 是建立在 Kubernetes](https://www.elastic.co/blog/introducing-elastic-cloud-on-kubernetes-the-elasticsearch-operator-and-beyond) [Operators](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/) 之上的，可以用来自动化定制资源和部署的维护。Elasticsearch 和 Kubernetes 的最新版本也为[联合搜索](https://www.elastic.co/blog/tribe-nodes-and-cross-cluster-search-the-future-of-federated-search-in-elasticsearch)和抢占提供了改进的支持。两个项目更新的速度使得评估、测试和执行升级成为一个连续的过程。

要了解更多关于我们如何在 Kubernetes 上扩展 Elasticsearch 的信息，请查看 LogDNA 举办的相应网络研讨会。

赞助新堆栈的云本地计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>