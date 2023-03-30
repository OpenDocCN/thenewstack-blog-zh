# AWS 希望其开源鞭炮变得更快

> 原文：<https://thenewstack.io/aws-wants-its-open-source-firecracker-to-become-faster/>

鞭炮已经成为亚马逊网络服务(AWS)的主要开源项目，而[鞭炮作为微虚拟机(micro virtual machines)的虚拟机管理器](https://github.com/firecracker-microvm) (VMM)的新功能在该公司的年度用户大会 [AWS Re:Invent](https://reinvent.awsevents.com/) 期间被降级为分组会议。

AWS 高管演示了鞭炮，并透露了项目路线图的一些细节，他们仍然关注 AWS 如何在开源社区的帮助下，继续帮助和改进鞭炮。然而，AWS 鞭炮项目如何反映该公司的承诺和开源社区理念仍未披露。

AWS 正在寻求在不久的将来——当然是在开源贡献者的帮助下——根据需要，使访问微卷快照的过程更快。最初的想法是提供一个虚拟化环境来隔离基于 Linux 内核虚拟机(KVM)的容器。开发者现在希望做的是允许访问，例如，微虚拟内存中的 Kubernetes 集群，“在你真正需要的时候，非常非常快地用你的快照让它达到一切正常的状态，” [Radu Weiss](https://www.linkedin.com/in/raduweiss/?originalSubdomain=ro) ，鞭炮的 AWS 软件开发经理，在分组会议和演示后告诉新的堆栈。

例如，如果在使用 bracket 拍摄容器快照的过程中，您无法完成该过程，bracket 应该很快就能够允许服务提供商在中断发生时恢复拍摄快照。

对于 2019 年的亮点，韦斯描述了鞭炮如何开始为 ARM 和 AMD CPUs 以及树莓 Pi 设备提供支持。该路线图概述了 Weiss 所说的“在无服务器计算平台的背景下，重点关注深度防御，如持续模糊测试和依赖性减少”。

在演示期间，AWS 软件开发工程师亚历山德拉·约尔达切展示了如何将鞭炮的虚拟机快照恢复时间缩短至 2 毫秒。约尔达切说，我们的目标是“随时为您的虚拟机拍摄快照”，然后“在您需要时，在 5 毫秒内启动它。” 演示由 4000 个微卷的快照组成，每个快照运行一个小的网络工作负载。

虽然该过程已经以毫秒为单位进行了测量，但是在处理大量快照时，对于大规模加载需求而言，节省的时间显然会增加。AWS 此前表示，这些改进应该在今年完成，AWS 代表不会对时间表或时间表是否有所改变发表评论。

如上所述，AWS 没有偏离鞭炮演示的主题来讨论该项目如何符合 AWS 在开源社区中发挥更大作用的雄心。然而，考虑到其专有的以及开源的相关服务，AWS 继续扩大其无服务器服务的范围。

近日，亚马逊 CTO [沃纳·威格尔最近写道:](https://www.allthingsdistributed.com/2019/08/modern-applications-at-aws.html)

*【我们预计，很快会有整整一代开发人员从未接触过服务器，只编写业务逻辑。原因很简单。无论您是构建全新的应用程序还是迁移传统应用程序，将无服务器原语用于计算、数据和集成，都可以让您从云所提供的最大灵活性中受益。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>