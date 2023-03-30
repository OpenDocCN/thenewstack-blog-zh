# 高性能计算的容器系统

> 原文：<https://thenewstack.io/apptainer-a-container-system-for-high-performance-computing/>

根据 Apptainer 创始人和项目负责人 [Gregory Kurtzer](https://www.linkedin.com/in/gmkurtzer) 的说法，用于高性能计算(HPC)的容器系统(以前称为 Singularity)已经加入了 [Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)，至少有一个既定目标，总结如下:“交叉授粉。”

“在 HPC 领域，我们在可扩展计算架构和模型方面积累了数十年的研究成果。我认为这还不能很好地转化为微服务编排，但我们看到更多传统上不是 HPC 消费者的公司需要 HPC 和类似 HPC 的功能，”Kurtzer 在电子邮件采访中写道。“该项目的目标是，向 Linux 基金会的迁移将促进生态系统的这两个部分之间的交叉授粉，从而产生更好、更有能力的系统。”

许多传统的容器运行时和编排工具优先考虑提供可伸缩性，而 Apptainer 则关注性能。Kubernetes 与 Apptainer 相比，Kurtzer 注意到 Kubernetes 的缩放因子与 HPC 和性能密集型计算有很大不同。

“虽然云可以扩展到成千上万的裸机主机，但 HPC 必须能够扩展到成千上万的内核和进程，所有这些内核和进程都可以相互协调地并行运行。想象一下，在数千台计算机上运行的数万个进程中，进程间通信每秒钟发生多次，”他写道。“Kubernetes 可以进行松耦合(或者说非耦合)的实例并行化，但它不擅长任何类型的紧耦合并行化，甚至不擅长针对可消耗资源(例如内存、内核、GPU 等)的一般性能密集型计算的丰富策略要求..)."

与此同时，这些系统的核心都有一个共同的组成部分——容器化的工作负载，为开发人员提供了容器最初采用的通用操作和可移植性的好处。开发人员在创建需要终端用户可伸缩性的应用以及人工智能和机器学习等性能密集型用例时，可以享受这些优势。随着时间的推移，这些开发人员越来越成为同一个群体，这个项目转移到 Linux 基金会的原因之一是它最近的增长，Kurtzer 将其归因于共同的兴趣。

## 奇点

Kurtzer 解释说:“多年来，Singularity 已经成为 HPC 中占主导地位的容器系统，最近我们看到非传统 HPC 环境对 Singularity 感兴趣，他们希望处理类似 HPC 的工作负载。

虽然有人努力在 Kubernetes 等系统中引入更多性能密集型功能，但仍然存在一些核心挑战。Kurtzer 解释说，在 Kubernetes 上运行的更多标准企业应用程序允许资源超额订阅，因为这些服务和微服务“几乎总是睡在一个选择循环(或 equiv)中，并且永远运行(从服务本身的角度来看，它永远不会结束)。”这使得在单个实例中耦合数百个微服务变得很容易，而在 HPC 中，性能密集型应用程序不会休眠，“它旨在尽可能快地高效运行硬件，直到特定组件(网络、存储、PCI、内存、CPU、GPU 等)出现瓶颈..)."

“因此，以企业和云为中心的功能与 HPC 截然不同，反之亦然。我们现在看到对异花授粉的吸收和兴趣正在显著增加。例如，我现在已经和几家超大规模公司谈过为他们的数据分析和人工智能模型构建巨型 HPC 系统，”Kurtzer 写道。“将 Singularity 移入 Linux 基金会并将其重命名为 Apptainer，为 OpenHPC 和 CNCF/OCI 等各种 LF 项目之间的交叉授粉提供了一个极好的基础。我们已经开始考虑如何将我们的安全和信任模型与 SigStore 和/或 Notary2 等项目结合起来。”

当我们第一次研究 HPC 的[容器的主题时，注意到的一个问题是，像 Singularity(现在的 Apptainer)这样的系统不符合 OCI 标准，但这种情况](https://thenewstack.io/roadmap-containers-for-high-performance-computing/)[已经得到补救](https://insidehpc.com/2019/02/singularity-3-1-0-brings-in-full-oci-compliance/)，这意味着组织可以轻松地将符合 OCI 标准的容器从一个系统带到另一个系统。通过加入 Linux 基金会，Apptainer 希望进一步融合使用容器的企业在微服务应用架构和性能密集型应用方面的能力。

Kurtzer 写道:“在项目成熟的这个阶段，加上对 HPC 和企业/云交叉的日益增长的需求，Singularity 项目的利益相关者都认为转移到 Linux 基础将有助于项目成熟，并将这些功能引入其他领域。”“企业、云、超大规模与 HPC 之间的功能共享不多。HPC 一直是一个孤岛，是时候改变这种状况了。生态系统的每个部分都有价值，而作为 HPC 中占主导地位的容器系统，Singularity 已经准备好进入下一个发展和成熟阶段。加入 Linux 基金会对大家都有帮助！”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>