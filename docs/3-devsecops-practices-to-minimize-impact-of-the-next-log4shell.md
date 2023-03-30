# 3 DevSecOps 实践将下一个日志 4Shell 的影响降至最低

> 原文：<https://thenewstack.io/3-devsecops-practices-to-minimize-impact-of-the-next-log4shell/>

[](https://www.linkedin.com/in/ajaygandhi/)

[Ajay Gandhi](https://www.linkedin.com/in/ajaygandhi/)

[Ajay 是 Dynatrace 的产品营销副总裁。](https://www.linkedin.com/in/ajaygandhi/)

[](https://www.linkedin.com/in/ajaygandhi/)[](https://www.linkedin.com/in/ajaygandhi/)

Log4Shell 是许多组织的分水岭。尽管安全评论员多年来一直警告人们会发现类似的漏洞，但这让 it 界的许多人感到惊讶。

Log4Shell 是一个[零日漏洞](https://en.wikipedia.org/wiki/Zero-day_(computing))，如果设备或基于互联网的应用程序运行 Log4j 2(一个流行的 Java 库)的特定版本，则远程攻击者可以控制该设备或应用程序。

Log4j 2 库无处不在，其影响可能会持续数年，因为威胁者会继续寻找未打补丁的实例。但是危机时刻也带来机遇。这为将应用程序安全性和漏洞管理更深入、更全面地嵌入到 IT 和开发实践的结构中提供了机会。

这不仅仅意味着安全性必须“左移”——在软件开发的早期测试安全性。它要求团队左移右移——测试已经投入生产的软件的安全性。有了这两种策略，开发人员可以构建更安全的应用程序，而运营和安全团队可以确保软件在生产中不会暴露于任何新的漏洞。

这是 DevSecOps 的最佳状态，开发、安全和运营团队在整个软件开发生命周期中通力合作。为了实现这一目标，组织需要以智能、自动化的方式将可观察性和安全性结合起来。

## 【Log4Shell 教会了我们什么

我们现在都知道 Log4Shell 的故事了。该漏洞在行业标准常见漏洞评分系统上获得了罕见的 CVSS 10 分制评级，这不仅是因为它的普遍性，还因为它相对容易被利用，并使大量系统对远程代码执行攻击开放。除了漏洞本身，全球对该事件的响应也充分说明了组织目前面临的安全和运营挑战。

一个挑战是越来越多地使用第三方开源代码来加速软件交付。根据一项估计，全球开发者去年从四大生态系统(Java、JavaScript、Python 和. NET)请求了超过 2.2 万亿个开源包。同一项研究发现，29%的热门项目包含至少一个漏洞。随着软件开发速度的加快、上市压力的激增以及应用程序依赖性变得更加复杂，找到这些漏洞越来越具有挑战性。

另一个挑战是数字复杂性。研究表明，大多数组织在一个多云环境中运行他们的应用程序，平均来说[跨越五个不同的平台](https://www.dynatrace.com/info/cio-research-report/)。位于这些云上的微服务、容器和 Kubernetes 基础设施造成了复杂性，许多监控解决方案都无法管理这种复杂性。因此，组织发现安全团队被警报淹没了，而真正的威胁却在雷达下悄悄潜入。

Log4Shell 暴露了这些挑战的程度。为了提高对下一次重大事故做出快速有效响应的机会，组织需要能够快速回答三个问题:

*   我们受到影响了吗？
*   哪些系统受到影响？
*   我需要先解决哪些问题？

为了获得这种洞察力，他们需要更一致的 DevSecOps 文化。以下是增强 DevSecOps 的三种方法，以提高态势感知能力并缩短漏洞响应时间:

## **1。让安全成为共同的责任**

安全性很难得到保证，市场压力、云复杂性和开源库的日益流行使安全性变得更加困难。这使得典型企业的网络攻击面扩大到几年前的数倍。它还为潜在的严重漏洞提供了更多的机会，使其进入开发周期，并持续到生产中。Log4Shell 是这个问题的典型代表。因此，比以往任何时候都更重要的是，我们要把安全作为组织内的共同责任，而不仅仅是口头上的承诺。

“共同责任”通常被用来表示更大的董事会认同，或在员工行为变化的背景下，但它在 it 部门也同样重要。我们需要开发人员在构建安全产品方面变得更加熟练，但我们也需要确保生产中的应用程序继续安全运行。打破开发人员、运营和安全团队之间的孤岛将推动真正的 DevSecOps 实践。为了实现这一目标，组织应该围绕一个集中的平台来统一团队，为他们提供可见性和控制力。

## **2。弥合运行时漏洞差距**

当 Log4Shell 出现时，即使是具有严格和健壮的安全姿态并遵循最新的最佳实践和行业标准的组织也受到了挑战。这突出了分层安全模型中需要填补的空白:运行时漏洞管理。为此，组织需要能够实时观察生产中正在运行的内容，并识别可能影响客户的漏洞。

这只能通过可观察性和安全性的融合来实现，因此团队需要了解他们的应用程序如何映射在一起以及他们的依赖关系是什么。这种融合产生的智能使团队能够根据对敏感数据和客户体验的潜在影响，确定他们需要首先修补的软件的优先级。通过将可观察性和安全性数据整合到单个平台中，组织可以创建单一的事实来源，以推动开发、运营和安全团队之间的真正协作。

## **3。自动化和整合以减轻压力**

当今的开发、安全和运营团队已经达到了极限。复杂、高度分散的应用程序、快速的发布周期以及大量的常见漏洞和暴露(CVE)使得有效的手动响应几乎不可能。当平均每天有 [50 个新简历被记录时，团队不可能修补所有的东西。他们不能在将代码发布到产品中之前手动测试每一点。](https://www.redscan.com/news/nist-nvd-analysis-2021-record-vulnerabilities/)

这就是为什么自动化必须作为 DevSecOps 的一个关键支柱构建到漏洞管理和可观察性中。组织需要一种方法，可以在代码的整个生命周期中测试代码的安全性，否则像 Log4Shell 这样的问题总是会出现。通过将运行时漏洞管理与 IT 服务管理解决方案相集成，他们可以帮助开发人员和安全团队了解哪些任务应该优先处理，哪些错误应该首先修复。将自动化安全门嵌入预生产环境还将确保生产中消除的漏洞不会随着开发人员的不断迭代而重新出现。

幸运的是，像 Log4Shell 这样的漏洞并不经常出现。尽管如此，第三方开源库的使用越来越多，增加了将来出现类似漏洞的可能性。当它来袭时，世界将更加依赖软件，云基础设施将更加复杂，并且最有可能的是，it 团队将更加捉襟见肘。

这就是为什么现在采取将可观察性与漏洞管理相结合的方法是有意义的。这将有助于团队在问题进入生产之前自动解决问题，并优先为随后出现的任何新问题修补生产代码。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>