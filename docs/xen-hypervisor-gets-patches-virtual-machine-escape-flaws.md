# Xen 虚拟机管理程序获得虚拟机逃逸缺陷的补丁

> 原文：<https://thenewstack.io/xen-hypervisor-gets-patches-virtual-machine-escape-flaws/>

Xen 项目本周修复了其广泛使用的管理程序软件中的严重漏洞，迫使虚拟服务器运营商安排维护停机时间来应用补丁并重启受影响的系统。

如果不进行修补，这些漏洞可能会从客户操作系统内部被利用来使虚拟机管理程序崩溃，从主机操作系统或其他客户中提取敏感信息，或者从虚拟机中逃脱并获得与虚拟机管理程序相同的权限，换句话说，获得对一切的完全控制。

尽管最近几个月 Xen 中修补的许多关键漏洞只影响了使用[半虚拟化](https://wiki.xen.org/wiki/Paravirtualization_(PV)) (PV)的基于 Xen 的虚拟机，但此次安全发布中修复的一些缺陷也影响了[硬件虚拟机](https://wiki.xen.org/wiki/Xen_Project_Software_Overview#HVM) (HVMs)。PV VMs 通过 API 使用基于软件的虚拟化，而 hvm 使用硬件辅助虚拟化，可以更好地利用现代硬件的某些功能。

本周修补的漏洞尚未获得[常见漏洞和暴露](https://cve.mitre.org/)(CVE)id，但它们在 [Xen 安全顾问 XSA-216 至 XSA-225](https://xenbits.xen.org/xsa/) 中有所描述。好消息是，根据 Qubes OS 安全团队的分析，由于某些要求或限制，其中大多数在实践中不容易被利用。

[Qubes OS](https://www.qubes-os.org/) 是一款面向安全的桌面操作系统，使用 Xen 隔离虚拟机内部的应用。由于 Xen 位于操作系统安全模型的核心，管理程序中的任何漏洞都是 Qubes 本身的潜在安全风险，并由其开发人员进行评估。

“每个[缺陷]要么需要一些竞争条件来获胜(XSA[217](https://xenbits.xen.org/xsa/advisory-217.html)，[218](https://xenbits.xen.org/xsa/advisory-218.html)，[219](https://xenbits.xen.org/xsa/advisory-219.html))，控制一个以上的虚拟机(XSA 218，219)，一些通常超出攻击者控制的内存分配，以某种特定方式失败或发生(XSA[216](https://xenbits.xen.org/xsa/advisory-216.html)，217，218，219，[222](https://xenbits.xen.org/xsa/advisory-222.html))，或者这些的组合，”Qubes“此外，一些错误被认为仅限于泄漏或拒绝服务(XSA 216， [221](https://xenbits.xen.org/xsa/advisory-221.html) )，或仅影响虚拟机内部安全(XSA [220](https://xenbits.xen.org/xsa/advisory-220.html) )。”

这并不意味着缺陷应该被忽略，不打补丁。Qubes 是一个面向桌面的操作系统，虽然 Qubes 可能很难满足一些利用需求，但对于在同一虚拟机管理程序上运行多个虚拟专用服务器的多租户数据中心来说，情况可能会有所不同。

例如，云托管提供商 Linode [不得不重启一些遗留的 Xen 主机服务器](https://status.linode.com/incidents/v1tg82dd8hq9)以便应用补丁。该公司建议客户转移到其 KVM(基于内核的虚拟机)服务器，以避免未来受到影响。

亚马逊网络服务在一份咨询报告中称，其客户的数据和实例没有受到这些 Xen 安全问题和补丁的影响。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>