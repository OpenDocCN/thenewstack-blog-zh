# 码头工人，武装团队把集装箱带到边缘

> 原文：<https://thenewstack.io/docker-arm-team-up-to-bring-containers-to-the-edge/>

在下周的 DockerCon 2019 上， [Docker](https://www.docker.com/) 和 [Arm](https://www.arm.com/) 将会预览一些技术，这些技术是他们最近宣布的战略合作伙伴关系的一部分。

两家公司计划合作创建一个基于云的开发环境，用于使用 Arm 硬件构建和交付基于容器的应用程序到云、边缘和物联网设备。

来自传感器、仪表和仪器的数据越来越多地在现场(边缘)以 5 到 8GB 的增量在节点中处理，而不是全部发送回中央数据中心。许多这些应用在数据分析中使用机器学习。在这些节点上运行的应用程序往往会频繁更新。

此次合作旨在开发一个环境，在该环境中，运行在 x86 上的应用程序也可以在 Arm 的低功耗硬件上无缝工作。

Docker 战略联盟执行副总裁 [David Messina](https://www.linkedin.com/in/davidmessina/) 表示:“扩展到 edge 进一步推进了我们为构建和运行所有应用提供单一平台的企业愿景。

创建开发者环境将是首要任务，从将 Arm 功能集成到 Docker 桌面社区开始。它将支持用编程语言编写的应用程序，包括 C++、Python、JavaScript、Java、Ruby、Go、Rust 和 PHP。

Arm 的 [Mohamed Awad](https://www.linkedin.com/in/moawad/) 在一篇[博客文章](https://www.arm.com/company/news/2019/04/arm-and-docker-better-together)中写道:“通过今天的发布，我们使【200 万 Docker 桌面开发人员】能够立即成为 Arm 开发人员，使用他们一直使用的相同 PC 或 Mac 开发环境，瞄准从嵌入式端点到云中的 Arm Neoverse 服务器的一切。

这两家公司正在向 Arm 开发人员生态系统提供基于 Docker 的解决方案，作为 Arm Neoverse 平台的扩展。

Docker 企业引擎将可用于亚马逊 EC2 A1 实例。AWS 去年 11 月推出了 EC2 A1 实例，基于 AWS 的 Graviton 处理器和 64 位 Arm Neoverse 内核以及 AWS 开发的定制硅。

这些公司表示，通过使用这些实例，在 Docker 的商业支持下，公司可以在 Arm 上节省高达 45%的横向扩展容器化应用程序。他们声称，许多云原生 Linux 应用程序可以不加修改地运行，而在某些情况下，可能需要简单的重新编译来生成 Arm 可执行文件。

“对于那些希望实现将现有云原生工作负载迁移到 Neoverse 服务器的好处的人，我们大大简化了开发流程。与此同时，我们还使物联网和嵌入式开发人员能够利用使用 Docker 带来的可移植性和可扩展性，”Awad 在他的帖子中写道。

进一步的工作将集中在完整的生命周期管理、统一的开发环境和扩展上。

Arm 一直在快速构建其生态系统，旨在让开发者更容易利用其技术构建应用。今年 2 月，它成为了云计算原生计算基金会的成员。

12 月，Rancher Labs 宣布与 Arm 合作，为企业提供管理 x86 集群中的 Kubernetes 及其[物联网部署](https://thenewstack.io/how-low-can-kubernetes-go-rancher-arm-team-to-find-out/)的单一方式。

Rancher 在 2 月份发布了 K3s，这是一款为物联网设计的轻量级生产级 Kubernetes 发行版，并刚刚宣布了一款名为 [k3OS](https://github.com/rancher/k3os) 的配套操作系统。

连续交付平台供应商 [Drone.io](https://drone.io/) 去年 8 月宣布支持 Armv7-A 和 Armv8-A，以帮助开发 Arm 架构的开发人员。

在 DockerCon 展会上，演示将在 Arm 展台(#P1)进行。该演示将展示 Docker 桌面上的产品集成，以及开发人员在桌面上开发基于 Arm 的容器、在桌面上、在 AWS 云(EC2 / A1)上或直接在嵌入式/物联网设备上运行和测试这些容器的工作流程。

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>