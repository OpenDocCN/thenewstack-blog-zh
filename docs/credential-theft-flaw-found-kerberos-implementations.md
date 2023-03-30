# 在大多数 Kerberos 实现中发现了凭据窃取缺陷

> 原文：<https://thenewstack.io/credential-theft-flaw-found-kerberos-implementations/>

微软、FreeBSD 和几个 Linux 发行版发布了安全更新，以修复一个严重的 Kerberos 漏洞，该漏洞可能允许中间人攻击者冒充服务器并可能窃取凭据。

这个漏洞是由 Kerberos 5 网络认证协议的开源实现 [Heimdal](https://h5l.org/) 中的开发者 [Jeffrey Altman](https://github.com/jaltman) 、 [Nicolas Williams](https://github.com/nicowilliams) 和 [Viktor Dukhovni](https://github.com/vdukhovni) 发现的。

这三名开发人员在分析 Williams 和 Dukhovni 为他们的公司创建的具有 Heimdal 特性的错误时，发现了 Kerberos 相互身份验证过程中一个更严重的问题。经过进一步调查，他们发现其他 Kerberos 实现，包括 Windows 和 MacOS 中的实现，也受到了影响。

这些独立开发的实现的共同点是，在认证过程中，它们使用的服务名取自一段未加密和未认证的数据，称为票证，而不是从 KDC(密钥分发中心)响应中的加密元数据中提取。

据这三位开发人员称，这种疏忽“允许位于客户机和它与之对话的服务(包括 KDC)之间的路径上(物理上或逻辑上)的攻击者在客户机上发起服务模拟攻击。”

该漏洞“可以通过多种方式被利用，在某些情况下，它可以导致远程凭据窃取，从而远程权限提升，在很大程度上击败 Kerberos，”他们在专门针对该漏洞的网站[上说](https://www.orpheus-lyre.info/)

该漏洞自 1996 年以来就存在于 Heimdal 中，并且自 Windows 2000 首次引入以来就存在于 Microsoft 的 Kerberos 实现中。开发者说，它之所以这么长时间没有被发现，原因之一是它没有以任何方式导致受影响的实现失败，也没有破坏它们之间的互操作性。

值得注意的是，问题不在协议规范本身。因此，并不是所有的实现都会受到影响。例如，最初开发该协议的麻省理工学院维护的 Kerberos 5 实现就不容易受到攻击。

奥特曼、威廉姆斯和杜霍夫尼以希腊神话中的吟游诗人俄耳甫斯的音乐让哈迪斯的看门狗塞伯勒斯睡觉的名字命名了脆弱的俄耳甫斯的七弦琴。他们警告说，关于这个缺陷还有更多曲折，但他们将把细节推迟几天，以便给用户时间来修补。

微软[修复了漏洞](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/CVE-2017-8495),作为周二发布的每月 Windows 安全更新的一部分。FreeBSD [也发布了补丁](https://www.freebsd.org/security/advisories/FreeBSD-SA-17:05.heimdal.asc)和更新的 Heimdal 包应该很快会被各种 Linux 发行版分发，[包括 Debian](https://security-tracker.debian.org/tracker/CVE-2017-11103) 。

Samba 的更新包[也已经发布，因为从 4.0.0 开始的所有 Samba 版本都包含了嵌入的 Heimdal 副本。](https://www.samba.org/samba/security/CVE-2017-11103.html)

“注意，这个漏洞是一个客户端漏洞，”三位开发人员说。"您必须修补所有受影响的客户端。您无法修补服务器来缓解或消除此漏洞。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>