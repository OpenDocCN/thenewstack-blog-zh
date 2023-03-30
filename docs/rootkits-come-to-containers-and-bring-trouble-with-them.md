# Rootkits 会出现在容器中并带来麻烦

> 原文：<https://thenewstack.io/rootkits-come-to-containers-and-bring-trouble-with-them/>

Rootkits 一直是服务器的一大难题。这些恶意程序的集合会隐藏在服务器上，同时允许它们的控制者以管理员级别访问计算机或网络。虽然他们不再像以前那样获得安全头条，但他们仍然活着，并造成损害。因此， [Aqua 的团队 Nautilus](https://www.aquasec.com/research/) 发现许多[攻击者使用高级持续威胁(APT)技术在云原生容器中植入 rootkit](https://blog.aquasec.com/advanced-persistent-threat-techniques-container-attacks?hs_preview=AaxLSEqI-53483235999)也就不足为奇了。

安保行业从来没有沉闷的时候。

apt 和 rootkits 齐头并进。APT 是敌人使用持续的、秘密的和复杂的黑客技术闯入你的系统的坚定努力。一旦进入，它们就保持隐藏状态，不速之客会窃取数据或设置恶意软件进行更大、更好的攻击。rootkit，顾名思义——root 访问是由一个隐藏的程序包完成的——与 APTs 配合得很好。

通常，由于其庞大的规模，亚太贸易协定是由民族国家执行的。可悲的是，Rootkits 可以被任何脚本小子植入。

Aqua 在这一系列最新攻击中发现了以下步骤:

1.  **运行一个普通的容器映像:**对手运行一个 [Alpine Linux](https://www.alpinelinux.org/) 容器映像。
2.  **逃到主机:**然后，攻击者挂载主机文件系统以逃离容器并获得对主机的访问权。
3.  **下载恶意脚本:**他们逃到主机后，在 cron 调度程序系统中编写命令，从远程源下载并执行恶意外壳脚本(cronb.sh)。
4.  **加载并执行恶意软件:**脚本 cronb.sh 是有效载荷，它执行攻击。

简单又丑。

Nautilus 团队发现，在“云原生环境中，攻击者通常在主机上执行 rootkits，以隐藏恶意进程，并减少他们逃离容器化环境后被检测到的机会。”当然，“rootkits 可以用来覆盖用户空间中的函数或二进制文件(例如，使用 [LD_PRELOAD](http://www.goldsborough.me/c/low-level/kernel/2016/08/29/16-48-53-the_-ld_preload-_trick/) )”最后一个是一个非常古老的 C 库技巧，但是它今天仍然被成功地使用和滥用。

具体来说，无论这些攻击者是谁，他们都在使用 [Linux 内核空间 rootkit 二乙酰吗啡](https://github.com/m0nad/Diamorphine)。如果他们不能获得二乙酰吗啡，他们会尝试使用用户空间 rootkit 作为退路。在这两种情况下，关键是对系统隐藏真正的恶意负载。

无论是 rootkit，在当前的 rootkit 攻击中，游戏的名称是隐藏恶意程序，如比特币矿工，它们对进程监控程序(如跟踪 Linux 进程的 [ps](https://man7.org/linux/man-pages/man1/ps.1.html) 或 [top](https://man7.org/linux/man-pages/man1/top.1.html) )具有高 CPU 使用率。他们通过操纵如何在 Linux 的/proc/ 文件系统中查看数据来做到这一点。几乎所有报告进程的用户空间工具都依赖于/proc/ filesystem 内容。因此，当您调用 top 时，您正在使用 [getdents](https://man7.org/linux/man-pages/man2/getdents.2.html) 或 getdents64 函数从 proc 中提取数据。这个 rootkit 拦截这些函数并隐藏隐藏进程的数据。

那么，你对此能做些什么呢？正如大家一直告诉你的。让你的 Linux 系统和开源软件保持最新。除非你打开了门，否则没有一个 rootkits 可以进来。用最新的安全软件保持关闭和锁定，没有已知和固定的漏洞，你很好。当然，很少会出现针对 Linux 的零日攻击，但这种情况很少见。已知的、固定的安全漏洞是大多数攻击者进入的真正途径。

此外，正如美国国家安全局(NSA)提醒我们的，您应该将系统配置为只加载具有有效数字签名的模块。这使得攻击者更难将恶意内核模块推入您的容器。

Aqua 还建议你使用 [Tracee](https://github.com/aquasecurity/tracee) 来保护自己。这是一个开源的 Linux 运行时安全和取证工具。它建立在[扩展 BPF (eBPF)](https://prototype-kernel.readthedocs.io/en/latest/bpf/) 之上。Tracee 0.5.0 及以上版本使您能够编写[开放策略代理](https://www.openpolicyagent.org/) (OPA) [减压阀签名](https://github.com/aquasecurity/tracee/issues/486)。这样做的目的是让你能够发现可疑的活动。例如，Aqua 添加了一些基本的签名，如“尝试加载内核模块检测”顾名思义，这可以让你检测可疑的内核驱动加载。有关如何使用 Tracee 检测权限提升的更深入分析，请查看在 BlackHat 2021 上由[团队 Nautilus 发表的演讲。](https://www.youtube.com/watch?v=LXP2tdBPNj8)

您也可以使用 [Aqua Enforcers 的](https://docs.pivotal.io/partners/aquasec/deploying-enforcer.html) [文件完整性监控(FIM)](https://www.tripwire.com/solutions/file-integrity-and-change-monitoring/what-is-fim/) 。这通过将当前文件状态与已知的良好基线进行比较来验证操作系统应用程序文件。如果 rootkit 更改了一些二进制文件的名称，并插入带有它们名称的新文件，它会发现这些更改，并警告您系统中有不怀好意的程序。

[https://www.youtube.com/embed/LXP2tdBPNj8?feature=oembed](https://www.youtube.com/embed/LXP2tdBPNj8?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>