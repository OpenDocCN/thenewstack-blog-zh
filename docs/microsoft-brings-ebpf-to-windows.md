# 微软将 eBPF 引入 Windows

> 原文：<https://thenewstack.io/microsoft-brings-ebpf-to-windows/>

如果您希望运行代码来提供可观察性、安全性或网络功能，那么在操作系统的内核中运行代码会给您带来很大的优势，因为内核可以看到并控制系统上的一切。

这很强大，但如果你做错了，可能会造成干扰或危险，无论是引入漏洞还是降低系统速度。

如果你正在寻找一种方法来利用这种特权环境而没有潜在的危险， [eBPF 正在成为一种替代选择](https://thenewstack.io/linux-technology-for-the-new-year-ebpf/)——现在它来到了 Windows。

## **不仅仅是联网**

最初 eBPF 代表“extended Berkeley Packet Filter”，更新了开源网络工具，在 Linux 内核中放置了一个数据包过滤器，以实现更高性能的数据包跟踪(现在通常称为 cBPF，代表经典 BPF)。

但现在它是一种通用机制，通过使用沙箱，在特权上下文中安全地运行多种代码，具有应用程序监控、分析和安全工作负载以及网络，因此它不再是一个真正的缩写。

特权上下文甚至不必是 OS 内核，尽管它仍然倾向于成为 OS 内核，eBPF 是内核模块(在 Linux 上)和设备驱动程序(在 Windows 上)的更稳定和安全的替代方案，在内核模块和设备驱动程序中，错误或漏洞代码会危及整个系统。

通常的实现是基于内核的虚拟机，用于底层数据包处理；在 Linux 上，您可以在不重新编译的情况下改变内核的行为，加载自己的事件驱动代码，这些代码将在响应“挂钩”时执行，这些“挂钩”是指网络事件、系统调用、函数条目和内核跟踪点等触发器。

这些代码可以通过使用助手调用来运行各种功能，并且它可以改变内核通常会做的事情:eBPF 程序可能意味着网络数据包被丢弃、系统调用被拒绝或者事件被记录下来以供跟踪。

这仍然是一种专门的技术，但开发人员可以使用相对高级的语言，如 C++，Go 或 Rust，但可以直接使用内核。

> “微软投资 eBPF 的原因之一是，我们看到了让数据平面本身可编程并可由软件控制的重要性，”

——戴夫·马尔茨。

eBPF 用于高性能网络和负载平衡，提供特定于应用程序的路由或服务质量，防止拒绝服务攻击并加强容器运行时安全性。使用 Calico 或 Cilium 的 Kubernetes 网络安全非常受欢迎，因为它提供了传统安全监控无法看到的 HTTP 流量的可见性。

在新的开放网络模型中使用 eBPF 有一些有趣的机会，这些模型是围绕开源的、基于 Linux 的 [SONiC](https://github.com/Azure/SONiC) 网络操作系统开发的，微软(eBPF 基金会的创始人之一)创建该系统是为了简化其 Azure 基础设施的构建，现在许多网络硬件供应商为小型云提供商和企业提供支持，特别是在金融服务以及超大规模应用等垂直领域。

SONiC 创始人兼 Azure 网络工程负责人[戴夫·马尔茨](https://www.linkedin.com/in/davemaltz/)告诉新堆栈:“微软投资 eBPF 的原因之一是因为我们看到了通过软件使数据平面本身可编程和可控的重要性。”。

分解网络堆栈意味着网络架构师可以选择他们想要运行的协议，并只使用所需的软件模块；不运行提供您不需要的功能的软件意味着更少的开销和更少的潜在错误。

它还允许网络操作系统使用公共 API 来提供功能；提供该 API 的代码可以改进，但依赖于它的代码在这种情况下不必更新，这允许网络堆栈中有更多的创新。

[DASH](https://github.com/Azure/DASH)(SONiC Hosts 的分布式 API)是一个为软件定义的网络数据平面做这件事的网络项目，使用 [SmartNICs](https://thenewstack.io/nvidias-planned-acquisition-of-arm-portends-radical-data-center-changes/) 和[其他硬件](https://thenewstack.io/mobile-machine-learning-ai-offload-engines/)通过在网络本身做更多的工作(如加密或密钥管理)来提高云服务的网络性能，以合并计算和网络的方式。

“我们需要公开更高级别的 API 来控制 SDN 数据路径，eBPF 是实现这一点的好方法，”Maltz 说。

在 Linux 上，eBPF 是 90 年代左右的一项功能的演变，但现在已经有足够的特性广泛适用于越来越多的应用程序。

“这些年来，它已经从我们可以在数据包到达时运行一些任意代码，发展到我们可以在发生其他事情时运行一些任意代码。我们看到越来越多的地方可以与内核挂钩，” [Isovalent](https://isovalent.com/) 的首席开源官 [Liz Rice](https://www.linkedin.com/in/lizrice/) 告诉我们。

eBPF 是调试、应用程序跟踪和性能故障排除的理想选择，可以获得可观察性数据，而没有通常的干扰和开销，并且可以为您无法改变的软件限制创建解决方案和兼容性修复。

![](img/f24f602ef38cbecca717a2866228817a.png)

[New Relic](http://newrelic.com/?utm_content=inline-mention) 的开源[Pixie](http://pixielabs.ai/)Kubernetes observability 平台所做的大部分事情都依赖于 eBPF 和 [Splunk](https://www.splunk.com/) 最近向[Cloud Native Computing Foundation](https://cncf.io/?utm_content=inline-mention)的 [OpenTelemetry 项目](https://opentelemetry.io/)捐赠了其 [Flowmill eBPF](https://docs.flowmill.com/) collector 应用程序和内核遥测技术。

这些遥测收集组件将帮助开发人员将来自不同层的遥测数据缝合在一起，并有助于简化 eBPF 的工作，微软合作伙伴软件工程师 Dave Thaler 建议道。

Thaler 说:“eBPF 是一种非常有效和安全的获取过程信息的方法，在收集什么和如何收集信息方面具有很好的灵活性。

网飞一直在使用 eBPF 来获得比 AWS 最初认为可能的更深入的指标，以分析亚马逊网络服务的性能，但当它第一次开始这项工作时，它仍然是专家的工具。“它现在似乎正成为主流，”RedMonk 联合创始人 [James Governor](https://twitter.com/monkchips) 告诉 The New Stack。

它是如此的有用和主流，以至于开发者和微软的客户开始问他们什么时候能在 Windows 中得到类似的东西。

## **为什么选择 Windows**

Thaler 告诉我们:“eBPF 已经成为一种革命性的技术，能够实现更好的可编程性、可扩展性和灵活性。他指出，这在 Windows 或任何其他操作系统上与在 Linux 上一样有用，在 Windows 和其他平台上使用通用工具和框架提供了工程效率。

“对于已经在 Linux 上使用 eBPF 的[开发人员]来说，在 Windows 上使用 eBPF 使相同类型的解决方案能够在两个平台上工作是很有吸引力的。即使对于那些只使用 Windows 的人来说，我们也相信 eBPF 的可编程性、可扩展性和敏捷性将为更广泛的受众开放开发。”

他预计 eBPF 通过 DASH 等方法为 SmartNICs 带来的同样的加速在将来也可能应用于 Windows。

Windows 已经有了通过调用公共 API 来扩展底层功能的方式，比如 [NDIS](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fwindows-hardware%2Fdrivers%2Fnetwork%2Froadmap-for-developing-ndis-drivers&data=04%7C01%7Cmary%40sandm.co.uk%7Cd59c4b1317384ee239a108d9b455e846%7C37c7766d87874f888075ac2e2ccaac3c%7C0%7C0%7C637739103349515429%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&sdata=xjNs8l0GaJO%2F7XmrsFAeO8Hl0Y43jEeclGp0voQ224A%3D&reserved=0) 、 [Windows 过滤平台](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fwindows%2Fwin32%2Ffwp%2Fwindows-filtering-platform-start-page&data=04%7C01%7Cmary%40sandm.co.uk%7Cd59c4b1317384ee239a108d9b455e846%7C37c7766d87874f888075ac2e2ccaac3c%7C0%7C0%7C637739103349525382%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&sdata=4BTtQVFT8ft895NipyV3Yl2z33Vsv%2BUMLuWy2G9wQKU%3D&reserved=0)、 [DTrace](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fgithub.com%2Fmicrosoft%2FDTrace-on-Windows&data=04%7C01%7Cmary%40sandm.co.uk%7Cd59c4b1317384ee239a108d9b455e846%7C37c7766d87874f888075ac2e2ccaac3c%7C0%7C0%7C637739103349525382%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&sdata=BNNCBu4H7qby27BC4%2BI%2FrpQzjP55e9mazGkMxPqHzVE%3D&reserved=0) 、[驱动拦截框架(DIF)](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fwindows-hardware%2Fdrivers%2Fdevtest%2Fverifier-command-line&data=04%7C01%7Cmary%40sandm.co.uk%7Cd59c4b1317384ee239a108d9b455e846%7C37c7766d87874f888075ac2e2ccaac3c%7C0%7C0%7C637739103349535359%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&sdata=kXrwojZV1vZ3%2B8rb3d9A73QHWMkpQBCGvPfI0z%2BngiI%3D&reserved=0) 等等。但是扩展 Windows 内核需要编写一个驱动程序并提交给微软签署，Thaler 指出，这是一个缓慢的过程。

由于 eBPF verifier 使用基于正式方法的分析来检查基于安全的代码，因此 eBPF 无需等待漫长的[批准]过程，即可实现快速扩展的灵活性，这在调试或 DDoS 缓解等时间关键的情况下尤其有用

“eBPF for Windows 将使开发人员能够使用多种现有的知名编程语言安全地使用这些框架，而无需编写内核驱动程序，并利用跨平台工具和经验的 eBPF 生态系统。”

Rice 对此表示赞同:“eBPF 为我们提供了一个非常强大的平台来构建像可观察性工具这样的东西，没有理由不像在 Linux 上一样适用于 Windows。”

重要的是，eBPF 被构建为在 Windows 上运行，而不是作为 Windows 的一部分，这意味着它将在现有版本的 Windows 上运行，而不需要更新操作系统。用于 Windows 的开源 [eBPF 项目支持 Windows 10、Windows Server 2016 和更高版本，微软为现有的开源 eBPF 项目贡献代码，以便它们可以与 Windows 以及 Linux(以及未来可能的其他操作系统)一起工作。](https://aka.ms/ebpf-for-windows)

当项目成熟时，它将转移到微软[描述的](https://cloudblogs.microsoft.com/opensource/2021/05/10/making-ebpf-work-on-windows/)作为“eBPF 生态系统中一个社区管理的基础”

## **基于开源的构建**

Windows 使用驱动程序，而 Linux 使用内核模块和 API，而不是系统调用，因此 eBPF 的实现需要稍有不同。微软选择的模块化架构也意味着 eBPF 可以用于更多的场景。

在运行之前，eBPF 字节码由运行在用户模式而不是内核中的开源 previous[静态验证器](https://github.com/vbpf/ebpf-verifier)进行检查:如果通过了所有的安全检查，代码要么被同样运行在用户模式的开源 uBPF JIT 编译器编译成本机代码，要么直接传递给 uBPF 解释器。解释器和编译后的本地代码都运行在内核模式。

Thaler 告诉我们，在用户模式下运行验证器和实时(JIT)编译器与在 Linux 上运行 eBPF 有很大的不同，但这是有意义的，这不仅仅是因为微软希望建立在已经决定为用户模式构建的现有社区项目上。

越来越多的趋势是将代码移出内核，因为如果驱动程序中有一个错误导致它崩溃，它不会关闭整个操作系统。

但这也意味着 eBPF 可以用来扩展用户模式守护进程，而不仅仅是内核。您甚至可以在一台设备上运行 eBPF，让它在另一台机器上提供功能和性能改进。泰勒解释道:

“我们认为，eBPF 构建模块(如验证器、解释器和 JIT 编译器)的代码的一个重要属性是，相同的代码不仅可以跨多个平台重用，而且可以在不同的上下文中使用，例如内置于操作系统内核中、在用户空间中运行、在可信执行环境中运行，甚至可以在独立于被扩展的操作系统的机器上运行。”

这意味着验证器必须非常可靠，并且需要受到保护，以便它像内核一样安全。

已经有一个用于验证器的测试套件，它将在准备生产之前进行模糊测试。验证程序为代码提供的安全属性也比微软通常在签署驱动程序之前对其进行的测试更强。

Thaler 指出，验证器和编译器都运行在 Windows 上的[特权系统服务中，用户空间 API 只能由管理员帐户调用，“我们正在研究未来的模型，其中验证器和编译器可以在单独的 VM 中运行，甚至可以在另一台机器上运行。”](https://docs.microsoft.com/en-us/windows/win32/services/protecting-anti-malware-services-#system-protected-process)

“eBPF for Windows 的许多安全强化工作仍然存在，这就是为什么它还没有被签署用于生产，只是测试环境，”他警告说。尽管你现在就可以安装并试用它，但你必须将你的 Windows PC 置于开发者模式，并启用测试签名的二进制文件；这对开发人员来说很常见，但出于安全原因，不适合生产系统。

你还必须坚持解释模式，除非你关闭[虚拟机监控程序强制代码完整性(HVCI)](https://techcommunity.microsoft.com/t5/windows-insider-program/virtualization-based-security-vbs-and-hypervisor-enforced-code/m-p/240571) 硬件虚拟化功能，Windows 使用该功能来保护内核模式进程，如登录服务免受攻击。JIT 编译器不会用 HVCI 信任的签名对代码进行签名，因此代码当前不会运行。

Thaler 指出，“如果其他条件相同，JIT 编译模式比解释模式更有效”，因此微软正在研究如何让 JIT 编译与 HVCI 一起工作。

## **跨平台代码**

开发人员可以使用现有的 eBPF 工具(如 clang)为 Windows 创建 eBPF 字节码，将它包含在 Windows 应用程序中，或者只是将它键入 Windows netsh 命令行工具中(就像 Linux 用户使用 Bpftool 一样)；它们都调用一个共享库来公开[Libbpf API](https://github.com/libbpf/libbpf)(并将代码传递给验证器)。

微软计划将任何你可以调用的东西作为公共 API，并在 Windows 中编写一个与 eBPF 相关的驱动程序，向 eBPF 公开。“eBPF 运行时确实提供了来自 eBPF 的额外构造，例如通过支持各种‘map’构造来使用共享内存。”

该代码可能与您在 Linux 上运行的 eBPF 代码相同，也可能不同，因为这取决于您是否在做 Windows 支持的事情。

一些 eBPF APIs 本质上是特定于 Linux 内核的，因为它们以一种依赖于内部实现细节的方式与功能交互或扩展功能。其他 eBPF APIs 扩展了跨平台通用的 TCP/IP 等功能，”Thaler 解释道。

调用网络套接字或绑定到 IPv4 或 IPv6 等通用协议，您可以重新编译 Linux eBPF 代码以在 Windows 上运行。

“我们的目标是拥有一个大型的跨平台 API 集，同时使任何人都能够轻松地为他们选择的平台添加额外的 API，例如扩展他们自己的驱动程序或用户空间应用程序中的功能，”Thaler 说。

这意味着如果 eBPF 字节码调用这些 API，相同的代码将在 Linux 和 Windows 上工作。

至于 eBPF 代码可以调用的钩子和助手函数，eBPF for Windows 已经支持两个钩子和超过 10 个跨平台助手，记录在 [bpf_helper_defs.h](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fmicrosoft.github.io%2Febpf-for-windows%2Fbpf__helper__defs_8h.html&data=04%7C01%7Cmary%40sandm.co.uk%7Cd59c4b1317384ee239a108d9b455e846%7C37c7766d87874f888075ac2e2ccaac3c%7C0%7C0%7C637739103349495522%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&sdata=cEx6vo%2FJklEhxhfic38yUmGOUNpgUCLg%2B%2BVXpqSj2z8%3D&reserved=0) 和 [ebpf_nethooks.h](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fmicrosoft.github.io%2Febpf-for-windows%2Febpf__nethooks_8h.html&data=04%7C01%7Cmary%40sandm.co.uk%7Cd59c4b1317384ee239a108d9b455e846%7C37c7766d87874f888075ac2e2ccaac3c%7C0%7C0%7C637739103349505476%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000&sdata=t1gPEXE2TTutNxzivw%2F1W%2BGNp4g0wVJkfU8TqfGzddg%3D&reserved=0) 中。

“对于核心 eBPF 执行上下文，微软不得不添加各种地图类型和助手功能的实现，因为没有可以立即利用的现有开源项目，”Thaler 说。“我们的希望是，随着时间的推移，这种实现将转移到跨平台项目，如通用 ebpf 项目，这样 eBPF for Windows 就可以使用了。”

他说，微软首先关注最常用的 API，以支持流行的应用程序，但任何调用公共 API 的钩子和助手都可以从社区中贡献出来。

因为 eBPF 到目前为止只在 Linux 上可用，所以用于检查 Kubernetes 集群的 eBPF 工具(如 Libbpf、Bpftool 或 Kinvolk 的 Inspektor Gadget suite，现在归微软所有)假设您将使用 Linux，并且依赖于 Linux 特定的功能和实现，甚至是其他平台上可用的功能和实现。

Linux 上的许多助手和挂钩本质上是特定于 Linux 的，或者公开了使用 Linux 实现细节的结构。其中一些不适用于任何其他平台，而一些可能适用，但其他平台使用不同的原生格式，”他解释道。

对于那些应用但只是使用不同的本机格式的应用程序，通过将数据复制到现有 eBPF helper 公开的格式中，一些跨平台的功能仍然可以存在，但性能代价很小。“微软正在与社区合作，将 Libbpf 和 Bpftool 中的本机和跨平台功能分离开来，以便它们也可以在 Windows 上使用。

更高级别的工具，如沃尔玛为 LF 网络组提供的用于 eBPF 网络应用程序的 [L3AF](http://l3af.io/) 生命周期管理和[编排](https://medium.com/walmartglobaltech/introducing-walmarts-l3af-project-how-do-we-use-ebpf-to-provide-network-visibility-in-a-8b9ae4d26200)项目(包括负载平衡、速率限制、流量镜像、流量导出器、数据包处理和性能调整)，目前也仅适用于 Linux 微软再次与 L3AF 社区合作，带来对 Windows 的支持。

排在 eBPF 将提供的可观察性和调试特性之前的第一个要求是它将在 Windows 上提供的拒绝服务保护。

eBPF 在 Windows 上的另一个巨大机会是，当组织需要调整诸如端口重定向或套接字处理之类的事情时，支持他们自己的遗留内部应用程序。如果您需要在应用程序需要端口 80 时使用端口 8080，或者您需要使用一个套接字，而中间件只公开一个 http 抽象，eBPF 使它更容易创建工作区——而不需要编写一个定制的驱动程序并获得签名。

许多使用 Windows 服务器的组织会发现这很有用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>