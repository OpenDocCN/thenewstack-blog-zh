# 德国电信如何利用 GitOps 管理边缘基础设施

> 原文：<https://thenewstack.io/how-deutsche-telekom-manages-edge-infrastructure-with-gitops/>

[](https://www.linkedin.com/in/mkress/)

[Mike Kress](https://www.linkedin.com/in/mkress/)

[Mike 是一位经验丰富的高管，领导 Weavework 的电信业务发展。Mike 正与我们的电信投资者、合作伙伴和客户密切合作，宣传和实施 GitOps，这是一套用于部署和管理云原生应用和基础架构的现代最佳实践。](https://www.linkedin.com/in/mkress/)

[](https://www.linkedin.com/in/mkress/)[](https://www.linkedin.com/in/mkress/)

德国电信(DT)是德国和欧盟的领先电信公司，拥有超过 2.42 亿移动用户和 1000 亿欧元的年收入。DT 的运营规模是当今很少有公司能做到的。特别令人感兴趣的是他们对边缘计算的尝试，以及他们如何用一个小团队大规模管理他们的边缘基础设施。

边缘计算，顾名思义，就是在尽可能靠近最终用户的地方进行尽可能多的处理。这可能意味着在本地服务器、附近的服务器甚至直接在设备上处理数据。目标是减少延迟并改善用户体验。边缘计算是物联网和 5G 的关键技术，不仅仅是电信公司。

作为世界上最大的电信公司之一，德国电信需要利用边缘计算的力量为其庞大的客户群提供先进的移动服务。虽然这是一个值得追求的目标，但它的每一步都伴随着复杂的挑战。

[Vuk Gojnic，](https://twitter.com/vukgojnic)德国电信负责 Cloud Native / Kubernetes 平台的班长负责该项目，并为应用所有者提供支持。这些应用程序所有者进一步向供应商和应用程序开发者提供基础设施服务。

## **采用平台法**

Gojnic 很快意识到，试图以传统方式构建这个系统是徒劳的，特别是考虑到他的大约 10 到 15 人的团队已经忙于管理其他基础设施项目。为了取得成功，这种边缘平台需要一种新的方法，这种方法可以减少手动操作，并且不会影响性能和数据安全性等基本要求。

Gojnic 决定采用平台方法来构建 DT 的边缘基础设施，这是过去几年来,[DevOps 状态](https://puppet.com/resources/report/2021-state-of-devops-report)报告推荐的策略，是高绩效 devo PS 团队的关键指标。它涉及到构建一个内部开发人员平台，在这个平台上，资源可以被模板化，并且可以很容易地被开发团队所使用。像 Gojnic 这样的专门平台团队负责管理和维护平台。对于平台团队来说，好处是减少手动重复工作，并能够构建可轻松扩展到整个组织的解决方案。

新平台的架构将支持数千种应用和服务，每秒处理数十亿次事件。该平台将在超过 10，000 个 Kubernetes 集群上运行，分布在 10 个数据中心和 10，000 个边缘位置。

## **GitOps 管理平台**

Gojnic 的团队从 Weaveworks 的团队那里获得了帮助，帮助他们遵循 GitOps 方法来构建这个平台。GitOps 是一种现代软件交付实践，它依赖 Git 存储库作为唯一的事实来源。它支持声明式基础设施等关键原则，其中系统的每个部分都在 Git 存储库中描述。它利用 Git 的内置版本控制功能来跟踪所有变更并自动实现合规性。此外，它使用像 Flux 这样的开源工具来发现生产系统偏离 Git 中声明的状态，并将系统恢复到原始状态。这些实践确保边缘基础设施等系统能够以可扩展的现代方式构建，从而减少工作量，提供所需的性能，并且不会影响重要的安全性和合规性要求。要开始使用 GitOps，我们建议[下载 Weave Gitops Core](https://www.weave.works/product/gitops-core) 。

## **与达斯希夫一起在边缘运输**

DT 建造了这个新平台，并将其命名为 [Das Schiff](https://github.com/telekom/das-schiff) ，德语意为“船”。它甚至开源了该平台，将其描述为“在 GitOps 循环中管理的自治云本地基础设施(self)的建立和监管引擎。”

Das Schiff 的核心是 Flux CD 工具，用于管理平台持续交付的所有方面。深入挖掘一下，Flux 正在使用的关键组件是其 Kustomization 控制器和 Helm 控制器。Kustomization 控制器监视对集群所做的更改，为这些更改生成 YAML 文件，生成 Kubernetes 清单，并按照定义的顺序运行管道。Helm 控制器从对象生成 Helm 图表，并自动执行测试、回滚和卸载软件包等操作。Das Schiff 还使用 Prometheus 和 Logstash 来监控时序指标和日志。你可以在这篇 [WeaveWorks 博客文章](https://www.weave.works/blog/multi-cluster-kubernetes-on-microvms-for-bare-metal)中读到更多关于达斯·希夫的建筑的内容。

Das Schiff 使 DT 团队能够在物理机上配置特定于边缘的硬件，如无线电或网络适配器和硬件加速器。它支持边缘的虚拟网络，以支持 DT 推动 5G 和边缘处理。Das Schiff 还支持“混合模式”，团队可以在 Kubernetes 集群中运行虚拟化和非虚拟化裸机节点的组合。考虑到边缘的资源限制，Das Schiff 使用 [AWS 鞭炮](https://aws.amazon.com/blogs/aws/firecracker-lightweight-virtualization-for-serverless-computing/)来提供微卷以显著减少池中节点的足迹。

虽然这是一项巨大的成就，但它并非没有挑战。由于其云原生架构，新平台是大规模分布式的，并且极具动态性。然而，通过对其方法进行战略性规划并利用平台方法和 GitOps，DT 能够构建一个可扩展到边缘并支持不同团队和业务需求的系统。

## **结论**

如果你对 DT 的这个项目感兴趣，或者如果你的组织正在推动 5G 网络或边缘计算，我鼓励你查看 GitHub 上的 [Das Schiff 项目](https://github.com/telekom/das-schiff)。要了解更多关于 GitOps 如何帮助 5G 部署的信息，请访问我们的网站[。](https://www.weave.works/solutions/telco/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>