# Docker 发布编排工具包

> 原文：<https://thenewstack.io/orchestration-toolkit-release-aims-prove-dockers-commitment-flexibility-community-ecosystem/>

Docker 今天发布了其承诺的编排工具包，该工具包于 12 月在 DockerCon Europe 上发布。这三个编排工具旨在展示 Docker 跨数据服务器托管基础设施的“100%可移植性”，包括支持混合云架构运行容器化的分布式应用。

去年在阿姆斯特丹宣布编排工具包时，Docker 间接回应了最初的社区关注，强调开发人员将拥有控制多容器、多主机应用程序如何在生产中构建、运输和运行的自由。

这三个编排工具是:Docker Machine、Docker Swarm 和 Docker Compose。Machine 和 Swarm 是测试版，而 Compose 是作为 1.1 版本发布的。

## 码头机器

[Docker Machine](https://docs.docker.com/machine/) 支持一个命令自动配置主机基础架构和安装 Docker 引擎。Docker，Inc .的企业营销副总裁 David Messina 说，它非常适合混合环境。对于每个数据托管基础架构提供商，系统管理员和运营人员“不必学习一套单独的命令来启动 Docker 容器应用程序”。梅西纳说，有了 Docker Machine，用户可以使用一个统一的命令来跨越基础设施。测试版提供了 12 个驱动程序，包括 Amazon EC2、Google Cloud Engine、Digital Ocean 和 VMware。

Docker 还无法量化他们的用户数量，这些用户可能希望在混合公共云架构中编排分布式应用程序，但 Messina 承认，“最终，这是更广泛的目标:机器无疑是实现这一目标的关键因素。”

## 码头工人群

[Docker Swarm](https://docs.docker.com/swarm/) 是一个集群和调度工具，可以根据应用的生命周期阶段、容器使用和性能需求自动优化分布式应用的基础设施。

“Swarm 有多种模型来确定调度，包括了解特定容器如何具有特定的资源需求——计算和内存是最明显的例子，”Messina 说。“Swarm 将使用一种调度算法来决定它应该在哪个引擎和主机上运行。Messina 给出了一个例子，在某些应用程序中，相似性可能是一个重要的考虑因素——某些容器可能最好在相同的主机上运行。

“Swarm 的核心方面是，当你使用多主机、分布式应用程序时，你希望保持开发者体验并实现完全的可移植性。Swarm 提供了这种连续性，但是您还希望具有灵活性:例如，能够为您正在使用的应用程序使用特定的集群解决方案。这确保了集群功能可以从笔记本电脑一直移植到生产环境中。”

## 保持群体的灵活性

Swarm 版本还附带了一个 Swarm API，供生态系统合作伙伴创建替代或附加的编排工具，这些工具可以覆盖 Docker 的 Swarm 优化算法，以实现更细微的特定用例。

这就是 Docker 称之为“包含电池但可更换”的方法。一些用户可能习惯于使用 Docker Swarm 来识别多容器、分布式应用程序架构的优化集群。其他人将希望使用 Swarm 的集群和调度部分来设置自己的参数，而还有一些人将期待生态系统合作伙伴的替代编排优化产品来推荐最佳的集群组合。

Apache Mesos 的公司赞助商 Mesosphere 是第一个使用 Swarm API 创建替代优化产品的 Docker 生态系统合作伙伴。其他人预计来自亚马逊、谷歌、Joyent 和微软 Azure。

“在 Swarm 首次宣布后，Mesosphere 和 Docker 走到了一起，因为两家公司的工程师立即看到了这两个项目如何合作，”Mesosphere 的营销副总裁 Matt Trifiro 说。

Docker 创始人兼首席技术官 Solomon Hykes 指出，Mesosphere 的技术是在 DockerCon EU 大规模运行容器的黄金标准(参见中的 35 分钟):

https://www.youtube.com/watch?v=sGWQ8WiGN8Y&t=13

Trifiro 表示，对于大规模运行的分布式应用程序，Mesosphere 的编排工具比“内置电池”版本的 Swarm 更适合识别优化的集群和调度编排:

他说中间层虫群整合有两点需要强调:

1.  **超大规模:**对于任何希望在高度自动化的环境中跨数百或数千台服务器(无论是在本地还是在云中)大规模运行容器的公司来说，Mesosphere 的技术是唯一一个经过大规模验证的公开可用的容器编排系统——在 Twitter、Groupon 和网飞等公司以及一些最大的消费电子和金融服务公司运行数百万个容器。
2.  **多租户工作负载多样性:** Mesosphere 的技术是组织在同一集群上以高度灵活的方式运行 Docker Swarm 工作负载和其他类型工作负载的唯一方法。例如，您可以在单个中间层集群上同时运行 Cassandra、Kafka、Storm、Hadoop 和 Docker Swarm 工作负载，所有这些工作负载共享相同的资源。这大大提高了群集资源的使用效率，并大大降低了运营成本和复杂性。

## Docker 撰写

在 Swarm 上运行的多容器应用也可以使用 Docker 的新[合成工具](https://docs.docker.com/compose)来构建。合成工具使用声明性 YAML 文件来维护所有应用程序容器的逻辑定义以及它们之间的链接。然后，可以动态更新构建的分布式应用程序，而不会影响编排链中的其他服务。

## 潜台词:我们可以和别人玩得很好

Docker 发布 Swarm 及其 Swarm API 的方式有助于缓解[当 Docker 在 12 月](https://thenewstack.io/docker-extends-platform-story-for-app-development-and-deployment-st-scale/)首次提出这些解决方案时出现的一些社区担忧。Docker 在为社区合作伙伴创造生态系统经济方面发挥了重要作用，这些合作伙伴开发了一些产品，增强了开发、监控、持续改进、QA 和其他需要在 docker 化的分布式应用环境中解决的流程。一些社区成员最初担心直接从 Docker 创建编排工具会过于严格地执行“Docker 做事方式”。社区成员担心，与其像 Mesosphere 那样能够创建一个集成产品，竞争的编排工具将需要使用一个精心设计的工作区，以便提供一个替代 Docker 的产品。

Docker 一再强调编排公告的 100%可移植性和 Swarm API 的“包含电池但可交换”特性，以巧妙地解决这个问题。

“如果你看看编排公告，所有这些工作和规划集成，现实是 Docker 编排工具特别开放与生态系统合作伙伴的合作，”Messina 说。“Docker 社区需要构建多容器和多主机的分布式应用——这是我们社区的绝对要求。这些工具以一种极其灵活的方式构建，并使用 API 进行设置，允许合作伙伴开发高级和丰富的服务。这里的整个想法是，我们希望保持开发体验和 100%的可移植性。社区希望如何登陆这些集装箱和优化集群是为自由选择而设置的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>