# Red Hat 修补了 OpenStack 发行版中的三个严重漏洞

> 原文：<https://thenewstack.io/red-hat-patches-three-serious-ansible-flaws-openstack-distribution/>

Red Hat 发布了针对 OpenStack 平台的安全更新，目的是修复一些重要和中等严重程度的漏洞。如果不修补，这些缺陷可能允许攻击者在多个服务的上下文中执行任意代码，从虚拟机中逃离，访问敏感信息或获得更高的权限。

[红帽 OpenStack 平台](https://www.redhat.com/en/technologies/linux-platforms/openstack-platform) 11.0 [中的 Ansible 包进行了更新，修复了三个漏洞](https://access.redhat.com/errata/RHSA-2017:1476)，其中一个被评为高严重性，在[常见漏洞评分系统](https://www.first.org/cvss/) (CVSS)中的评分为 8 分(满分 10 分)。

Ansible 是一个基于 SSH 的远程任务执行系统，管理员使用它来自动化应用程序部署和配置管理。最严重的漏洞被跟踪为 [CVE-2017-7466](https://access.redhat.com/security/cve/cve-2017-7466) ，该漏洞源于未能正确验证从 Ansible 托管客户端系统发送到服务器的数据。成功利用该漏洞可导致以服务器权限执行任意代码。

Ansible 中修补的另外两个漏洞可导致信息泄露( [CVE-2017-7473](https://access.redhat.com/security/cve/CVE-2017-7473) )和通过 [jinja2 Python 模板系统](http://jinja.pocoo.org/)执行代码，默认标记为不安全( [CVE-2017-7481](https://access.redhat.com/security/cve/CVE-2017-7481) )。

适用于 RHEL 6 的 Red Hat Enterprise Linux open stack Platform 5.0 收到了 qemu-kvm-rhev 包[的更新，以修复四个重要漏洞](https://access.redhat.com/errata/RHSA-2017:1441)。该软件包包含在 KVM(基于内核的虚拟机)模式下运行虚拟机所需的组件。

两个漏洞， [CVE-2016-9603](https://access.redhat.com/security/cve/CVE-2016-9603) 和 [CVE-2017-7980](https://access.redhat.com/security/cve/cve-2017-7980) ，位于 QEMU 的 Cirrus CLGD 54xx VGA 仿真器的 VNC 显示驱动和 Cirrus CLGD 54xx VGA 仿真器支持中。来宾操作系统中的特权用户可以利用这两个漏洞来脱离虚拟机，并以 QEMU 进程的权限在主机系统上执行任意代码。

其他两个漏洞，CVE-2017-2633 和 CVE-2017-7718，可能被特权来宾操作系统用户利用来破坏 QEMU 进程，从而造成拒绝服务情况。

Red Hat 在其安全顾问中表示，在安装 qemu-kvm-rhev 包更新后，所有 qemu 虚拟机都应该关闭并再次启动，以便补丁生效。

Red Hat OpenStack Platform 6.0、7.0、8.0 和 9.0 的 python-django 包中修复了一个漏洞，该漏洞可能允许攻击者针对 OpenStack 仪表板执行[跨站点脚本](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) (XSS)攻击。该漏洞( [CVE-2017-7233](https://access.redhat.com/security/cve/CVE-2017-7233) )具有中等严重性，是由于未正确过滤 is_safe_url()函数中的用户输入造成的。

另一个中度严重性漏洞( [CVE-2017-2673](https://access.redhat.com/security/cve/CVE-2017-2673) ) [已在 Red Hat OpenStack Platform 9.0 的 openstack-keystone 包](https://access.redhat.com/errata/RHSA-2017:1461)中修复。 [Keystone](https://wiki.openstack.org/wiki/Keystone) 是一种 OpenStack 身份服务，它处理用户认证和授权，并根据分配给用户的角色限制用户活动。修复的漏洞可能导致请求项目权限的用户被意外授予所有角色的权限，包括管理角色。

Red Hat OpenStack Platform 9.0 中还更新了 OpenStack Orchestration package、 [Heat](https://wiki.openstack.org/wiki/Heat) 、[以修复两个漏洞，这两个漏洞可能允许攻击者通过服务日志目录(](https://access.redhat.com/errata/RHSA-2017:1464) [CVE-2017-2621](https://access.redhat.com/security/cve/CVE-2017-2621) )访问敏感信息，并通过触发过于详细的错误消息( [CVE-2016-9185](https://access.redhat.com/security/cve/CVE-2016-9185) )来获取有关内部网络服务的信息。

关于通过红帽订阅管理(RHSM)或红帽网络(RHN)经典服务获取和应用更新的说明在红帽网站上的[支持文章](https://access.redhat.com/articles/11258)中提供。

[红帽](https://www.openshift.com/)和 [OpenStack](https://www.openstack.org/) 是新栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>