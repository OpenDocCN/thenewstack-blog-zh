# 利用共担责任模式提高安全性

> 原文：<https://thenewstack.io/harness-the-shared-responsibility-model-to-boost-security/>

当组织决定将其应用程序的工作负载转移到公共云提供商时，他们需要了解提供商分担了一些责任。换句话说，这一举措并不是一种“定了就忘了”的情况。组织需要考虑的领域包括:

*   软件或应用程序更新和补丁
*   安全问题(包括安全软件)
*   网络(包括策略和防火墙)
*   资源存取

除了资源管理之外，[共享责任模型](https://orca.security/resources/blog/cloud-security-shared-responsibility-model-problem/)有助于确保组织的基础设施配置正确且安全。为了保护您的应用程序和重要信息，您组织中的所有相关成员都必须知道根据共同责任模型谁负责什么。

## **了解共同责任模式**

在我们定义分担责任模型之前，让我们先来看一个简单的、现实生活中的类比，它可以用来说明这个模型。

我猜你可能在某个时候租了一套公寓或一间酒店房间。在这两种情况下，您可能希望管理层提供基本的安全性。你也可能意识到，你不能只是让你的窗户和门开着，并期望你的财产一直是安全的。此外，我相信你知道把你的车停在指定的地方并不能保护你不被偷，不出故障，也不会因为你没有支付停车罚单而被解雇。

同样的概念也适用于云提供商(类似于上述场景中的酒店业主或公寓经理)和使用其云技术的客户(类似于租户)。虽然这个场景说明了[共享责任模型](https://thenewstack.io/containers-break-the-shared-responsibility-model-between-cloud-providers-and-ops/)的基础，但是需要注意的是，责任可以根据您采用的基础设施服务的类型而转移。例如，您可以使用平台即服务(PaaS)、软件即服务(SaaS)、基础设施即服务(IaaS)或无服务器设置。

### **一切都是为了安全**

最终，共享责任模式完全是关于[安全性](https://orca.security/resources/blog/how-to-optimize-security-within-your-cloud-environment/)。组织需要知道谁负责什么，这个问题的答案取决于您是使用 IaaS、PaaS、SaaS 还是无服务器。下图将帮助您了解与您的设置相关的界限:

正如您在上面的图片中看到的，无论您使用哪种类型的服务，您都有责任保护您的应用程序。在这种情况下，您的信息、数据和端点都被视为应用程序的一部分。

这意味着，作为客户，您要对您的应用程序如何处理 SQL 注入、暴力攻击和类似事件负责。你也要对你的[密码在系统或数据库中的存储方式](https://orca.security/resources/blog/how-orcas-cloud-security-solution-detects-weak-passwords/)负责(无论它们是纯文本还是加密的),以及升级或修补你现有的编程语言版本。例如，当有更好更安全的版本可用时，继续使用 PHP 5 是不负责任的。

另一方面，云提供商负责提供和修补操作系统(至少如果你使用 PaaS 的话)，并负责使用最新版本的 [Kubernetes](https://thenewstack.io/kubernetes/) 。然而，组织仍然需要制定自己的工作流程来使用这些功能，例如选择允许组织安排更新的发布渠道。一些云提供商可能会“强制”更新(出于安全原因)，并为操作系统、Kubernetes 版本等设置终止日期。

以存储为例。云提供商提供存储(存档或易于访问的存储)。同时，客户负责保护数据(使用类似密钥管理服务的东西)和数据的可访问性。同样的概念也适用于其他资源，如虚拟化、服务器和网络。

## **结论:应用共同责任模式**

在云技术出现之前，组织完全负责自己的计算资源，从软件和硬件到外围设备，如电缆、配线架、电源，甚至建筑物访问代码。

有了今天的现代云技术，组织再也不用担心这些事情了。诚然，组织有责任保护其信息、数据和终端。然而，根据他们使用的基础设施类型(IaaS、PaaS、SaaS 或无服务器)，他们现在与其云提供商共同承担某些方面的安全责任。这种责任共享模式有助于保证您的云基础架构完全安全。

要了解更多关于云安全差距以及如何预防它们的信息，您可以下载 [Orca 的“2022 年公共云安全状况报告”](https://orca.security/lp/2022-state-public-cloud-security-report/)或注册免费的[云安全风险评估](https://orca.security/lp/cloud-security-risk-assessment/)。

**延伸阅读**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>