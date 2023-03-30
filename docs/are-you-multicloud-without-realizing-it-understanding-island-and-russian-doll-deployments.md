# 你是多重云吗？了解“岛屿”和“俄罗斯娃娃”部署

> 原文：<https://thenewstack.io/are-you-multicloud-without-realizing-it-understanding-island-and-russian-doll-deployments/>

[](http://mist.io/)

[Chris PS altis](http://mist.io/)

[Chris PS altis 是 Mist.io 的联合创始人兼首席执行官，mist . io 是一个开源的多云管理平台，为组织提供了一种现成的方法来使多云可管理。他的背景是计算机视觉和机器学习。他热爱开源、Python 和解决问题。在创办 Mist.io 之前，Chris 做过研究员、软件工程师和项目经理。](http://mist.io/)

[](http://mist.io/)[](http://mist.io/)

不幸的是，在业界，多云是一个定义模糊的术语。有一些用例是明确的多云设置——例如，在亚马逊网络服务、谷歌云平台和 Azure 中同时运行。但也有很多灰色地带——多云和混合云之间的界限在哪里？两者在功能上有什么区别？

在 [Mist.io](https://mist.io/) ，当我们考虑多云及其给部署带来的复杂性时，我们实际上并没有考虑供应商或公共云提供商的数量，而是考虑我们使用单一 API 管理整个部署并在一个位置获得部署全局视图的能力。这意味着一个组织甚至可以在一个云提供商上获得类似多云的体验。

我们看到了两种部署模式，一种称为“孤岛部署”，另一种称为“俄罗斯娃娃部署”，这两种部署模式的行为都非常像多云，即使只涉及一家云提供商。这两种模式都涉及在单个云上的部署，但仍然需要单独的管理，并且最终会有许多与在多个公共云提供商中运营相同的复杂性。大多数使用孤岛部署或俄罗斯玩偶部署的用户几乎肯定不会说他们正在使用多云，但他们必须处理许多在多个公共云环境中的人会遇到的问题。

以下是关于这两种部署模式的更多信息，组织使用它们的原因以及它们带来的复杂性。

## 岛屿部署

许多组织将其工作负载划分到如此程度，以至于它们本质上是不同的云。API 调用可能是相同的，但是有不同的帐户、不同的用例、不同的人连接到每个云并运行不同类型的工作负载。

如果您有三个完全独立的 Kubernetes 集群，一个用于生产，一个用于暂存，一个用于开发，您是在多个云中还是在单个云中？

在另一个例子中，OpenStack 用户很少升级旧的部署，因此，最终使用多个版本的 OpenStack。当您考虑到他们可能为每个版本的 OpenStack 提供生产、试运行和开发环境时，OpenStack 的安装数量很容易达到两位数。那还是一片“云”吗？

每个 AWS 区域都有自己的区域 API 端点，您不能在一个 API 调用中管理不同 AWS 区域的所有资源。那么，如果你有多个 AWS 区域，你是多云吗？

虽然这些场景不符合“多云”的通常定义，但它们存在许多相同的挑战，例如缺乏集中管理和可见性功能。如果您采用这种“孤岛”方法，您可能在技术上不是多云，但您管理云环境的实际体验将更类似于多云方法，而不是单个云环境。

## 俄罗斯玩偶云

这在裸机云中更常见，但也适用于任何支持嵌套虚拟化的公共云。例如，我可以创建一些 AWS 实例，然后在这些实例上安装 OpenStack。在 Mist.io，我们正在用 [Equinix Metal](https://metal.equinix.com/?utm_content=inline-mention) 做类似的事情。我们从 Equinix 获得裸机，然后在其上安装 [VMWare vSphere](https://tanzu.vmware.com?utm_content=inline-mention) ，然后是 OpenStack 和 Kubernetes。我们需要所有这些环境，这样我们可以测试我们的集成，我们使用这个环境进行测试和 QA。

这是一朵云吗？还是四个？我们只有一家供应商，但是在该供应商提供的基础上还有许多环境。仅仅因为一切都依赖于裸机并不意味着我可以从单个 API 端点控制所有的环境。

大多数拥有“孤岛”或“俄罗斯娃娃”部署的人会说他们不在多个云中。但这并没有考虑到这些类型的设置会有多复杂，以及它们与多种云环境的情况有多相似。在跨环境可见性、管理和控制方面也存在类似的挑战。

当讨论在多云环境中运行的挑战和复杂性时，重要的是要记住，一些应用程序架构，即使是在单个云中，也会出现许多与真正的多云部署相同的问题。这也是为什么看待多云的最佳方式不是简单的“是/否”,而是一个光谱，有些架构是“纯粹的”单一云，有些显然是多云，而许多则处于两者之间的灰色地带。这样做不仅有助于组织更成功地进行真正的多云部署，还有助于他们在单一云上进行嵌套和/或高度分段的部署。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>