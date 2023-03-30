# 开源安全是 DevSecOps 的首要任务，但打补丁仍然太慢

> 原文：<https://thenewstack.io/open-source-security-top-of-mind-in-devsecops-but-patching-still-too-slow/>

[Synopsys](https://www.synopsys.com/software-integrity.html) 赞助本帖。

 [蒂姆·麦基

Tim 是 Synopsys CyRC(网络安全研究中心)的首席安全策略师。作为一名安全策略师，Tim 将他在分布式系统工程、关键任务工程、性能监控、大规模数据中心运营和全球数据隐私法规方面的技能应用于解决客户问题。他从这些活动中吸取了经验教训，并在 RSA、Black Hat、开源峰会、KubeCon、OSCON、DevSecCon、DevOpsCon、Red Hat Summit 和 Interop 等全球知名活动中发表演讲。蒂姆也是奥莱利媒体出版的作者。](https://www.linkedin.com/in/mackeytim/) 

开源在当今的软件生态系统中扮演着重要的角色。根据 Synopsys 网络安全研究中心的 2020 年“[开源安全和风险管理(OSSRA)](https://www.synopsys.com/software-integrity/resources/analyst-reports/2020-open-source-security-risk-analysis.html) ”报告，所有现代代码库都可能包含开源组件和库，开源通常占整个代码的 70%或更多。与开源使用增长并行的是不受管理的开源带来的安全风险——2019 年新思科技审计的代码库中，75%包含已知安全漏洞的开源。

Synopsys 最近发布了其 OSSRA 报告的姊妹篇“2020 年的 [DevSecOps 实践和开源管理”，其中涉及了对 1500 名从事网络安全、软件开发、软件工程和 web 开发的 IT 专业人员的调查结果。该调查探讨了世界各地的组织用来解决开源漏洞管理的策略，以及商业代码中过时或废弃的开源组件的问题。](https://www.synopsys.com/software-integrity/resources/analyst-reports/devsecops-practices-open-source-management.html?cmp=brand-sig&utm_medium=referral&utm_source=thenewstack)

“DevSecOps Practices and Open Source Management in 2020”显示，安全性和组件的漏洞是调查受访者最关心的问题，这些问题在审查新的开源组件时被列为首要选择标准。

## **未打补丁的开源漏洞:开发者痛苦的主要来源**

从调查结果中可以明显看出，未打补丁的漏洞是开发人员痛苦的主要来源。超过一半(51%)的受访者表示，他们需要两到三周的时间来应用开源补丁。超过 50%的美国受访者(全球范围内为 40%)报告称，他们为了解决开源漏洞而中断了交付计划。这可能与只有 38%的人在软件开发生命周期的早期使用自动化软件组合分析(SCA)工具来解决开源安全问题有关。自动化 SCA 解决方案允许开发团队在他们的代码中识别和跟踪开源，降低安全性和许可证合规性风险，并使用现有的 DevOps 工具和流程自动实施开源策略。不使用 SCA 工具的组织可能仍然在使用手动过程来识别和管理开源——这些过程会减慢开发人员的速度，并迫使他们在安全性方面进行追赶。

重要的是要记住，开源开发团队所采用的安全实践可能与创建定制代码的内部团队不同。开源安全更新可能不会与专有编码团队使用的 sprint 周期或发布时间间隔联系在一起。给定开源组件的默认设置可能不符合组织的安全策略。识别与开放源代码相关的风险需要准确理解应用程序中使用的所有开放源代码，包括商业库中嵌入的开放源代码。

## **从软件 BOM 开始**

这就是 SCA 工具可以扮演的角色——从软件材料清单(BOM)开始。全面的软件 BOM 不仅列出了所有开源组件，还列出了所使用的版本、每个项目和所有依赖项的下载位置、代码调用的库以及这些依赖项链接到的库。

软件 BOM 的概念来源于制造业，其中传统的物料清单是详细列出产品中所有项目的清单。例如，当发现有缺陷的零件时，BOM 使汽车制造商能够精确地确定哪些车辆受到影响，从而开始维修或更换过程。同样，维护准确、最新的软件 BOM(包括开源组件的清单)对于组织来说是必要的，以确保他们的代码是高质量、合规和安全的。与制造业一样，开源组件的 BOM 允许您快速查明易受攻击的组件，并适当地确定补救工作的优先级。

正如“2020 年的 DevSecOps 实践和开源管理”中所指出的，许多组织(尤其是美国的组织)应该加快他们的补丁时间表。生产级 SCA 解决方案是将修补时间从数周缩短到数天的关键，它可以持续监控新漏洞并提供缓解指南。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>