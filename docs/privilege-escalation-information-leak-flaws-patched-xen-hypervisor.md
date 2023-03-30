# Xen 虚拟机管理程序修补了权限提升和信息泄漏缺陷

> 原文：<https://thenewstack.io/privilege-escalation-information-leak-flaws-patched-xen-hypervisor/>

Xen 项目修复了广泛使用的 Xen 虚拟化管理程序中的五个新漏洞。这些缺陷可能允许攻击者突破虚拟机，从主机系统访问敏感信息。

根据[](https://www.qubes-os.org/news/2017/08/15/qsb-32/)[Qubes OS](https://www.qubes-os.org/)的安全团队的分析，这是一个依赖 Xen 作为其安全模型的操作系统，大多数漏洞源于用于域间共享内存的机制。在 Xen 下，主机系统和虚拟机(来宾)在不同的安全域中运行。

最严重的漏洞位于[半虚拟化](https://wiki.xen.org/wiki/Paravirtualization_(PV)) (PV)虚拟机的内存管理代码中，允许来宾将其权限提升至主机权限，从而破坏它们之间的关键隔离层。该漏洞被跟踪为 CVE-2017-12137，并在 Xen [XSA-227](https://xenbits.xen.org/xsa/advisory-227.html) 安全公告中涵盖。

Xen 支持两种类型的虚拟机:半虚拟化(PV)，它通过 API 使用基于软件的虚拟化，以及[硬件虚拟机](https://wiki.xen.org/wiki/Xen_Project_Software_Overview#HVM) (HVMs)，它利用直接内置到现代 CPU 中的虚拟化特性。在这两者中，PV 被认为是遗留模式，并且在过去几年中一直是 Xen 中严重的特权提升缺陷的来源。

在信息安全中，特权提升漏洞是授予用户比正常情况下更多的权利或权限的安全缺陷。在操作系统的上下文中，这可能意味着从受限用户那里获得机器上的完全管理权限(root)。在 Xen 等虚拟机管理程序的环境中，这可能意味着脱离虚拟机并获得主机系统上的权限，这可能会导致共享相同物理硬件的所有虚拟机受到损害。

跟踪为 [CVE-2017-12135](https://xenbits.xen.org/xsa/advisory-226.html) 的传递授权机制中的第二个漏洞，可能允许控制来宾操作系统的攻击者使 Xen 崩溃，从而导致拒绝服务情况。然而，不能排除特权升级和信息泄露的可能性，Xen 团队在一份咨询报告中说。

在最近的版本中修补的另外两个漏洞， [CVE-2017-12136](https://xenbits.xen.org/xsa/advisory-228.html) 和 [CVE-2017-12134](https://xenbits.xen.org/xsa/advisory-229.html) ，也可以被利用来使 Xen 崩溃，并可能允许权限提升。其中，后者实际上并不在 Xen hypervisor 本身中，而是在用于合并相邻的特定于 Xen 的块 IO 请求的 Linux 内核机制中。除了拒绝服务和权限提升之外，该缺陷还可能导致敏感信息泄漏。

最后，第五个修复的漏洞，跟踪为 [CVE-2017-12855](https://xenbits.xen.org/xsa/advisory-230.html) ，可能导致访客在另一个域释放内存帧之前使用主机授予的内存帧。这也可能导致信息泄露。

Xen 被广泛用于云托管环境，但公共和私有，以建立虚拟专用服务器。多租户数据中心通常面临更大的攻击风险，因此它们的所有者被迫重新启动服务器，以便在服务器发布后立即应用 Xen 补丁。Xen 项目会提前通知一些大型托管公司，以便他们可以安排维护窗口。

[![](img/035f781299a0ef3abc9421b5534f4d43.png)](https://summit.pagerduty.com/global)

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>