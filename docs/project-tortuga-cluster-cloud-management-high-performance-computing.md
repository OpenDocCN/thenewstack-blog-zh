# Tortuga 项目:面向高性能计算的集群和云管理

> 原文：<https://thenewstack.io/project-tortuga-cluster-cloud-management-high-performance-computing/>

工作负载管理供应商 [Univa](https://www.univa.com/products/navops.php) 拥有开源技术，最初被称为 Unicloud，后来被称为 Navops Launch，为高性能计算(HPC)工作负载提供了一个改进的云入口。

在阿帕奇 2.0 许可下，它将被称为[托尔图加项目](https://github.com/UnivaCorporation/tortuga)。这是一个通用的集群和云管理框架，应用程序包括高性能计算(HPC)、大数据框架、Kubernetes 和横向扩展机器学习/深度学习环境。

据 Univa 总裁兼首席执行官 [Gary Tyreman](https://www.linkedin.com/in/garytyreman/) 称，拥有数千台服务器的计算农场执行建模和回归等任务的企业客户正在寻求将 HPC 工作负载迁移到云。

Tortuga 是一个通用的集群和云管理框架，它通过可重复的模板在本地、云和混合云配置中自动部署集群。

它可以处理虚拟和裸机环境，包括针对 Amazon Web Services、Google Cloud、Microsoft Azure、OpenStack 和 Oracle Cloud Infrastructure 的云特定适配器，并完全支持自带映像(BYOI)。它有一个内置的策略引擎，允许用户根据不断变化的工作负载需求动态创建、扩展和拆除基于云的基础架构。云资源的管理、监控和记账与本地服务器相同。

宾夕法尼亚大学沃顿商学院转向 Univa Grid Engine 和 Navops Launch，为研究人员扩展其 HPC 环境。它提供了内部硬件与 AWS 计算资源的无缝集成，无需停机。该组合还支持爆发功能，因此研究人员可以根据需要启动任意多的计算密集型任务。

Navops 副总裁兼总经理 Rob Lalonde 表示，作为一个开源项目，Tortuga 可以采取多种不同的方式，包括为其他云提供商提供适配器，支持新的集群技术和基础设施即服务平台，如面向云的 OpenShift、web UI 和策略引擎的其他功能。

该公司的 Navops 产品线专注于云计算之旅。该公司早在 2016 年就推出了 [Navops Command](http://www.navops.io/command.html) ，这是一款针对 Kubernetes [的自动化工作负载放置和策略管理解决方案，但 HPC 工作负载在很大程度上一直停留在内部，Tyreman 说。然而，在过去的两年中，向云的迁移已经成为该公司客户的两位数百分比。](https://thenewstack.io/univas-new-powerful-navops-command-working-kinks-kubernetes/)

“我们看到这两者相结合，人们正在构建并期待我们构建一个云原生 HPC 环境。这意味着环境中有适合 Kubernetes 的基于容器的运行时或应用程序，基于容器的运行时或面向 HPC 的应用程序，意味着批处理，以及非基于容器的工作负载。将 Kubernetes 从内部扩展到云是关键的价值支柱之一，”他说。

Launch 包含一个使用 Puppet 创建资源适配器的核心，这些适配器可以与裸机配置和云 API 进行对话。

“通过指向不同的资源适配器，我可以说，‘给我一个具有该软件的节点和一个具有该硬件的资源适配器。’这些硬件可以在云中，也可以在你的防火墙后面，”泰勒曼说。

该公司制造了一些混乱，因为专注于 Kubernetes 的 [Navops Command](https://thenewstack.io/univas-new-powerful-navops-command-working-kinks-kubernetes/) 的一部分也被称为 Navops Launch。这是 Unicloud 的一部分，它涉及 Puppet 系统配置工具、Docker 容器、Kubernetes 和 Red Hat 的极简原子主机 Linux。Navops 命令为该组合添加了调度和策略管理功能。

在关于新堆栈的[上一篇文章](https://thenewstack.io/achieving-cloud-native-hpc-capabilities-mixed-workload-environment/)中，Lalonde 写了如何在混合工作负载环境中实现云原生 HPC 功能。

Navops 是新堆栈的赞助商。

专题图片: [Thomas Bonnin](https://www.flickr.com/photos/thomas-bonnin/) 的《Tortuga marina》，根据 [CC BY-SA 2.0 授权。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>