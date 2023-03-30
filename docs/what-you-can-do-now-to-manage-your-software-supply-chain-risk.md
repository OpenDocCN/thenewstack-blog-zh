# 你现在能做什么来管理你的软件供应链风险

> 原文：<https://thenewstack.io/what-you-can-do-now-to-manage-your-software-supply-chain-risk/>

[](https://www.synopsys.com/blogs/software-security/author/bhatc/)

[Chai Bhat](https://www.synopsys.com/blogs/software-security/author/bhatc/)

[Chai 是 Synopsys 公司的安全解决方案经理。](https://www.synopsys.com/blogs/software-security/author/bhatc/)

[](https://www.synopsys.com/blogs/software-security/author/bhatc/)[](https://www.synopsys.com/blogs/software-security/author/bhatc/)

虽然让每个人在假期都忙碌的 Log4j 危机对许多人来说是一个警钟，但减轻它并不能解决供应链攻击的更大问题。实施实践来管理供应链风险比以往任何时候都更加重要。供应链漏洞不断被发现。例如，新年刚过，帕洛阿尔托网络公司的研究人员就发现了一个软件供应链活动，用窃取数据的克星感染了苏富比的房地产网站。该活动通过 Brightcove 云视频平台实例分发。

为了从网站上抓取敏感数据，这种类型的攻击者注入恶意的 JavaScript 代码来接管 HTML 表单页面的功能，收集敏感的用户信息并将其重定向到恶意的收集服务器。然后，这些信息可用于创建貌似真实的网络钓鱼和社会工程攻击。

仅仅保护你的周边已经不够了。为了在你的软件中建立信任，保护你的软件供应链是至关重要的。该过程的第一步是通过建立[软件材料清单(SBOM)](https://www.synopsys.com/blogs/software-security/software-bill-of-materials-bom/) 来盘点你的软件供应链。创建 SBOM 的过程不仅仅涉及库存。构建 SBOM 意味着调查您的软件是如何构建、配置和部署的。当您知道您拥有什么、它来自哪里、谁在维护它、何时应该修补它以及修补是否已经完成时，您就提高了您的组织执行自动化漏洞修补的能力。

## 建立软件供应链风险管理(SSCRM)计划

构建一个准确的 SBOM 是开发人员应该承担的核心活动，但这只是一个可靠的 SSCRM 计划的开始。[美国国家标准与技术研究所(NIST)](https://www.nist.gov/) 开发了[网络安全供应链风险管理(C-SCRM)](https://csrc.nist.gov/Projects/cyber-supply-chain-risk-management) 和[安全软件开发框架](https://csrc.nist.gov/publications/detail/sp/800-218/draft)，为如何管理供应链风险提供建议。该框架定义了实施全面风险管理计划和正式 C-SCRM 计划的参数。

全面的风险管理计划应该整合到您的整个组织中。您的计划应该识别和管理关键的软件组件和供应商，并考虑它们的整个生命周期。

NIST 建议采取以下步骤来实施风险管理计划:

1.  确定推动收入的关键业务目标和流程。
2.  创建当前和未来软件许可证的清单。
3.  研究并记录供应商如何支持软件许可证。
4.  了解您的软件如何支持关键流程。
5.  创建一个计划来解决已发现漏洞的软件。

谈到供应链安全，NIST 建议您确保您的软件供应商:

*   坚持安全软件开发生命周期( [SDLC](https://www.synopsys.com/glossary/what-is-sdlc.html) )实践。
*   揭露漏洞。
*   提供补丁管理。
*   维护产品的批准供应商名单。
*   提供软件组件清单。

## 实施全面的 C-SCRM 计划

要实施 NIST 概述的全面的 C-SCRM 计划，您的组织需要做以下工作:

### 定义您的 SSCRM 路线图

确保供应链安全的第一步是定义您寻求的安全级别，并制定达到该级别的计划。你可以通过评估组成你的软件供应链的人员、过程和技术来做到这一点。理想情况下，您将引入第三方专家来进行评估。第三方专家为这种系统性的问题解决工作带来了新的视角，这在很大程度上是因为他们没有构建供应链决策的机构记忆。一旦你对供应链的风险有了清晰的了解，你就可以建立一个多年的策略来减轻和减少这些风险。

### 软件组合分析和二进制分析

SCA 和二进制分析是任何供应链风险管理解决方案的核心，因为如果您不知道您的软件中有什么，您就无法构建准确的 SBOM。更重要的是，除了声明的依赖项和清单之外，您还需要能够调查软件内容的工具。

完整的 SCA 解决方案采用:

*   **自动化开源检测**。重要的是，您的自动化开源检测策略要做一个完整的清单，一个不依赖于已声明的依赖项的清单。
*   **详细的安全性和合规性报告。**您的 SCA 解决方案应该编写关于安全性和合规性的详细报告，并定期提供关于组件质量的见解，以确保您只使用由强大的开源社区积极维护的高质量组件。
*   **自动化开源治理实施。**您的 SCA 解决方案应该自动执行开源治理，与您定义的风险容忍度保持一致，并且只需要开发和运营团队的有限输入和行动。

### 分析二进制文件、可执行文件和库

同样重要的是，无论清单声明什么，SCA 解决方案都要分析开源组件的二进制文件、可执行文件和库。您希望 SCA 系统能够:

*   检查二进制容器映像中清单中未公开的开源组件。例如，Docker 文件。
*   分析应用程序和容器以发现安全问题，包括已知和未知的漏洞。

### 恶意代码检测

您确信您的系统没有恶意代码吗？恶意代码可能会潜伏数月甚至数年，直到被激活。这种类型的代码可能隐藏在软件的表面之下，通常很难用传统的扫描工具检测出来。安全专家结合使用密集的手动扫描和自动检测来查找生产二进制文件、配置和数据中的可疑构造。专家还可以就恶意代码管理的适当方法和漏洞补救策略提供建议。

### **云和容器安全**

2021 年的报告显示，与保护云和容器相关的活动显著增加。研究表明，组织正在开发自己的能力来管理[云安全](https://www.synopsys.com/software-integrity/solutions/cloud-security.html)和评估他们的共同责任模式。

您现在可以采取的保护基础架构的步骤包括:

*   为您的云和容器策略定义一个策略，并构建一个路线图。确定您的公司应该使用哪些策略、功能和活动来支持高效的云安全计划。这需要了解您当前的云采用状态，并通过使用成熟的云安全参考架构和成熟度评估框架来定义可实现的未来状态。
*   进行[架构风险评估](https://www.synopsys.com/software-integrity/software-security-services/software-architecture-design.html)以检查您的潜在攻击面，确定安全控制的不足之处，并获得专家关于如何改进的建议。风险评估还识别可能导致业务风险的技术风险，根据风险发生的可能性确定风险的优先级，并规定缓解任务。
*   通过迁移前后的评估确保安全的云迁移。这包括使用具有基线安全控制的安全参考实施来构建和部署云应用，以及执行[静态应用安全测试](https://www.synopsys.com/software-integrity/security-testing/static-analysis-sast.html)，软件组合分析和动态分析。
*   保护好你的集装箱。通过彻底的[漏洞评估](https://www.synopsys.com/glossary/what-is-vulnerability-assessment.html)、[渗透测试](https://www.synopsys.com/software-integrity/application-security-testing-services/penetration-testing.html)、架构风险/ [威胁模型](https://www.synopsys.com/glossary/what-is-threat-modeling.html)和[开发安全操作](https://www.synopsys.com/glossary/what-is-devsecops.html)考虑事项，识别并降低云容器风险。
*   优化和管理云。这需要对配置、策略、控制和集成执行定期的云安全状态管理运行状况检查。它还包括根据需要对警报和事件进行补救、调查和响应。
*   确定行动的优先级并实施行动，以改善您的威胁态势并弥补差距。

## 供应链风险是商业风险

现在所有的生意都是软件生意。企业要么构建软件作为其产品和服务的一部分，要么购买软件并使用它来运营业务。软件是所有其他关键基础设施的关键基础设施，因此，它带有必须管理的重大风险，就像任何其他风险一样。这就是为什么现在构建安全流程的工作会随着您的发展而获得回报。作为稳健的 SSCRM 计划的一部分，投资建设 SBOM 比以往任何时候都更加重要。Log4j 和苏富比视频数据浏览等违规事件表明，每个企业都必须将安全放在首位。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>