# Red Hat 的 OpenShift 4 增加了关键的核心操作系统功能

> 原文：<https://thenewstack.io/red-hats-openshift-4-adds-knative-key-coreos-features/>

使用容器进行应用程序开发和部署可以同时带来新的效率和复杂性。对于希望减轻这些复杂性的企业来说，托管和支持服务，如 [Red Hat OpenShift](https://www.openshift.com/) 可能是答案。本周在波士顿举行的[红帽峰会](https://www.redhat.com/en/summit/2019)上，红帽,[最近收购了流行的](https://thenewstack.io/turning-blue-ibm-to-acquire-red-hat/)[红帽企业 Linux](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux) 发行版背后的公司，推出了 Openshift 4，它在一份公司声明中表示，该系统已经“重新设计，以解决生产系统中容器编排的复杂现实”。

OpenShift 的最新版本“旨在通过推动各地 Kubernetes 部署的自动化更新，在混合云中提供类似云的体验”，并引入了许多最近发布的功能。OpenShift 4 新增了 [CodeReady Workspaces](https://developers.redhat.com/products/codeready-workspaces/overview/) ，这是谷歌基于 Kubernetes 的 [Knative](https://cloud.google.com/knative/) 无服务器框架的开发者预览版，基于 Kubernetes 的事件驱动自动缩放(KEDA)，结合了 Istio、Jaeger 和 Kiali 项目的 OpenShift 服务网格，以及操作符的一般可用性，这些都是在 OpenShift 3.11 的开发者预览版中引入的[。](https://www.redhat.com/en/blog/generally-available-today-red-hat-openshift-container-platform-311-ready-power-enterprise-kubernetes-deployments)

在接受新堆栈采访时，Red Hat 的产品战略总监 Brian Gracely 解释说，OpenShift 4 通常专注于增加简单性，同时扩展功能。

“客户要求我们简化在每个云环境中的部署、更新和部署新型应用程序，”Gracely 说。“对于我们来说，这是架构上的一大进步，它简化了运营团队的平台，并继续扩大了可以在 OpenShift 上运行的应用数量和应用类型。”

格雷斯利经常谈到让之前采用的功能成为 OpenShift 的“一等公民”，比如之前由 CoreOS 提供的操作功能，红帽[去年收购了该功能。在这一点上，Red Hat 宣布了 Red Hat Enterprise Linux CoreOS，这是 Red Hat Enterprise Linux 的一个特定于 OpenShift 的嵌入式变体，它提供了一个轻量级的、完全不可变的、容器优化的 Linux OS 发行版。然而，Gracely 指出，对于允许开发人员通过自动化生命周期以更简单的方法将有状态应用程序引入他们的工作中来说，操作符是真正重要的。OpenShift 4 将运营商带入了完整的成果，使他们成为架构的核心部分，并将](/red-hat-will-acquire-coreos-greater-kubernetes-presence/) [OperatorHub.io](http://operatorhub.io/) 嵌入到 OpenShift 平台中，提供了类似应用商店的功能。

“当您拥有复杂的、有状态的应用程序(数据库、队列服务、流服务、存储服务)时，启动并运行它们并围绕它们构建生命周期需要花费相当多的时间。Operator 框架说，让我们把所有那些你过去必须要有人类知识才能做到的事情，整理成代码，并使用这个自动化框架使它们变得可部署，”Gracely 解释道。“我们已经看到独立软件供应商生态系统的巨大吸收，认为这很好，因为我们现在不仅可以嵌入我们的应用软件，还可以嵌入运营第一天和第二天的运营需求，这些需求将在世界各地的每个 Kubernetes 环境中一致运行。”

CodeReady Workspaces 是今年早些时候发布的，它通过自动包含在基于 web 的 IDE 中编码、构建、测试、运行和调试容器化应用程序所需的工具和依赖关系，使开发人员更容易地处理云原生应用程序。

除此之外，OpenShift 4 还采取了几个步骤来确保它不管是云还是应用程序都可以工作。Red Hat 在一份声明中指出，OpenShift 最近已经突破了 1，000 个客户的门槛，它希望在未来几个月内为主要的公共云供应商提供“适应性和异构支持[……]，包括阿里巴巴、亚马逊网络服务(AWS)、谷歌云、IBM 云、微软 Azure、OpenStack 等私有云技术、虚拟化平台和裸机服务器。”Gracely 说，包含 Knative 也有助于这一点，因为“无服务器现在只是成为我们可以在平台上支持的另一种应用类型或模式。”

最后，在另一份声明中，Red Hat 还宣布了 Azure Red Hat OpenShift 的正式上市，该产品为 Microsoft Azure 带来了一个联合管理的企业级 Kubernetes 解决方案。这一声明伴随着 KEDA 的推出，该公司在一份声明中表示，“支持在 Kubernetes 上部署无服务器事件驱动的容器，在 OpenShift 中启用 Azure 功能”，并“允许通过 Red Hat OpenShift 在混合云和内部加速开发事件驱动的无服务器功能”。

红帽是新堆栈的赞助商。

图片来自 Pixabay 的免费照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>