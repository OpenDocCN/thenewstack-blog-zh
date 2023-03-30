# 肮脏的管道是一个可怕的 Linux 烂摊子

> 原文：<https://thenewstack.io/dirty-pipeline-is-an-awful-linux-mess/>

在我写这篇文章的时候，已经有一个恶意的漏洞利用了最新的 Linux 内核漏洞， [Dirty Pipeline](https://dirtypipe.cm4all.com/) ，任何 J. Random 用户都可以覆盖/etc/passwd 中的 root 密码字段。LWN.net[的专家称之为](https://lwn.net/)[令人不安的内核漏洞。](https://lwn.net/Articles/887056/)“我称之为‘现在就开枪吧’的安全问题。

但是我们不要那样做，好吗？这里是 411 在[脏管道，又名 CVE-2022-0847](https://access.redhat.com/security/cve/cve-2022-0847) 。网络主机系统管理员和程序员麦克斯·凯勒曼早在 2021 年就发现了这个安全漏洞，但他起初并不确定发生了什么。在流了很多血、汗、泪和研究之后，凯勒曼追踪到问题出在 Linux 5.8 中变得至关重要的 Linux 内核的变化。凯勒曼写道，有了这次更新，“只需将新数据写入以特殊方式准备的管道，就可以覆盖页面缓存中的数据。”

## 情况变得更糟了

好吧，那很糟糕。但是更糟的还在后面。凯勒曼发现，“为了让这个漏洞更有趣，它不仅可以在没有写权限的情况下工作，还可以在只读 btrfs 快照和只读挂载(包括 CD-ROM 挂载)上工作不可变的文件。这是因为页面缓存始终是可写的(对于内核而言)，写入管道从不检查任何权限。”

我的天啊。

如果这敲响了一个微弱的警钟，它应该。 [2016 年的脏牛 Linux bug](https://www.zdnet.com/article/the-dirty-cow-linux-security-bug-moos/) 也有类似特征。但是，正如凯勒曼所观察到的，“但是更容易被利用。”

太棒了。绝对精彩。

## 高分

红帽给它一个 7.8 的通用漏洞评分系统(CVSS)评级。那很高。就我个人而言，我很想称之为比这更糟糕。除了已经存在的漏洞，当我阅读代码和凯勒曼关于他如何发现脏管道的一步一步的精彩描述时，我确信还有其他方式来滥用这个安全漏洞。

这就是这对你的意义。任何使用 Linux 内核的发行版在 5.8 及更高版本中都容易受到攻击。这意味着几乎所有的 Linux 产品发行版都容易受到攻击。

## 好消息，坏消息

好消息是 Linux 内核安全团队已经修复了 Linux 5.16.11、5.15.25 和 5.10.102 中的漏洞。所以，尽快开始修补您的 Linux 发行版吧。

坏消息是，截至美国东海岸周一晚上，并非所有发行版都发布了补丁。例如，[Red Enterprise Linux Server(RHEL)](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux?intcmp=7013a0000026H3vAAE)8 可能会受到攻击，Red Hat 声明“目前没有针对此缺陷的缓解措施”最近的 Ubuntu 发行版也是如此[。](https://ubuntu.com/security/CVE-2022-0847)

通常，在本文的这一点上，我会告诉你尽快修补你的操作系统。这一次，我告诉你要密切注意你的系统，不要做任何有趣的事情，并准备好在有补丁发布的时候给你的 Linux 打补丁。

或者，如果您能够胜任这项工作，并且认为消除这个问题值得冒一次险，那么可以自己动手将您的生产系统的测试版本升级到 5.16.11、5.15.25 或 5.10.102。如果你在软件栈中没有遇到任何令人窒息的回归或错误，那么你可以试着将你的自制补丁投入生产，直到你的官方补丁可用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>