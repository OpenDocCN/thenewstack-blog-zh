# 使 CI/CD 快速安全

> 原文：<https://thenewstack.io/making-ci-cd-fast-and-secure/>

[Twistlock](https://www.paloaltonetworks.com/prisma/cloud) 赞助了这篇帖子。

 [吐温·泰勒

吐温是 Twistlock 的客座博主，也是 Fixate IO 的撰稿人。他在谷歌开始了他的职业生涯，在那里，他参与了 AdWords 团队的技术支持。他的工作包括审查堆栈跟踪和解决影响客户和支持团队的问题，以及处理升级。后来，他建立了品牌社交媒体应用程序和自动化脚本，以帮助初创公司更好地管理他们的营销业务。如今，作为一名科技记者，他帮助 IT 杂志和初创公司改变团队构建和发布应用程序的方式。](https://cloudplatformonline.com/TNS-CI-CD-with-Kubernetes.html?utm_source=google&utm_medium=email&utm_campaign=FY18-Q3-americas-nurture-email-wd-icb_tns&utm_content=cicd&utm_term=tns) 

在 CI/CD 管道中，有许多工具在工作:像 GitHub 这样的代码库、容器注册表、构建自动化工具、测试自动化工具和部署自动化工具。每个部署中都有多个用户进行协作，包括多个开发人员、QA 和 IT 运营人员。还有多个环境，包括开发、测试、试运行和生产。

这些组件、用户和资源中的每一个都由标签和唯一标识符来标识。当这些用户、组件和资源中的每一个彼此交互时，事件发生，并且这些事件创建数据记录。所有这些标识系统各部分的数据以及整个系统中发生的事件一起构成了元数据。这是确保系统可见性的关键。

[Grafeas](https://grafeas.io/) 是一个元数据 API，它存储并帮助分析 Kubernetes 系统中生成的所有元数据。它是全面的，能够跟踪您使用的任何工具，并且足够灵活，可以考虑您添加到工具链中的任何新工具。它包括访问控制，以便您可以定义哪些组件和用户可以创建或修改元数据，哪些组件和用户只能读取元数据。通过以这种方式保护元数据，您可以放心地在对事件进行分类时使用元数据作为事实的来源。

元数据通常被视为无关紧要的信息。Grafeas 之类的工具正在改变这种状况，让元数据在监控和保护 CI/CD 管道方面发挥核心作用。这是在 CI/CD 周期的每一步实现持续反馈的方法。最好的一点是，这种反馈是自动的，它可以随着您的系统而扩展，并提供在任何给定时刻真实发生的事情的准确视图。在一个复杂的动态系统中，这种持续的反馈是必不可少的。

## 自动化安全策略

此外，Grafeas 与另一个名为 [Kritis](https://github.com/grafeas/kritis) 的工具配合使用，该工具允许您定义可以在系统上实施的安全策略。这些策略可以基于元数据。它们允许您定义规则，只允许授权用户将容器映像部署到生产环境中，或者确保自动阻止部署有漏洞的容器映像。

与 Kritis 类似，[准入控制器](https://kubernetes.io/docs/reference/access-authn-authz/admission-controllers/)是 Kubernetes 的一个特性，它允许您定义任意的策略来更好地控制和管理 CI/CD 流程。它有一个插件列表，可以拦截和管理对 Kubernetes API 的所有调用。准入控制器插件可用于强制限制特权容器可以执行的命令，或者确保任何请求都不会超过名称空间中设置的资源配额。准入控制器的应用程序很多，它们一起使管理员能够更好地控制在生产环境中运行 Kubernetes 集群的各个方面。

Kritis 和准入控制器都允许您对 Kubernetes 管理实施自动化策略。Twistlock】与谷歌合作支持 Kritis。Twistlock 利用 Kritis 的优势来支持其策略执行和图像扫描功能。

## 部署多个安全流程

在云原生计算时代，防火墙发生了变化。而不是外围的、无所不包的防火墙；容器化的应用程序利用粒度防火墙来保护单个服务。这些防火墙适应应用程序和网络的规模和复杂性，并通过策略进行控制。粒度分布式防火墙的好处是，即使一个防火墙被攻破，其他防火墙仍然安全。这提供了多层安全性。

采用这种方法的一个开源工具是 Project Calico。它实施基于策略的网络安全，将应用程序视为基于云的服务集合。它围绕每个服务创建微型防火墙，并以分布式方式保护它们。

[Twistlock](https://www.twistlock.com/) 通过使用其[云原生应用防火墙(CNAF)](https://www.twistlock.com/2018/01/25/enterprise-grade-cloud-native-application-firewall/) 和[云原生网络防火墙(CNNF)](https://www.twistlock.com/2017/09/29/cloud-native-network-firewall-twistlock-2-2-deep-dive/) 也采用了这种方法。CNAF 了解应用程序，并使用防火墙保护应用程序中的每项服务。同样，CNNF 适应分布式网络架构，并保护服务之间的通信，无论这些服务托管在何处——单个数据中心内还是跨多个公共云平台。

在容器的世界里保护 CI/CD 管道不是一件容易的事情。有许多方面需要考虑。通过采用动态安全实践和多重安全流程，您可以保护当今的云原生应用。无论是使用元数据和 Grafeas 等功能强大的工具，使用 Kritis 等工具基于元数据实施策略，使用准入控制器实施更加任意的策略，还是使用云原生防火墙保护应用程序和网络层，它们都是容器安全的基本要素。虽然工具是可用的，但它需要结合战术安全措施和现代云原生工具来提供云原生应用程序所需的安全性。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>