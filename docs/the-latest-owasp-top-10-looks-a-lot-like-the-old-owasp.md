# 最新 OWASP 十大表面 Web 开发安全缺陷

> 原文：<https://thenewstack.io/the-latest-owasp-top-10-looks-a-lot-like-the-old-owasp/>

近 20 年来，[开放 Web 应用安全项目(OWASP)](https://owasp.org/) 。一个非盈利基金会一直致力于提高软件安全性。在最近更新的 [OWASP 的十大](https://owasp.org/www-project-top-ten/)最关键的网络应用[安全](https://thenewstack.io/category/security/)风险列表中，该组织吹嘘一个新的图形设计和一页信息图，但是内容，实际的安全风险，都太熟悉了。

的确，有三个新的类别，四个类别的命名和范围发生了变化，并且在 2021 年十大名单中进行了一些整合。即便如此，我们以前也见过其中的大部分:

*   [A01:2021-被破坏的访问控制](https://owasp.org/Top10/A01_2021-Broken_Access_Control/) 94%的应用程序都经过了某种形式的被破坏的访问控制的测试。映射到破坏访问控制的 34 个常见弱点枚举(cwe)在应用程序中出现的次数比任何其他类别都多。
*   [A02:2021-密码故障](https://owasp.org/Top10/A02_2021-Cryptographic_Failures/)，以前被称为敏感数据泄露，这是一个更广泛的症状，而不是根本原因。这些是导致敏感数据泄露或系统受损的加密故障。
*   [A03:2021-注射](https://owasp.org/Top10/A03_2021-Injection/) 94%的应用程序都经过了某种形式的注射测试，其中 33 个 cwe 在应用程序中的出现次数位居第二。这包括跨站点脚本。
*   [A04:2021-不安全设计](https://owasp.org/Top10/A04_2021-Insecure_Design/)是一个新的类别。这里的重点是从基本设计问题开始的安全缺陷。如果 web 设计人员使用威胁建模、安全设计模式和原则以及参考架构，就可以对抗这种威胁。
*   [A05:2021-安全错误配置](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)随着我们使用越来越多高度可配置的软件，这种情况越来越常见也就不足为奇了。你知道如何保护你的 Kubernetes 集群吗？以前的类别为 [XML 外部实体](https://owasp.org/www-project-top-ten/2017/A4_2017-XML_External_Entities_(XXE)) (XXE)现在是这个类别的一部分。
*   [A06:2021-易受攻击和过时的组件](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)之前的标题是使用具有已知漏洞的组件。这个已经成为头条新闻，因为它是[软件供应链](https://thenewstack.io/securing-the-software-supply-chain-with-a-software-bill-of-materials/)中被破坏的组件
*   [A07:2021-识别和认证失败](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/)先前被破解认证。它现在包括了涉及识别失败的[常见弱点列举(CWE)的](https://cwe.mitre.org/)。
*   [A08:2021-软件和数据完整性故障](https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/)是一个新的类别，它专注于对软件更新、关键数据和 CI/CD 管道做出糟糕的安全假设。这是软件供应链失误的另一个变种。
*   [A09:2021-安全记录和监控故障](https://owasp.org/Top10/A09_2021-Security_Logging_and_Monitoring_Failures/):这个名字说明了一切。
*   [A10:2021-服务器端请求伪造](https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/)虽然此类攻击相对较少，但社区成员对这种攻击媒介感到担忧。

如果您已经关注 OWASP 列表有一段时间了，您可能已经注意到，现在重点更多地放在战略问题上，而不是具体的漏洞分类。这意味着，那些声称提供 OWASP 十大安全漏洞完整覆盖的程序，我们可以说，掩盖了真相。是的，一些安全程序仍然可以帮助你处理你的安全弱点，但是这个新的列表更多的是呼吁你在总体安全方面更加努力，而不是简单地提供一个问题清单来修复。

那是因为——剧透警报！—我们的安全问题不仅仅是当前的安全漏洞。是的，它们表现为具体的问题，但在它们之下是一般性的问题，我们还没有解决。

例如，使用旧的、不安全的库和程序，比如当 [Equifax](https://www.zdnet.com/article/equifax-blames-open-source-software-for-its-record-breaking-security-breach/) 使用过时的 [Apache Struts](https://struts.apache.org/) 并泄露数千万美国人的个人数据时，仍然是一个太常见的问题。但是，如果你使用软件安全链标准，如 [ISO 软件包数据交换(SPDX](https://thenewstack.io/spdx-software-supply-chain-spec-becomes-an-iso-standard/) )，来跟踪你的程序，你将大大避免 OWASP 问题 6 和 8。

当然，正如 [Philippe De Ryck](https://www.linkedin.com/in/philippederyck/?originalSubdomain=be) ，[务实网络安全](https://pragmaticwebsecurity.com/)创始人在 OWASP 十大网络研讨会上所说的那样，“我希望在这样一个世界里，我可以告诉他们(人们)，‘使用这个和这个，这个和这个，你就完成了’，但是。”我们还没有到那一步，但我真的希望我们将来能达到那一步。"

我不抱太大希望。这份名单令人担忧。OWASP 自 2003 年以来发布了这些标准，虽然名称和涵盖的具体领域有所变化，但问题仍然存在。

解决方案不是不充分的安全程序，而是教育开发人员如何将基本的安全性融入他们的程序。它让公司支持程序员将安全性嵌入他们的软件。只有当安全性成为开发人员和管理人员的首要任务时，我们才能最终拥有真正安全的软件。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>