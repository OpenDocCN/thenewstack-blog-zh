# 30%的 Apache Log4j 安全漏洞仍未修补

> 原文：<https://thenewstack.io/30-of-apache-log4j-security-holes-remain-unpatched/>

这听起来像一个糟糕的笑话。我的意思是，我们都知道开源 Java 日志库 [Apache Log4j](https://logging.apache.org/log4j/) 非常糟糕。[国家漏洞数据库(NVD)](https://nvd.nist.gov/) 将其评为 [10.0 CVSSv3](https://nvd.nist.gov/vuln/detail/CVE-2021-44228) ，这是最差的可能。最后，但并非最不重要的是， [Log4j 也到处使用](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/)。几个月后，这个安全漏洞有多少被修复了？全部吗？远非如此！根据云安全公司 [Qualys](https://www.qualys.com/) 的数据，只有 70%被打了补丁。" [30%的 Log4j 实例仍然容易被利用。](https://blog.qualys.com/vulnerabilities-threat-research/2022/03/18/qualys-study-reveals-how-enterprises-responded-to-log4shell)

这太疯狂了。即使你不关心保护你自己或你的客户——或者，更有可能的是，你太无知而不会修补你的软件——美国美国联邦贸易委员会(FTC)也会因为你没有修复问题而对你罚款。哦，你知道吗，Qualys 恶意软件威胁研究总监 Travis Smith 报告说 Qualys 已经发现了“企图勒索的攻击”,其中一些已经成功了——由 Conti、Khonsari 和一些国家支持的对手发起的

你真的想丢掉你的生意吗？

CISA 和 NCSC 已经报告了 1495 种易受 log 4 外壳攻击的产品。其中，Qualys 发现了 52 家出版商的 1065 个程序仍在使用！

## 问题在哪里

那么，这些问题出在哪里呢？嗯，他们中的绝大多数，超过 80%，是在 Linux 上。我喜欢说 Linux 比它的替代品更安全，但这并不意味着它是安全的。而且，如果您仍然在运行不安全的 Log4j 版本，那么系统的其他部分再安全也没有用。如果窗户大开着，没人会在意你门上的锁。

超过一半的包含 Log4j 的程序也不再受支持。你的软件供应商修补这些漏洞的可能性微乎其微。如果你还在运行过时的程序，停止吧。你只是在自找麻烦。

## 进行修复

不确定你是否会受到攻击？使用 Qualys 的新[开源 Log4j 扫描实用程序](https://github.com/Qualys/log4jscanwin)来查看您的防御是否已经崩溃。我的意思是，你早就应该运行 [Log4j 故障扫描仪](https://thenewstack.io/how-to-find-dangerous-log4j-libraries/)，但迟做总比不做好。

如果你没有发现问题，Qualys 声称检测后的平均补救时间是 17 天。不过你可以做得更快。可以远程利用的系统修补速度更快，仅用了 12 天。这实际上是你认为修补或缓解这个问题有多重要的问题。

我给你简单说一下。修复 Lof4j 漏洞对贵公司来说是一个至关重要的问题。是的，很痛苦。相信我，在遭受勒索软件攻击后进行清理，或者向客户解释为什么他们的数据会丢失，这是一件更痛苦的事情。已经修好了！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>