# 为什么开发人员应该学习 Kubernetes

> 原文：<https://thenewstack.io/why-developers-should-learn-kubernetes/>

[](https://www.linkedin.com/in/stevenjtidwell/)

[Steve tid well](https://www.linkedin.com/in/stevenjtidwell/)

[Steve 已经在科技行业工作了二十多年，从事过从最终用户支持到扩展全球数据接收和分析平台的各种工作，为一些最大的网络流媒体事件处理数据分析。他曾为多家公司工作，帮助他们改善运营和自动化基础设施。](https://www.linkedin.com/in/stevenjtidwell/)

[](https://www.linkedin.com/in/stevenjtidwell/)[](https://www.linkedin.com/in/stevenjtidwell/)

在基于容器的软件开发工作流的兴起的推动下，Kubernetes 作为部署这些容器的首选平台在最近几年得到了广泛的应用。

自 2016 年以来，[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)进行了一项年度调查，以评估各种工程组织对容器和云原生技术的采用情况。根据 [CNCF 2020 年调查](https://www.cncf.io/wp-content/uploads/2020/11/CNCF_Survey_Report_2020.pdf)的受访者，92%的公司在生产中运行容器，其中 83%的公司使用 [Kubernetes](https://kubernetes.io/) 作为他们的编排工具。

与此同时，许多组织也在采用 [DevOps](https://thenewstack.io/demystifying-devops-essential-building-blocks-of-a-devops-approach/) 和[站点可靠性工程(SRE)](https://thenewstack.io/no-sre-is-not-the-new-devops-unless-it-is/) 最佳实践来提高其应用程序的可靠性，并缩短交付新应用程序功能所需的时间。

由于这种采用，工程团队看到了合并操作和开发最佳实践的好处。运营团队变得越来越面向服务和软件，开发团队正在了解他们部署应用程序的平台和环境。

最近几年的重点是应用于操作最佳实践的软件开发，这导致了交付和可靠性的显著改进。但是有时，开发团队并不总是拥有在开发环境之外有效地使用他们的应用程序所需的操作技能。

虽然构建和运输容器化的应用程序可以消除维护独特开发环境的需要，但开发人员了解容器在运行时如何工作是至关重要的。尤其是在使用像 Kubernetes 这样的管弦乐队时，在制作中更是如此。开发人员可能不需要拥有完整的操作技能，但是他们需要学习足够多的关于 Kubernetes 和生产环境的知识，以便成为 DevOps 团队中可靠的参与者。

## 向左移动

随着 DevOps 和 SRE 的采用，在软件开发领域也有很多关于“左移”的讨论。其核心是，左移意味着在软件开发生命周期(SDLC)的早期关注问题检测和预防，以提高整体质量。更健壮、自动化的持续集成/持续交付(CI/CD)管道和测试实践是这种工作方式的最好例子。

左移也适用于运营最佳实践。从前，开发人员会编写他们的应用程序，然后交给运营部门部署到生产中。从那时起，事情发生了巨大的变化，旧的模式不再像以前那样工作了。

了解应用程序所在的平台至关重要。成功的工程组织努力确保开发和运营团队避免各自为政。相反，他们的目标是在软件开发生命周期的早期进行协作，以便编码、构建、测试和部署都被参与该过程的所有团队很好地理解。

开发人员不需要成为 Kubernetes 的专家，但是他们应该精通能够影响其应用程序性能的技能。CI/CD、生产部署、监控和了解 CPU、内存以及集群和 pod 运行状况等技能是应用程序难题的重要组成部分。

了解组织使用的应用程序平台和工具的一些基础知识对提高开发和运营效率大有帮助。拥有这些技能有助于开发人员更快、更有效地响应事件，从而在出现问题时无需升级到另一个团队即可解决问题。

## 开发人员和运营团队需要知道什么

开发人员和运营工程师都需要了解一些他们的同行所知道的事情。

*   与其他提供商相比，他们需要了解他们选择的云提供商的各种服务和功能的特点。无论云是公共云、私有云还是混合云，这些知识都适用。
*   他们需要认识到为他们的应用程序提供资源的财务影响，并从开发人员的角度理解如何降低成本和消除浪费。在云中构建新的环境和基础设施非常简单，这也意味着如果我们管理资源不当，很容易忘记这些成本会以多快的速度增加。例如，当策略设置不正确时，考虑自动扩展策略及其对成本的影响是一个好主意。
*   他们需要了解应用程序性能管理，尤其是用于分析和改进应用程序性能的工具和技术。
*   他们需要知道适当的事故响应技术，以便在事故发生时处理事故，并在适当的时候上报事故。DevOps 的一个基本原则是接受并找到减轻失败的方法，因此当事件发生时，高效和有效地处理事件是至关重要的。
*   他们需要在开发和操作围栏的两边建立反馈循环，以便所有团队都知道他们的工具或应用程序中的任何缺陷，以及开发人员可能如何纠正它们。工具和环境的共享所有权是鼓励这一点的一个很好的方式。

那么开发者具体应该了解 Kubernetes 的哪些内容呢？

*   他们组织的 CI/CD 系统如何工作，从概念到生产，从代码检入到构建、测试和部署。
*   kubernetes[pod](https://kubernetes.io/docs/concepts/workloads/pods/)以及它们与[容器](https://kubernetes.io/docs/concepts/containers/)的关系。
*   应用程序如何与 Kubernetes [网络](https://kubernetes.io/docs/concepts/services-networking/)交互，包括[服务](https://kubernetes.io/docs/concepts/services-networking/service/)、 [DNS](https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/) 和[负载均衡](https://kubernetes.io/docs/concepts/services-networking/)。
*   关于常用工具的知识，用于本地测试他们的部署和建模他们的应用程序如何部署，例如 [minikube](https://minikube.sigs.k8s.io/docs/) 、 [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) 、 [helm](https://github.com/helm/helm) 、 [kind](https://kind.sigs.k8s.io/) 和 Kubernetes [dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) 。
*   [监控、记录和调试](https://www.logdna.com/learn-kubernetes/logging-and-monitoring-kubernetes)集群和容器，以备出错时使用。

当然，运营和开发团队还可以了解更多关于他们如何一起工作的知识，但是这些都是很好的起点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>