# 从正在展开的 Log4j 紧急事件中吸取教训

> 原文：<https://thenewstack.io/learning-from-the-unfolding-log4j-emergency/>

[](https://www.linkedin.com/in/charlottemfreeman/)

 [夏洛特·弗里曼

夏洛特从事科技和安全方面的写作已经超过 20 年。她目前是 Synopsys 软件完整性小组的高级安全作家。](https://www.linkedin.com/in/charlottemfreeman/) [](https://www.linkedin.com/in/charlottemfreeman/)

信息安全世界已经“全体出动”处理无处不在的 [Log4j](https://logging.apache.org/log4j/) 基于 Java 的开源日志框架中的 [Log4j 漏洞](https://thenewstack.io/another-day-another-log4j-vulnerability/)。这个漏洞上周被列在 [CVE-2021-44228](https://cve.mitre.org/cgi-bin/cvename.cgi?name=2021-44228) 下，在通用漏洞评分系统(CVSS)中以 10 分制的分数发布，这就是为什么它被视为紧急情况。

该漏洞利用了一个新发现的缺陷，该缺陷使 Log4j 的某些版本能够通过不需要身份验证的 [LDAP](https://searchmobilecomputing.techtarget.com/definition/LDAP#:~:text=LDAP%20(Lightweight%20Directory%20Access%20Protocol)%20is%20a%20software%20protocol%20for,or%20on%20a%20corporate%20Intranet.&text=500%2C%20a%20standard%20for%20directory%20services%20in%20a%20network.) 目录查找协议执行任意文本。这意味着 Log4j_2 漏洞，也称为 Log4jShell，允许攻击者执行远程代码执行，以在易受攻击的系统上部署勒索软件、远程访问木马和 web 外壳。

自上周首次报告该漏洞以来，已经发起了超过 180 万次攻击。安全公司的遥测报告显示，包括民族国家行为者在内的攻击者已经使用至少 70 种不同的恶意软件家族，将所有企业全球网络的一半作为目标。世界各地的 Twitter、论坛和群聊都在进行热烈的讨论，这有助于激发人们对该漏洞的持续关注。这些讨论也推动了关于如何不仅缓解这个问题，而且缓解类似这样的未来问题的研究。

有一些 DevSecOps 和 AppSec 协议可以帮助您保护您的组织免受正在展开的 Log4j_2 危机和其他类似危机的影响。以下是您应该采取的六种缓解措施，以构建更强大的深度防御和 AppSec 协议来保护您的组织免受这些威胁。

1.  **漏洞通知。**您无法修复自己不知道的漏洞，因此实施自动警报系统可以最大限度地缩短从漏洞发现到信息传播到团队的时间。这将帮助您最大限度地提高响应能力，并识别哪些应用程序利用了问题组件。使用像[黑鸭](https://www.synopsys.com/blogs/software-security/black-duck-security-advisories-benefits/)这样的健壮的软件组成分析(SCA)解决方案，根据他们软件[物料清单(SBOM)](https://www.synopsys.com/blogs/software-security/software-bill-of-materials-bom/) 中的项目直接向开发者或产品所有者发送实时警报，将会简化您的恢复能力。
2.  **易被利用:输入和输出验证。**成功利用 Log4j_2 漏洞意味着你忽略了几个[安全编码原则](https://www.synopsys.com/glossary/what-is-code-review.html)。来自不可信来源的数据(即用户控制的输入)通常不应该在没有清理的情况下连接到日志文件中。当数据来自未经验证的来源(无论是人类用户还是其他应用程序)时，尤其如此。流入敏感区域(如可能呈现给其他人的数据库和日志)的数据应该接受输出验证。不这样做本身就是一个日志注入漏洞，这个漏洞早就为人所知，并被归类为 CWE 117 ，在 [CERT Java 编码规则](https://wiki.sei.cmu.edu/confluence/display/java/IDS03-J.+Do+not+log+unsanitized+user+input)中也有描述。您的第一道防线是确保您的应用程序没有这类缺陷。
3.  **网络架构和网络级访问控制**。成功利用 Log4j_2 漏洞需要攻击者能够将有效负载传输到外部系统或从外部系统泄漏数据。这可能包括传输代码以执行外壳或启动密码挖掘恶意软件。启动与外部主机的通信应始终锁定在最低限度。来自[互联网安全中心(CIS)](https://www.cisecurity.org/controls/network-monitoring-and-defense/) 的指导方针涵盖了这一点，许多其他控制框架也是如此，包括米特 ATT & CK，它在 [M1037 中有一整个类别的缓解措施，涵盖了网络过滤](https://attack.mitre.org/mitigations/M1037/)。对于客户端应用程序，使用沙盒技术(即使只有内置的操作系统和 JVM 功能)可以进一步减少可用的利用途径的范围。
4.  **应用架构风险。**适当部署防御性编程技术可以帮助您避免最糟糕的情况，即未经身份验证的外部用户访问应用程序必须公开才能运行的应用程序元素。一个设计良好的应用程序应该锁定[服务器端输入过滤](https://wiki.sei.cmu.edu/confluence/pages/viewpage.action?pageId=88487865)，以将接受的数据限制为那些预期的类型和范围值。为什么你的登录页面需要允许$和{字符？尽管自由文本搜索字段允许各种各样的字符可能是有意义的，但是您应该消除敏感数据(如密码)在整个体系结构的日志中的传播。[交互式分析工具](https://www.synopsys.com/software-integrity/security-testing/interactive-application-security-testing.html)可以帮助您可视化应用数据流，包括跨应用和微服务边界的数据流，以便您可以找出哪些数据需要去往何处，并确保存在适当的过滤。
5.  **日志记录、监控和异常检测。不，这不是讽刺。异常检测例程应该能够发现应用程序的异常行为，例如尝试连接到不适当的主机、启动进程或访问通常不与之交互的文件。有一个长长的防御和检测控制层列表，可以配置为沙盒环境的一部分，使现实世界的利用几乎不可能。或者，如果确实发生了攻击，这些控制可以显示访问了什么，并支持违规调查团队确定真正的业务影响。**
6.  软件组件透明性、供应商管理和成熟开源的采用。Log4j _ 2 漏洞如此重要的一个原因是，它是一个无处不在的软件风险的完美例子，这些软件不是我们自己开发的，包括我们日常使用的产品中嵌入的软件。这就是为什么您应该有一个准确的 SBOM——通过准确识别在哪里使用了 Log4j 这样的组件，以及您应该与哪些产品或供应商合作进行补救，来简化响应和调查。开源代码的成熟管理也是这场网络野火的重要组成部分。正如新思科技[网络安全研究中心](https://www.synopsys.com/software-integrity/cybersecurity-research-center.html) (CyRC)首席安全策略师蒂姆·麦基喜欢说的，“没有开源这样的供应商。”在 Log4j 的例子中，这个库似乎仍然被 Apache 基金会作为一个更广泛的社区计划的一部分积极地维护和支持着。但是许多图书馆是在没有特定群体甚至专门个人支持的情况下开发的，后来被抛弃或遗忘。了解您的开源组件的出处，包括它们的社区支持级别，提供了一个指示器，指示您在哪里容易受到这种潜在风险的攻击。

没有人想掩盖所有团队正在夜以继日地修补整个网络的 Log4j_2 漏洞的努力，但重要的是要记住问题不在于这个特定的黑客。每一次攻击，从臭名昭著的 [Heartbleed](https://www.synopsys.com/blogs/software-security/mitigating-impact-of-log4j-log4shell/) 到最近披露的[木马源](https://www.synopsys.com/blogs/software-security/mitigating-impact-of-log4j-log4shell/)，都是 AppSec 的一次学习机会。

Log4j_2 的早期经验表明，安全原则是处理这些高风险软件供应链安全事件的关键。这一事件是一长串供应链攻击中的又一个，当今全球互联的软件供应链的性质意味着在可预见的未来，易受攻击的软件组件可能会成为反复出现的威胁。组织要取得成功，必须将一系列安全活动融入 IT 系统的规划、构建和操作文化中。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>