# Systemd 缺陷使得 Linux 发行版争相修补

> 原文：<https://thenewstack.io/systemd-flaw-leaves-linux-distributions-scrambling-patch/>

Ubuntu、Fedora、Arch Linux 和其他 Linux 发行版发布了针对一个严重的任意代码执行漏洞的修补程序，该漏洞可通过恶意域名系统(DNS)数据包来利用。

该缺陷是在 [systemd-resolved](https://www.freedesktop.org/software/systemd/man/systemd-resolved.service.html) 中发现的，该服务是近年来许多 Linux 发行版采用的 [systemd](https://freedesktop.org/wiki/Software/systemd/) 初始化系统的一部分。解析服务通过查询 DNS 服务器为本地应用程序提供网络名称解析。

这个被追踪为 [CVE-2017-9445](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-9445) 的漏洞是由 [Chris Coulson](https://twitter.com/chrisccoulson) 发现的，他是 Canonical 的软件工程师，也是 Ubuntu 团队的成员，他注意到在处理特定大小的数据包时，systemd-resolved 无法分配足够大的缓冲区。

“恶意的 DNS 服务器可以利用这一点，通过使用特制的 TCP 有效载荷进行响应，欺骗 systemd-resolved 分配一个太小的缓冲区，并随后在缓冲区末端之外写入任意数据，”Coulson 在开源安全邮件列表上发布的建议中说。

这可能导致 systemd 解析的守护程序崩溃，或者在其上下文中执行潜在的恶意代码。

攻击者可以通过多种方式向运行 systemd-resolved 的 Linux 系统发送恶意 DNS 数据包。其中之一是在不安全的无线网络上或通过受损的路由器发起中间人攻击。

幸运的是，并不是所有的 Linux 系统都受到影响，因为有些发行版不使用 systemd，即使在使用 systemd 的发行版中，也不是所有的发行版都包含 systemd-resolved。例如，SUSE 和 openSUSE 发行版[不提供这个组件](https://www.suse.com/security/cve/CVE-2017-9445/)，而 Debian 9 (Stretch)包括它，服务[在默认情况下不启用](https://security-tracker.debian.org/tracker/CVE-2017-9445)。以前的 Debian 版本根本没有易受攻击的代码。

Red Hat [将此漏洞](https://access.redhat.com/security/cve/cve-2017-9445)评定为重要，并将其分配给[通用漏洞评分系统](https://nvd.nist.gov/vuln-metrics/cvss)(CVSS)7.5 分，但确定它不影响 Red Hat Enterprise Linux 7 附带的 systemd 版本。然而，[fedora 受到影响并发布了补丁](https://bodhi.fedoraproject.org/updates/FEDORA-2017-29d909f5ec)。

Ubuntu 、 [Arch Linux](https://bugs.archlinux.org/task/54619) 以及可能其他发行版也受到影响。用户应该检查他们是否有任何 systemd 的更新，并且应该尽快部署补丁。根据 Coulson 的说法，该缺陷可能是在 2015 年的 systemd 版本 223 中引入的，并影响到 233 之前的所有版本。

[红帽](https://www.openshift.com/)是新栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>