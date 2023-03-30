# Red Hat 保护了 Linux 内核 OpenStack 中的网络缺陷

> 原文：<https://thenewstack.io/red-hat-patches-flaws-linux-kernel-openstack-networking/>

Red Hat 修复了 OpenStack 子系统中的一个重要漏洞，该子系统用于管理进出虚拟机的网络连接。如果不进行修补，它可能允许攻击者从虚拟机访问网络资源。

该漏洞在常见漏洞和暴露(CVE)数据库中被跟踪为 [CVE-2017-7543](https://bugzilla.redhat.com/show_bug.cgi?id=1473792) ，位于 openstack-neutron 中，openstack-neutron 是[红帽 open stack 平台](https://www.redhat.com/en/technologies/linux-platforms/openstack-platform)的一个“可插拔、可扩展和 API 驱动”的组件，用于为虚拟机提供网络服务。

在一份[安全公告](https://access.redhat.com/errata/RHSA-2017:2452)中，Red Hat 将该漏洞描述为一次轻微的超频更新引发的“竞争条件”。在 OpenStack 术语中，过云是租户使用的生产云，而不是控制云或欠云，后者用于引导生产云。

过云更新通过将 net . bridge . bridge-nf-call-ARP tables、net . bridge . nf-call-IP 6 tables 和 net . bridge . bridge-nf-call-IP tables 设置为 0 来禁用中子安全组。反过来，这禁用了 iptables，Linux 内核防火墙，造成了严重的安全风险。

“这场竞赛只是由一次更新引发的，此时攻击者可以访问暴露的租户虚拟机和网络资源，”Red Hat 在其公告中说。

针对 OpenStack 6.0 (Juno)、7.0 (Kilo)、8.0 (Liberty)、9.0 (Mitaka)、10.0 (Newton)和 11.0 (Ocata)发布了更新的中子相关软件包，以修复该漏洞。

本周，Red Hat 还发布了几个版本的 Red Hat Enterprise Linux 6.7 和 7.3 扩展更新支持的内核补丁，以修复中度和重要的漏洞，这些漏洞可能被远程利用，并可能导致拒绝服务情况、任意代码执行或权限提升——获得比运行受影响组件的用户更高的权限。

Red Hat Enterprise Linux 6.7 的更新修复了一个被跟踪为 [CVE-2017-7895](https://nvd.nist.gov/vuln/detail/CVE-2017-7895) 的漏洞。此缺陷自四月份以来就已为人所知，位于网络文件系统(NFS)版本 2 和 3 的内核服务器实现中。

如果被利用，该漏洞可能导致任意代码执行，这也是它在通用漏洞评分系统中被评为 9.8 分(满分 10 分)的原因。该漏洞已于 6 月在 Red Hat Enterprise Linux 7.3 和 7.4 中得到修补。

红帽是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>