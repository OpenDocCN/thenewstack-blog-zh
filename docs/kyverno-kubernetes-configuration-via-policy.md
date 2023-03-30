# Nirmata 的 Kyverno:通过政策的 Kubernetes 配置

> 原文：<https://thenewstack.io/kyverno-kubernetes-configuration-via-policy/>

kubernetes-管理供应商 [Nirmata](https://www.nirmata.com/) 已经开源了一个名为 [Kyverno](https://github.com/nirmata/kyverno/) 的项目，该项目使用户能够通过策略验证、变异和生成配置。

借助 Kyverno，集群管理员可以独立于工作负载配置管理特定于环境的配置，并为其集群实施配置最佳实践。

在企业中，有集群操作角色和几个使用 Kubernetes 的开发团队。

“凭借它提供的所有灵活性，您如何实施组织所需的配置管理和通用策略的最佳做法？Nirmata 创始人兼首席执行官[吉姆·巴格瓦迪亚](https://twitter.com/jimbugwadia?lang=en)说:“比如确保图像注册表是可信的注册表，确保为应用程序配置健康检查，配置资源配额，甚至根据环境设置改变现有配置。

对于突变，策略可以写成类似于 [Kustomize](https://github.com/kubernetes-sigs/kustomize) 的覆盖，或者写成 [JSON 补丁](http://jsonpatch.com/)。验证策略也使用覆盖式语法，支持模式匹配和条件(if-then-else)处理。

作为准入控制器，它检查传入的数据，并根据名称、类型或标签选择器检查数据是否与资源匹配。那么可以使用这些规则中的一个来改变配置、改变现有的配置或者验证现有的设置。

Kyverno 从 kube-apiserver 接收验证和变更许可 webhook HTTP 回调，并执行许可策略或拒绝请求。使用 Kubernetes 事件捕获策略实施。Kyverno 还报告了现有资源的政策违规情况。

以前在 Nirmata 本身的管理层中实现的策略引擎已经作为一个定制资源被移到 Kubernetes 中。它独立于 Nirmata 工作——与 [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) 或任何你想用于 CI/CD 管道的工具一起工作。

当最近在西雅图参加 ChefConf 2019 的人们正在讨论配置管理工具在 Kubernetes 世界中的[角色时，Bugwadia 将 Kyverno 称为配置管理管道中的最后一步。](https://thenewstack.io/chef-and-kubernetes-better-together/)

虽然有其他替代工具，如[开放策略代理(OPA)](https://www.openpolicyagent.org/) 、[北极星](https://github.com/reactiveops/polaris)和其他工具，但 Nirmata 团队希望做两件事:不仅仅是验证配置，而且能够在应用配置时更新和编辑配置。

“您可能只需要一个实例，但在生产中，您希望确保有多个副本在运行。诸如此类的东西，您可以快速地将这些策略定义为 Kubernetes 对象。这是一个 Kubernetes 资源，它遵循所有的声明式管理最佳实践，它有标签选择器、通配符…我们在执行策略时生成 Kubernetes 对象，因此资源所有者可以很好地了解正在发生的事情，”他说。

它也希望它是 T4 库伯内特斯土著的 T5。他坚持认为，其他供应商为其他用例创造了技术，然后试图将其应用于 Kubernetes。

策略是一组有序的规则，每个规则都有唯一的名称和可选的消息。每个规则匹配一个或多个资源，且属于单一类型(生成、变异、验证。)

“您可以检查您的 pod 配置是否有资源配额。它可以自动改变的东西，像存储类的基础上，你的集群设置；生成默认值，这对于安全性非常重要—当您创建一个新的名称空间时，您需要一组新的默认值。一旦制定了这些政策，我们就可以自动生成这些，”他说。

该项目的 GitHub 页面警告说，它仍在积极开发中，还没有准备好投入生产使用。

Chef 和 Nirmata 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>