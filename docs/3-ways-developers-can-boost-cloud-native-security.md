# 开发人员提高云原生安全性的 3 种方式

> 原文：<https://thenewstack.io/3-ways-developers-can-boost-cloud-native-security/>

[](https://www.linkedin.com/in/timhinrichs/)

 [蒂姆·辛里奇

蒂姆·辛里奇是开放政策代理项目的联合创始人，也是 Styra 的 CTO。在此之前，他共同创立了 OpenStack Congress 项目，并且是 VMware 的一名软件工程师。Tim 花了 18 年时间为不同领域开发声明性语言，例如云计算、软件定义的网络、配置管理、web 安全和访问控制。他于 2008 年获得斯坦福大学计算机科学博士学位。](https://www.linkedin.com/in/timhinrichs/) [](https://www.linkedin.com/in/timhinrichs/)

过去，数据隐私和安全的责任落在非开发团队身上，如 IT、安全或合规团队。但这种情况正在改变。

由于采用了云原生技术和趋势，如[策略即代码](https://blog.styra.com/blog/what-is-unified-policy-as-code-and-why-do-you-need-it?utm_medium=pr&utm_source=the_new_stack&utm_campaign=awn&utm_content=blog)，开发人员比以往更加关注安全性。根据 [Styra 2022 云-原生一致性报告](https://registration.styra.com/2022_cloud_native_alignment_report.html?utm_medium=pr&utm_source=the_new_stack&utm_campaign=awn&utm_content=report)，超过一半的开发人员认为他们的组织应该在未来 12 个月内加强其数据隐私工作。超过四分之三(77%)的 IT 决策者同意这一观点。

这种注重安全的心态是一件好事。开发人员有机会在他们的组织内加强并帮助面向未来的应用内安全性。但这需要的不仅仅是正确的态度。

要实现真正的改变，开发人员需要遵循开发、安全和操作(DevSecOps)最佳实践，并采用正确的技术。

## **云开创了安全新时代**

开发人员对安全性的兴趣由来已久。谷歌[搜索数据](https://trends.google.com/trends/explore?date=all&geo=US&q=devsecops)显示，对“什么是 DevSecOps”和“DevSecOps vs. DevOps”等术语的查询最早出现在 2014 年，自 2017 年以来一直稳步上升。

云、微服务、容器化和 API 是这种新兴兴趣的原因。这些创新技术不仅改变了应用程序的构建和运行方式，还改变了安全方面的需求。在现代环境中，开发人员、工程师和架构师需要考虑数据隐私和安全性，因为当今的应用程序受益于将安全措施嵌入到离散组件中。

在云变得像今天这样无处不在之前，传统的网络安全依赖于基于边界的模型。防火墙和浏览器隔离系统等措施实质上是“包围”内部网络和系统。应用程序和数据是安全的，因为它们托管在物理隔离的基础架构上。在这种情况下，开发人员专注于应用程序的构建，而 IT 团队专注于安全性。

但是，随着组织开始其数字化转型之旅，IT 不能简单地围绕其技术环境建立壁垒。这种向云的转移打开了更多的攻击面，使网络安全更加复杂，并要求从一开始就建立安全性。与此同时，[微服务架构革新了软件开发](https://thenewstack.io/microservices-transformed-devops-why-security-is-next/)，让应用内安全性变得前所未有的重要。

在微服务出现之前，大多数应用程序都是由几个完整的代码块组成的。即使对一行代码的更改也会影响整个应用程序。但是今天，微服务允许应用程序被分解成数百个独立的软件片段。这些代码比以往任何时候都更加复杂，使软件团队能够在不影响应用程序其余部分的情况下进行频繁的更改。

这使得开发人员、IT 团队及其公司基本上有两种选择:1)利用微服务架构的优势，在应用程序中嵌入超粒度安全控制，或者 2)继续使用传统的分层安全控制，以孤立、被动的方式处理网络安全，我们知道这将带来更高的安全和合规性风险。

## **开发者提高应用内安全性的三种方法**

虽然[云](https://www.gartner.com/en/newsroom/press-releases/2020-11-17-gartner-forecasts-worldwide-public-cloud-end-user-spending-to-grow-18-percent-in-2021)和[微服务](https://www.itproportal.com/news/microservice-architecture-growing-in-popularity-adopters-enjoying-success/#:~:text=The%20%E2%80%9CMicroservices%20Adoption%20in%202020,businesses%20have%20now%20adopted%20microservices.)可能会为组织带来更多的漏洞，但开发团队的思维模式和授权的使用——控制谁和他们能做什么——可以帮助软件团队缩小差距。我亲眼目睹了组织如何通过改善授权状态来增强应用程序的安全性，我相信通过以下最佳实践，开发人员可以提高他们的授权技能并改善应用程序的安全性:

1.  **早谈安全，常谈**。无论软件规划和开发在您的组织中如何运作，做出改变永远不会太迟。与您的架构师和安全团队展开对话，了解您的组织如何从一开始就将安全性融入到应用程序功能中。
    通过在设计阶段纳入安全性，可以更容易地确定平台中何处可以广泛构建安全性，以及特定服务中何处需要构建授权。例如，通过一些预先考虑，您可以以一种使添加授权变得简单的方式来设计您的应用程序的 API。尽早并经常地讨论安全性可以帮助您开发一个在设计上零信任和兼容的应用程序。
2.  **规范知识和语言**。虽然授权相对简单，但是有许多语言和策略结构可供开发人员选择。没有标准化，软件团队很难协同工作、更新策略和扩展安全性。
    鼓励你的团队采用开源标准，如[开放策略代理(OPA)](https://www.openpolicyagent.org/) ，这是事实上的授权方法；SPIFFE，一种机器认证的健壮方法:和 Envoy，这是一种广泛采用的执行策略的网络代理。这些项目以及云计算原生计算基金会(CNCF)拥有的其他项目可以免费使用，并且可以结合使用，以帮助您在应用程序和基础架构中一致地实施授权策略。
3.  **创建一个框架。**[Styra 2022 云-原生一致性报告](https://registration.styra.com/2022_cloud_native_alignment_report.html?utm_medium=pr&utm_source=the_new_stack&utm_campaign=awn&utm_content=report)发现，大多数 IT 决策者和开发人员在由哪个团队管理各种政策、合规性和云安全责任的问题上意见不一。为了防止因缺乏一致性而导致的后果，如浪费时间和重复工作，或者更糟的是，责任缺失和易受攻击的云环境，需要建立一个策略生命周期框架。
    开发人员、产品经理、运营、安全和合规团队都致力于授权，一个框架将确保明确的责任归属、全面的明确预期和简化的工作流程。除了改进策略管理，框架还将使新员工和技术的加入变得更加容易。

随着越来越多的应用在云原生架构上设计、构建和部署，安全性对于开发人员的角色来说只会变得更加重要。开发人员和组织抵制 DevSecOps 思维方式的时间越长，他们最终需要做的就越多。

通过现在接受以安全为中心的思维模式并采用授权最佳实践，您的软件团队可以从开发生命周期的一开始就支持应用程序安全性、数据隐私和合规性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>