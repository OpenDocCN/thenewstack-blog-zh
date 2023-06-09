# 2023 年云原生测试趋势

> 原文：<https://thenewstack.io/cloud-native-testing-trends-for-2023/>

随着云原生软件开发的不断发展，遵循 DevOps 工作流进行测试的重要性变得更加明显。在底特律的 KubeCon + CloudNativeCon，我有机会与数百名 DevOps 工程师接触，了解他们最新的测试方法。

随着 Kubecon 2023 Europe 于下个月推出，我想分享一些我在与 DevOps 工程师交谈时观察到的在云原生环境中进行测试的趋势。

2023 年，我们将看到组织采用新的云原生技术，同时升级他们的基础架构，特别是正在过渡到 Kubernetes 和 GitOps 的公司。一个突出的测试趋势是向更多集成测试和更快自动化的转移，预计将在 2023 年主导云原生测试领域。

## 在云原生环境中测试的挑战

在云原生环境中进行测试可能具有挑战性，因为它涉及跨多个平台和服务的测试，使用一组不同的工具，这些工具在不同的团队和工作流中可能会有很大的差异。云原生应用的分布式特性意味着测试必须在更大的规模上进行，需要测试更多的组件。

DevOps 团队还必须考虑底层基础设施对测试的影响，因为基础设施的变化会影响应用程序的行为。为了克服这些挑战，组织正在采用云原生测试策略，该策略将自动化和测试集成到开发过程中。

## 公司正在做更多的集成测试和自动化测试工作流程

Kubernetes 和云原生软件的兴起极大地增加了需要测试的组件数量。随着微服务架构越来越流行，测试单个代码单元(单元测试)已经不足以确保应用程序的整体性能和可靠性。集成测试，即结合多个单元并根据规范评估系统的性能，变得越来越有必要。

在拥有更多资源的更成熟的组织中，集成测试已经成为规范，但是手动集成测试可能是耗时和资源密集型的。今年，基于我们去年看到的趋势，我预测集成测试实践将继续向完全自动化转变，将公司从仅仅进行单元测试提升到更加敏捷，同时进行集成测试。

## DevOps 将更多地参与测试和测试自动化

随着组织转向云原生测试，DevOps 工程师在测试中的角色变得越来越重要。DevOps 不仅仅是自动化软件开发，还包括自动化测试和部署过程。

DevOps 工程师越来越多地掌握测试的所有权，像 [Testkube](http://testkube.io) 这样的工具可以帮助他们轻松地将测试集成到他们的工作流程中。通过采用协作测试方法，DevOps 工程师可以确保在整个开发生命周期中完成测试，从而降低错误进入生产环境的风险。

## 公司将实施更持续的测试策略

持续测试是一种测试方法，包括早期测试和整个开发生命周期的测试。通过采用持续的测试策略，组织可以确保在整个开发过程中完成测试，从而降低错误进入生产环境的风险。

持续测试也允许组织在开发过程的早期检测和修复错误，减少了错误修复的时间和成本。通过采用持续的测试策略，组织可以提高软件开发过程的速度和质量，从而加快上市时间并获得更好的用户体验。

## 拥抱现代的云原生测试

为了引领测试创新，在 [Kubeshop](https://kubeshop.io/) 我们开发了 [Testkube](http://testkube.io) ，目标是让所有类型的测试云本地化，让开发运维团队更加轻松。这些不同类型的测试包括:

*   **负载测试:**使用像 K6、Jmeter 或 cannon 这样的工具
*   **API 测试:**使用 Postman、SoapUI、银杏等。
*   **前端/端到端测试:** Cypress，剧作家
*   **通用:基于 Java、Golang、Python、Javascript 的测试。**

只要可以在 Docker 映像中运行，任何测试都可以使用 [Testkube](http://testkube.io) 进行云原生测试。

由于它将测试流程编排和执行直接集成到 Kubernetes 中，并将测试工作流程从 CI/CD 管道中分离出来，因此与网络访问、自动化、配置和管道设置相关的挑战变得不再是问题。

[Testkube](http://testkube.io) 简化了测试流程，使 DevOps 团队能够在他们的 K8s 集群中快速轻松地运行集成和自动化测试，这与传统的 CI/CD 管道和更现代的 GitOps 工作流都很好地配合。有了 Testkube，您不必重新编写或调整您现有的测试来开始，只需将它们集成到您当前的测试过程中，无缝升级到集成测试。

## 结论

在现代软件开发中，开发和测试是不可分割的。随着云原生技术的不断发展，DevOps 团队必须采用新的测试实践，以确保其应用程序的性能和可靠性。

通过采用现代的云原生测试方法和使用类似于 [Testkube](http://testkube.io) 的工具，DevOps 团队可以简化他们的工作流程，并在当今快节奏的软件开发环境中获得竞争优势。

加入我们的 [Discord 社区](https://discord.gg/hfq44wtR6Q)或在我们的 [GitHub Issues](https://github.com/kubeshop/testkube/issues) 页面上创建功能请求，了解更多关于 Testkube 的信息，以及它如何帮助您的团队实现云原生测试。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>