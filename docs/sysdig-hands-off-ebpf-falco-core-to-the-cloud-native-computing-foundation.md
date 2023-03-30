# Sysdig 将 eBPF Falco 核心移交给云本地计算基金会

> 原文：<https://thenewstack.io/sysdig-hands-off-ebpf-falco-core-to-the-cloud-native-computing-foundation/>

2018 年，云原生安全公司 [Sysdig](https://sysdig.com/) 向云原生计算基金会(CNCF)贡献了 [Falco](https://falco.org/) 运行时安全项目。现在，该公司正在跟进增加的开源 Sysdig 内核模块的[贡献](https://sysdig.com/blog/sysdig-contributes-falco-kernel-ebpf-cncf/)，其用于 Linux 内核的扩展 Berkeley Packet Filter (eBPF)探测器，以及两个 Falco 库，所有这些都将作为 [Falco 项目](https://github.com/falcosecurity)的一部分，位于 [falcosecurity](https://github.com/falcosecurity) GitHub 资源库中的 [CNCF](https://cncf.io/?utm_content=inline-mention) 下。

Sysdig 开源项目的内核和 eBPF 探针都是核心组件，它们允许 Sysdig 和 Falco 通过收集[系统调用](https://en.wikipedia.org/wiki/System_call)来收集系统数据，而库 [libsinsp](https://github.com/falcosecurity/libsinsp) 和 [libscap](https://github.com/falcosecurity/libscap) 负责处理捕获的数据。更具体地说，libsinsp 是一个内核事件丰富库，libscap 是一个系统调用捕获库，完全支持捕获文件抽象。

虽然图书馆本身已经是开源的，但所有这些现在都将是开源的，它们的知识产权将移交给 CNCF。

根据 Sysdig 首席技术官和创始人[洛里斯·德吉奥安尼](https://www.linkedin.com/in/degio)的说法，这些工具和库最初可能是考虑到 Sysdig 和 Falco 的实现而设计的，但它们能够用于各种其他目的，他希望这种贡献将导致那种创新。

“这个捐赠是核心堆栈，用于从 Linux 系统的内核收集信息，并以有意义和丰富的方式将这些信息传递给应用程序。Degioanni 在一次采访中说:“这些可用于构建运行时安全工具，如 Falco，用于构建开源 Sysdig 等入侵分析工具中的取证，但也可用于编写大量应用程序，既包括安全领域，也包括性能管理领域。“我们期待社区接受这一真正强大的知识产权。我们期待着看到社区能够在有趣和创造性的应用方面带来什么。”

Degioanni 在一篇博客文章中解释说，Sysdig 内核和 eBPF 探针提供了相同的功能，但是“内核模块更高效，而 eBPF 方法更安全、更现代。”他进一步解释说，eBPF 允许用户通过编写脚本来扩展 Linux 内核，然后由内核运行，而不改变内核本身，让用户访问内核活动，而不会将系统稳定性或安全性置于风险之中。

唯一的问题是 eBPF 可能很难使用，eBPF probe 简化了这一点，使开发人员更容易访问故障排除、性能分析、取证和威胁搜索功能。

Degioanni 说:“这是过去几年来 Linux 和操作系统中发生的最令人兴奋的事情之一，因为它为从本质上扩展 Linux 并将其模块化打开了大门，每个人都可以在任何时候这样做，而不必重新编译内核，然后做一些非常技术性的事情。

Degioanni 说，他认为捐赠是一个更大的战略和运动的一部分，在这个战略和运动中，即使在通常封闭的安全世界中，行业也在朝着开源而不是专有软件的方向发展。

“我们坚信安全的未来将是开放的，”Degioanni 说。“我们正在见证基于 Kubernetes 和所有其他项目的云新堆栈的形成，这些项目是云原生计算基础的一部分。我们见证了这样一个事实:人们，尤其是在云计算的新世界中，不希望采用基于专有供应商封闭标准的传统方法。这笔捐款是对这一战略的特别加倍。”

虽然 Degioanni 拒绝透露他们是否与 CNCF 的任何具体项目进行了沟通，以备未来的潜在实施，但他确实表示，他们“正在与 CNCF 的所有不同项目进行广泛沟通”，“这可能有利于许多 CNCF 项目，包括像 Kubernetes 这样的深度项目。”

有了这个贡献，Falco 栈的全部都是开源的，并由 CNCF 所有和指导。

由 [L N](https://unsplash.com/@younis67?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/s/photos/probe?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>