# Log4Shell 生活！

> 原文：<https://thenewstack.io/log4shell-lives/>

自从开源 Java 日志库 [Apache Log4j](https://logging.apache.org/log4j/) 的核心安全漏洞被揭露以来，大约一年过去了。由此产生的[零日漏洞](https://thenewstack.io/security-trouble-in-argo-continuous-delivery-program/)、 [CVE-2021-44228](https://nvd.nist.gov/vuln/detail/CVE-2021-44228) ，又名 [Log4Shell](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/) ，今天依然存在。太疯狂了。但这是真的。

最近，[网络安全和基础设施安全局(CISA)](https://www.cisa.gov/) 披露，不仅黑客仍在成功使用 Log4Shell，伊朗政府特工也在使用它来[撬开联邦政府机构 VMware 系统](https://www.cisa.gov/uscert/ncas/alerts/aa22-320a)。

哦，别这样！已经修补好了！

## 利用

具体来说，威胁参与者利用 Log4Shell 来访问该组织的未打补丁的 [VMware Horizon 服务器](https://www.vmware.com/products/horizon.html)。一旦进入，他们就打开了一个已知恶意 IP 地址的连接。通过该链接，他们运行 Windows PowerShell 命令，向 Windows Defender 添加排除规则，将 c:\驱动器列入白名单。这使他们能够将可执行文件放入 c:\驱动器，而无需进行病毒扫描。

他们穿了什么？好吧，只要你还在摆弄政府服务器，你也可以从黑客那里赚钱，所以他们在机器上安装了 [XMRig 加密货币挖掘恶意软件](https://cyware.com/news/a-brief-understanding-of-the-xmrig-monero-miner-malware-d7c05714)。

完成后，攻击者转向了更多的乐趣和游戏。他们转移到了 [VMware VDI-KMS](https://docs.vmware.com/en/VMware-Horizon-7/7.13/virtual-desktops/GUID-488FF47B-96F4-4F28-836C-6041D8B3745C.html) 主机上。从那里，他们上传。

*   PS exec-微软为系统管理员设计的一款工具。
*   米米卡兹——一个证件盗窃工具。
*   [Ngrok](https://attack.mitre.org/versions/v11/software/S0508/)–一个反向代理工具，用于将内部服务代理到 Ngrok 域，然后用户可以在*上随机生成的子域中访问该域。ngrok[。]木卫一。CISA 观察到一些商业产品出于良性目的使用这种工具；然而，这种攻击绝不是良性的，它绕过了典型的防火墙控制，

通过这些工具，攻击者获得了凭据并创建了一个流氓域管理员帐户。使用新创建的管理员帐户，他们使用微软的远程桌面协议(RDP)感染了其他主机。登录到每台主机后，攻击者手动禁用 Windows Defender 并植入 Ngrok 可执行文件和配置文件。这样，即使 Ngrok 从一台机器上被删除，或者他们在例行重启期间失去了对受感染机器的访问，它仍然存在。

他们试图接管域控制器，从而结束了攻击。与此同时，他们使用 Active Directory 获得了所有连接到域的计算机的列表，并试图—令人惊讶！—更改本地管理员帐户的密码，并尝试[从本地安全机构子系统服务(LSASS)](https://attack.mitre.org/versions/v11/techniques/T1003/001/) 转储身份和访问管理(IAM)数据。在这一点上，该机构发现了一些严重的错误。

## 修补它

这个故事，一个非常典型的自动化 Windows 攻击的故事，始于 Log4Shell。补丁 Log4Shell，这一切都不会发生。

请注意，这次攻击暴露了许多其他问题。例如， [PowerShell 做了什么让非管理用户可以使用](https://attack.mitre.org/versions/v11/mitigations/M1026/)？如果没有双因素身份验证(2FA ),本地管理员帐户究竟在做什么？

所以，我不能把这一切都归咎于修补 VMware 的失败。这个系统有很多安全方面的问题。但是，如果你不能绝对肯定你已经修补了 [Log4J](https://thenewstack.io/log4j-the-pain-just-keeps-going-and-going/) 的每个实例，那么早就该这么做了。

哦，如果你错过了一个，开始拆开那台机器和每一个联网的系统，找到现在隐藏在其中的恶意软件。到这个时候，很明显你所有的机器都被入侵了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>