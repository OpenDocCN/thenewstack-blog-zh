# 您的开发实践是否引入了 API 安全风险？

> 原文：<https://thenewstack.io/are-your-development-practices-introducing-api-security-risks/>

为什么 [61%](https://www.imperva.com/resources/resource-library/white-papers/improve-api-performance-with-a-sound-api-security-strategy/) 的决策者说提高 API 安全性是一个关键的优先事项？不幸且令人担忧的现实是，网络罪犯将 API 用作获取组织数据和业务逻辑的途径，而且往往就在他们的眼皮底下。

由达信麦克伦南网络风险分析中心完成的一项[研究](https://www.imperva.com/resources/resource-library/reports/quantifying-the-cost-of-api-insecurity/?utm_medium=PR&utm_source=Organic-Referral)发现，每 13 起安全事件中就有一起可归因于 API 相关风险。你做了足够的工作来保护你的 API 和底层数据免受有动机的攻击者的攻击吗？

企业使用的 API 数量将在 2023 年继续快速增长，因为组织依赖它们在应用程序和数据存储之间交换数据。将近一半的[企业](https://www.imperva.com/resources/resource-library/white-papers/improve-api-performance-with-a-sound-api-security-strategy/)在内部或公开部署了 50 到 500 个 API，而更大的企业可能有超过 1000 个。如今，据估计, [API 不安全](https://thenewstack.io/why-api-security-is-different-and-how-the-openapi-spec-can-help/)每年导致 410 亿到 750 亿美元的损失。随着生产中的 API 数量成倍增加，预计在未来几个月将会听到更多与易受攻击的 API 相关的安全事件。

## **不安全的开发滋生 API 安全风险**

通常与 API 相关的安全事件源于不安全的开发实践。

当我与开发人员和安全负责人交谈时，我越来越多地听到这两个组织职能部门正在合作，因为他们认识到即使是一个简单的漏洞，如配置错误，也可能暴露他们组织的数据。

今天，API 的关键问题归结为可见性。开发人员将它们发布到生产环境中的速度比安全团队审查或分类它们的速度还要快。这使得无法识别潜在的漏洞并降低未来的风险。

在零售行业，过去一年中有 3%[到 5%](https://www.imperva.com/resources/resource-library/reports/the-state-of-security-for-ecommerce-2022/) 的 API 流量被导向未记录或[影子 API](https://thenewstack.io/shadow-zombie-and-misconfigured-apis-are-a-security-issue/)，即安全团队不知道存在或不再保护的端点。虽然这一流量百分比看似微不足道，但它代表了一个漏洞，有动机的网络犯罪分子可以利用这个漏洞发起攻击并泄露敏感数据。

下面是两个不安全开发实践的常见例子，它们导致了与 API 相关的安全事件的增加:

*   **未经安全审查或控制而发布的 API:**这种实践创建了对安全团队和 [API 网关](https://thenewstack.io/dont-be-fooled-api-gateways-arent-a-security-panacea/)不可见的影子 API。影子 API 可以像公开的、安全的 API 一样访问相同的敏感信息，但是没有人知道它们在哪里，它们连接到什么，或者谁在访问它们。
*   **API 未被正确禁用:**废弃或僵尸 API 成为网络犯罪活动的潜在滋生地，通常在开发人员和安全运营部门的权限之外。这些不受监控的 API 相当于一个未锁定的窗口。有动机的犯罪分子可以潜入以访问数据或执行更复杂的攻击，通常开发人员或安全团队都不知道。

成功的安全事件通常会利用 API 实现漏洞。对于大多数公司来说，这种攻击不容易通过可预测的攻击模式识别出来，而且几乎不可能阻止。唯一有效的对策是使用持续的 API 监控，将威胁情报反馈给 DevOps 团队，这样开发人员可以在 API 被利用之前快速修改它的实现。

## **每个开发人员都应该关注自动化威胁**

针对 API 业务逻辑的[自动化攻击](https://thenewstack.io/can-you-bot-proof-your-applications-and-apis/)的数量将在 2023 年增长，因为网络罪犯利用僵尸网络实施恶意攻击。

API 是此类攻击的主要目标，因为网络罪犯可能会使 API 端点过载不需要的流量。最终，攻击者的目标是使用 API 作为蓝图来寻找内部对象或数据库结构进行利用。例如，连接到前端服务的易受攻击的 API 端点后端会使最终用户面临风险。一名研究人员甚至[发现了](https://samcurry.net/web-hackers-vs-the-auto-industry/)一种滥用汽车的 API 和远程信息处理系统来远程执行各种任务的方法，例如锁车。

过去，开发 CAPTCHA 等机器人管理技术是为了阻止机器人访问仅供人类用户使用的网页。但是，这种安全方法假设所有自动流量都是恶意的。随着应用程序环境的成熟和增多，自动化对于执行简单的功能变得至关重要。因此，这意味着组织不能依赖简单的 [web 应用防火墙](https://thenewstack.io/rethinking-web-application-firewalls/)规则，默认情况下，这些规则会阻止来自自动化来源的所有流量。相反，他们需要快速识别和区分好的和坏的机器人流量。

虽然为了实施安全控制和策略而减缓创新是不现实的，但是应该部署自动化工具来支持安全开发并实现应用程序和服务可用性。

## **积极主动。网络安全风险不会消失**

现代互联网是一个 API 的功能生态系统。随着网络犯罪分子完善他们的攻击方法，他们将威胁到我们日常依赖的在线服务的稳定性。

以下是组织在 2023 年可以实施的几种工具和流程，以控制 API 安全风险:

*   **实现有效的反馈循环:**有效的反馈循环旨在帮助 DevOps 和 SecOps 团队协作并降低 API 安全风险，它不仅仅是一个好东西，它还是对抗复杂业务逻辑和对象级攻击的重要第一步。反馈环使组织能够简化应用发布工作流，使开发人员能够专注于提供最佳数字体验，并通过应用运行时的可见性和控制提供安全性。
*   自动化:这将是确保在开发生命周期的所有阶段都符合 DevSecOps 标准和实践的关键因素。自动化使 DevSecOps 团队能够快速承担更多的安全责任，包括自动化代码分析、合规性监控和威胁调查，从而确保保护能够跟上应用程序的变化。自动化安全测试工具的集成通常是第一步。例如，静态应用程序安全测试(SAST)和动态应用程序安全测试(DAST)工具可以在整个开发过程中使用。
*   **机器学习:**在区分恶意和正常 API 流量时，机器学习是一种有价值的资源，有助于促进大规模监控。否则，安全分析师只能尝试关联日志，并确定行为模式是否相似。由于许多针对 API 库的攻击来自自动化机器人，组织应该寻找一种统一的解决方案，使用机器学习来了解 API 流量，并检测和阻止恶意活动。

开发人员需要与安全团队合作，采用相同的敏捷思维来保护现代应用程序，跟上它们启动和发布的步伐。

API 是有动机的网络罪犯的完美目标，因为它直接通向数据存储，并且通常没有足够的防御措施来保护。当 API 被利用时，后果包括失去客户和合作伙伴的信任、潜在的合规风险和对底线的影响。这就是为什么大多数决策者和开发领导者应该将 API 安全性作为 2023 年的优先事项。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>