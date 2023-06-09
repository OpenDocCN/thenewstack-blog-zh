# 为什么安全行业的工作负载保护全错了

> 原文：<https://thenewstack.io/why-the-security-industry-has-workload-protection-all-wrong/>

[](https://www.linkedin.com/in/tgonen/)

 [TJ 戈宁

TJ 是 Check Point Software Technologies 的云安全产品战略主管。他是云安全方面的主题专家，拥有数十年用创新解决方案解决企业问题的经验。在加入 Check Point 之前，他是 Protego Labs(已被 Check Point 收购)的联合创始人兼首席执行官。](https://www.linkedin.com/in/tgonen/) [](https://www.linkedin.com/in/tgonen/)

随着基于云的服务大大加快了应用程序的部署和持续升级，IT 安全在过去十年变得越来越复杂。但是，如果云让一切都快了一百倍，由于速度和复杂性，它也以同样的速度增加了对这些应用程序的威胁。组织报告称，他们的安全团队的规模不断扩大，以努力跟上发展步伐，但这更多地是由于保护云中应用程序工作负载的“旧世界”方法造成的，这种方法通常基于对[工作负载保护](https://www.checkpoint.com/cyber-hub/cloud-security/what-is-workload-protection/)实际上是什么的误解。

工作负载保护的概念在几年前由分析师首次推广，他们明确表示，通过云部署应用程序需要新的元素(如容器)才能发挥作用。此外，这些应用程序实际上可以变得无需服务器，存在于云基础架构的任何位置，具体取决于何时需要它们。这些元素以及应用程序本身被称为“工作负载”。因此，“工作负载保护”变得与解决容器和无服务器安全性的解决方案紧密相关。

问题是，许多安全团队已经采用了这种定义(并继续这样做)，认为工作负载保护只是拥有一个良好的容器和无服务器安全解决方案。他们经常忽视保护应用程序本身的需要，或者实际上忽视构成云部署工作负载的任何其他元素。

然而，企业最关心的是应用程序的质量和功能。无论是面向客户的 web 服务还是后端软件，它都不关心容器，也不关心应用程序如何分布在云的服务器基础设施上。但是当安全团队告诉他们工作负载受到保护时，他们通常谈论的不是应用程序本身。

尽管现在有了更准确、更全面的工作负载保护定义，例如，Gartner 现在使用术语“[云原生应用程序保护](https://www.checkpoint.com/cyber-hub/cloud-security/what-is-cloud-native-security/)”,但旧的定义继续在市场中制造不协调和混乱。这也部分是由于安全行业本身的原因；以及它将向客户推广和销售的产品进行划分的方式，这反过来又延续了 20-30 年前的本地思维模式。

当组织第一次向在线世界开放自己时，他们很快面临一系列对其数据和基础架构的新威胁。因此，安全公司涌现出来解决这些问题——首先向他们销售防火墙，然后是防病毒解决方案，最后是一整套分散的漏洞管理和威胁防御产品。随着攻击类型的增加，防御的种类也在增加。然而，在某种程度上，这种解决方案的激增变得难以管理，整合过程开始发生，从而导致更全面的安全方法。

然而，这种单点解决方案的思想在解决基于云的安全威胁方面一直存在，每个新元素—容器、无服务器等。—被视为要保护的单个攻击媒介，为每个解决方案分配了单个团队。所有这些都导致了安全部门的膨胀。考虑到 web 服务领域的快速发展，这是完全可以理解的——但是它有重复以前在内部部署中所犯错误的风险。

即使是那些了解工作负载保护不仅仅意味着容器和无服务器安全性的组织，也最终部署了单点解决方案来解决其他要素，例如配置策略和状态管理，以及应用程序安全性本身。但是，尽管这种零碎的方法在短期内理论上是可行的，但它既不高效也不可扩展——无论安全团队的规模有多大。正如在本地环境中一样，整合是唯一明智的前进方式。

最终，使用单点解决方案来正确管理云中的工作负载安全性是不可能的，因为(正如我已经提到的)云发展得太快了。在现实世界中部署和保护一个数据中心可能需要几个月的时间，但在云中启动一个数据中心只需一毫秒，如果只是一小部分配置出错，这种潜在的漏洞很快就会扩散开来。当问题在这种环境中出现时，试图手动修复是行不通的。云的速度和复杂性要求解决方案既全面又自动化。

一段时间以来，应用程序开发一直由自动化驱动，使 DevOps 团队能够几乎连续地将代码部署到同样自动化的云基础架构中。要使安全性在这种环境中真正有效，并作为一个整体解决方案发挥作用，它需要从一开始就存在于开发流程中，并在编码时将配置策略融入到应用程序中。实现这一点的唯一方法是通过自动化，指导开发人员始终生成安全、合规的代码，这些代码可以识别什么是正常的，什么是异常的，并自动对变化和潜在威胁做出反应，而无需人工干预。

在云中，整体的[工作负载保护](https://www.checkpoint.com/cloudguard/workload-protection/)解决方案是一个自动化的解决方案——没有其他可行的方法。如果不能自动化，它就不是一个解决方案。如果安全团队不想被管理其组织的 web 应用的任务完全淹没，他们需要与他们的 DevOps 团队合作，实施保护整个应用工作负载的解决方案，而不仅仅是特定于云的功能。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>