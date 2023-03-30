# 软件供应链安全:拆除筒仓

> 原文：<https://thenewstack.io/software-supply-chain-security-tearing-down-the-silos/>

现在是做黑客的好时机。随着[云原生](https://thenewstack.io/category/cloud-native/)技术的采用继续以不减的速度增长，大量的漏洞和潜在攻击媒介很容易被入侵者利用。

Kubernetes[的特性——允许应用程序扩展、分布和共享——也在容器化的环境中创造了许多弱点。形成云原生环境的](https://thenewstack.io/category/kubernetes/)[容器](https://thenewstack.io/category/containers/)和[微服务](https://thenewstack.io/category/microservices/)的高度相互依赖的性质也意味着，在许多情况下，只需要一个漏洞或暴露的网络端口就可以导致整个网络的[中断和破坏](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/)。

攻击媒介之一是开发人员用来构建应用程序的开源代码，这些代码可能包含隐藏的漏洞。一旦部署完毕，每个 Kubernetes 集群都可能包含多个名称空间、受到不当保护的机密、大量互连的容器(具有多个依赖项)以及要监控的微服务和其他基础设施。

GitOps 的版本控制存储库(GitHub、 [GitLab](https://about.gitlab.com/?utm_content=inline-mention) 、Bitbucket)、整个[持续集成/持续交付(CI/CD)管道](https://thenewstack.io/category/ci-cd/)、云基础设施和 Kubernetes 集群本身也都在安全团队的关注之下。

换句话说，应用程序和基础设施安全性都是适当的云原生安全性所必需的，这两者都属于[供应链安全性](https://thenewstack.io/the-challenges-of-securing-the-open-source-supply-chain/)的范围。

针对应用程序和基础架构安全性，存在许多独立的工具和平台。然而，通常缺少的是一个可以作为单一来源或控制台来监控和管理整个供应链的单一平台。不仅应该合并应用程序和基础架构安全性，还应该消除分隔它们的管理的孤岛。

Palo Alto Networks 的 [Prisma Cloud 高级主管兼首席架构师 Barak Schoster Goihman](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention) 告诉新堆栈:“应用单一解决方案来管理整个供应链的安全性，包括 CI/CD、Git 和云部署，以便获得应用程序和基础架构以及云安全性所需的所有可见性，这变得绝对必要。

在融合应用和基础设施安全时，从生产周期一开始就实现自动化至关重要，这也是所谓的[“左移”趋势](https://thenewstack.io/shift-left-how-security-pros-should-prepare-developers-for-devsecops/)的原因。因此，正如 DevOps 团队所了解的那样，使用[策略作为代码](https://thenewstack.io/cloud-engineers-try-policy-as-code-to-cure-misconfiguration-woes/)，其中的代码定义并管理规则和条件，以便应用程序从一开始就遵循安全标准。

在本文中，我们不仅看到了为什么有必要将供应链安全的所有组件集成到一个控制台中，而且还提供了这样一个平台如何工作的示例。

## 为什么开发人员会成为安全的薄弱环节

开发周期的安全性在许多方面仍然是软件供应链中最薄弱的环节。这很大程度上与易受攻击、维护不当的开源代码有关，这些代码是开发人员正在构建的软件的一部分。

根据 Palo Alto Networks 的 Unit 42 使用 [Checkov](https://www.checkov.io/) (由 Palo Alto Networks 去年收购的公司 [Bridgecrew](https://bridgecrew.io/?utm_content=inline-mention) 创建的开源静态代码分析工具)进行分析的结果，在作为 code [Terraform](https://github.com/hashicorp/terraform) 存储库的受欢迎的基础设施的 4，055 个模板和 38，480 个文件中，63%的模板包含一个或多个不安全的配置，49%的模板包含至少一个关键或高度不安全的配置。

“任何人都可以在开源的 Terraform 知识库上发布一个模块，所有的 Terraform 模块都是开源的，可以在 GitHub 上获得，”[该报告称](https://www.paloaltonetworks.com/content/dam/pan/en_US/assets/pdf/reports/Unit_42/unit-42-cloud-threat-report-2h-2021.pdf)。

在报告引用的一个未具名的“大型 SaaS 供应商”的案例中，Unit 42 的一名研究人员在三天内发现了几个关键的软件开发缺陷，“这些缺陷可能会使客户面临类似于[网络安全管理软件产品](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/)和[卡西亚](https://thenewstack.io/kaseya-sera-whatever-will-be-will-be/)的攻击。”

该报告称，“总体而言，调查结果表明，许多组织可能仍会对云中的供应链安全产生错觉。”。

开发人员显然不希望在堆栈中引入漏洞，但是如果没有适当的工具(如策略即代码流程)来审查代码，并且随着以更快的节奏创建和提交代码的压力越来越大，一些开发人员可能会寻求冒险。

“不是开发者不关心安全，而是他们也不想成为安全专家，”[企业战略集团的分析师梅林达·马克斯](https://www.linkedin.com/in/melindamarks22)告诉新堆栈。“对于安全团队来说，开发人员将要做的许多事情最终都很难管理。”

开发人员通常会从商业供应商或开源代码库提供商那里寻找满足他们当时需求的最佳代码。

“开发人员将从他们需要的任何地方提取代码，他们可能会也可能不会遵循安全流程，或使用安全工具，如自动扫描仪等来确保它的安全，”马克斯说。

“然后，如果他们将代码投入使用，就很难判断它是否有缺陷。所以，很多都是基于配置的。”

Marks 说，如果没有适当的策略-代码和安全工具来检查代码是否安全，“如果开发人员必须为安全人员提交一张票来进行检查，将需要很长时间”。“如果这个过程需要很长时间来运行，并且打乱了他们的开发过程，那就不会发生。”

开发人员经常提交在持续集成过程的后期阶段才被拒绝的代码，例如当该代码已经被配置为 YAML 文件时。

充满漏洞的糟糕代码也可能被部署。在这两种情况下，如果没有自动化的工具和过程，一旦发现漏洞，通常要由开发人员来修复和重新提交代码，而不会出现漏洞——因此降低了生产率，因为开发人员的许多工作必须重做。

## 融合应用和基础设施安全性

将应用程序和基础设施的安全性合并到一个单一的平台框架下，是维护适当的安全性和避免开发过程中断的显而易见的解决方案。为此，帕洛阿尔托网络公司[发布了 Prisma 云供应链安全](https://thenewstack.io/palo-alto-networks-single-panel-provides-umbrella-security/)。

该公司表示，有了它，从生产周期的一开始就可以获得软件供应链中潜在漏洞或错误配置的完整视图，同时扩展到整个部署和部署后阶段。该平台通过将 Palo Alto Networks 的 Prisma 云安全产品与 Bridgecrew 的全面左移安全功能相集成来提供这一功能。

帕洛阿尔托网络公司 Prisma Cloud 的开发者倡导者 [Stephen Giguere](https://uk.linkedin.com/in/stevegiguere) 说:“一切都联系在一起，我们特别关注供应链，它可以是你的应用程序代码和安全基础设施代码。

对于安全团队来说，无论漏洞是在部署之后还是在开发过程中暴露出来，修复都是通过供应链安全自动完成的。自动发现允许使用内置扫描器提取代码资产并对其建模，并使用拉请求进行补救。

此外，从一开始代码库扫描就可以识别和修复应用程序代码中使用的开源包中的可怕漏洞。整个 [DevOps](https://thenewstack.io/category/devops/) 团队可以利用整个供应链的单一控制台图形可视化，涵盖应用和基础设施安全。

马克斯说，“这对整个供应链的安全意味着获得可见性，找到问题并快速修复它们。”

*Palo Alto Networks 和 Bridgecrew 的 Prisma Cloud 将于 3 月 23 日至 24 日举办 Code to Cloud 虚拟峰会，面向从业者。该活动将围绕结合开发和基础设施安全以及其他与软件供应链安全相关的主题展开讨论。您可以在此注册活动[。](https://start.paloaltonetworks.com/code-to-cloud-summit.html?utm_source=the-new-stack&utm_medium=blog)*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>