# OpenStack 的新公共通行证计划可以启动联合云管理

> 原文：<https://thenewstack.io/openstacks-new-public-passport-program-kickstart-federated-cloud-management/>

在悉尼的 OpenStack 峰会上，OpenStack 推出了[全球 Passport 计划](https://www.openstack.org/passport)，这是一种企业通过使用 OpenStack 新 passport marketplace 中可用的免费增值类型包之一在公共云中测试 OpenStack 的方法。

该方法的想法是允许企业和机构试用提供 OpenStack 服务的公共云提供商。 [OpenStack Foundation](https://www.openstack.org/) 首席运营官[马克·科利尔](https://www.linkedin.com/in/markcollier/)宣布:“公共云工作组为此付出了巨大努力。

但是这项工作可以超越一次测试一片云的能力。“他们还在考虑未来的功能，以便更容易地在 OpenStack 公共云之间移动，”Collier 说。

换句话说，如果 OpenStack 的 passport 的“未来功能”转向同时开放其网络中所有公共云提供商的访问，而不是为客户提供尝试一个公共云提供商的机会，会怎么样？

> “基本上，联盟的核心思想是提供商‘拥有’客户”——Mariano Cunietti，EnterCloudSuite

EnterCloudSuite 的首席技术官 Mariano Cunietti 说:[EnterCloudSuite](https://twitter.com/mcunietti)是一家基于 OpenStack 的云提供商，提供全面的网络和云服务。在不久的将来，他设想一个新的联合公共云基金会，它可以来自 OpenStack 的合作伙伴，并为所有提供 OpenStack 服务的公共云提供商提供多个网关。

“如果 OpenStack 提供商能够联合起来，并能够在定义的边界内，在某个值得信赖的合作伙伴的基础架构上创建用户、租户和资源，会怎么样？如果小型提供商能够利用多区域、多可用性区域的全球超大规模提供商的可扩展性、弹性和可靠性，会怎么样？”库涅蒂问道。

### 联合云管理如何大规模扩展全球应用分布

Cunietti 举了一个需要运行不同类型工作负载的客户的例子。其中一些任务可能需要低延迟，以便对用户的请求做出快速响应。这些工作负载必须更贴近网络上的用户，然后由本地提供商托管。但是，作为一家媒体公司，该客户还要求每晚使用 1，000 个内核来对视频文件进行批量编码。该提供程序太小，无法容纳此重载，该请求将被拒绝，以支持大型超大规模提供程序。

如果有联合，提供商可以激活联合供应商(即另一个云公共提供商)上的资源池，以使用资源。供应商很高兴，因为这些资源被闲置，消耗电力而不产生收入。

现在，Cunietti 补充说，客户还需要在美国、远东和南美开展业务，而欧洲供应商并没有在这些地区开展业务。如果客户正式同意，供应商可以列出能够满足全球存在请求的外部联合供应商的区域。Cunietti 概述说，除了地理位置之外，其他特定需求的驱动因素可能是实例和存储的价格、电力成本、容量、某些功能的可用性或其他基础设施要求。

“基本上，联合的核心思想是提供商‘拥有’客户，但也可以表现为来自远程提供商的本地资源。计费是背对背管理的，合规性是通过让客户直接接受第三方供应商的 SLA 来管理的，”Cunietti 说。可以说，这种“合作竞争”可以改善“每个供应商的能力和上市时间。”

“我们已经看到，在设计、部署和迁移应用程序方面的直接支持是小型、熟练的提供商能够以快速、有效和廉价的方式提供的价值。客户更喜欢它:有时你需要一个教练来帮你，而不是一堆文件，”Cunietti 说。

### 联合云管理的工具集

随着最近 Docker 对 Kubernetes 编排引擎的支持，这一计划成为了“完美风暴”。一个标准终于在基础设施的较低层被定义，而 Docker/containerd 已经是上层部署的标准。现在可以实现多云，原生可移植性比以往任何时候都更近。”

OpenStack 在实现上一直饱受碎片化之苦。它生来就是被定制的，当用户从一个云迁移到另一个云时，它缺乏标准。

但现在是时候看看 [Kubernetes](/category/kubernetes/) 如何成为轻松运行复杂基础设施的基础了，在许多可用工具的帮助下实现这一点: [Helm](https://wiki.openstack.org/wiki/Openstack-helm) charts 和它的[单眼](https://kubeapps.com/) UI，例如，一个界面，它使选择库和将一切作为 Kubernetes 集群自动部署变得容易。

在这场风暴中，另一个关键组件是使 OpenStack 联盟可行的软件: [Sentinel](https://github.com/entercloudsuite/openstack-sentinel) ，OpenStack 的一个管理工具，由[马世民](https://www.linkedin.com/in/spjmurray/)与英国云运营商 DataCentred 合作开发，它允许一个提供商利用一个安全的代理，让另一个云提供商在其云中创建用户。

为了在联盟中赚钱，每个云提供商在公开 OpenStack 标准 API 时已经有了自己的 API 端点。Cunietti 表示，在这种系统下，可以很容易地明确列出每个最终客户的云使用情况，如果客户通过另一家云供应商访问服务，会计报告可以传递给最终客户开具发票。

cunietti——他的 EnterCloudSuite 是唯一一家完全欧洲化的开源提供商，由欧盟委员会数字部门 T10 聘请来管理 52 个机构的云基础设施——称之为“应用于云提供商的微服务”

Cunietti 表示，EnterCloudSuite 迄今为止的成功是因为他们理解(并接受)了云(无论是私有还是公共)是一种过渡，而不是转换:“我们不仅仅提供基础设施，它还是一个路线图。云是一段你必须走过的旅程，你不能跳跃，我们帮助你理解-或记住-你的业务是什么。”

如果云管理提供商被商品化，那么满足业务和本地需求的能力就是价值所在。

“我们都听说过这句老话，但我想说相反的话:立足本地，放眼全球，”库涅蒂说。

OpenStack 基金会是新堆栈的赞助商。

专题图片:让·法布尔雕塑“测量云的人”的照片，由马克·博伊德拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>