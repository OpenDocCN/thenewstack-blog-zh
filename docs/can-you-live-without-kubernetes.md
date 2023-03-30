# 没有 Kubernetes 你能活吗？

> 原文：<https://thenewstack.io/can-you-live-without-kubernetes/>

容器提供了一种将应用程序包装到它自己的独立包中的方法，包中包含了成功运行所需的一切，比如库和运行时。显然，您可以在单个主机上运行容器，使用 Ansible 或 Chef 之类的工具进行部署，但是这种方法越来越少见了。因为实际上，大规模运行容器的关键是编排。

至少，orchestrator 使您能够放置容器，在主机出现故障时迁移它们，并提供配置管理、网络配置和存储等附加服务。

Kubernetes (K8s)显然是大众市场的领导者和自然的默认选择，但它需要大量的时间和深刻的理解来部署、操作和故障排除。鉴于其复杂性，至少值得考虑它是否是您组织的正确选择。

另一个选择，特别是如果你打算部署到公共云上，只需从主要的云供应商之一选择托管的 Kubernetes 服务，如[微软的 Azure Kubernetes 服务(AKS](https://azure.microsoft.com/en-gb/services/kubernetes-service/) )、[亚马逊弹性 Kubernetes 服务(EKS](https://aws.amazon.com/eks/) )或[谷歌 Kubernetes 引擎(GKE)](https://cloud.google.com/kubernetes-engine) 。

对于使用混合云方法或内部部署的企业来说，Kubernetes 发行版，如 [Red Hat 的 OpenShift](https://www.openshift.com/try?utm_content=inline-mention) 很有意义，它在 Kubernetes 已经提供的基础上增加了许多额外的功能，包括通过 OpenShift 路由器将来自外部世界的流量路由到您的 web 服务。

“使用 Kubernetes，你需要一种精心策划的体验，”独立技术顾问、奥莱利的《构建微服务》一书的作者萨姆·纽曼(Sam Newman)对《新堆栈》说。“所以你看到的是，企业组织要么正在构建自己的平台，要么正在购买 OpenShift。”

这种趋势很可能会继续下去，最终我们会发现自己可能在使用功能即服务(FaaS)或类似的抽象，并且很大程度上没有意识到这反过来是在使用 Kubernetes。但是，还有哪些其他编排选项值得考虑呢？

## Nomad:比 K8s 更灵活

在 Kubernetes 的直接竞争对手中， [Hashicorp 的](https://www.hashicorp.com/?utm_content=inline-mention) [Nomad](https://www.nomadproject.io) 有一个非常灵活的模型来运行不同类型的应用程序工作负载——包括 Java 应用程序、虚拟机(VM)、Hadoop 作业等等——并允许大量的定制。

它与 Hashicorp 堆栈的其他成员——Vault 和 Consul——也很好地合作，因此尽管它可能不是大众市场的竞争对手，但如果[想要这种灵活性](https://thenewstack.io/conductor-why-we-migrated-from-kubernetes-to-nomad/)，它可能很值得一看。

纽曼告诉我们:“我最近与一个非常大规模的金融科技客户合作，他正在转向 Nomad。”“他们这样做的原因是，他们已经围绕内部抽象创建了他们的应用程序堆栈，并发现因为 Nomad 比 Kubernetes 允许更多的定制，就您可以运行的工作流而言，这有点像 Mesos 的做法，这更适合他们在公共云提供商上运行 Nomad，然后调整 Nomad 的内容以在其上运行他们现有的堆栈。”

另一个 Nomad 案例研究涉及游戏公司 Roblox。作为该公司游戏服务器从 Windows 到 Linux 大规模迁移的一部分，它选择 Nomad 作为其 orchestrator，使用 [Docker](https://www.docker.com/?utm_content=inline-mention) 作为容器运行时和 Terraform 进行配置。

Roblox 在其自己的裸机基础设施上运行其大部分服务，同时还战略性地利用多家云供应商，包括 Azure、[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)和谷歌云平台，以允许游戏公司尽可能靠近游戏玩家运行服务，无论他们位于何处。

Nomad 的灵活性是 Roblox 决定的关键。该公司[表示](https://www.hashicorp.com/case-studies/roblox)它“能够作为单一协调器，在迁移之前、期间和之后无缝地就地部署 Windows 和 Linux 工作负载。”

这一迁移使该游戏公司通过降低许可成本一年节省了 500 多万美元。同时，通过切换到运行 64 位，他们能够增加可用内存并支持更大的游戏实例。

此后，该公司在裸机和云中的 20 个集群中的 11，000 多个节点上部署了 Nomad，为 200 多个国家的 1 亿名月活跃用户提供服务，99.995%的正常运行时间。

## 你能跳过容器编排吗？

第二个值得考虑的选择是直接跳到 FaaS 的一个平台，比如 Azure Functions、AWS Lambda 和谷歌云功能。这些提供了一种非常简单的构建分布式系统的方法。

您部署了一些代码—一个函数—它处于休眠状态，直到某件事情发生，比如一个文件到达一个特定的位置或者一条消息到达一个队列，然后您的函数运行。完成后，它会关闭。

底层平台处理按需上下旋转这些功能，并且您可以在适当的地方运行多个副本。一些非常先进的工程将冷启动和热启动时间保持在可管理的水平，这种方式很难在现场复制。

您可以从该平台获得一定程度的健壮性，而无需自己做任何工作，并且您只需为正在运行的代码付费，这使得 FaaS 在您的负载较低或不可预测的情况下是一个特别好的选择。

BBC 走了这条路，将 Lambda 函数作为构成 BBC 网站的核心技术栈的一部分。整个系统混合使用 Lambda 和 EC2 实例，后者用于 Lambda 函数调用成本过高的情况。

也许一个更令人惊讶的 FaaS 案例研究是可观察性供应商。他们产品的核心是一个名为 Retriever 的定制数据库，灵感来自脸书的水肺。检索器没有固定的模式，除了时间戳之外没有预定义的索引，并且是多租户的。

它从 Kafka 主题中获取数据，将其存储在本地 SSD 或亚马逊 S3 中，并在 AWS Lambda 中实现了[数据读写层。对于供应商来说，实现起来很有挑战性，但是这样做将蜂窝的响应时间提高了一个数量级。](https://www.infoq.com/podcasts/aws-lambda-custom-database-retriever/)

然而，使用 FaaS 平台的缺点是，他们仍然感觉像是处于开发的早期阶段，因此他们确实有局限性。

您对给予每个运行时调用的资源的控制是有限的；函数通常在运行时间上有上限；大多数函数调用被认为是无状态的，尽管 Azure 持久函数支持暂停给定函数的状态，并允许它在调用停止的地方重新启动。

此外，如果基础设施的其他部分不能很好地扩展，FaaS 的动态扩展特性会带来问题。

## PaaS 选项

第三种选择是平台即服务(PaaS)，如 [Heroku](https://www.heroku.com) 、 [Platform.sh](https://platform.sh) 或 [Railway](https://railway.app) 。Heroku 确实为开发人员的生产力树立了标杆，但不幸的是，自从 Salesforce 收购了它之后，它并没有得到很大的发展。也就是说，如果您的应用程序能够适应给定的平台约束，PaaS 可能是一个有效的选择。

成立于 2015 年的 [Cycle.io](http://cycle.io) 是这个领域中一个有趣的、相对较新的供应商，位于 PaaS 和 orchestrator 之间。它不是基于 Kubernetes 构建的，也不使用 Docker。它也不兼容 Kubernetes API，但是它符合 OCI 标准，这意味着底层容器是交叉兼容的。

“我们开始构建 Cycle，”该公司的首席执行官兼创始人杰克·华纳(Jake Warner)告诉 New Stack，“因为我之前用 [OpenStack](https://www.openstack.org) 经历过这种情况，我长期打赌同样的事情也会发生在 Kubernetes 上:也就是说，在某个时候，人们会说‘嘿，我对能够定制一切不感兴趣。我希望它能正常工作。"

Cycle 采用了一种与供应商无关的容器编排方法，目前支持 AWS、 [Equinix Metal、](https://metal.equinix.com/?utm_content=inline-mention)和 [Vultr](https://www.vultr.com/) ，其他的也在路上。在我们的谈话中，华纳强调该公司经常提供自动更新——大约每 10 到 14 天一次——这甚至连管理 EKS 和 GKE 等 Kubernetes 服务的[都难以应对](https://docs.aws.amazon.com/eks/latest/userguide/update-cluster.html?utm_source=thenewstack&utm_medium=website&utm_campaign=platform)。相比之下，2021 年的一项数据狗研究报告称，最受欢迎的 Kubernetes 版本已经有 17 个月了。

除了自动更新，Cycle 的重点是对开发者友好，而不是像大多数平台那样专注于开发。此外，该团队旨在找到一个最佳点，在该点上，it 可以将复杂性保持在最低水平，同时仍然支持大多数用例，从而减少对大型运营团队的依赖。

目前，Cycle 的大多数客户都是种子和 A 轮初创企业，涉及多个行业。华纳说，他们的共同点是，他们已经壮大了整体工程团队，但还没有开始专门组建运营团队。通过 Cycle，华纳希望这些初创公司可能永远不需要传统的运营团队。

让一家基础设施公司放心的是，这家公司的运营很保守。“我们正在这里建立一个真正的企业，我们的客户想知道我们会在这里，”华纳说。“所以我们公司有一条规定，任何时候我们都有至少两年的跑道。这样，如果发生了不好的事情，我们有足够的时间去适应。”

Cycle 也许最好被认为是类似于 Nomad 的连续体的另一端；虽然该平台可以支持深入的技术使用案例，但它并不是最适合需要空隙部署、需要控制内存加密或具有非常特殊硬件要求的应用程序的组织。

它目前也没有 GPU 支持，尽管华纳告诉我们这将在下个月左右到来。

然而，如果您正在寻找一个能够让您拥有 PaaS 特性的解决方案，但是是在您自己的基础设施上，Cycle 可能值得一试。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>