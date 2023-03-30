# 微软发现双重 Linux 安全问题:Nimbuspwn

> 原文：<https://thenewstack.io/microsoft-discovers-dual-linux-security-problems-nimbuspwn/>

谁会想到呢？近年来拥抱 Linux 的微软现在正在寻找并帮助修复 Linux 的安全漏洞。这方面最大的例子就是微软最近发现的 [CVE-2022-29799](https://ubuntu.com/security/CVE-2022-29799) 和 [CVE-2022-29800](https://ubuntu.com/security/CVE-2022-29800) 。这对[systemd](https://www.freedesktop.org/wiki/Software/systemd/)[networkd-dispatcher](https://gitlab.com/craftyguy/networkd-dispatcher)安全漏洞，被命名为 [Nimbuspwn](https://www.microsoft.com/security/blog/2022/04/26/microsoft-finds-new-elevation-of-privilege-linux-vulnerability-nimbuspwn/) ，可以链接在一起获得 Linux 系统上的 root 权限。

我讨厌根级漏洞。

这件事的一个好处是，这真的不是一个 Linux bug，而是一个 systemd 安全问题。所以不使用 systemd 的 Linux 发行版，比如流行的 container 发行版， [Alpine Linux](https://www.alpinelinux.org/) ，对 Nimbuspwn 是免疫的。尽管如此， [Canonical](https://canonical.com/) ， [Ubuntu Linux](https://ubuntu.com/) 的母公司称之为[高优先级 bug](https://ubuntu.com/security/CVE-2022-29799) 。

Networkd-dispatcher 是用于 systemd-networkd 连接状态更改的根级调度程序守护程序。它类似于[网络管理器-调度器](https://developer-old.gnome.org/NetworkManager/stable/NetworkManager.html)，但是在事件类型上有更多的限制。它通过[桌面总线(D 总线)](https://www.freedesktop.org/wiki/Software/dbus/)监听来自 systemd-networkd 的信号。这是一种进程间通信通道(IPC)机制，主要用于 Linux 桌面。

## 微软在这个案子上

[微软 365 Defender 研究团队](https://www.microsoft.com/security/blog/windows-defender-research/)在监听系统总线消息对以 root 身份运行的服务执行代码审查和动态分析时发现了问题。

微软为什么要这么做？毕竟，Windows 的安全问题足够让微软的安全团队再忙上一两代人。这是因为微软现在有了自己的 Linux 版本，如[Windows Subsystem for Linux(WSL)2.0](https://docs.microsoft.com/en-us/windows/wsl/install)，以及 Linux 安全程序，如[Microsoft Defender for Endpoint on Linux server](https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux)，现在包含了[端点检测和响应(EDR)能力](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-generally-available/ba-p/2048539)。简而言之，保护 Linux 现在也是微软的事情。

具体来说，研究人员发现 D-Bus 暴露了一个全局系统总线。Networkd-dispatcher 有几个问题可能会导致系统总线出现问题。这包括一个[目录遍历](https://portswigger.net/web-security/file-path-traversal)，CVE-2022-29799，一个[符号链接竞争](https://capec.mitre.org/data/definitions/27.html)，以及一个[检查时间使用时间(TOCTOU)竞争条件](https://cwe.mitre.org/data/definitions/367.html)，CVE-2022-29800。把它们放在一起，这意味着麻烦。

## 容易做到

要消除 Numbuspwn 漏洞，漏洞代码需要拥有总线名称。不幸的是，虽然这听起来很难，但有几个 Linux 环境可以轻松实现这一点。这包括 [Debian](https://www.debian.org/) 桌面 Linux 家族，几个 [gpgv](https://www.gnupg.org/documentation/manuals/gnupg/gpgv.html) 插件(在 [apt-get](https://linux.die.net/man/8/apt-get) 安装或升级时启动)，以及 [Erlang 端口映射器守护进程(epmd)](https://www.erlang.org/doc/man/epmd.html) 。部分潜在问题似乎是 systemd 安装了策略片段/usr/share/dbus-1/system . d/org . free desktop . network 1 . conf。该配置文件允许在 systemd-network 用户帐户下运行的进程拥有该名称。

微软发现问题后，研究人员做了正确的事情。他们通知了网络调度维护人员克莱顿·克拉夫特。这些漏洞的修补程序现在已经发布。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>