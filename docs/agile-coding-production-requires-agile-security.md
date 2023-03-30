# 敏捷编码生产需要敏捷的安全性

> 原文：<https://thenewstack.io/agile-coding-production-requires-agile-security/>

[](https://www.linkedin.com/in/brianschwarz/)

 [布莱恩·施瓦茨

布莱恩是 Fortinet 应用安全产品总监。Brian 拥有 20 多年的企业网络和安全解决方案工作经验，主要负责 Fortinet 的 web 应用程序和 API 安全解决方案。](https://www.linkedin.com/in/brianschwarz/) [](https://www.linkedin.com/in/brianschwarz/)

组织投入大量资源开发新代码。有时代码是为了修复错误，有时是为了改善用户体验，有时是为了交付全新的功能。无论目的是什么，期望所有的努力都将为组织带来价值。但是，每当最新代码的部署被低效或过时的安全控制所阻碍时，组织的投资回报(ROI)就会减少。组织永远不应该以 ROI 的名义绕过安全控制，但是为了确保您永远不会陷入在两者之间做出选择的境地，我们实施这些安全控制的方式应该尽可能不增加部署流程的摩擦。

组织如何以一种更快地将代码投入生产的方式实现安全性，以便他们能够从最新和最棒的代码中获得全部价值？这是 2013 年的《[凤凰计划:一部关于 IT、DevOps 和帮助你的企业赢得](https://www.amazon.com/Phoenix-Project-DevOps-Helping-Business/dp/0988262592)的小说》中探讨的问题，作者花了很多时间讨论“在制品”或 WIP 的概念。WIP 的概念并不新鲜，但是“凤凰计划”*提出了减少 WIP 是成功开发的关键。减少 WIP 的一个关键因素是以最小化部署延迟的方式实现适当的安全控制。*

 *## **开发运维测试环境的常见挑战**

DevOps 团队修复问题，并努力为我们的用户带来新的功能，在将最新和最棒的代码投入生产的过程中，每一次延迟都会影响业务。开发人员的一个常见场景和痛点是，当他们将代码推入测试环境时，发现一些预先存在的安全控制与他们的新代码不兼容。这使得开发和安全团队争先恐后地进行必要的修改，以使代码正常工作。这些更改可能发生在应用程序或安全控件中，仅仅确定应用程序或安全控件是否应该更改就可能非常耗时。这些冲突在流程中暴露得越晚，解决的成本就越大，而且应该从人-小时和延迟的投资回报两个方面来衡量成本。

## **高级云安全可助一臂之力**

为了避免代码实现问题，安全性应该与每个组织的 DevOps 实践紧密集成，或者也称为 DevSecOps。这里有三个有用的提示:

1.  选择易于部署和管理的安全工具。我们面临的安全技能短缺不会很快消失，而且你不能指望你现有的开发团队已经拥有广泛的安全技能。寻找能够提供有效安全性的工具，但不要产生增加管理开销的误报。你只有这么多员工。部署正确的工具，以便最大限度地减少花费在劳动密集型策略调整和误报解决上的时间。有了合适的工具，您的团队将有更多的带宽来专注于更高价值的任务。寻找包含简化部署的工具的解决方案(例如，【FortiGate 的云形成模板)或者可以作为服务使用的解决方案(例如， [FortiWeb Cloud WAF 即服务](https://www.fortiweb-cloud.com/index/login))。
2.  选择能够让您在部署应用程序的任何地方保持一致的安全状态的工具。[现代企业网络多种多样，通常跨越多个环境](https://www.fortinet.com/blog/business-and-technology/integration-everywhere-adaptive-cloud-security-solutions-to-protect-all-environments)。如今，典型的企业通常在一系列私有数据中心和公共云中部署应用程序。您需要遵循您的应用程序和数据的安全解决方案，以便跨所有云提供一致、无缝的安全性和简化的操作。
3.  创建流程，使开发人员能够在将用于生产的相同安全配置中进行开发。利用 API 和自动化工具快速轻松地构建“生产级”操作环境。将“添加安全控制”留到流程的最后，会增加令人不快的突发意外的几率。不要让设置安全性成为让您的新代码停留在 WIP 状态的任务。

## **结论**

“凤凰计划”已经推出几年了，但它仍然是快速了解 DevOps 基础知识的很好的入门读物——令人惊讶的是，将其作为“DevOps 小说”进行介绍效果很好。如果我们的安全控制和流程将代码作为 WIP 保留太久，我们就会成为业务的障碍。安全不仅仅是做生意的成本；如果我们做得好，并且能够在不损害安全性的情况下实现快速代码部署，安全性就会成为一种业务推动因素和竞争优势。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*