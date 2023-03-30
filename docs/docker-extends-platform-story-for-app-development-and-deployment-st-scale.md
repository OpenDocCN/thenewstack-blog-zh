# Docker 有一个新的编排平台，但 API 还不能很快推出

> 原文：<https://thenewstack.io/docker-extends-platform-story-for-app-development-and-deployment-st-scale/>

在今天的 DockerCon Europe 上，Docker，Inc .宣布了一套新的开放平台和编排服务，用于大规模的连续生命周期应用程序开发和部署。

此次发布还包括一系列附带的开放 API 中的第一个，旨在帮助生态系统合作伙伴创建与新的 Docker 编排产品保持一致并集成的产品和服务。在开发者的高需求中，未来 API 的时间线不是几个月，这可能会让一些生态系统合作伙伴失望，他们已经等待了一段时间，以获得将使他们的生态系统产品与 Docker 引擎集成的“插件 API”。

今天宣布的三项新编排服务旨在为用户提供 Docker 应用程序开发、部署和生产环境，这些环境针对机器、集群和分布式架构环境进行管理。

首席执行官 Ben Golub 在本周的一次采访中表示，以前的应用程序是在几个独立的容器上运行的。现在，开发人员在大量服务器上运行多个容器，并且可能跨不同的数据中心。这意味着对编排、集群、联网和存储功能的更深需求，这些功能可以以可移植的方式按主题执行。

Docker 高管认为，其服务的创建是对 Docker 集装箱化方法快速增长的必要回应。Docker 在其公告中引用了由 18，000 个工具和 60，000 个 Docker 化应用组成的生态系统，称 Docker 在应用环境中的快速普及是“转型转变”的一部分，这种转变反过来又创造了对自适应编排功能的需求。开发和 DevOps 环境已经从“移动缓慢的整体式应用程序”转变为“停靠式分布式应用程序”。因此，开发人员需要将多容器、多主机的应用程序堆叠在一起，这些应用程序可以独立于底层的主机基础设施工作。新的 Docker 编排服务旨在通过通用的用户界面和工具提供这种灵活性。

### **仔细查看编排产品**

#### **对接机**

Docker Machine 提供单个用户界面，使开发人员能够准备运行 Docker 化分布式应用程序的主机。从用户界面平台，开发人员可以在任何 Linux 主机上提供 Docker 引擎，无论是裸机、虚拟机还是云中。Docker 表示，这将供应过程加快到了几秒钟。

#### **码头工人群**

Docker Swarm 可在任何类型的混合环境中，跨主机集群自动优化应用程序工作负载。同样，单一用户界面允许开发人员和开发运维人员使用 Docker Swarm 的自动集群来优化工作负载，还可以设置自定义约束来管理更复杂的工作负载放置。

#### **Docker 撰写**

Docker Compose 支持跨多个容器的编排。例如，数据库、web 和负载平衡容器都可以组装到跨多个主机的分布式应用程序中。编排是通过在 YAML 文件中表达容器依赖关系，并通过 Docker 用户界面进行管理来组成的。

**开放 API，支持生态系统合作伙伴创造互补产品**

随着服务的推出，Docker 还发布了面向 Docker Machine 的开放 API，面向 Swarm 和 Compose 的 API 预计将于 2015 年上半年发布。

开放的 API 将是 Docker 用户能够定制他们的编排和使用他们自己选择的生态系统工具的基本方式。最初，编排服务带有 Docker 自己的默认实现(Docker 称之为“包含电池”)。

在新的一年，当 Swarm 和 Compose 的 API 可用时，这将意味着开发人员可以创建替代 Docker 设置的实现配置(Docker 称之为“电池可拆卸”)。例如，对于 Docker Swarm，开发人员将能够使用生态系统合作伙伴的产品，这些产品可以基于 Swarm 功能集创建特定的集群或调度服务。生态系统合作伙伴将使用 Swarm API 来创建这样的产品。

类似地，API 将使开发人员能够通过单个容器使用编排服务。Docker 指出，虽然大多数社区使用多容器，但单容器用例已经增加了两倍，Docker 的目标是继续支持这种用例。

虽然所有三个编排服务都在 alpha 版本中，但生态系统合作伙伴将无法为 Swarm 或 Compose 创建新的工具产品和服务，直到 API 可用。

但是 Docker 在支持生态系统通过 API 开发补充产品方面没有很好的历史，所以生态系统提供商将编排服务的功能集集成到他们的工具中的潜在六个月等待可能会遇到一些焦虑。

例如，生态系统合作伙伴 [Tutum](https://thenewstack.io/tutum-offers-docker-container-management) 已经在等待插件 API 的消息，这些 API 在最近的 [Docker 治理顾问委员会](https://thenewstack.io/managing-growth-and-fostering-an-ecosystem-in-the-open-docker-reports-on-engagement-and-performance-metrics)上被标记为需要开发。

“我们最初听说 Docker 将是一个支持 API 的系统，但我们还没有看到这一点。因此，我们有兴趣听听如何处理这些原料药，”首席技术官费尔南多·梅奥在欧洲码头博览会前几天说。

“如果我不得不在 Docker 中做我的替代工作，那么它就不是真正的替代。它将生态系统解决方案降级为第二层工具，”Tutum 首席执行官 Borja Burgos 补充道。当时，Burgos 正在谈论 Docker 进军存储和网络功能，但该评论也与生态系统合作伙伴创建替代 Docker 默认编排配置的方法的能力相关。

### Docker 应该也是编排平台吗？

在 DockerCon Europe 之前，Red Hat 的高级战略总监 Lars Herrmann 承认需要更多的容器编排服务，但不确定 Docker 是否应该提供此类服务。

**11 月初，红帽测试版发布了[红帽企业版 Linux 7 原子主机](http://www.redhat.com/en/about/blog/small-footprint-big-impact-red-hat-enterprise-linux-7-atomic-host-beta-now-available)，使开发者能够运行不可知的应用容器。在能够运行 Docker 容器的同时，新版本同样关注于让 Linux 容器得到更广泛的使用。**

 **Herrmann 说:“Docker 是一个伟大的项目，但 Docker 公司对他们想把技术带到哪里有一定的愿景，所以在某些方面我们肯定能认识到 CoreOS 现在已经做了什么。

“容器是 Linux 操作系统的核心功能，也是 Docker 的核心功能，它使与 Linux 容器的交互变得容易。Linux 容器可以在没有 Docker 的情况下运行，但 Docker 使它变得更容易，这是 18 个月前的颠覆性时刻。Docker 无疑有助于加快开发工作流程。

“当时我们做出与 Docker 合作的决定，Docker 的任务是开集装箱。我们的工作是将 Docker 的颠覆性潜力与 Linux 容器服务的健壮性结合起来。尽管对 Docker 有如此多的宣传和兴奋，但我们仍处于这一旅程的开始。在过去的六个月中，我们已经看到了很多在混合环境中编排复杂应用程序的创新。让许多部件相互对话是非常复杂的。

Herrmann 说:“我们倡导一种更加模块化、松散耦合的同类最佳服务，这种服务可以集成，而不必将每一项功能都驱动到一个单一的代码基中，最终成为一个单一的二进制代码。”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**