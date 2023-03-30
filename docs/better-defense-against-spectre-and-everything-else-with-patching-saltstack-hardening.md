# 通过修补、盐堆加固，更好地防御 Spectre 和其他任何东西

> 原文：<https://thenewstack.io/better-defense-against-spectre-and-everything-else-with-patching-saltstack-hardening/>

[](https://www.saltstack.com/)

[Mehul revan kar](https://www.saltstack.com/)

[Mehul 是 SaltStack 的高级安全产品经理，他负责构建解决方案，帮助 Salt 用户保护其跨云、本地、混合以及物联网平台的基础设施。在加入 SaltStack 之前，Mehul 在 Tenable 领导了多个漏洞管理和政策合规性研究团队。他和妻子及两个孩子住在佐治亚州的亚特兰大。](https://www.saltstack.com/)

[](https://www.saltstack.com/)[](https://www.saltstack.com/)

在过去的几年里，我们已经看到影响基础设施软件的安全漏洞数量出现了前所未有的增长。根据[国家漏洞数据库](https://nvd.nist.gov)发布的常见漏洞和暴露(CVE)统计数据，2017 年发现的漏洞是 2016 年报告的两倍多，而 [2018 年](https://nvd.nist.gov/vuln/search/results?form_type=Advanced&results_type=overview&search_type=all&pub_start_date=01%2F01%2F2018&pub_end_date=12%2F31%2F2018)已经发现了与 2016 年大致相同数量的漏洞。这些数字甚至还不包括 2017 年未被授予 CVE 的近[8000 个漏洞](https://www.infosecurity-magazine.com/news/7900-vulnerabilities-didnt-make-it/)。

虽然 2017 年见证了 WannaCry 和 Equifax 黑客等最知名的致命漏洞，但 2018 年一开始就出现了 Spectre 和 Meltdown 漏洞。

一月份，我们分享了我们对 SaltStack 如何帮助[修复 Spectre 漏洞](https://saltstack.com/event-driven-security-automation-spectre-meltdown/)的见解。我们仍然相信，正如我们当时所做的那样，智能的、事件驱动的安全自动化是评估任何给定组织的风险和减轻威胁的关键。

这里有一些方法来帮助保护您的数据免受 Spectre 以及许多其他漏洞的攻击，其中许多漏洞尚未被发现。

## 典型漏洞响应和补丁周期

组织在修补其基础架构中的漏洞时通常采用两层方法。第一层通常涉及作为例行修补周期的一部分而被修补的漏洞；这个过程可以每周、每月、每季度甚至每年进行一次。(一个真实但可怕的事实是，一些组织每年只打补丁)。

第二层是为非常紧急、严重程度高的漏洞保留的，如 WannaCRY、Apache struts 2/Equifax([CVE-2017-5638](https://nvd.nist.gov/vuln/detail/CVE-2017-5638))或 HeartBleed。当这种漏洞成为新闻时，通常的漏洞修补程序就退居其次了。“现在就想尽一切办法修补漏洞”的心态占据了上风。当 C-Level 的主管要求每天(如果不是每小时)更新漏洞修复状态时，这一点尤其正确。

在这两种情况下，SaltStack 对 SecOps 团队都是非常宝贵的，但它真正的价值是在第二种情况下显现出来的。

在这种情况下，需要回答三个紧迫的问题:

*   我们容易受到[在此插入脆弱性]的攻击吗？
*   如果是，有多少资产是脆弱的？
*   我们要多久才能修补、补救或实施解决方案？

为了解释 SaltStack 如何提供帮助，我将使用最近历史上两个非常著名的漏洞:HeartBleed 和 [MS17-010](https://docs.microsoft.com/en-us/security-updates/securitybulletins/2017/ms17-010) 又名 WannaCRY。

## 识别和修补易受攻击的资产

修补漏洞的第一步是识别哪些资产易受攻击。漏洞通常与软件或硬件的特定版本相关联；比如 1.0 版易受攻击，1.1 版打了补丁。该过程的第一步是列举安装在基础设施中的易受攻击的应用程序的软件版本。

SaltStack 附带了一个非常强大的远程执行和自动化框架，该框架可以规范日常系统操作(例如列出软件版本，以及用一个命令升级和删除软件)，这些操作被称为执行模块。

让我们以 HeartBleed 为例，看看 SaltStack 会有什么帮助。

## 心脏出血

在 Heartbleed 的例子中，要回答的第一个问题是:“有多少资产上有 OpenSSL，安装了哪些版本？”

有了 Salt，这个问题可以用一个简单的命令来回答:

```
mehul@saltmaster:~$  sudo salt  \*  pkg.version openssl

web-prod1:

     1.0.1-4ubuntu5.11

web-centos:

     1.0.1e-15

web-debian:

     1.0.1e-2+deb7u4

```

注意，系统对执行模块和函数“pkg.version”进行了规范化，它适用于各种操作系统。SaltStack 通过调用 Red Hat 系统上的 rpm、Ubuntu 上的 apt-get 以及其他操作系统的相关实用程序，智能地询问软件包版本。

这使得在紧张局势下识别易受攻击的资产变得容易。该命令的输出可以格式化为 YAML 或 json，以便对输出执行额外的处理。

这里有一个例子:

```
mehul@saltmaster:~$  sudo salt  \*  pkg.version openssl  --output=json

```

### 修补 OpenSSL

就像列出 OpenSSL 版本一样，将 OpenSSL 升级到最新版本也可以通过一个 Salt 命令来完成。这里有一个例子:

```
mehul@saltmaster:~$  sudo salt  '*'  pkg.upgrade name=openssl

```

【注意:在基于 apt 的系统上，这将执行完整的系统升级。]

完成后返回如下输出:

```
openssl:

             ----------

             new:

                 1.0.2g-1ubuntu4.12

             old:

                 1.0.2g-1ubuntu4.10

```

这些命令在几秒钟内就可以在数千个系统中执行和完成。因此，访问 SaltStack 等强大的自动化平台有助于降低漏洞带来的风险，这种漏洞在几天到几分钟内就会被广泛利用。

在某些情况下，如零日漏洞，此时没有可用的补丁，唯一的选择是实施一个变通办法或停止服务。SaltStack 在这种情况下也很有用。这里有一个例子:

```
mehul@saltmaster:~$  sudo salt  'fs-dev*'  service.stop ftpd

```

SaltStack 配备了超过 [475 个执行模块](https://docs.saltstack.com/en/latest/ref/modules/all/index.html)，如 pkg &服务，并且很容易添加新模块或扩展现有模块以满足特定的用例。

## WannaCry

当 [WannaCry](https://www.csoonline.com/article/3227906/ransomware/what-is-wannacry-ransomware-how-does-it-infect-and-who-was-responsible.html) 勒索病毒爆发时，它利用 SMBv1.0 协议中的一个漏洞，迅速感染了大量系统。它利用了永恒之蓝漏洞，该漏洞作为影子经纪人转储的一部分被披露。

### 禁用 SMBv1.0

作为对 WannaCry 的回应，限制感染的首要建议之一是在应用[补丁](https://docs.microsoft.com/en-us/security-updates/securitybulletins/2017/ms17-010)之前[禁用 SMBv1.0](https://support.microsoft.com/en-us/help/2696547/how-to-detect-enable-and-disable-smbv1-smbv2-and-smbv3-in-windows-and) 。

正如前面的情况一样，SaltStack 用户可以通过使用 reg 和 system Windows 执行模块对其 Windows 基础架构运行单个 Salt 命令来实现这一点。这里有一个例子:

```
mehul@saltmaster:~$  sudo salt  'win*'  reg.set_value HKEY_LOCAL_MACHINE  'SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters'  'SMB1'  ‘0’

```

如果注册表修复是通过其他方法实现的，如 GPO 或 PowerShell，SaltStack 可以通过 reg read 函数帮助验证修复。

```
mehul@saltmaster:~$  sudo salt  'win*'  reg.read_value HKEY_LOCAL_MACHINE  'SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters'  'SMB1'

```

### 重启系统

设置注册表项是不够的；为了使它生效，系统也需要重新启动。SaltStack 编排可应用于任务自动化，以根据需要重启系统:

```
mehul@saltmaster:~$  sudo salt  'win*'  system.reboot

```

### 应用补丁

最后，当需要应用补丁时，Salt 可以下载并安装补丁:

```
mehul@saltmaster:~$  salt  'win7*'  win_wua.install KB4022168

```

## 使用盐堆进行系统强化

[Gartner](https://www.gartner.com/smarterwithgartner/why-cloud-security-is-everyones-business/) 预测，“到 2020 年，95%的云安全故障都是客户的错。”虽然被动修补漏洞很好，但通过系统加固来防止利用漏洞也是一种谨慎的方法。事实上， [Gartner 还建议](https://www.gartner.com/smarterwithgartner/is-the-cloud-secure/)“与传统数据中心相比，利用云基础设施的可编程性来提高安全保护的工作负载遭受的安全事故至少会减少 60%。”

SaltStack 可用于使任何系统跨混合云环境可编程。最佳实践是在第一次和每次都正确配置系统，然后在系统脱离强化和安全状态时自动执行自我修复例程。

系统加固可防止漏洞被利用，即使安装了易受攻击的软件版本。一个例子是，如果 Apache 没有被用作 web 服务器，就禁用或删除它。SaltStack 可以在远程系统上强制执行正确的配置，通过一个称为盐状态文件的概念来满足或超过系统强化要求。

状态文件允许用户在 YAML 文件中定义远程系统所需的“状态”。下面是一些例子:

```
remove_telnet:

   telnet:

     pkg.removed

Ensure_telnet_off:

   service.dead:

     -  name:  telnet.socket

sshd_root_restrict_login:

   file.replace:

     -  name:  /etc/ssh/sshd_config

     -  pattern:  '^\s*PermitRootLogin.*[yY]es.*'

     -  repl:  'PermitRootLogin no' 

End Result

```

几乎每天都有新的漏洞发布，而修补这些漏洞或实施解决方案的流程大致相同。公司必须修补得更好，但如上所述，“强化他们的系统”也符合他们的最佳利益。虽然从定义上来说，没有一个系统是完全锁定的，但是正确安装补丁和更新同时使用强化技术的双管齐下的方法将对实现您的安全目标大有帮助。

SaltStack 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>