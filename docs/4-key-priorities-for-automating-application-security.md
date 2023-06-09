# 自动化应用安全的 4 个关键优先事项

> 原文：<https://thenewstack.io/4-key-priorities-for-automating-application-security/>

几个月前，我的同事写了一篇文章，强调了传统应用程序安全性早该升级的一些原因。那篇文章中详述的挑战仍然是世界各地的组织最关心的问题。如今的云原生应用如此复杂和动态，以至于传统的应用安全和漏洞管理方法已经跟不上了。这种差距越来越给组织带来安全风险。现在，[新的研究](https://www.dynatrace.com/info/cloud-application-security-ciso-research-1/)强调了这种情况对于开发团队来说变得更加具有挑战性。

## **传统的应用程序安全工具不再适用于今天**

 [杰克·马萨尔

Jack 是网络安全产品营销负责人，在网络安全、企业 IT 基础设施和云安全领域拥有超过 15 年的技术经验。在 Dynatrace，他帮助为其市场领先的软件智能平台添加了新的安全应用。](https://www.linkedin.com/in/jackmarsal/) 

随着微服务、容器、Kubernetes、开源软件和敏捷开发已经成为组织的技术堆栈和生产管道的组成部分，CISOs 表示，这些技术和实践在应用安全方面创造了新的盲点。现有的安全工具不是为现代云环境设计的，现代云环境比传统计算环境要复杂和动态得多。因此，检测和管理软件漏洞变得越来越困难，以至于在新研究中接受调查的 71%的 CISOs 表示，当他们将代码投入生产时，他们不确定代码是否没有漏洞。当你考虑到只有 3%的 CISOs 说他们对运行时漏洞有实时可见性时，这并不奇怪。绝大多数人根本不知道他们团队投入生产的代码中潜在漏洞的程度。

由于传统的应用程序安全测试和风险评估无法跟上现代云环境的步伐和 DevOps 团队的快速创新周期，精确的风险评估变得几乎不可能。这是由于一系列越来越普遍的因素造成的:

*   快速软件发布周期。
*   使用经常包含安全漏洞的开源软件。
*   使用容器，容器快速旋转，对传统的运行时安全控制相对不透明。
*   使用微服务，这涉及许多依赖关系和通信路径，通常跨越多个云边界。

## **团队淹没在漏洞警报和误报中**

该研究还强调了 DevSecOps 团队被迫手动筛选大量安全警报的程度，其中许多是误报，即源代码中存在的漏洞，但在生产中并未实际使用。

平均而言，组织每月会收到 2，169 个新的安全漏洞警报，其中 77%的 CISOs 将这些警报中的大部分识别为不需要采取措施的误报，并且不是真正的漏洞。整理这些误报消耗了安全团队的宝贵时间和注意力。更糟糕的是，超过三分之二的 CISOs 告诉我们，很难根据漏洞的潜在风险和影响对其进行优先级排序。因此，团队不仅被迫处理大量的警报，他们甚至不知道哪些是最迫切需要处理的，哪些是不重要的。

由于手动工具和工作流太慢，开发人员需要在速度和安全性之间做出令人沮丧的选择。业务需求经常驱使团队优先考虑速度，但是这种选择将组织及其客户都暴露在不必要的风险中。当 28%的 CISOs 表示他们的应用程序开发人员有时会绕过漏洞扫描来更快地交付软件，而 64%的 CISOs 表示开发人员在将代码投入生产之前并不总是有时间解决漏洞时，很明显大多数组织都将自己暴露在不必要的风险中。

DevSecOps 控制这些问题的最佳方式(更重要的是，创建一个可行的、长期的、经得起未来考验的漏洞管理方法)是采用一个完全自动化的应用程序安全系统，该系统是专为当今快节奏的云原生环境设计的。

## **应用安全现代化的 4 个优先领域**

为了实现应用程序安全性方法的现代化和自动化，DevSecOps 团队应该开始关注几个关键的优先事项:

1.  **强调运行时可见性** : 50%的 CISOs 表示他们最担心应用程序运行时阶段的漏洞暴露，这是攻击最有可能发生的地方。
2.  **将漏洞测试工具与可观察性解决方案合并**:现代可观察性解决方案能够独一无二地提供上下文数据，例如微服务正在建立的连接，89%的 CISOs 表示这将使风险评估更加自动化和更加准确。
3.  **确保安全问题的实时可见性**贯穿整个软件生命周期、预生产和生产:90%的 CISOs 认为这将有助于在不影响安全性的情况下快速发布新版本。
4.  **确保所有安全测试都 100%自动化**，这样开发人员就不会遗漏任何步骤:这包括在生产和预生产环境中，在运行时对应用程序、库和代码进行自动和持续的分析。77%的 CISOs 认为这将确保应用程序安全性能够更好地跟上现代云原生环境的步伐。

DevSecOps 团队只有在生产环境中出现实际运行时漏洞时，有办法识别和评估这些漏洞的确切影响，才能确保云原生应用程序是安全的。解决困扰对静态源代码进行操作的现有应用程序安全工具的误报问题的最佳方式是采用一种运行时方法，该方法由来自生产环境的实时信息提供信息。通过在整个软件开发生命周期中利用自动、广谱的可观察性和上下文驱动的分析，团队可以根据实际暴露和业务影响，立即识别重要的漏洞警报。

自动化 DevSecOps 流程和消除手动工作有助于团队消除盲点和误报，确定暴露实际风险的漏洞警报的优先级，并减少对缓慢的手动安全测试的依赖。所有这些都有助于更准确地实时回答漏洞的原因、性质和影响。

不应该要求 DevSecOps 在速度和安全性之间做出选择。部署到动态、容器化的云原生堆栈中并提供连续、自动覆盖的自动化应用程序安全性确保团队不必做出错误的选择，而是可以推动更快、更安全的创新发布周期。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>