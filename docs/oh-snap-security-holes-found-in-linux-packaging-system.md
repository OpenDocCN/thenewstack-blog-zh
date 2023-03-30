# 哦，太好了！Linux 打包系统中发现安全漏洞

> 原文：<https://thenewstack.io/oh-snap-security-holes-found-in-linux-packaging-system/>

[Canonical](https://canonical.com/) 的 [snap](https://snapcraft.io/) ，和[的红帽](https://www.redhat.com/en)的 [flatpaks](https://flatpak.org/) 一样，都是基于容器的 Linux 软件打包和部署程序。虽然 snaps 与 Ubuntu Linux 的联系最为紧密，但它也用于在许多 Linux 发行版上分发和安装 Linux 程序。而且，唉，Qualys 的[研究小组](https://www.qualys.com/research/security-advisories/)，已经发现了几个难以发现但[令人讨厌的 Linux 安全问题](https://www.qualys.com/2022/02/17/cve-2021-44731/oh-snap-more-lemmings.txt)包括[哦 snap！更多的旅鼠利用](https://blog.qualys.com/vulnerabilities-threat-research/2022/02/17/oh-snap-more-lemmings-local-privilege-escalation-vulnerability-discovered-in-snap-confine-cve-2021-44731)。

尽管名字很滑稽，但这些安全漏洞是严重的。在最坏的情况下，这个 7.8 通用漏洞评分系统(CVSS)评级的安全漏洞可用于获取默认 Ubuntu 安装的完全 root 权限。哎哟！

但是，在 Canonical 开始工作之前，请仔细看看。在发现 snap 漏洞的同时，Qualsys 还发现了您将在所有 Linux 发行版中发现的安全问题。分别是 [CVE-2021-3996](https://ubuntu.com/security/CVE-2021-3996) 和 [CVE-2021-3995](https://access.redhat.com/security/cve/cve-2021-3995) 在 util-linux (libmount 和 umount)；glibc (realpath()和 getcwd())中的 [CVE-2021-3998](https://access.redhat.com/security/cve/cve-2021-3998) 和 [CVE-2021-3999](https://access.redhat.com/security/cve/cve-2021-3999) ，systemd (systemd-tmpfiles)中的 [CVE-2021-3997](https://access.redhat.com/security/cve/cve-2021-3997) 。

安全研究人员还表示，“发现和利用 snap-confinet 中的漏洞极具挑战性(特别是在 Ubuntu 的默认安装中)，因为 snap-confinet 使用了非常防御性的编程风格、 [AppArmor](https://apparmor.net/) profiles、seccomp 过滤器、mount 名称空间和两个 Go 助手程序。”尽管如此，他们还是发现了两个漏洞。

## 在沙盒中运行

不过，在开始之前，为了让您快速了解，快照是在沙箱中运行的自包含应用程序，通过中介访问主机系统。与传统的 Linux 软件管理器(如 Debian DEB 和 Red Hat RPM)不同，它们将程序作为软件包安装，将所有其他依赖项作为单独的软件包安装，快照与所需的依赖项预先捆绑在一起。这使得在任何带有 Snap 服务的 Linux 上部署它们变得很容易。

近年来，这种安装 Linux 应用程序的[新方式变得非常流行](https://www.zdnet.com/article/the-future-of-linux-desktop-application-delivery-is-flatpak-and-snap/)。虽然 snaps 在 Linux 桌面领域最为人所知，但它也用在服务器上，事实上，它也用于完整的 Linux 发行版，如物联网(IoT) [Ubuntu 核心发行版](https://ubuntu.com/core)。

## Snapd

第一个问题是 snap 守护进程 snapd 没有正确验证 snap-confined 二进制文件的位置。因此，恶意用户可以将二进制文件硬链接到另一个位置。这反过来意味着本地攻击者可能能够利用此问题执行其他任意二进制文件并提升权限。

研究人员还发现，在为快照准备私有装载命名空间时，snapd snap-confinet 二进制文件中存在争用情况。这样，本地攻击者就可以通过在 snap 的私有装载命名空间内绑定装载他们自己的内容来获得 root 权限。这样，他们就可以让 snap-confinet 执行任意代码。从那里，攻击者很容易开始权限提升，试图一路到达 root 用户。

没有办法直接利用这一点。但是，如果攻击者能够以非特权用户的身份登录，攻击者就可以很快利用这个漏洞获得根用户特权。

## 补丁救援

Canonical 发布了一个修补程序来修复这两个安全漏洞。该补丁在以下受支持的 Ubuntu 版本中可用:21.10；20.04 和 18.04。一个简单的系统更新就可以很好地解决这个问题。这个问题也存在于不再受支持的 Ubuntu 发行版中，比如 21.04 和 20.08。在这里，你应该更新到目前支持的 Ubuntu 发行版。最后，目前还没有针对 Ubuntu 16.04 ESM(扩展安全维护)的补丁，但应该会很快发布。

鉴于这个漏洞的高度危险性，我强烈建议您尽快修补您的发行版。你会很高兴你做了。

一位 Canonical 代表说:“一如既往，我们感谢我们所在的伟大社区，感谢它负责任地发现并披露了此类安全问题。我们也非常感谢我们的安全和 snap 平台团队中的专业人员，他们迅速采取行动缓解了漏洞，同时也非常感谢其他组织中的专业人员，他们及时处理了所披露的相关问题。到目前为止，由于自动刷新，世界上大多数快照分布式平台安装已经通过更新得到修复。其他打包系统的更新也已推出。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>