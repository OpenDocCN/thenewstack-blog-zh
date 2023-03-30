# Linux 服务器面临“堆栈冲突”内存损坏缺陷的威胁

> 原文：<https://thenewstack.io/linux-bsd-solaris-servers-risk-compromise-stack-clash-flaw/>

攻击者可以绕过 Linux、OpenBSD、NetBSD、FreeBSD 和 Solaris 中的一个重要内存损坏防御，以获得 root 权限并完全控制受影响的系统。

这个问题是由安全供应商 Qualys 的研究人员发现的，并被称为“堆栈冲突”，因为它涉及到堆栈与另一个内存区域(如堆)的“冲突”。周一，它[被公开披露，与发布漏洞补丁的操作系统维护者合作。](https://www.qualys.com/2017/06/19/stack-clash/stack-clash.txt)

将堆栈溢出到另一个内存区域的安全隐患至少在 12 年前就已经为人所知。安全研究人员[盖尔·德拉鲁](https://twitter.com/gaeldelalleau)在 2005 年 [CanSecWest](https://cansecwest.com/) 安全会议上的一次报告中描述了这个问题，五年后，前 Qubes 操作系统开发者 Rafal Wojtczuk 找到了一种通过 X 服务器利用它的方法( [CVE-2010-2240](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-2240) )。

为了应对这些以前的漏洞，Linux 内核开发人员添加了一种保护机制，称为[堆栈保护页](https://blogs.gnome.org/markmc/2005/05/11/stack-guard-page/)。这是一个 4KB 大的内存页面，映射到堆栈下方——堆栈变小，堆变大——在顺序覆盖期间写入它应该会触发分段故障。

“正如 Qualys 发现的那样，这种方法的问题在于，在可以以某些非顺序方式控制堆栈内存分配的情况下，有可能跳过堆栈保护页并操纵相邻的内存区域，”漏洞情报公司 [Risk Based Security](https://www.riskbasedsecurity.com/) 的首席研究官 Carsten Eiram 通过电子邮件表示。

Qualys 的研究人员编写了七个概念验证漏洞，通过用户空间应用程序利用该漏洞来获得完全的根权限。虽然这些都是本地权限提升攻击，但不排除存在远程攻击媒介。

Qualys 的研究人员在一篇博客文章中说:“我们调查的一个远程应用程序(Exim 邮件服务器)被证明完全是侥幸无法被利用。”。

Qualys 的 Stack Clash 漏洞追踪为 [CVE-2017-1000364](https://nvd.nist.gov/vuln/detail/CVE-2017-1000364) ，但该公司的研究人员也发现了一些相关漏洞: [CVE-2017-1000365](https://nvd.nist.gov/vuln/detail/CVE-2017-1000365) 和 [CVE-2017-1000367](https://nvd.nist.gov/vuln/detail/CVE-2017-1000367) 。

后者于 5 月底披露，允许 Sudoers 用户通过 sudo 工具获得完全 root 权限。然而，当与 Stack Clash 结合使用时，这个 sudo 缺陷允许所有本地用户获得任何 Linux 系统上的 root 权限。

Qualys 的研究人员和基于风险的安全建议系统管理员尽快部署 Stack Clash 漏洞的补丁，因为本地权限升级到 root 的风险很高。

一个临时的解决方法是将本地用户和远程服务的硬 RLIMIT_STACK 和 RLIMIT_AS 设置为“合理的低值”然而，这很难做到正确，因为如果值太大，它仍然可能允许一些攻击，如果值太低，它将破坏应用程序。

好消息是，Qualys 的研究人员计划在向公众发布他们的概念验证之前，给用户足够的时间来修补他们的系统。

许多 Linux 发行版，包括 [Red Hat](https://access.redhat.com/security/cve/CVE-2017-1000364) 、 [Debian](https://security-tracker.debian.org/tracker/CVE-2017-1000364) 、 [Ubuntu](https://people.canonical.com/~ubuntu-security/cve/2017/CVE-2017-1000364.html) 和 [SUSE](https://www.suse.com/support/kb/doc/?id=7020973) ，都发布了针对该漏洞的安全公告。

[红帽](https://www.openstack.org/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>