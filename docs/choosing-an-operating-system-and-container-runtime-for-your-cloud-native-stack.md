# 为您的云原生堆栈选择操作系统和容器运行时

> 原文：<https://thenewstack.io/choosing-an-operating-system-and-container-runtime-for-your-cloud-native-stack/>

容器重新定义了操作系统(OS)的角色。随着许多繁重的工作转移到容器运行时，操作系统变成了一个提供物理资源访问的薄层。这种转变产生了一种新的操作系统，称为容器优化操作系统(COS)。

正如我们在本系列的[上一篇文章](https://thenewstack.io/the-most-popular-cloud-native-storage-solutions/)中所了解到的，COS 构成了[云原生栈](https://thenewstack.io/what-is-the-modern-cloud-native-stack/)的基础层，是集群物理基础设施之上的一层。

与传统操作系统相比，COS 是一个轻量级操作系统，占用空间小得多。它包含运行容器运行时所需的最基本的组件。选择正确的 COS 对维护 CaaS 部署大有帮助。

客户可以在红帽的 [Fedora CoreOS](https://getfedora.org/en/coreos?stream=stable) 和 Talos Systems 的[以及 Kinvolk GmbH 的](https://kinvolk.io/#flatcar-linux)平板汽车集装箱 Linux 之间进行选择。或 Rancher Labs 的 RancherOS(截至 2020 年 7 月，该公司正在被 SUSE 收购)部署 COS。

大多数供应商提供可选的商业订阅计划，包括定期更新、补丁和专业支持。

## 容器运行时

容器运行时负责管理容器的生命周期，提供执行环境，并充当工作负载和主机操作系统之间的接口。

2015 年，[Linux 基金会发起了开放容器倡议](https://www.opencontainers.org/) (OCI)，以实现容器运行时实现之间的对等。OCI 目前定义了两个规范:[运行时规范](https://github.com/opencontainers/runtime-spec)(运行时规范)和[图像格式规范](https://github.com/opencontainers/image-spec)(图像规范)。

根据 OCI 网站，运行时规范概述了如何运行一个“文件系统包”,它被解压到一个磁盘上。在高层次上，OCI 实现将下载 OCI 映像，然后将该映像解包到 OCI 运行时文件系统包中。

映像格式规范定义了如何创建 OCI 映像(通常由构建系统完成)以及如何输出映像清单、文件系统(层)序列化和映像配置。

Docker Enterprise 被 Mirantis 收购后，Docker Engine 商业版( [Docker Engine Enterprise](https://www.mirantis.com/software/docker/container-runtime/) )由 Mirantis 出售；这提供了企业级支持和专业服务。

[containerd 项目](https://containerd.io/)已经发展成为容器运行时的行业标准。这是云计算原生计算基金会的一个毕业项目，在许多生产环境中都有使用。 [CRI-O](https://cri-o.io/) 目前是一个 [CNCF 孵化项目](https://www.cncf.io/projects/)，社区积极参与。

[Docker 引擎](https://www.docker.com/products/container-runtime)(现在的 Docker-CE)是容器管理平台使用的最流行的容器运行时之一。Frakti 是 Kubernetes 的一个基于管理程序的容器运行时，它通过在专用虚拟机中运行 pods 来提供更强的隔离。除此之外，其他选择包括[武士刀容器](https://katacontainers.io/)和 [runC](https://github.com/opencontainers/runc) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>