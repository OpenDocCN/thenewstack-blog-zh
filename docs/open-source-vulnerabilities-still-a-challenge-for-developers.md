# 开源漏洞对开发者来说仍然是一个挑战

> 原文：<https://thenewstack.io/open-source-vulnerabilities-still-a-challenge-for-developers/>

在所有行业领域，开源软件继续对软件安全构成挑战。我们都知道，商业和开源软件、应用程序和操作系统中的漏洞会导致软件供应链违规，但现在我们看到攻击者正在瞄准 web 应用程序、API 服务器、移动设备和构建它们所需的软件组件。

新思科技发布了最新版的开源安全年度报告[开源安全与风险分析(OSSRA)](https://www.synopsys.com/software-integrity/resources/analyst-reports/open-source-security-risk-analysis.html) 。该报告由 [Synopsys 网络安全研究中心(CyRC)](https://www.synopsys.com/software-integrity/cybersecurity-research-center.html) 创建，着眼于黑鸭审计服务团队进行的 1700 多项商业代码库审计的结果。

Synopsys 每年都会发布 OSSRA 的调查结果，以帮助业界了解开源安全和许可风险状况。通过研究[开源](https://thenewstack.io/open-source-culture-starts-with-programs-and-policies/)的使用趋势和市场洞察，开发者可以更深入地了解他们在链接软件生态系统中的角色。

新思科技 2022 年审计的 1703 个代码库中，96%包含开源。航天、航空、汽车、交通、物流；EdTech 和物联网是该报告中包含的 17 个行业中的三个，这些行业在其审计的代码库中 100%开放源代码。在其余的垂直领域，超过 92%的代码库包含开源代码。

## 代码中存在高风险漏洞

自 2019 年以来，OSSRA 所有 17 项业务的高风险漏洞增加了至少 42%，在零售和电子商务领域飙升至 557%，在计算机硬件和半导体领域飙升至 317%。

OSSRA 今年的报告中新增了一个五年回顾，对开源和安全趋势进行了更全面的描述。尽管行业不同，审计代码库的整体开源内容全面增长。几个行业还显示出在其代码库中发现的漏洞数量惊人地增加，表明缺乏漏洞缓解措施。

一个仍然存在挑战的重要领域是补丁程序管理。在被审计的代码库中，89%包含了已经过时超过四年的开源代码(比 2022 年的报告增加了 5%)。91%的人使用的组件不是最新的可用版本，也就是说，有更新或补丁，但没有应用。随着[补丁管理](https://thenewstack.io/the-great-security-debate-is-patching-useless/)，许可冲突继续带来安全问题。今年，54%的审计代码库包含许可证冲突，比去年增加了 2%。

不更新软件是有正当理由的，但是 91%的数字中很大一部分可能是由于[开发团队没有意识到有一个开源组件的新版本可用。如果一家公司没有维护其代码中使用的开放源代码的准确和最新的清单，一个组件可能会被忽视，直到它暴露在高风险的利用中。找出它在哪里被使用并更新它的竞赛开始了。](https://www.synopsys.com/glossary/what-is-devsecops.html)

这正是 Log4j 所发生的事情，一年多后仍然是一个问题。尽管它获得了公众的关注，并且企业可能采取许多步骤来验证和修复 Log4j 在其代码库中的存在，但它仍然存在于所有代码库中的 5%和经审计的 Java 代码库中的 11%。

## 建立安全的开源最佳实践

建立软件治理最佳实践可以帮助您启动开源软件管理计划，以保护您的资源和数据免受零日漏洞的影响。这包括定义策略、建立批准过程、进行彻底的软件审计和建立 SBOM。

### **1。定义您的政策**

为您的组织构建一个开源策略可以最小化您的法律、技术和业务风险。您希望确定您的主要利益相关者，然后定义您组织的开源软件目标、现有利用率和目标使用情况。该策略应涵盖开源补丁和许可证，并确定谁将负责维护它们。理想情况下，您的策略应该定义获得开源软件的可接受来源，以及如何确定一个软件包是否合适。它还应该说明谁可以获得开源软件，以及使用或分发它是否需要许可。

### **2。创建审批流程**

建立一个批准过程来评估一个软件包是否满足你的组织的需求和质量标准。考虑代码质量、支持、项目成熟度、贡献者声誉和漏洞模式。考虑这些标准的批准过程将防止团队在您组织的代码中拥有同一软件包的多个版本，其中一些可能没有被修补或升级。任何审批流程都需要快速的请求处理。预先批准的开源列表会有所帮助。

### **3。开源软件审计**

审计揭示您的开源软件，并确保遵守公司法规。这可以帮助您找到符合开源许可和漏洞披露的组件。您应该在整个软件开发生命周期(SDLC)中执行开源扫描，但是您应该确保每次将应用程序构建到使用开源软件的候选版本中时都进行最终扫描，尤其是当您依赖于第三方的组件时。

### **4。建造 SBOM**

软件材料清单(SBOM)是代码库中所有开源和第三方组件的列表。一个 [SBOM](https://thenewstack.io/openssf-brings-sbom-and-sdpx-to-python/) 还列出了管理这些组件的许可证、代码库中使用的组件版本及其补丁状态，这允许安全团队快速识别任何相关的安全或许可证风险。自动化此操作消除了手动、不准确的开源清单。它还有助于识别易受攻击的组件并快速检测新出现的漏洞。如果你没有意识到你有，你就不能修补它。

## 新思科技如何提供帮助

Synopsys 有许多工具可以提供帮助。从功能强大的[软件组合分析](https://www.synopsys.com/software-integrity/security-testing/software-composition-analysis.html?intcmp=sig-blog-sbom) (SCA)工具，如 [Black Duck](https://www.synopsys.com/software-integrity/security-testing/software-composition-analysis.html) 到我们的两款新 SaaS 产品 [Polaris fAST Static 和 fAST SCA](https://www.synopsys.com/blogs/software-security/polaris-fast-static-sca/) ，Synopsys 可以帮助您的组织生成完整的开源 SBOM。像这样的 SCA 工具可以持续地提供开源信息，确保您对自己的开源风险有最新的了解，并允许您清点代码中的开源和第三方组件。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>