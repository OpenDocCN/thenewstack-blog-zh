# 边缘服务网格的新维度

> 原文：<https://thenewstack.io/where-service-mesh-and-smartnics-meet/>

智能网络接口控制器(SmartNICS)将服务网格置于网络和应用层交汇的中心位置。随着硬件和软件的集成而来的新的维度正在迎来新一代的功能，例如加密操作和资源利用的新方法。

在上个月的 VMworld 大会上，VMware 将 SmartNICs 作为蒙特雷项目[的一部分，该项目旨在将 Kubernetes 深度集成到 vSphere 中。它证明了 VMware 对数据中心不断变化的看法，并展示了其与英特尔和其他生态系统提供商的合作，以提供一个使用 Kubernetes 的平台。尤其令人感兴趣的是运营二级和三级数据中心的电信市场。](https://blogs.vmware.com/vsphere/2020/09/announcing-project-monterey-redefining-hybrid-cloud-architecture.html)

资源曾经被认为是丰富的——只要增加更多的机器。现在，随着网络压力越来越大，利用率成为影响开发人员体验和我们如何看待网络和应用的核心问题。峰值负载是一个越来越令人担忧的问题，这使得智能网卡对芯片制造商、超大规模云服务、二级和三级数据中心提供商和软件供应商具有吸引力。

## 身份很重要

智能网卡和服务网格的结合为扩展身份管理以管理边缘设备开辟了道路。

“虽然服务网格可以在没有加密身份平面的情况下运行，但不可避免地会创建弱形式的身份，以允许服务到服务的通信和发现，”VMware Tanzu Foundation Services 的产品线经理[安德烈斯·维加](https://www.linkedin.com/in/avegaarias/)说，他曾是被 HPE 收购的 [Scytale](https://www.hpe.com/us/en/newsroom/blog-post/2020/02/hpe-acquires-scytale-to-advance-open-secure-edge-to-cloud-strategy.html) 的开源经理。维加是 CNCF [SPIFFE 和 SPIRE](https://spiffe.io/) 身份控制平面项目的产品经理。

“许多服务网格实现都采用了 SPIFFE 规范的部分实现作为可靠的身份基础。在这些情况下，使用智能网卡可以加速和卸载加密、计算和密钥轮换，”Vega 说。

有了更有意义的边界，就有机会实现更专业化的服务网格。“出现了专门针对安全性优化的轻量级服务网格，如 Tanzu 服务网格或 [NGINX 服务网格，](https://www.nginx.com/blog/introducing-nginx-service-mesh/)”Vega 说。

“SmartNICs 可以在这一领域发挥非常重要的作用，”Vega 说。

硬件方面的挑战之一是总线加密。Vega 说，网卡上的处理器提供了一种从 CPU 卸载这些操作的方法。添加强加密身份可以在服务网格的动态协商和建立底层连接中发挥作用。也就是说，仅当 SmartNIC 可以通过身份验证并且策略允许此类连接时。

## 智能网卡基础知识

对于那些不熟悉 SmartNICs 的人来说，一个很好的例子就是微软是如何使用它们的。

微软在其 [Azure 应用 Azure Accelerated Networking(AccelNet)](https://www.microsoft.com/en-us/research/uploads/prod/2018/03/Azure_SmartNIC_NSDI_2018.pdf)中使用 FPGAs，该应用作为该公司在公共云中的智能网卡。smart NIC 使用基于现场可编程门阵列(FPGAs)的自定义 Azure SmartNICs，通过将主机网络卸载到硬件来降低传统网络堆栈的复杂性。

处理开销很大，SmartNIC 的速度超过 25GB、50GB 和 100GB(将来还会超过 400GB)。NIC 卡中的处理器是在硬件中执行编程网络处理的明显优势。

> 我们今天看到的是我们对网络和应用技术的看法发生了变化。服务网格是两者结合的一层。

Mary Branscombe 在[关于 Azure 使用 FPGAs 的新堆栈](https://thenewstack.io/developers-fpgas-cloud/)中写道，实际上，定制硅是有成本的。CPU 处理被卸载到可通过 FPGAs 编程的网络接口卡(NIC)。

FPGAs 已经使用了很长时间。不过，Branscombe 的文章概述了 FPGAs 的不同之处。这些门支持针对特定算法定制的大规模并行处理，因此功耗低于 GPU。值得注意的是，NVIDIA 还与 VMware 在蒙特利项目上合作。

[https://www.youtube.com/embed/edfA5X6itik?feature=oembed](https://www.youtube.com/embed/edfA5X6itik?feature=oembed)

视频

## VMware 和英特尔

VMware 云计算副总裁兼首席技术官 [Kit Colbert](https://www.linkedin.com/in/kitcolbert/) 表示，VMware 与英特尔的合作关系从三个方面体现了智能网卡的重要性:

*   **性能** : SmartNICS 使计算更接近网络 IO 流量。性能提高，延迟降低，核心 CPU 周期得以节省。申请的周期更多。
*   **运营模式**:许多传统的虚拟机管理程序功能可以放在 SmartNCS 上，例如存储虚拟化和网络虚拟化安全。它允许 VMware 支持某些使用情形下的裸机工作负载。“你开始在一台物理主机内拥有一个分布式系统，”科尔伯特说。“它实际上为我们提供了一整套工具，可以用来简化操作。”
*   **安全性**:有了 SmartNIC，“我们现在可以将管理程序拆分开来，”科尔伯特说。“在两个不同的 CPU 上运行它，您可以获得更深入的防御。您可以将所有这些安全功能直接放在 SmartNIC 上，而不会影响性能。”网络流量不会变慢，也不会占用核心 CPU 周期。

## 输入 gRPC

Tetrate 是基于 Envoy 和 Istio 构建的服务网格。Tetrate 首席执行官兼创始人 [Varun Talwar](https://www.linkedin.com/in/varuntalwar/) 是 Istio 的联合创始人。他还是谷歌 gRPC(一种低延迟分布式服务通信协议)的产品经理。根据 Talwar 的估计，它仍然处于开发周期的早期，但他预计在两年内将会有对 SmartNICs 更深的需求和兴趣。

塔尔瓦说，智能芯片有三个优点。按照顺序，它们是可以卸载的性能、安全性和数据负载。

他以 gRPC 为例，说明一种需要 smartNICs 所能提供的卓越性能的技术。谷歌内部使用 gRPC 来运行其服务。大量的时间花费在通过网络封送服务上。Talwar 说，SmartNICs 可以帮助解决延迟和性能问题，这将导致更多地采用服务网格等技术。

Talwar 说，数据负载只会增加，安全可以在硬件中更有效地管理。例如，随着服务的横向扩展需求不断增加，云服务提供商希望降低运营成本。将安全性转移到硬件中可以提供更好的资源利用率，并允许硬件成为信任的基础。

“如果这是在硬件中完成的，并且软件知道如何与硬件配合，用户会处于更好的状态吗？是的，当然，”塔尔瓦说。

要让各方坐到谈判桌前，还有一些工作要做:软件提供商、云服务和芯片制造商，他们不仅在硬件中运行代码，还知道软件的回报是什么。

但是最终，开发者的体验才是最重要的。SmartNIC 可能有很多潜力，但挑战在于为开发人员提供出色的体验，以便他们在现有棕色地带环境中使用服务网格技术、类似库的方法(如 gRPC)或代理(如 Envoy)时，甚至不必考虑底层是什么。

这将取决于英特尔等硬件厂商、软件厂商和云服务提供商，以建立一个开放的合作模式。资源利用达到极限是一个正在出现的痛点，这可能会加速合作。资源得到了最大化。服务网格增加了对资源的需求。从本质上说，服务网增加了另一项税收。

使用服务网格的精明客户现在开始询问如何降低横向扩展架构的成本。

我们今天看到的是我们对网络和应用技术的看法发生了变化。服务网格是两者结合的一层。SmartNICs 是一项关键技术，可以实现更高水平的性能、加密操作和资源利用方式。如今，答案是向集群添加更多的机器，但这种方法已经过时了。

Lyft 的软件工程师 Matt Klein 说,“特使计划将会无处不在。“最理想的情况是，人们不会知道他们在引擎盖下使用的是 Envoy 或 Kubernetes。业界已经在致力于更高层次的平台抽象。智能网卡和内核卸载是这一努力的逻辑延续。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>