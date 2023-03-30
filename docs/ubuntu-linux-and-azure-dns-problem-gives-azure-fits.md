# Ubuntu Linux 和 Azure 的 DNS 问题给了 Azure 灵感

> 原文：<https://thenewstack.io/ubuntu-linux-and-azure-dns-problem-gives-azure-fits/>

三年多来，Linux，而不是 Windows Server，一直是微软 Azure 上最流行的虚拟机(VM)操作系统。而且，在云上使用的所有 Linux 发行版中， [Canonical Ubuntu 一直是最受欢迎的](https://www.zdnet.com/article/ubuntu-linux-continues-to-rule-the-cloud/)。唉，这不是一个“是的，对于 Linux 的故事！”恰恰相反。甚至 Linux 也有它的问题，最近，Ubuntu 18.04 中最近的 [DNS 更新导致 Azure VMs](https://status.azure.com/en-us/status) 失败。大量 Azure 虚拟机出现故障。

麻烦开始于世界协调时 2022 年 8 月 30 日 06:00，问题持续到 8 月 31 日。现在，它已经成为历史，我们只能希望我们不会看到重复，同时记住，云，像任何其他技术一样，会不时地失败。

## 问题的核心

问题的核心是，当一个安全补丁 [systemd 237-3ubuntu10.54 被用于 Ubuntu 18.04](https://bugs.launchpad.net/ubuntu/+source/systemd/+bug/1988119) 实例时，它使它们无法解析 DNS 查询。这，当然，打破了网络，就是这样。跟着我重复。总是 DNS。

修复了 [CVE-2022-2526](https://access.redhat.com/security/cve/CVE-2022-2526) ，一个 [systemd 如何处理 DNS 包的释放后使用内存漏洞](https://bugzilla.redhat.com/show_bug.cgi?id=2109926)。如果不修复，这是一个高级别的安全问题，可能会关闭系统并获得根级别的权限。除了 Ubuntu 18.04，红帽企业版 Linux (RHEL) 7 和 8.x 以及 [Debian Linux](https://security-tracker.debian.org/tracker/CVE-2022-2526) 中也存在安全漏洞及其修复。

所以，你会问，为什么这个问题没有出现在所有地方，出现在各种各样的云中？这是因为微软 Azure 有一个特定的 [netplan](https://netplan.io/) 设置，一种特定于 Ubuntu 的设置云网络的方式，它使用“驱动程序”匹配来设置网络。如果执行了 [udevadm](https://linux.die.net/man/8/udevadm) 触发器，包含该信息的对将丢失。然后，下次执行 netplan 时，服务器会丢失其 DNS 信息。简而言之，责任不全落在 Ubuntu 身上。Azure 也应该得到公平的份额。

## 怎么修

也就是说，64 位的问题是:“我如何修复它？”有几个答案:

当然，您可以重启实例。这将给你的虚拟机一个新的 DHCP 租约和新的 DNS 解析器。

微软还为 [Azure Kubernetes 服务(AKS)](https://thenewstack.io/azure-kubernetes-service-replaces-docker-with-containerd/) 集群部署了自动修复。但是，很重要的一点是，一些 AKS 节点不在自动修复检测范围内，因此它们没有得到修复。

这个故事的寓意是，一如既往，总是检查 DNS，以防出现任何问题。是的，我很认真。即使是对复杂的基于云的系统的简单修复也会导致非常复杂的问题。因此，在修补生产系统时，即使是最小的问题，也要小心。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>