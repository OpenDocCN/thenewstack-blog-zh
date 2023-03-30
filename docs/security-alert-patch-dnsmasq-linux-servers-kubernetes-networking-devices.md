# 安全警报:在您的 Linux 服务器、Kubernetes 和网络设备上安装 Dnsmasq 补丁

> 原文：<https://thenewstack.io/security-alert-patch-dnsmasq-linux-servers-kubernetes-networking-devices/>

来自谷歌的安全研究人员最近在 [dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html) 中发现了严重的漏洞，这是一个用于 Linux、BSD 和 macOS 的软件包，用于为网络设置域名服务器(DNS)和动态主机配置协议(DHCP)服务。

Dnsmasq 也在 Kubernetes 中使用，它在 1.5.8、1.6.11、1.7.7 和 1.8.0 版本中包含了一个打补丁的 DNS pod。 [Kubernetes 1.8](http://blog.kubernetes.io/2017/09/kubernetes-18-security-workloads-and.html) 于 9 月 28 日发布，也有一些其他的安全增强。由于其占地面积小，dnsmasq 也广泛用于路由器和其他网络设备，以及防火墙和移动设备热点。

谷歌研究人员[发现了三个远程代码执行缺陷](https://security.googleblog.com/2017/10/behind-masq-yet-more-dns-and-dhcp.html)，三个拒绝服务问题和一个信息泄露漏洞，这些漏洞可以帮助攻击者绕过地址空间布局随机化(ASLR)反利用机制。他们与 dnsmasq 维护者 [Simon Kelley](http://www.thekelleys.org.uk/) 合作，在 dnsmasq 2.78 版本中修复了这些缺陷。

> 如果 dnsmasq 被配置为提供外部 DNS 或 DHCP 服务，这些漏洞可能会被 internet 利用。

Linux 服务器管理员应该确保他们从发行版维护者那里获得了更新的 dnsmasq 包。但是，该软件也存在于各种基于 Linux 的嵌入式网络设备中，包括路由器，这些设备需要从各自的供应商处获得更新。

其中一个远程代码执行漏洞，跟踪为 [CVE-2017-14491](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-14491) ，可通过 DNS 被利用，另外两个 [CVE-2017-14492](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-14492) 和 [CVE-2017-14493](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-14493) 可通过 DHCP 被利用。如果 dnsmasq 被配置为提供外部 DNS 或 DHCP 服务，这些漏洞可能会被 internet 利用。

安全公司 Trend Micro [的研究人员发现大约 100 万台设备运行易受攻击的 dnsmasq 版本，并在公共互联网上暴露 DNS 服务(端口 53)。](http://blog.trendmicro.com/trendlabs-security-intelligence/dnsmasq-reality-check-remediation-practices/)

除了与 Kelley 合作修复漏洞，谷歌的研究人员还为该项目提供了一个补丁，旨在强化 dnsmasq，防止未来的漏洞利用。该补丁仍需审查并集成到软件中，但其目标是在 Linux 内核的 **seccomp-bpf** 沙盒机制下运行 dnsmasq。沙盒使得攻击者在将来利用软件中的远程代码执行缺陷时更加困难。

沙盒大大增加了攻击者利用漏洞以内核权限执行任意代码的难度，因为目标进程被一个额外的层隔离，这需要一个单独的漏洞和利用来击败。

在谷歌的补丁被接受并整合到 dnsmasq 之前，用户[可以下载](https://github.com/google/security-research-pocs/blob/master/vulnerabilities/dnsmasq/sandbox/dnsmasq-sandbox.patch)并手动应用到他们的安装中。当然，在生产系统上部署补丁之前，应该进行全面的测试。

建议用户尽快升级他们的系统，因为可以利用这些漏洞进行概念验证，黑客可以利用这些漏洞进行恶意攻击。

就 Kubernetes 版本 1.8 而言，基于角色的访问控制(RBAC)功能已经达到稳定状态，新版本还提供了对通过网络策略过滤出站流量的测试支持。此外，Kubelet 节点代理现在有对传输层安全性(TLS)证书轮换的 beta 支持，这有望简化安全集群操作。

[谷歌](https://cloud.google.com/kubernetes-engine)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>