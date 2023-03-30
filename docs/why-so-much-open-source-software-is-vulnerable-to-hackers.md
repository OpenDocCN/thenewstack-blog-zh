# 为什么如此多的开源软件易受黑客攻击

> 原文：<https://thenewstack.io/why-so-much-open-source-software-is-vulnerable-to-hackers/>

Synopsys 网络安全研究中心最近的一份报告发现，多达 84%的企业正受到他们在系统中使用的开源代码的威胁，其中最明显的是 JavaScript，这是目前使用最广泛的基于开放标准的代码框架。

由历史悠久的电子设计自动化(EDA)和安全提供商 [Synopsys](https://synopsys.com) 发布的[开源安全和风险分析(OSSRA)](https://www.synopsys.com/software-integrity/resources/analyst-reports/open-source-security-risk-analysis.html) 报告描述了基于全球 17 个行业的 1700 项审计的商业软件开源安全、合规性、许可和代码质量风险的现状。该研究显示，高达 84%的代码库包含至少一个已知的开源漏洞——比去年增加了 4%。

例如，理解和使用 [JavaScript](https://thenewstack.io/brendan-eich-on-creating-javascript-in-10-days-and-what-hed-do-differently-today/) ，使黑客能够发现[漏洞](https://thenewstack.io/owasp-top-10-a-guide-to-the-worst-software-vulnerabilities/)并进行网络利用，因为网络上的大多数应用程序都使用 JavaScript 或其库。由于 JavaScript 可以用来读取保存的 cookies，因此经常被用来开发跨站点脚本程序，以达到黑客攻击的目的。

## 叫醒电话

该报告为依赖开源软件的公司敲响了警钟，开源软件长期以来一直是许多不同类型的应用程序和基础设施软件的基础。它建议补救来自开放源代码、专有代码和商业代码的业务风险的第一步是对业务使用的所有软件进行全面的清点，无论这些软件来自何处或如何获得。这将涉及创建一个[软件材料清单(SBOM)](https://www.synopsys.com/blogs/software-security/software-bill-of-materials-bom/) ，它列出了一个应用程序中的所有开源组件，以及它们的许可证、版本和补丁状态。

OSSRA 的报告揭示了其他几个相关的发现。例如:

*   在过去的五年中，开放源码的使用有了显著的增长，其中教育技术领域的增长最为显著；其开源实例的数量增长了 163%。
*   该报告还发现，高危漏洞以惊人的速度增加，自 2019 年以来，零售和电子商务领域的高危漏洞激增了 557%。
*   相比之下，物联网(IoT)领域的总代码中有 89%是开源的，在同一时期，高风险漏洞增加了 130%。同样，航空航天、航空、汽车、运输和物流垂直行业的高风险漏洞增加了 232%。
*   与使用许可组件相比，使用没有许可的开源组件使许多组织面临更大的违反版权法的风险。
*   可用的代码质量和安全补丁没有足够频繁地应用于大多数代码库。在包含风险评估的 1，480 个经审计的代码库中，91%包含过时版本的开源组件。这可能导致漏洞被网络罪犯利用，他们总是在寻找软件供应链中的弱点。

许多商业和专有代码库是通过合并和收购交易获得的。随着时间的推移，公司使用数百个(通常是数千个)应用和网络服务，收购公司几乎不可能了解新系统引入其漏洞的所有信息。

新思软件完整性集团的高级软件解决方案经理 Mike McGuire 告诉 TNS:“漏洞只是软件行业业务的一部分。“但并不是所有的弱点都是一样的。我认为更令人担忧的是我们在几乎一半的代码库中发现的高风险漏洞。”

许多公司定期编制自己的软件和网络安全漏洞报告。其中包括[思科系统](https://www.cisco.com/c/en/us/support/security/identity-services-engine/products-security-advisories-list.html)、 [Fortinet](https://www.fortinet.com/blog/threat-research/predict-threats-and-secure-networks-with-epss) 、[北极狼](https://arcticwolf.com/)、 [Imperva](https://www.imperva.com/cyber-threat-index/) 等等。

## 测量严重性

McGuire 说，网络安全研究中心是这样定义高风险漏洞的:

“他们从众多(行业)安全源中获取建议，进行分析，然后发送给我们的客户。作为这种分析的一部分，他们分配严重性分数。谈到开源漏洞，他们使用的是 [CVSS 评分系统](https://arcticwolf.com/resources/blog/cvss-measuring-severity-of-an-it-security-vulnerability/)。它(严重性)还取决于是否存在漏洞；是否有可用的修补程序；利用的类型；对于某些人来说，浏览和实际开发应用程序是多么容易；这是否可以远程完成；以及您是否有权访问正在运行的实例。因此，所有这些(属性)都被考虑在内。然后这个分数告诉我们它是否是一个高严重性的漏洞，”McGuire 说。

[新思软件完整性集团总经理杰森·施密特](https://www.linkedin.com/in/mjasonschmitt/)表示，报告的发现强调了开源作为当今大多数软件的底层基础的现实。Schmitt 说，在今年的审计中，使用的开源组件的平均数量同比增长了 13%(从 528 个增加到 595 个)，这进一步增强了实施全面的 [SBOM](https://thenewstack.io/sbom-everywhere-the-openssf-plan-for-sboms/) 的重要性。

McGuire 说，以现代开发速度管理开源风险的关键是保持应用程序内容的完全可见性。他说，通过将这种可见性构建到[应用生命周期](https://thenewstack.io/cloud-native-application-lifecycle-difference-continuous-change/)中，企业可以用所需的信息武装自己，以做出关于风险解决的明智、及时的决策。

总部位于加州山景城的 Synopsys 公司为电子设计自动化(EDA)、半导体知识产权、软件质量和安全解决方案开发电子产品和软件应用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>