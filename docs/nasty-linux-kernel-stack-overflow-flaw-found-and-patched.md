# 发现并修补了严重的 Linux 内核堆栈溢出漏洞

> 原文：<https://thenewstack.io/nasty-linux-kernel-stack-overflow-flaw-found-and-patched/>

又来了。另一个令人讨厌的安全漏洞，[CVE-2022-0435:2021 年 11 月，](https://www.openwall.com/lists/oss-security/2022/02/10/1) [Appgate](https://www.appgate.com/) 高级漏洞开发者[塞缪尔·佩奇](https://www.appgate.com/blog/a-remote-stack-overflow-in-the-linux-kernel)在研究 Linux 堆溢出安全漏洞 [CVE-2021-43267](https://www.sentinelone.com/labs/tipc-remote-linux-kernel-heap-overflow-allows-arbitrary-code-execution/) 时发现了 Linux 内核中的远程堆栈溢出。Page 的发现是 Linux 内核的[透明进程间通信(TIPC)](https://www.kernel.org/doc/html/latest/networking/tipc.html) 协议联网模块中远程和本地可达的堆栈溢出。

顾名思义，TIPC 用于集群内通信。使用节点和这些节点之间的链接的概念来管理集群拓扑。使用 TIPC 发送的消息可以通过 UDP 或以太网发送。到目前为止，一切顺利。

## 监测框架

但是，2016 年 6 月，TIPC 模块获得了自己的监控框架。

有了这个特性，节点可以监视集群的网络拓扑，并与同一域中的其他节点共享它的视图。不幸的是，它的健全性检查不够好。研究人员发现伪装成对等节点是可能的。这样，就可以在本地或远程建立与目标的链接，并加载包含任意有效负载的恶意域记录。你可以看到这将导致什么。

是的，的确如此，正如 Page 所写的，“利用漏洞是微不足道的，并且可以通过内核恐慌导致拒绝服务。”我不知道你怎么样。没有另一次 Linux 内核级的拒绝服务攻击，我也能活下去。

该漏洞存在于 Linux 内核 4.8 到 5.17-rc3 版本中。然而，尽管 TPIC 模块存在于大多数主流发行版中，但它必须被加载才能被利用。“此外，”佩奇写道，“对于远程攻击，目标需要已经建立了 TIPC 载体，即该漏洞会扩展到使用 TIPC 的系统。”

## 可能会更糟

换句话说，情况可能会更糟。

尽管如此， [Red Hat](https://www.redhat.com/en) 给这个 TIPC 安全漏洞的通用漏洞评分系统(CVSS)评分是 7.1，这足以引起我的注意。

虽然现在已经有了一个 [TIPC 补丁](https://github.com/torvalds/linux/commit/9aa422ad326634b76309e8ff342c246800621216)并且可以从大多数主要的 Linux 发行版中获得，但是 Red Hat 还有其他一些我认为你应该认真对待的警告。

首先，如果你没有使用 TIPC，但是你正在加载你的 Linux 实例:停止。您可以使用简单的 root 命令来阻止模块的加载:

`# echo "install tipc /bin/true" >> /etc/modprobe.d/disable-tipc.conf`

如果 TIPC 模块已经加载，您需要重新启动系统。这是因为只要有任何网络接口处于活动状态并且协议正在使用中，您就不能卸载 TIPC。

此外，Red Hat 建议您使用传输层来分离和/或保护(通过 IPSec/MACSec 等加密和认证)节点之间的通信。加密这种流量总是一个好主意。你永远不知道谁可能会偷看你的流量到半信任的节点。

因此，在这一点上，我敦促你修补你的系统，并考虑其他方式来保护你的内部网络。补丁将停止这个问题，但总有一个新的攻击在等着你。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>