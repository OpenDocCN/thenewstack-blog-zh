# SaltStack 扩展到安全合规性扫描和补救领域

> 原文：<https://thenewstack.io/saltstack-expands-into-security-compliance-scanning-and-remediation/>

[SaltStack](https://www.saltstack.com/) 希望将运营人员从“审计地狱”中解救出来

该公司的旗舰配置管理软件 [Saltstack Enterprise](https://saltstack.com/saltstack-enterprise/) 的一个新功能将包括审计和即时补救配置错误和漏洞的能力。

SaltStack 首次亮相[Salt stack SecOps](https://saltstack.com/secops/)**将于明年初在该公司本周在盐湖城举行的年度用户大会 [SaltConf18](https://saltconf.com/) 上全面上市。**

 **SaltStack 产品副总裁 Alex Peay 指出，该功能是由于用户提出了许多关于如何扩展 Salt 配置管理软件以涵盖安全性的问题。

越来越多的组织开始使用安全提供商提供的扫描评估工具。这种工具通常可以扫描一组机器，以确保它们配置正确，并发出一份报告，列出未通过审核的机器以及具体的问题。配置不正确的机器可能会为恶意攻击者提供破坏的入口点。

“我们处理这个问题的方式不同于所有其他评估工具，”Peay 说，并指出它利用 Salt 的复杂目标功能来提供完全自动化的发现和即时补救服务，这是配置管理和安全合规性软件的第一次。

Peay 解释说，虽然安全公司的现有服务可以帮助满足外部或内部的安全和合规要求，但它们对运营团队构成了挑战，他们必须在扫描后修复有问题的计算机并重新运行扫描。有时，可以通过工具(如 SaltStack)或手动脚本来修复机器。但是，将问题列表转移到补救流程中是一项手动且耗时的任务。

“这导致了很多深夜和周末，”皮伊说。对于转向自动化开发运维流程的组织来说，补救可能是一个严重的瓶颈。

SaltStack 自动化了发现和补救过程。该软件可以检查数千台机器，如果发现配置错误，立即修复它们。或者，它可以生成一个报告，允许管理员设置修复它们的时间(例如，在非工作时间)。

最初，SaltStack 将使用来自信息安全中心( [CIS](https://www.cisecurity.org/) )、美国国防信息局安全技术实施指南(DISA·斯蒂格斯)和国家标准与技术研究所( [NIST](https://www.nist.gov/) )的所需配置设置。这类指南对操作系统进行了数千次检查，从关闭[远程登录端口](https://thenewstack.io/the-lost-worlds-of-telnet/)到定义指导用户访问权限的设置。用户还可以定义自己的检查，并混合使用外部和内部合规性检查表。

这样的补救服务可以由 Salt Minions 轻松执行，Salt Minions 是安装在每台 Salt 控制的机器上的代理。该服务最初将支持最广泛使用的 Linux 和 Unix 发行版，以及 Windows 的最新版本。这些配置将在内部管理，并保存在一个公共存储库中(可能是 GitHub)。

Peay 说，最初，SaltStack SecOps 将专注于配置设置，但随着时间的推移，它可能会包括其他安全需求，如补丁管理和漏洞补救。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**