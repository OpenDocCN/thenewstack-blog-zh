# Shippable 为 Arm 服务器带来了持续的集成和交付

> 原文：<https://thenewstack.io/shippable-brings-continuous-integration-and-delivery-to-arm-servers/>

持续集成和部署(CI/CD)软件提供商 Shippable 已经与芯片制造商 [Arm](https://www.arm.com/products/processors) 和裸机服务提供商 [Packet](https://www.packet.com/) 合作，专门为 [Arm v8-A 架构](https://developer.arm.com/products/architecture/learn-about-the-arm-architecture)提供持续集成和交付(CI/CD)平台。

Arm 开源支持总监 Jeff Underhill 表示:“通过这种合作……我们让开发人员能够轻松访问 CI/CD 工具和基础设施，这些工具和基础设施是开发、测试和部署基于 Arm 的解决方案所必需的。

作为合作的一部分，从事开源项目的 Arm 开发人员可以从 Packet 的云中免费在 32 位和 64 位基于 Arm 的机器上运行他们的构建和测试工作流。商业项目可以“自带 Arm 节点”，使用 Shippable 进行软件验证工作流。

“我们在 Shippable 的愿景是，不管你使用什么编程语言；你用什么应用架构，是微服务还是容器还是功能；你用什么样的操作系统；我们不在乎你部署到什么云。现在我们谈论的是，我们不在乎你是部署到 x86 机器还是 Arm 机器，”Shippable 联合创始人兼首席执行官 [Avi Cavale](https://www.linkedin.com/in/avinc) 说。

他说，随着低功耗处理器越来越受欢迎，Arm 今年早些时候联系了他的公司，为 Arm 开发人员解决一些问题。他说，Arm 机器最初针对物联网设备，可以运行任何应用程序，只要有合适的基础设施。例如，富士通和日本研究所理研已经基于 Arm 架构建造了一台原型[超级计算机，将于 2021 年部署。](https://www.hpcwire.com/off-the-wire/fujitsu-completes-post-k-supercomputer-cpu-prototype-begins-functionality-trials/)

Cavale 说:“Packet 提供的一些机器有 128 个 CPU 和 1TB 内存，这是裸机，所以如果你愿意，你可以运行 Kubernetes 集群和数千个容器。”

整个 x86 vx 还没有定论。他说，尽管在对英特尔 x86 芯片进行名为 Meltdown 和 Spectre 的攻击(黑客可以从受保护的内核内存中访问敏感信息)后，Linux 创作者 Linus Torvalds 建议，“也许我们应该开始更多地关注 Arm64 的人。”

Arm 功能只是 Shippable 主平台的另一个选项。他说，整个想法是确保开发者不必做任何不同的事情来使用它们。

今天，使用 Arm 芯片组的应用程序正在 x86 仿真器上运行。虽然 80%到 90%是准确的，但它们并不能提供完全的信心。但当这些应用程序部署在基于 Arm 的本地架构上时，它们就开始崩溃，他说，所以实际上，CI/CD 提供了一个误报。

该公司不得不重构其核心部分，以提供原生 Arm 功能。他说，主要的云提供商不提供 Arm 芯片组，因此与 Packet 结盟。

除了重构之外，它还必须为基于 Arm 的架构更新 Python 库，并添加常用的编程语言，如对基于 Arm 的技术更基础的 C++。

他说，客户需要一种通用的方法来管理非常异构的环境。Shippable 在 1 月份宣布支持多种操作系统，包括 Windows、Mac OS 和 CentOS。

Packet 首席执行官 [Zac Smith](https://www.linkedin.com/in/zsmith/) 表示:“在正确的基础设施上进行测试可以区分愉快的构建过程和痛苦的构建过程，尤其是在 edge、物联网和其他快速增长领域固有的多样化硬件环境中。

[Packet 一直在扩展](https://thenewstack.io/living-edge-packet/)它在边缘计算领域的触角。去年 8 月，它宣布了裸机服务器的现货市场。今年 2 月，它宣布了基于 24 核 AMD EPYC 7401P 处理器的“ [c2.medium](https://www.packet.net/bare-metal/servers/amd-epyc/) 平台。

与此同时，Arm 最近还宣布与三星建立[合作伙伴关系，将 Arm 的 Artisan 物理知识产权与三星铸造工艺技术相结合，用于高性能计算。在一项名为](https://www.hpcwire.com/off-the-wire/samsung-foundry-and-arm-expand-collaboration-to-drive-hpc-solutions/) [Project Trillium](https://developer.arm.com/products/processors/machine-learning) 的计划中，Arm 推出了“从头开始”为机器学习设计的特定处理器。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>