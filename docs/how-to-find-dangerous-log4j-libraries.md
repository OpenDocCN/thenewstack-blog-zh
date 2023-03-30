# 如何找到危险的 Log4j 库

> 原文：<https://thenewstack.io/how-to-find-dangerous-log4j-libraries/>

Apache [log4j](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/) 日志库已经成为技术的新冠肺炎。我们刚修好一个版本，另一个版本就冒出来烦我们。截至 12 月 21 日，最新修补的 Log4j 是版本 [Log4j 2.17.0。](https://www.zdnet.com/article/apache-releases-new-2-17-0-patch-for-log4j-to-solve-denial-of-service-vulnerability/)如果你把它安装在正确的位置，那就很好。

此时，有三个独立的 Log4j 安全问题。 [CVE-2021-45046](https://nvd.nist.gov/vuln/detail/CVE-2021-45046) ，原版，获得了完美的 10 分， [CVE-2021-44228](https://nvd.nist.gov/vuln/detail/CVE-2021-44228) ，它的危险小得多的表亲。这些共同构成了 [Log4Shell](https://www.dynatrace.com/news/blog/what-is-log4shell/) 漏洞。此外，还有另一个单独的 log4j 拒绝服务(DoS)攻击， [CVE-2021-45105](https://nvd.nist.gov/vuln/detail/CVE-2021-45105) 。

### 寻找讨厌的图书馆

当然，诀窍是找到那个讨厌的 Apache 日志库。Log4j 在地球上到处都被使用…火星也是。是的，[未打补丁的 Log4j 就在火星基心灵手巧直升机上。](https://www.linkedin.com/pulse/remote-code-execution-bugs-found-mars-joachim-bauernberger/)

安全研究人员已经花了两周时间四处挖掘，试图猜测它曾经签署的每个外包 Java 项目的依赖关系。太多的代码隐藏在 Java 归档文件(JARs)中。

正如安全副总裁 Josh Bressers 所解释的，“log4j 漏洞带来的挑战之一就是找到它。Java 应用程序和依赖项通常采用某种打包格式，这使得分发和运行变得非常容易，但却很难弄清楚这些软件包的内容。”

你看，Bressers 继续说，“当在 Java 中工作时，依赖关系被编目为 Java 档案文件，通常称为 JAR 文件。这些包可以作为 Java 库使用，但是这里的问题是 JAR 文件可能开始看起来像俄罗斯的嵌套玩偶。一个 JAR 文件可以包含 JAR 文件，而这些 JAR 文件也包含 JAR 文件。它基本上是一路向下的 JAR 文件。”

“尽管如此，所有的希望并没有失去！”布雷瑟斯总结道。您可以使用两个 Anchore 开源项目 [Syft](https://github.com/anchore/syft) 和 [Grype](https://github.com/anchore/grype) ，来检测和识别 log4j，即使它被埋在第三圈 JAR 文件中。

### 其他可用的工具和程序

您可以使用其他工具来尝试发现 log4j 的易受攻击版本。一些主要的安全概述扫描器现在包括了用于查找潜在易受攻击的 log4j 库的工具。其中包括: [Cyber CNS](https://www.cybercns.com/) 、 [F-Security Elements](https://www.f-secure.com/us-en/business/solutions/elements) 、 [LionGuard](https://insights.liongard.com/apache-vulnerability-liongard-steps) 、[Microsoft Defender for Endpoint](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/#TVM)、[Qualys Application Scanning](https://www.qualys.com/apps/web-app-scanning/)和 [Tanium](https://www.tanium.com/) 。

还有一些程序，几乎都是开源的，可以用来查找 log4j 库。

按字母顺序排列如下:

祝狩猎愉快！愿你所有的补丁都在假期前做好。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>