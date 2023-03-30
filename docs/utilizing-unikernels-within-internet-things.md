# 驳斥单核批评

> 原文：<https://thenewstack.io/utilizing-unikernels-within-internet-things/>

单内核编译工具 [Unik](https://github.com/emc-advanced-dev/unik) 的创造者 [Idit Levine](https://www.linkedin.com/in/iditlevine) 断言，围绕单内核的安全和工具担忧被大大夸大了，他也是戴尔 EMC 的云首席技术官。

作为一个相对较新的概念，Unikernels 可以被认为是精简的容器，只具有运行手头特定工作负载所需的功能。它们可以节省存储空间和提高性能，但它们绝不是一项成熟的技术。

几个月前，莱文当时在 EMC 的一位同事指控[说，单内核从根本上来说是不安全的](https://thenewstack.io/unikernels-will-create-security-problems-solve/)，因为它们提供了对操作系统最深层的“零环”访问。而在此之前几个月，Joyent 的首席技术官也很快指出了单核的另一个问题:[缺乏工具](https://thenewstack.io/good-luck-debugging-unikernels-joyents-chief-technology-says/)。

在最新一期的 [The New Stack Makers](https://thenewstack.io/podcasts/makers/) 播客中，Levine 简明地回答了这两种批评，并讨论了单核的第一个可能用例，即在物联网上为边缘设备供电。采访由 TNS 创始人亚历克斯·威廉姆斯和执行主编约阿布·杰克逊在法兰克福云铸造峰会上进行。

[批驳单核批判](https://thenewstack.simplecast.com/episodes/debunking-unikernel-criticisms)

在安全问题上，Levine 指出，unikernels 不是为裸机设计的。相反，它们将在虚拟机中运行，提供所需的安全性。“我要说的是，单内核更安全。虚拟机管理程序为我们提供了硬件隔离，这比您从 Linux 操作系统获得的更好。”

“为什么我们有多用户空间？我们这样做的原因是为了保护进程。如果你的有麻烦，我想确保它不会影响我的，”她指出。

至于工具，Levine 指出，这将随着围绕该技术的社区的形成而出现。Levine 注意到，正是社区作为一个整体联合起来创建了新的工具，以解决容器首次被使用时的安全问题。

在单核的许多潜在用例中，嵌入式设备引起了越来越多的社区兴趣，例如最近为基于单核的 [MirageOS](https://mirage.io/) 举办的黑客马拉松，这是一个运行在 [Xen 虚拟机管理程序](https://www.xenproject.org/)上的树莓 Pi 库操作系统。MirageOS 社区目前正致力于月内发布的 3.0 版本，增加了对 IBM Solo5 unikernel 的支持。

Raspberry Pi 板等物联网设备为开发人员提供了迭代和试验单核的机会。“在 IoT 上运行，你通常没有很多空间，希望东西小。如果只运行一个进程，您将获得更多的性能、安全性和内存来运行单核。Levin 解释说:“嵌入式系统以后肯定会成为单核的一个用例。

随着 EMC 最近发布的 [Unik-Hub](https://github.com/emc-advanced-dev/unik-hub) ，用户也能够以类似于 Docker Hub 的方式创建和共享 unikernels。

[![barcelona](img/19403431e61caee7d8e0ebecb3ae0718.png)](https://www.eventbrite.com/e/openstack-summit-pancake-breakfast-tickets-27692501016)

[云铸造基金会](https://www.cloudfoundry.org/)是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>