# KernelCI 加入 Linux 基金会加速 Linux 内核硬件测试

> 原文：<https://thenewstack.io/kernelci-joins-linux-foundation-to-accelerate-linux-kernel-hardware-testing/>

测试软件本身就有足够的困难，但是当你谈论 Linux 内核——直接与硬件接口的软件——时，这种情况会增加无数的复杂性。当然，其中一个复杂性是 Linux 打算运行的设备的数量，从各种各样的台式机、笔记本电脑和手机，到 Raspberry Pis 和其他边缘设备。每个设备都代表了一个需要测试 Linux 内核的新环境，这就是 [KernelCI](https://kernelci.org/) 的作用。

KernelCI 是一个[开源](https://github.com/kernelci/)，专注于[上游 Linux 内核](https://www.kernel.org/)开发的分布式测试自动化系统，最近刚刚加入了 [Linux 基金会](https://www.linuxfoundation.org/)，得到了 BayLibre、Civil Infrastructure Platform、Collabora、Foundries.io、Google、Microsoft 和 Red Hat 的支持。该项目于 2014 年首次启动，其既定任务是“在上游内核树到达主线之前检测、平分、报告和修复它们的回归”，目前该项目针对近 250 个独特的硬件平台测试 Linux 内核，但通过加入 Linux 基金会，它希望进一步扩大这一数字。

“传统上，测试只在最常见的硬件上进行。但是因为 Linux 比任何其他操作系统运行在更多的硬件上，所以在所有硬件上测试它也很重要，”嵌入式 Linux 咨询公司 BayLibre 的联合创始人兼 KernelCI 项目的联合创始人 Kevin Hilman 在一份声明中解释道。“Linux 基金会的支持使我们能够扩展我们五年前开始的伟大工作，并为我们与不断增长的社区建立一个光明的未来。”

## 跨各种硬件的 Linux 内核测试

在接受 New Stack 采访时，Hilman 将该项目的起源描述为来自 Linux 内核开发人员和 ARM 社区的草根努力，该社区包括各种嵌入式系统设备，如 Raspberry Pi。

“它诞生于面向开发人员社区的 Linux 内核开发人员社区，多年来它不断发展壮大，我们开始收到要求更多功能、测试内核更多部分、添加更多硬件和建立实验室的请求。慢慢地，我们在世界各地的分布式电路板农场中添加了一些硬件，这就是我们今天的处境，”希尔曼说。“Raspberry Pi 是成千上万种不同的单板计算机中的一个例子，这些计算机都有运行 Linux 的 ARM 处理器。因此，我们这些为这种类型的系统维护 Linux 内核的人，我们只是有这么多种硬件，我们希望确保 Linux 内核仍然可以工作。”

在目前的版本中，KernelCI 监控大约 100 棵 Git 树，新的 Git 树可以通过手动电子邮件请求添加到 KernelCI 的测试过程中。但是 Hilman 说，KernelCI 未来的重点是扩展硬件的种类，并可能包括稳定的上游 Linux 内核之外的其他类型的软件，如 Fedora 和 Debian。除了扩展 KernelCI 的能力之外，Hilman 说他希望通过加入 Linux 基金会，KernelCI 能够与 Linux 内核测试领域的其他项目合并。

至于“下一代 KernelCI”，Hilman 说他希望利用一些围绕微服务架构的设计和工具。

希尔曼说:“如果你想到一个树莓派坐在某人的壁橱里，每隔一段时间启动一次 Linux，并像微服务一样发出日志——所有这些小电路板都在上下运行测试——有很多这种分布式云工具和日志分析材料实际上非常适合这个问题。”“所以我一直在思考，随着项目的发展，我们如何利用这种容器管理和分布式日志捕获、收集和分析，这些东西实际上与我们在 KernelCI 中所做的事情非常相关。”

Linux 基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>