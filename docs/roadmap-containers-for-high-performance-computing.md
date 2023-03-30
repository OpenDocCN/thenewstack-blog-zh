# 高性能计算的容器

> 原文：<https://thenewstack.io/roadmap-containers-for-high-performance-computing/>

Docker 技术客户经理 Christian Kniep 在最近于汉堡[集装箱日](https://containerdays.io/)和其他地方举行的一系列会谈中预测，通过对技术进行一些调整，Docker 集装箱可以为超级计算机和高性能计算(HPC)带来前所未有的效率。

迄今为止，超级计算世界很少注意容器，尽管它们可以为痴迷于性能的生态系统带来更高的效率。在某种程度上，这是由于体系结构的差异——超级计算的紧密耦合模型与容器化也适用的松散耦合的“微服务”体系结构不一致。安全问题也起了作用，因为对在工作节点上运行 [Docker 守护进程](https://thenewstack.io/red-hat-buildah-provides-a-way-to-build-containers-without-the-docker-daemon/)的担忧吓坏了一些人。

但 Kniep 指出，一些工作自然适合 HPC 模式，例如人工智能工作，这可以利用超级计算机通过其丰富的 GPU 提供的强大向量处理能力。本周， [SC500](https://www.top500.org) ，每年两次运行世界上最快的超级计算机，[宣布](https://www.top500.org/news/us-regains-top500-crown-with-summit-supercomputer-sierra-grabs-number-three-spot/)名单上所有计算机的收集能力都超过了 exaflop，达到 1.22 exaflops。一个 exaflop 是每秒一千个 petaflops 或五千万亿次浮点运算。这些系统中有 110 个使用了 GPU，其中 98 个是 Nvidia 的。

超级计算机旨在运行大型工作负载，如天气预报或分子建模，作为跨越数百甚至数千台服务器的单个应用程序。Kniep 指出，尽管最初与云计算有相似之处，但这两种架构之间确实存在一些根本差异。如果 Docker 或其他云原生厂商希望服务于这一市场，就必须考虑这些差异。

例如，为了利用特定的加速硬件，如 GPU 或高速互连，HPC 应用程序通常是特定于主机的，它们是为一个平台而设计的。从这个意义上说，它们是特定于硬件的，而不是 Docker 坚持的与硬件无关的方法。其次，HPC 程序往往是紧密耦合的。它们可能有多个组件，但是它们都需要访问共享的内存空间。

“HPC 需要在共享资源上运行，”正如 Kniep 在 [2018 HPC 顾问委员会瑞士会议](http://www.hpcadvisorycouncil.com/events/2018/swiss-workshop/index.php)的一次演讲中所说[(他上周在 ContainerDays EU 上做了类似的演讲)。与当今大多数 Docker 设置不同，在 HPC 设置中，多个节点将读写单个共享文件系统。每个节点还必须安全地维护自己的数据集，不受其他节点的入侵。](https://www.youtube.com/watch?v=r9bPHKiagco&list=WL&index=2&t=1773s)

通常，Docker 赋予容器与容器本身相同的特权集。然而，这种做法是不安全的，因为有人可以用其他人的 ID 创建一个容器，授予他们该用户的全部权限。因此，出于安全目的，不应信任容器设置的用户和组权限。

作为解决这个问题的概念验证，Kniep 为 Docker 引擎开发了一个迷你代理，用启动容器的用户的权限覆盖容器的权限。在这种情况下，用户的权限被重新附加到容器上，而不是依赖于容器本身声明的内容。

HPC 的另一个重要方面是应用程序完全绕过操作系统内核的能力，这是 HPC 中的一种常见方法，通过允许应用程序直接与专用硬件(如 GPU 或互连)通信来提高性能，而无需通过操作系统。

这个问题的最初解决方案可能是将特定于主机的驱动程序移动到容器上，这将增加容器的大小(仅 Nvidia Cuda 驱动程序就可能高达 1GB)。更好的选择是将驱动程序放在主机上，然后将它们映射到容器本身。然后，每个主机可以使用预定义的“装载点”将其自身的特征映射到容器上

Kniep 的 Docker 引擎代理也处理这项任务，只需要用户输入关于硬件要求(即 GPU 或 Infiniband 连接)以及共享库在主机上的位置。

## 工作需要完成

有了这些变化，您可以使用 Docker 在 HPC 系统上暂存所有容器化的工作负载，包括那些需要共享空间和不需要共享空间的工作负载。这种方法将提供虚拟机的所有灵活性，但具有 HPOC 爱好者喜欢的线速性能。

一些开源倡议已经解决了将容器引入 HPC 空间的问题，最著名的是[移位器](https://github.com/NERSC/shifter)和[奇点](http://singularity.lbl.gov/)。Kniep 警告说，这些努力没有遵循[开放容器倡议](https://www.opencontainers.org/)的规范，并且可能与可以构建在 OCI[runc](https://github.com/opencontainers/runc)和 [containerd](https://containerd.io/) 之上的云原生工具在架构上不一致。

Kniep 补充说，除了适应共享内存和内核旁路，还需要更多的后续工作。需要做的工作是将容器化的工作负载放入 HPC 工作负载调度器，最值得注意的是 [Slurm](https://www.hpc.cam.ac.uk/using-clusters/running-jobs) ，这将为其他 HPC 调度器铺平道路。这些工作负载调度器处理 [MPI](http://mpitutorial.com/tutorials/mpi-introduction/) ，这是一个复杂的消息传递接口，提供运行相同作业的不同节点之间的通信。

另一个不错的特性是支持无盘节点，以节省部署时间。作业的容器映像在共享文件系统上复制一次，因此每个节点上的容器引擎可以启动自己的实例。这比让数千个容器引擎同时从同一个存储库中下载同一个映像，然后一个接一个地提取完全相同的文件系统要有效得多。

[https://www.youtube.com/embed/r9bPHKiagco?start=1773&feature=oembed](https://www.youtube.com/embed/r9bPHKiagco?start=1773&feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>