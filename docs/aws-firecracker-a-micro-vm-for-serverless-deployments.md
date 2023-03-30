# AWS 鞭炮:用于无服务器部署的微型虚拟机

> 原文：<https://thenewstack.io/aws-firecracker-a-micro-vm-for-serverless-deployments/>

意识到需要为无服务器工作负载带来基于虚拟化的安全性和多租户，Amazon Web Services 开源发布了一个非常适合无服务器环境的“微型虚拟机”。

许多无服务器工作负载是事件驱动的，并且通常是短暂的，现有的虚拟化技术不太适合这种工作流。“我们需要一些东西，可以给我们虚拟机基于硬件虚拟化的安全边界，同时保持更小的包大小和容器及功能的灵活性，”AWS 的技术传道者 Arun Gupta 和 AWS 无服务器产品经理 [Linda Lian](https://www.linkedin.com/in/lindamlian/) 在[发布的一篇博客文章中写道](https://aws.amazon.com/blogs/opensource/firecracker-open-source-secure-fast-microvm-serverless/)。

该公司在本周于拉斯维加斯举行的 [AWS re:Invent](https://reinvent.awsevents.com/) 用户大会上宣布了该项目。

构建在基于 Linux 内核的虚拟机(KVM)上，用 Rust 编写，[cracken](https://github.com/firecracker-microvm)提供了一种在传统的非虚拟化环境中创建微型虚拟机(microVMs)的方法。AWS 首席布道者 [Jeff Barr](https://twitter.com/jeffbarr) 在[一篇进一步详细描述该技术的帖子](https://aws.amazon.com/blogs/aws/firecracker-lightweight-virtualization-for-serverless-computing/)中解释说，微虚拟机在不到一秒钟内创建，并提供传统虚拟机提供的安全性和工作负载隔离以及容器的资源效率。鞭炮提供了一个简单的客人模型，静态链接，和一个进程监狱，访问一个小的，严格控制的系统调用列表。

鞭炮目前运行在英特尔处理器上，2019 年将支持 AMD 和 ARM 芯片。它可以轻松运行在裸机服务上，包括 AWS 自己的[。金属实例](https://aws.amazon.com/about-aws/whats-new/2018/05/announcing-general-availability-of-amazon-ec2-bare-metal-instances/)。在他的帖子中，Barr 提供了如何在 n i3.metal 实例上运行鞭炮的演示。AWS 本身使用鞭炮来为其 Fargate 服务的客户运行容器化的工作负载。

AWS 还推出了基于 containerd 的原型 T1，它将允许在 Docker runtime 或 Kubernetes 等容器服务中管理微型虚拟机。

鞭炮是根据 Apache 2.0 许可的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>