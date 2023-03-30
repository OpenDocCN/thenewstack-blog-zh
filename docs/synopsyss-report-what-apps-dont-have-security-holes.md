# Synopsys 的报告:哪些 app 没有安全漏洞？！

> 原文：<https://thenewstack.io/synopsyss-report-what-apps-dont-have-security-holes/>

95%的 web 应用程序——这不是一个输入错误，95%——都有安全漏洞。

我知道程序安全性很差，你也知道。我们都知道。但是当 [Synopsys](https://www.synopsys.com/software-integrity.html?utm_content=inline-mention) 在其最新报告中公布“[软件漏洞快照:10 大最常见的 Web 应用程序漏洞](https://c212.net/c/link/?t=0&l=en&o=3709261-1&h=1027664030&u=https%3A%2F%2Fwww.synopsys.com%2Fsoftware-integrity%2Fresources%2Fanalyst-reports%2Fsoftware-vulnerability-trends.html%3Fcmp%3Dpr-sig%26utm_medium%3Dreferral&a=Software+Vulnerability+Snapshot%3A+The+10+Most+Common+Web+Application+Vulnerabilities)95%的测试程序都存在某种形式的漏洞，这让我目瞪口呆。

但你知道更糟的是什么吗？这比去年的结果要好，去年的结果发现 97%的测试应用程序存在安全漏洞。

这并不意味着这些都是精彩的表演。四分之三的 bug 属于中等风险或更低风险。尽管如此，仍有 20%存在高风险漏洞，4.5%存在严重漏洞。这些数字再次好于去年的报告，但仍然非常糟糕。

## 测试和目标

这些结果来自对 2，700 个软件目标进行的 4，300 次安全性测试。这包括 web 应用程序、移动应用程序、源代码文件和网络系统。绝大多数(82%)是 web 应用程序或系统。而 13%是移动应用程序，其余的是源代码或网络系统/应用程序。测试中涉及的行业包括软件和互联网、金融服务、商业服务、制造、消费服务和医疗保健。

大多数测试都是侵入性的“黑盒”或“灰盒”测试。这包括[渗透测试](https://c212.net/c/link/?t=0&l=en&o=3709261-1&h=3796080672&u=https%3A%2F%2Fwww.synopsys.com%2Fsoftware-integrity%2Fapplication-security-testing-services%2Fpenetration-testing.html%3Fcmp%3Dpr-sig%26utm_medium%3Dreferral&a=penetration+testing)、[动态应用程序安全测试(DAST)](https://c212.net/c/link/?t=0&l=en&o=3709261-1&h=3921454239&u=https%3A%2F%2Fwww.synopsys.com%2Fsoftware-integrity%2Fsecurity-testing%2Fdast.html%3Fcmp%3Dpr-sig%26utm_medium%3Dreferral&a=dynamic+application+security+testing+(DAST)) 和[移动应用程序安全测试(MAST)](https://c212.net/c/link/?t=0&l=en&o=3709261-1&h=2245877018&u=https%3A%2F%2Fwww.synopsys.com%2Fglossary%2Fwhat-is-mobile-application-security.html%3Fcmp%3Dpr-sig%26utm_medium%3Dreferral&a=mobile+application+security+testing+(MAST)) ，模拟真实世界的攻击者探测。

这意味着，根据 Synopsys 软件完整性集团安全咨询副总裁 Girish Janardhanudu 的说法:“侵入式黑盒测试技术，如 DAST 和 pen 测试，对于暴露软件开发生命周期中可利用的漏洞特别有效，应该成为任何完善的应用程序安全测试制度的一部分。”他是对的。

虽然静态分析、动态分析和软件组合分析在保护代码方面都有它们的位置，但成品的真实测试是必不可少的。例如，22%的目标存在跨站点脚本(XSS)漏洞。几乎所有的 XSS 漏洞只有在应用程序运行时才会显现出来。

## 十大漏洞

Synopsys 还在 77%的目标中发现了 OWASP 的 10 大漏洞。来吧，人们！阅读 OWASP 测试指南[并执行！没那么难！其中，应用程序和服务器配置错误占全部漏洞的 18%。另外 18%是因为访问控制问题。换句话说，Ops 也需要加强它的安全游戏。安全问题并不都落在开发者肩上。](https://owasp.org/www-project-web-security-testing-guide/)

他们还发现——告诉我你以前是否听说过——迫切需要一份[软件材料清单(SBOM)](https://thenewstack.io/securing-the-software-supply-chain-with-a-software-bill-of-materials/) 。在 21%的渗透测试中发现了易受攻击的第三方库。除非你确切地知道你的代码中有什么，否则你对易受攻击的组件是无能为力的。不信就问问用了 Log4j 的[错版的人。](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/)

千万不要以为只有高级别的安全漏洞才能让你得手。正如 Synopsys 指出的那样，低风险漏洞也可能被利用来为攻击提供便利。以常见的冗长的服务器标语为例。它们出现在几乎一半的基于 web 的应用程序中，它们提供了危险的数据，如服务器的操作系统名称、类型和版本号。有了这些信息，攻击者就知道应该对您的技术体系发起什么样的攻击。

[新思科技](https://thenewstack.io/synopsys-rapid-scan-can-now-security-check-proprietary-code/)也警告说外部安全测试是必须的。当然，他们提供了自己的 [Synopsys 应用服务测试工具](https://www.synopsys.com/software-integrity/security-testing.html)，但他们没有错。也就是说，他们也认为不错，古老的人类测试仍然有它的位置。这可能很费时间，但仍然很重要。

最后，该公司还警告说，我们在保护网络流量和服务器方面做得很糟糕。薄弱的 SSL/TLS 配置是 Synopsys AST 服务整体测试中发现的最大漏洞。令人震惊的是，77%的测试目标具有糟糕的 SSL/TLS 配置。这是不可接受的。基本的网络安全不在开发范围之内。尽管如此，如果你怀疑你的公司因为糟糕的网络安全让任何一个随机的黑客进入你的应用程序，是时候向你的 CISO、首席信息官和首席技术官抱怨了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>