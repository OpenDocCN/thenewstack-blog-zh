# Kyverno，一个新的 CNCF 沙盒项目，提供了 Kubernetes-Native 策略管理

> 原文：<https://thenewstack.io/kyverno-a-new-cncf-sandbox-project-offers-kubernetes-native-policy-management/>

[Honeycomb](https://www.honeycomb.io/) 正在赞助新 Stack 对 Kubecon+CloudNativeCon 北美 2020 的报道。

[Kyverno](https://kyverno.io/) ，由 [Nirmata](https://nirmata.com/) 打造的开源 Kubernetes-native policy engine，本周在沙盒级别加入了[云原生计算基金会(CNCF)](https://www.cncf.io/) 。开发团队希望该软件将有助于 Kubernetes 策略的采用，通过提供一种使用本地工具和语言的方法，而不是要求用户学习和采用新的工具和语言。

Nirmata 创始人兼首席执行官 Jim Bugwadia 表示，Kubernetes 政策的复杂性不仅与 Kubernetes 及其解决的问题的复杂性有关，还与其声明性有关。Kubernetes 的声明式方法允许用户声明一个预期的最终状态，然后 Kubernetes 试图匹配，这是它的优势之一，他说，但这也导致了这种复杂性。

Bugwadia 解释说:“由于 Kubernetes 中配置管理的声明性，有许多细节需要指定。“对于每种配置，API 中都有数百个参数。挑战就来了，特别是如果你是一个企业，你想让你的团队配置什么？应该集中管理什么团队配置？您如何确保您的团队遵循最佳实践？诸如此类的事情需要集中管理。需要有审计和报告。这就是为什么策略引擎对 Kubernetes 如此关键和重要，尤其是对企业用例而言。”

Kyverno 使用 YAML 或 JSON 来完成这项工作，与 Kubernetes 的方式非常相似，并且依赖于熟悉的工具，如 [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) 、 [git](https://git-scm.com/) 和 [kustomize](https://github.com/kubernetes-sigs/kustomize) 。Bugwadia 解释说，相比之下，CNCF 的另一个项目 [Open Policy Agent](https://www.openpolicyagent.org/) 要求用户使用减压阀，这是一种定制的“强大的”语言，“但同时，它学习起来很复杂，管理起来也很复杂，我们发现，当我们与我们的客户和 Kubernetes 管理员交谈时，他们希望使用相同的 Kubernetes 原生模式，相同的定义和管理资源的方式，以及他们喜欢的所有工具。”

根据一份声明，Kyverno 不仅帮助创建策略，还执行“准入控制”，其中 Kyverno“作为一个验证和变异的 webhook 运行，与 Kubernetes API 服务器一起提供配置安全性，并阻止无效和不符合要求的配置”。Bugwadia 指出这一点，以及其变异和生成策略的能力，是该项目的突出特点。

Bugwadia 说:“Kyverno 还可以改变资源，也可以动态生成资源，这允许您进行非常细粒度的配置管理，这是手动不可能做到的。“有了 Kyverno，您可以自动化这些用例。例如，我们的一些客户正在使用 Kyverno 将证书自动安装到 pod 中，甚至可以生成边车容器。所有这些现在都可以自动化，设置为策略，然后从那里开始基本上是自动驾驶的。”

Bugwadia 表示，他们希望 Kyverno 可以帮助大幅增加 Kubernetes 策略的广泛使用，由于其复杂性，目前很少采用该策略。

“今天，在应用安全策略方面往往存在许多挑战。Bugwadia 说:“一些调查显示，只有 10%到 15%的 Kubernetes 用户只是因为复杂性才考虑应用策略。“我们发现有必要改善 Kubernetes 的整体安全状况，以及企业内部的合规水平。我们希望利用默认策略，将 Kubernetes 用户的比例从 10%提高到 90%以上。”

展望未来，Kyverno 项目还希望与其他 CNCF 项目合作，如另一个新的 CNCF 沙盒项目 [cert-manager](https://cert-manager.io/docs/) ，Bugwadia 表示，该项目已表示有兴趣将 Kyverno 用于证书管理政策。

加入 CNCF，他说，导致这些形式的合作，这是我们无法做到的。

Gerd Altmann 通过 Pixabay 提供的特写图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>