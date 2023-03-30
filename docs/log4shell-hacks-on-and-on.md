# Log4Shell 一直在攻击

> 原文：<https://thenewstack.io/log4shell-hacks-on-and-on/>

维基百科称 [Log4Shell 是流行的 Apache 日志程序 Log4j 中的零日漏洞](https://en.wikipedia.org/wiki/Log4Shell)。关键词是“曾经”Log4Shell，尽管自从 [Log4j2 2.17.1](https://logging.apache.org/log4j/2.x/security.html) 在二月份发布以来已经有了它的补丁，但它仍然活着，并且还在制造麻烦。

事实上，[网络安全和基础设施安全局(CISA)](https://www.cisa.gov/) 和美国海岸警卫队网络司令部(CGCYBER)已经发布了一份联合网络安全咨询(CSA)来警告我们，包括国家支持的高级持续威胁(APT)行为者在内的黑客们[仍在利用 CVE-2021-44228(](https://www.cisa.gov/uscert/ncas/alerts/aa22-174a)[log 4 shell](https://www.cisa.gov/uscert/ncas/alerts/aa22-174a)[)](https://www.cisa.gov/uscert/ncas/alerts/aa22-174a)[VMware Horizon](https://www.vmware.com/products/horizon.html)和[统一访问网关(UAG)](https://docs.vmware.com/en/Unified-Access-Gateway/index.html) 。

## 尚未应用的补丁

为什么？因为组织仍然没有应用适当的补丁。已经开始了！跟上它。这是隐藏在一些无证程序中的代码！这些是主要的 VMware 计划。 [VMware 几个月前发布了修复程序](https://www.vmware.com/security/advisories/VMSA-2021-0028.html)！已经修补好了！

如果不这样做，CISA 建议您“将所有受影响的 VMware 系统视为受到危害”这是一个严重的问题。如果您忘记了，Log4Shell 可以让系统执行任意代码。这样，黑客就可以完全控制您易受攻击的系统。

我想我们都同意这是个坏消息！对！？当然，没错。

除了成为你系统的根用户， [Cisco Talos 报告说 Log4Shell 正被用来植入 AvosLocker 勒索软件](https://blog.talosintelligence.com/2022/06/avoslocker-new-arsenal.html)。一旦攻击者站稳了脚跟，他们就会继续在您的 Linux 和 Windows 系统中制造麻烦。只是事情一件接一件！

被利用的不仅仅是 VMware 的程序。其他程序，甚至是新程序，仍然对 Log4Shell 攻击开放。正如[丹·墨菲](https://www.linkedin.com/in/dan-murphy-86bb5b66/)、 [Invicti Security](https://www.invicti.com/) 杰出架构师所说，“[现代软件往往是由许多不同组件拼凑而成的](https://mytechdecisions.com/network-security/log4shell-cisos-up-at-night/)，修复 Log4Shell 漏洞并不是那么简单。有时这些依赖是可传递的——软件开发人员添加一个开源包，这个开源包依赖于一个包，而这个包又依赖于 Log4j。因此，开发人员不知道他们在代码中引入了易受攻击的组件。”

## 需要 SBOMs

我们所有的程序都非常非常需要[软件材料清单(SBOM)](https://thenewstack.io/securing-the-software-supply-chain-with-a-software-bill-of-materials/) 是有原因的。

此外，Murphy 补充道，“Log4Shell 的真正危险在于较旧的应用程序。”这是因为这些“通常存在于应用程序基础设施的灰尘层中，只是偶尔在典型的执行流程之外被调用。”除非您已经检查过它们是否有问题，否则您可能首先知道的是，当您每月运行一次它们时，攻击者会冲进来利用它们。

如果您已经受到威胁，CISA 建议您采取以下步骤:

1.  隔离受损系统
2.  分析相关的日志、数据和工件。
3.  所有软件都应该更新和打补丁。
4.  减少非必要的面向公众的托管服务，以限制攻击面，并实施 DMZ、严格的网络访问控制和 WAF 来防范攻击。
5.  建议组织实施身份和访问管理(IAM)的最佳实践，方法是引入多因素身份认证(MFA)、实施强密码和限制用户访问。

你知道你一直以来都应该做的事情。与此同时，检查和扫描您的代码，旧的和新的，寻找 Log4Shell 漏洞。他们还在那里，而且和以前一样危险。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>