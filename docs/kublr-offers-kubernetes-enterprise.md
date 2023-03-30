# Kublr 为企业提供 Kubernetes

> 原文：<https://thenewstack.io/kublr-offers-kubernetes-enterprise/>

总部位于华盛顿特区的初创公司[kubrl](http://kublr.com/)坚持认为 [Kubernetes](/category/kubernetes/) 开源容器编排引擎仍未准备好迎接黄金时代，旨在减轻为企业设置和部署 Kubernetes 集群的痛苦。

“对于 Kubernetes 本身，您必须设置和配置很多东西。有了 Kublr，它就已经被设置和配置好了——备份、安全，所有这些事情你都必须让你的开发者去做。这涉及到大量的劳动力成本。市场总监[凯瑟琳·帕格尼尼](https://twitter.com/catherineoltrey?lang=en)说:“这些都是现成的。“对于许多公司来说，这是遥不可及的，因为他们没有能够设置它的人。”

Kubernetes 服务提供商不断增长的领域的一部分，包括 [CoreOS](https://thenewstack.io/coreos-takes-cloud-portability-tectonic-release/) 、 [Platform9](https://thenewstack.io/platform9-offers-developers-flexibility-todays-multi-cloud-world/) 、 [Distelli](https://thenewstack.io/distelli-manages-kubernetes-deployments-across-multiple-clouds/) 和 [StackPointCloud](https://thenewstack.io/stackpointcloud-makes-kubernetes-setup-3-step-process/) 。甚至[微软最近也发布了](https://thenewstack.io/draft-gives-developers-uplift-containerizing-apps-kubernetes/)一款新的开源 Kubernetes 部署工具，名为 [Draft](https://thenewstack.io/draft-gives-developers-uplift-containerizing-apps-kubernetes/) ，旨在减轻开发人员对 Kubernetes 的痛苦。

Kubernetes 的其他服务提供商似乎都有自己的利基，如 Kubernetes 之上的应用程序管理，据 Kublr 首席执行官 Slava Koltovich 说。Kublr 专注于企业的需求。最初由谷歌创建并作为开源项目发布， [Kubernetes](https://kubernetes.io/) 现在由[云本地计算基金会](https://www.cncf.io/)管理。

Koltovich 说:“我们的目标不仅是提供一个良好的界面来部署这些集群，或者像其他一些公司一样，尽可能多地部署云提供商，而是部署企业级 Kubernetes，使组织更容易管理它。”

## 附带利益

Kublr 源于定制软件开发公司 [Eastbanc Technologies](https://www.eastbanctech.com/) 的工作，该公司为客户创建了应用程序，如[哥伦比亚特区地铁政府](http://dc.gov/)、其[地铁运输系统、](https://www.wmata.com/) [、华盛顿邮报](https://www.washingtonpost.com/)和[红十字会](http://www.redcross.org)。

它之前为 API 管理开发了一个类似的产品。这家名为 [Apiphany](https://www.washingtonpost.com/business/capitalbusiness/eastbanc-technologies-sells-one-of-its-homegrown-start-ups-to-microsoft/2013/11/08/2e2b15ce-4700-11e3-bf0c-cebf37c6f484_story.html?utm_term=.c1803807e897) 的公司在 2013 年被卖给了微软。

母公司是容器的早期采用者，并为 Docker 和 Kubernetes 开源项目做出了贡献。Koltovich 说，Kublr 从与客户的合作中成长起来——它一遍又一遍地执行 Kubernetes 的任务。

“最初部署 Docker 时，流程编排来自手工编写的脚本。当集群技术可用时，我们正在试验 Docker Swarm 和其他技术。然后我们发现了 Kubernetes，我们认为它是公开市场上最好的集群管理平台。…主要是因为它的成熟，”他说。

然而，Kubernetes“仍然没有为企业的黄金时间做好准备。当你部署 Kubernetes 时，你需要注意一些安全问题，与云提供商有一定程度的集成，比如负载平衡。…"

因为 Kubernetes 仍然是一个新产品，所以仍然很难管理，他说。该公司认为其中一个问题是它不能在实现后就交给客户。

“如今部署 it 非常困难，尤其是当您考虑到所有的安全性[注意事项]、所有的策略、高可用性要求等时。这涉及到很多我们想要消除的工作，”他说，并将 Kublr 描述为一个集群管理平台。

## 附加奖金

Koltovich 说，Kublr 技术本身已经可以生产，但它仍致力于将其作为自助服务选项提供。

ku bler 首席建筑师 Oleg Chunikhin 解释说，ku bler 的核心是提供纯粹的 Kubernetes。它增加了在更复杂的拓扑结构中使用 Kubernetes 的方法。

虽然它没有改变 Kubernetes 本身，但它添加了一些模块，使其更适合企业，例如管理更复杂的拓扑结构、备份和恢复的方法，以及与不同身份管理系统的集成。

Koltovich 表示，Kublr 提供了一些市场上独一无二的功能，包括:

*   对多云混合、多网络部署的现成支持。“如果一个组织想要部署到美国东海岸的亚马逊，但他们有非常高的可用性标准，即使亚马逊数据中心停机，他们也不能停机。他们可能想在西海岸保留一份，也许在 Azure。它支持这种场景。通过一个非常简单的用户界面或配置文件和命令行，用户可以部署这种类型的 Kubernetes，”他说。如果组织正在从本地数据中心过渡，但不能一次完成，需要一段时间才能完成，或者需要在本地保留一些数据，它也支持混合部署。

*   它提供智能监控。Koltovich 解释说:“Kubernetes 本身在自我修复方面做得很好，但它产生了大量需要分析的数据，以便了解您的集群发生了什么情况。“这种分析需要当今许多组织都不具备的技能。我们做 Kubernetes 集群管理已经有一段时间了；现在，我们正在将这些专业知识打包到产品中，以便组织能够从中受益。我们获取这些 Kubernetes 数据，通过我们的知识引擎进行处理，为管理员提供健康[信息]和可操作的警报。我们清楚地定义了系统管理员必须做的事情。”

*   它还提供开箱即用的备份和恢复、数据和流量加密、证书、密钥和令牌管理等。

[最近的研究](https://thenewstack.io/parity-check-bright-grey-container-prediction/)表明了编排服务提供商的美好未来，这可能是 Koltovich 说 Eastbanc Technologies 计划保留而不是出售 Kublr 业务的原因。

在 [451 Research](https://451research.com/) 最近的一份研究报告中，79%的受访者[报告使用容器编排软件](https://thenewstack.io/parity-check-bright-grey-container-prediction/)。大约 52%用于生产，17%用于试验或用于测试/开发。

[云本地计算基金会](https://www.cncf.io/)和 [CoreOS](https://coreos.com/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>