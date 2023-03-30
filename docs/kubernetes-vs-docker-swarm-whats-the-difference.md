# Kubernetes vs. Docker Swarm:有什么区别？

> 原文：<https://thenewstack.io/kubernetes-vs-docker-swarm-whats-the-difference/>

Savaram rav Indra

Savaram rav Indra 是 Mindmajix.com 和 Tekslate.com 的内容贡献者。他热衷于撰写不同领域的文章，包括一些最具创新性和新兴的软件技术、数字营销和商业。

今天，[容器化](https://thenewstack.io/category/containers/)已经改变了我们部署软件和使用微服务的方式。随着使用基于 Linux 的虚拟容器开发应用程序的趋势不断发展，对虚拟容器的管理和部署提出了更高的要求。

Kubernetes 和 Docker 是容器编排的两个主要参与者。他们为自己开拓了声誉卓著的利基市场，巩固了他们在码头和集装箱生态系统中的地位。这两个工具都使您能够处理运行一个或多个服务的服务器集群。所以，在进入比较部分之前，让我们先来了解一下这两个工具。

## 什么是 Kubernetes？

Kubernetes 是 Google 创建的一个开源平台，用于[容器部署操作](https://thenewstack.io/how-to-deploy-a-container-with-docker/)，扩展和缩减，以及跨主机集群的自动化。这种生产就绪、企业级的自我修复(自动扩展、自动复制、自动重启、自动放置)平台是模块化的，因此可以用于任何体系结构部署。

Kubernetes 还在集装箱之间分配货物。它旨在通过将容器分组并将其命名为逻辑单元，来缓解工具和组件在私有云和公共云中运行应用程序所面临的问题。它们的优势在于易于扩展、不受环境限制的可移植性和灵活的增长。

[https://www.youtube.com/embed/XfBrtNZ2OCw](https://www.youtube.com/embed/XfBrtNZ2OCw)

视频

## 什么是 Docker Swarm？

作为一个平台，Docker 彻底改变了软件打包的方式。Docker Swarm，简称 Swarm，是一个开源的容器编排平台，是 Docker 的本地集群引擎。任何与 Docker 容器一起运行的软件、服务或工具在 Swarm 中都同样运行良好。此外，Swarm 使用与 Docker 相同的命令行。

Swarm 将一个 Docker 主机池变成一个虚拟的单一主机。Swarm 对于那些试图适应协调环境的人，或者那些需要遵循简单部署技术，但又有不止一个云环境或一个特定平台来运行它的人特别有用。

## Kubernetes 对 Docker Swarm

尽管这两个开源编排平台提供了许多相同的功能，但这两个平台的操作方式还是有一些基本的区别。以下是一些值得注意的要点。本节比较了 Docker Swarm 和 Kubernetes 的特性，以及选择其中一个平台的优缺点。

### 应用

Kubernetes: 可以利用服务(或微服务)、部署和 pod 的组合在 Kubernetes 中部署应用程序。

**Docker Swarm:** 在 Docker Swarm 中，应用程序可以作为微服务或服务部署在 Swarm 集群中。YAML(YAML 不是标记语言)文件可以用来识别多容器。而且，Docker compose 可以安装应用程序。

### 建立工作关系网

**Kubernetes:** 网络模型是一个平面网络，允许所有的豆荚相互交流。网络策略指定了 pod 之间的交互方式。扁平网络通常被实现为覆盖。该模型需要两个 CIDRs:一个用于服务，另一个用于 pods 获取 IP 地址。

**Docker Swarm:** 加入 Swarm 集群的节点为跨越 Docker Swarm 中每个主机的服务生成覆盖网络，并为容器生成仅主机的 Docker 桥网络。用户可以选择加密集装箱数据流量，同时在 Docker Swarm 中自行创建覆盖网络。

### 可量测性

**Kubernetes:** 对于分布式系统，Kubernetes 更多的是一个一体化的框架。这是一个复杂的系统，因为它提供了关于集群状态和一组统一的 API 的有力保证。这降低了容器扩展和部署的速度。

**Docker Swarm:** 与 Kubernetes 相比，Docker Swarm 可以更快地部署容器，这允许更快的反应时间来按需扩展。

### 高可用性

**Kubernetes:**Kubernetes 中的所有 pod 都分布在节点之间，这通过容忍应用程序的故障来提供高可用性。Kubernetes 中的负载平衡服务会检测不健康的 pod 并将其删除。因此，这支持高可用性。

Docker Swarm: 由于服务可以在 Swarm 节点中复制，Docker Swarm 还提供了高可用性。Docker Swarm 中的 Swarm manager 节点负责整个集群，并处理 worker 节点的资源。

### 容器设置

**Kubernetes:** Kubernetes 使用自己的 YAML、API 和客户端定义，这些定义都与标准 docker 定义不同。因此，您不能利用 Docker Compose 或 Docker CLI 来定义容器。在切换平台时，YAML 定义和命令需要重写。

**Docker Swarm:**Docker Swarm API 并没有完全包含 Docker 的所有命令，但是提供了 Docker 的许多熟悉的功能。它支持与 Docker 一起运行的大多数工具。然而，如果 Docker API 在某个特定的操作中有缺陷，没有一个简单的方法可以通过使用 Swarm 来解决。

### 负载平衡

**Kubernetes:**pod 通过服务公开，可以用作集群中的负载平衡器。通常，入口用于负载平衡。

**Docker Swarm:** Swarm 模式由一个 DNS 元素组成，该元素可用于将传入请求分发到服务名称。服务可以自动分配或在用户指定的端口上运行。

那么[库伯内特斯对 Docker](https://thenewstack.io/docker-versus-kubernetes-start-here/) 呢？我们对此也有想法。Kubernetes 和 Docker 是不同的软件包，为开发者提供了很好的工具。请阅读我们的文章，了解更多关于在项目中使用这两者的信息。

## 总之是 Kubernetes 还是 Docker Swarm？

Kubernetes 支持更复杂的更高要求，而 Docker Swarm 提供了一个简单、快速的解决方案。Docker Swarm 在喜欢快速部署和简单性的开发人员中非常受欢迎。与此同时，Kubernetes 被各种运行流行服务的知名互联网公司用于生产环境。

Kubernetes 和 Docker Swarm 都可以运行许多相同的服务，但在某些细节上可能需要稍微不同的方法。因此，通过[学习 Kubernetes](https://mindmajix.com/kubernetes-training) 和 Docker 并比较它们的各种特性，您可以决定为您的容器编排选择正确的工具。

*最后更新于 2022 年 11 月 29 日*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>