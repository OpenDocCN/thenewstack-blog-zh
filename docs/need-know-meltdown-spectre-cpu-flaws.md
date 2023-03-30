# 关于 Meltdown 和 Spectre CPU 缺陷你需要知道什么

> 原文：<https://thenewstack.io/need-know-meltdown-spectre-cpu-flaws/>

计算机行业正在竞相应对影响现代计算机和移动设备中大多数处理器的几个新漏洞。这些缺陷使得新的攻击能够打破操作系统中关键的内存防御，并绕过基本的隔离层，包括那些对虚拟化和容器技术至关重要的隔离层。

最严重的缺陷被称为 Meltdown 或 [CVE-2017-5754](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5754) ，允许在用户空间运行的应用程序从内核内存中提取信息，其中可能包含密码、加密密钥和其他秘密等敏感数据。好消息是，Meltdown 可以通过软件补丁在很大程度上得到缓解，不像其他两个被统称为 Spectre 的漏洞( [CVE-2017-5753](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5753) 和 [CVE-2017-5715](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5715) )需要 CPU 微码更新，并可能在未来一段时间内困扰行业。

Meltdown 和 Spectre 都源于现代 CPU 的一个与性能相关的特性，称为投机执行。当处理器到达程序控制流中的条件分支时，这就开始起作用了。CPU 不是进入空闲状态，等待看到程序将采取的路径，而是使用内部算法来猜测最可能的路径，并提前执行指令。如果后来发现选择的路径是不正确的，则推测性的执行结果在对系统可用之前被丢弃，并且 CPU 沿着正确的路径继续执行。

过去一年中，来自多个组织的研究人员独立发现，通过监控 CPU 缓存中的操作计时，可以对推测性执行结果进行某些观察，这些观察可用于重建数据。这种泄漏并不新鲜，被称为缓存计时旁路。

Meltdown 是利用这种 CPU 特性的一种特殊方法，它与特权提升问题相结合，[主要影响英特尔 CPU](https://newsroom.intel.com/press-kits/security-exploits-intel-products/)、[，但也影响一些 ARM 处理器](https://developer.arm.com/support/security-update)。它是由三个团队独立发现的: [Google Project Zero](https://googleprojectzero.blogspot.com/) 的 Jann Horn 赛博思科技[的维尔纳·哈斯和托马斯·普雷舍](https://www.cyberus-technology.de/)；以及来自[格拉茨科技大学](https://www.tugraz.at/home/)的丹尼尔·格鲁斯、莫里茨·利普、斯特凡·曼加德和迈克尔·施瓦茨。

来自格拉茨理工大学的团队[之前提出了一种隔离内核和用户空间内存的新方法](https://gruss.cc/files/kaiser.pdf)，以防止针对内核地址空间布局随机化(KASLR)的基于硬件的攻击，这是一种安全防御，使利用整个类别的漏洞更加困难。

他们的新方法[被称为 KAISER](https://lwn.net/Articles/738975/) ，是内核地址隔离的缩写，可以有效地去除旁路，但在 Linux 内核中实现时，它被重命名为内核页表隔离(KPTI)。碰巧的是，即使它的目的是作为 KASLR 硬化，KPTI 也减轻了熔毁。

KPTI 出现在 1 月 2 日发布的 Linux 内核的最新稳定版本 4.14.11 中，但尚未向后移植到长期支持的(LTS)版本，如 4.9.x 或 4.4.x。如果你运行的是基于 Linux 的系统，请确保在 KPTI 补丁为你的版本发布后立即更新内核。

微软[也发布了 Windows 客户端和服务器](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/adv180002)的补丁，但是[它们可能会导致与某些杀毒产品](https://support.microsoft.com/en-us/help/4072699/important-information-regarding-the-windows-security-updates-released)的冲突。如果你的安全产品不兼容，在部署微软的 Meltdown 补丁之前，你必须禁用它或者从它的开发者那里获得兼容性补丁。有一个注册表设置可以检查，还有一个兼容性列表由安全架构师 Kevin Beaumont 维护。

苹果也开发了自己的熔毁缓解技术，并作为 macOS 10.13.2 的一部分发布。该公司将为 Safari 和 macOS 发布额外的补丁，以缓解 Spectre 的缺陷。

KPTI 的问题在于，对于涉及许多系统调用和中断的工作负载，它[会对系统性能](https://access.redhat.com/articles/3307751)产生影响。数据库等 I/O 密集型任务也将受到影响。[测试仍在运行](https://www.phoronix.com/scan.php?page=article&item=linux-kpti-pcid&num=2)以确定不同应用的确切影响，但对于大多数用例来说，性能影响预计不会很大。

Red Hat 操作系统平台副总裁 Denise Dumas 表示:“从消费者到企业 It 组织，应用他们收到的安全更新非常重要。由于这些安全更新可能会影响系统性能，Red Hat 提供了有选择地启用它们的功能，以便更好地了解对敏感工作负载的影响

Meltdown 还对虚拟化环境和容器技术(如 Docker、LXC 和 OpenVZ)产生了严重的安全影响，这些技术共享同一个内核。 [Xen](https://blog.xenproject.org/2018/01/04/xen-project-spectremeltdown-faq/) 、 [VMware](https://www.vmware.com/us/security/advisories/VMSA-2018-0002.html) 、 [QEMU](https://www.qemu.org/2018/01/04/spectre/) 、 [Citrix](https://support.citrix.com/article/CTX231390) 和 [Red Hat](https://access.redhat.com/security/vulnerabilities/speculativeexecution) 都发布了安全建议或博客文章，描述了对其虚拟化软件的影响。

像亚马逊 AWS、谷歌云、微软 Azure、Rackspace 和 T21 数字海洋这样的大型云提供商也发布了建议和计划维护窗口，以便在必要时应用补丁。建议客户在其客户操作系统中安装补丁。

Spectre 攻击更加普遍，迄今为止展示的变种仅用于欺骗其他应用程序，而不是内核，以暴露它们自己的内存和秘密。强迫像浏览器这样的应用程序泄露密码和其他敏感信息有严重的影响，KPTI 没有解决这个问题。

与 Meltdown 相比，Spectre 缺陷影响了更多来自所有供应商的 CPU，包括英特尔、AMD 和 ARM。AMD 表示，Meltdown 不会影响其任何处理器，由于架构差异，Spectre 的一个变种对其 CPU 的“利用风险接近于零”。

彻底解决 Spectre 将是一项长期的工作，将涉及部署需要由计算机原始设备制造商分发的 CPU 微码补丁，以及针对操作系统和应用程序的补丁，如针对浏览器的补丁。还值得指出的是，到目前为止演示的两种 Spectre 变体可能不是滥用推测性执行功能的唯一方式，研究人员很可能在未来提出改进的技术。最终，这种性能机制可能不得不在未来几代处理器中重新审视、重新设计或删除。

研究人员在 Spectre 白皮书中表示:“软件隔离技术以各种名义得到了极其广泛的部署，包括沙箱、进程分离、容器化、内存安全、证据携带代码。”“支撑所有这些的一个基本安全假设是，CPU 将忠实地执行软件，包括其安全检查。不幸的是，推测性执行违反了这一假设，它允许对手破坏存储器和寄存器内容的保密性(而不是完整性)。因此，许多软件隔离方法都会受到影响。”

[谷歌](https://cloud.google.com/kubernetes-engine)、[数字海洋](https://www.digitalocean.com/)、、[微软](https://azure.microsoft.com/en-us/?v=17.14)和[红帽](https://www.openshift.com/)是新栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>