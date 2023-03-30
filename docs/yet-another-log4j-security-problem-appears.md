# 又出现了另一个 Log4j 安全问题

> 原文：<https://thenewstack.io/yet-another-log4j-security-problem-appears/>

是的，另一个。幸运的是，已经有一个可用的补丁:Log4j 2.17.0。

你不能编造这些东西。当第一个 [Apache Log4j 零日漏洞](https://www.zdnet.com/article/log4j-zero-day-flaw-what-you-need-to-know-and-how-to-protect-yourself/) [CVE-2021-44228](https://nvd.nist.gov/vuln/detail/CVE-2021-44228) 及其“完美”的通用漏洞评分系统(CVSS)(满分 10 分)被披露时，情况已经够糟糕了。但是，随后，它很快又出现了另一个安全漏洞， [CVE 2021-45046](https://nvd.nist.gov/vuln/detail/CVE-2021-45046) 。这没那么糟，但也够糟了。然后， [Blumira](https://www.blumira.com/) 发现了利用[这对 Log4j 安全问题](https://www.zdnet.com/article/security-firm-blumira-discovers-major-new-log4j-attack-vector/)的另一种方法。但是等等！现在又一个新的、有趣的独立 Log4j 安全漏洞被发现: [CVE-2021-45105](https://nvd.nist.gov/vuln/detail/CVE-2021-45105) ！

## 补丁可用

在你完全崩溃之前，就像其他人一样，修复这个问题的补丁已经发布了。要修复这个，你需要把你的 Log4j 库升级到 [Log4j 2.17.0](https://www.zdnet.com/article/apache-releases-new-2-17-0-patch-for-log4j-to-solve-denial-of-service-vulnerability/) 。

Apache 解释说，这一次的问题是，新的 2.16 版本“并不总是防止查找评估中的无限递归”，这使得它容易受到拒绝服务攻击。虽然它没有 CVSS 评分为 7.5 的原版那么糟糕，但也足够糟糕了。

这个安全漏洞存在于 Apache Log4j2 的所有版本中，从最初的 2.0-alpha1 到 2.16.0。它们都不能防止库因自引用查找而出现不受控制的递归。

因此，“当日志记录配置使用带有上下文查找的非默认模式布局(例如＄＄{ CTX:loginId })时，控制线程上下文映射(MDC)输入数据的攻击者可以手工创建包含递归查找的恶意输入数据，从而导致将终止进程的 StackOverflowError。”我想我们都知道一旦陷入无限递归查找循环会发生什么:Kaboom 和 DoS。

引发这个问题非常简单。你只需给应用程序一个有毒的字符串，然后，哒哒，瞬间崩溃。

Akamai Technologies 的[冈本英树](https://www.linkedin.com/in/hideki-okamoto-28366769/?locale=en_US)，趋势科技研究院的[盖伊·莱德费恩](https://www.linkedin.com/in/guy-lederfein/)，以及一位匿名的漏洞研究员都发现了这个问题。这个问题还在探索中。作为恶意软件研究小组， [vx-underground](https://www.vx-underground.org/) 在推特上写道，“令人担忧的是[并非所有的边缘案例都被探索过](https://twitter.com/vxunderground/status/1471974370570608648)也就是说，普遍的共识是解决这一最新问题的最佳方法是升级到 Log4j 2.17.0。

## 缓解问题

您可以通过应用 2.17.0 补丁并在日志配置的 PatternLayout 中用线程上下文映射模式(%X、%mdc 或%MDC)替换＄{ CTX:log inid }或＄＄＄{ CTX:log inid }等上下文查找来缓解这一问题。Apache 还建议删除＄{ CTX:log inid }或＄＄{ CTX:log inid }等配置中对上下文查找的引用，这些配置中的字符串来自外部应用程序源，如 HTTP 头或用户输入。

和以前一样，您需要尽快解决这个最新的安全漏洞。作为安全研究员， [CronUp](https://www.cronup.com/) 的[german fernández](https://twitter.com/1zrr4h?lang=en)指出，物联网(IoT) Mirai 未来组合僵尸网络已经将 [Log4Shell 作为蠕虫](https://twitter.com/1ZRR4H/status/1472753641295683585)添加到其自我传播的武器库中。费尔南德斯补充说，这“仍然是一个基本的利用，但他们已经有了。”

如果 Mirai 未来组合正在部署它，那么其他僵尸网络来敲你的门，试图用 Log4Shell 攻击来破坏你的系统只是个时间问题。回去工作吧，我的朋友。安全分析师和开发人员的工作永远不会结束。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>