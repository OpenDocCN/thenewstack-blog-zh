# 2018:Kubernetes 和互操作性之年

> 原文：<https://thenewstack.io/2018-year-kubernetes-interoperability/>

[](https://www.cloudfoundry.org/)

[Childers](https://www.cloudfoundry.org/)

[Childers 在大规模计算和开源软件方面已经花费了超过 18 年的时间。2015 年，他成为云铸造基金会的联合创始人，担任技术参谋长。他是 Apache CloudStack 的第一任副总裁，在 SunGard 领导企业云服务时，他帮助推动了该平台的发展，后来又在 Cumulogic 担任产品战略副总裁。在 SunGard 之前，他领导了包括 IRS.gov、USMint.gov、美林和 SEI Investments 在内的组织的任务关键型应用程序的重建工作。Chip 是 OSCON、LinuxCon North America、LC Japan、LC EU、ApacheCon、O ' Reilly Software Architecture Conference 等活动的资深演讲者。在空闲时间，奇普喜欢带着他的黑色实验室徒步旅行，驾驶双体船和太阳鱼，并试图跟上他年轻的女儿。](https://www.cloudfoundry.org/)

[](https://www.cloudfoundry.org/)[](https://www.cloudfoundry.org/)

2018 年将会是“云计算”的重要一年。

我预计有两大趋势将在 2018 年真正起飞:

1.  通过开源和跨开源的互操作性。
2.  围绕 Kubernetes 的标准化作为下一代基础设施抽象。

别急，细节来了。

就其本身而言， [Kubernetes 是一个伟大的故事](/category/kubernetes/)。更好的是它所推动的互操作性运动。在 Kubernetes 上实现可互操作的云原生应用的一个重要部分是[开放服务代理 API](https://www.openservicebrokerapi.org/) 。OSBAPI 支持跨产品和供应商的云服务的可移植性。这是一个跨多个组织的合作项目，包括 Fujitsu、Google、IBM、Pivotal、Red Hat 和 SAP，它使开发人员、ISV 和 SaaS 供应商能够为在云原生平台上运行的应用程序提供服务。2017 年，我们看到微软和谷歌采用了该 API。今年晚些时候，亚马逊和 Pivotal 合作，通过代理公开亚马逊的服务。红帽用它来支持 OpenShift 市场。

OSBAPI 是一个精心设计的 API，简洁中带着美丽。它得到了正确的抽象。经过几次迭代，抽象仍然保持强大，使 OSPABI 能够继续在使用中增长，并随着时间的推移而发展，最终变得更加强大。

围绕 OSBAPI 的宝贵生态系统是其成功的关键因素之一。许多财富 100 强企业都在使用 Cloud Foundry 应用程序运行时，它带来了一个实现 API 的生态系统。由于该技术解决了正确的问题，并且 API 是以正确的方式设计的，因此 Cloud Foundry 社区引入其他成员来帮助监督和管理 OSBAPI 是有意义的。有了一个更可寻址的市场，就有了一个更大的生态系统。OSBAPI 是正和游戏的一个很好的例子——在这个游戏中，每个人都是赢家，不会以他人为代价而有任何损失。

Kubernetes 社区对 OSBAPI 的接受是一个很好的证明。随着它被越来越广泛地采用，我们更加清楚地看到了多平台软件系统使用该 API 与后台服务对话的好处。我们围绕该 API 制定的目标即将实现。OSBAPI 最初是在 Cloud Foundry 社区中开发的，它本来是开放的，允许它发展，所以它在 Cloud Foundry 平台之外也很有用。其意图是，随着对使用它的支持越来越多，越来越多的竞争云提供商希望在它的基础上进行构建，并使用它来展示他们的能力。

一个很好的例子是谷歌、Pivotal 和 VMware 正在与 PKS 合作，其中包括连接到谷歌云功能，因此开发人员可以利用谷歌强大的机器学习功能。在 2018 年，你可以期待 OSBAPI 成为跨 Kubernetes 和 [Cloud Foundry 应用运行时](https://www.cloudfoundry.org/container-runtime/)发行版提供服务的标准载体。您还可以期望这种类型的互操作性不仅仅局限于服务。包括 CF App Runtime 和 Kubernetes 如何交互。下面会有更多内容。

## 作为下一代基础设施抽象的 Kubernetes

Kubernetes 正迅速成为消费基础设施的下一代方法。2018 年，这应该会成为一种必然。直到最近，IaaS 功能还是以虚拟机为中心的。Kubernetes——尤其是托管的 Kubernetes 服务——将消费者的交互从虚拟机转移到容器。结合各种努力，使 Kubernetes 的部署和管理更容易为企业数据中心(例如:Pivotal 和 VMware 的 Pivotal Container Service—[PKS](https://pivotal.io/platform/pivotal-container-service)—或 SUSE 的 Container-as-a Platform)，它开始看起来像一个普遍可用的基础设施 API。

Kubernetes 不是一个以应用为中心的平台。这是一个容器平台，可以用于许多不同的用例。如何构建或管理容器的问题是现在更重要的考虑因素之一。我们在 Cloud Foundry 社区中看到了一些不同的方法，他们找到了将 CF 应用运行时部署到 Kubernetes 上的方法，作为一个基础设施目标。现在生态系统中有几个选项，虽然我们不知道最终哪一个会胜出，但显然需要在 Kubernetes 集群中以一种管理良好的方式运行应用程序运行时。

尽管如此，还是有一些限制。虽然 Kubernetes 的简单性很美，但它并不完全像以虚拟机为中心的基础设施服务那样支持多租户，即使在同一家公司的客户中也是如此。但这是 Kubernetes 社区将随着时间的推移而改进的领域。

一个有趣的方法是 SUSE 的一个项目，它用 CF 应用程序运行时组件创建容器，并将它们部署到 Kubernetes 集群中。这有可能在现有的 Kubernetes 集群中提供一个轻量级的 CF 环境，并促进技术和社区之间的互操作性。

Kubernetes 的广泛使用意义重大，但需要注意的是:Kubernetes 的出现本身并不会改变您设计应用程序的方式。它所做的是提供一个基于容器的基础架构底层，这比过去以虚拟机为中心的基础架构有许多优势。然而，原生云不仅仅是容器。它是关于重新思考应用程序应该如何设计、部署和管理，以适应一个更加分布式的系统。

随着 Kubernetes 成为基础设施的新模式， [Cloud Foundry 应用运行时](https://www.cloudfoundry.org/container-runtime/)高度关注定制应用开发体验。两者都可以用于绑定到可以存在于多个云环境中的后台服务。开发经验和互操作性对每个人都有好处:用户、开发人员和开源社区。

今年，您可以期待看到这些技术与这些趋势一起汇聚，为“云原生”的含义创造一个更清晰、更有说服力、更完整的视图。

[云铸造基金会](https://www.cloudfoundry.org/)是新堆栈的赞助商。

由[约翰·汤纳](https://unsplash.com/photos/p-rN-n6Miag?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>