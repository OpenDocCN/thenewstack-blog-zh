# Solo.io 发布 Gloo Mesh 企业版，全面上市

> 原文：<https://thenewstack.io/solo-io-launches-gloo-mesh-enterprise-to-general-availability/>

经过几年[的开发和仅仅](https://thenewstack.io/supergloo-unifies-management-of-multiple-service-meshes/)[三个月的测试](https://www.solo.io/blog/gloo-mesh-enterprise-beta-release/)，Solo.io 已经[于本月发布了](https://www.solo.io/blog/gloo-mesh-enterprise-hits-the-ga-milestone/)Gloo Mesh 企业服务网格，标志着 API 的稳定性和一系列新功能，是为了响应测试期间的客户反馈而构建的。Gloo Mesh Enterprise 是该公司的企业级 Kubernetes-native 解决方案，可帮助组织安装和管理 Istio 服务网格部署。

虽然 Gloo Mesh Enterprise 可能刚刚达到这一里程碑，[solo . io](https://www.solo.io)CEO[Idit Levine](https://twitter.com/idit_levine)谈到大量未透露姓名的客户已经在生产中使用该产品，部署跨越 40 多个数据中心、1，200 个集群和 Istio 服务网格实例。

“当你以这样的规模跑步时，你需要做很多事情。这正是 Gloo Mesh 的用途。Gloo Mesh 基本上是在说，“爬，走，跑，飞。””Levine 说，他指的是该产品不仅能够帮助服务网格采用和安装的初始步骤，还能够帮助第二天的操作，并增加了处理复杂的多集群、多云、多区域部署的功能。

首先，Gloo Mesh Enterprise 为 Istio 的前三个版本提供了联邦信息处理标准(FIPS)合规性和长期支持，而不仅仅是 Istio 上游社区版本的最后一个版本。

从那里，Gloo Mesh Enterprise 通过该公司的 Istio 开发者门户[Gloo Portal](https://thenewstack.io/solo-io-launches-a-developer-portal-for-istio/)[添加了高级 API 功能，并促进了更高级的第二天功能，如回滚和委托。](https://docs.solo.io/gloo-portal/latest/)

它还让用户能够使用 WebAssembly 扩展他们的[服务网格部署，Solo.io 也为](https://thenewstack.io/webassembly-could-be-the-key-for-cloud-native-extensibility/)[提供类似 Docker 的体验](https://thenewstack.io/solo-io-promises-docker-like-experience-with-a-webassembly-hub-for-envoy-extensions/)。最后，Gloo Mesh Enterprise 通过为那些在许多位置运行许多集群的大型组织提供一个集中的管理和观察点，来协助那些最复杂的部署—这将是 Levine 提到的“飞行”。

[https://www.youtube.com/embed/ltdgT0t563o?feature=oembed](https://www.youtube.com/embed/ltdgT0t563o?feature=oembed)

视频

在测试计划期间，Solo.io 收到了超过 2000 个参与测试的请求，有 400 名开发人员参加了 Solo.io 测试版 Slack 频道。作为测试版计划反馈的结果，Solo.io 增加了[许多功能](https://www.solo.io/blog/a-technical-dive-into-gloo-mesh-ga/)，包括部署在每个集群上的 Istio 服务网格的单一玻璃视图、集中式流量管理和控制、全局服务路由和负载平衡、完全符合 FIPS 标准的 Istio 构建、跨多个集群使用 WebAssembly 扩展 Istio 的能力，以及集中式日志记录和调试。

“我想确保它是防弹的，并把它放在许多人的手中，”Levine 谈到 Gloo Mesh Enterprise 普遍上市的时间时说。“我们添加了许多企业功能。”

Levine 提供了另一个针对测试期反馈进行升级的例子。以前，Gloo Mesh Enterprise 可能要求拥有多个群集的用户授予权限，以允许它能够在每个群集上写入。这种凭证共享并不是最安全的方式，尤其是对于大型组织而言，因此 Gloo Mesh Enterprise 转向了拉模式，该模式使用每个集群上的代理连接到控制平面，以便更好地与大型多集群环境中的现有安全模式配合使用。

感兴趣的组织可以[请求 Gloo Mesh Enterprise 的免费试用](https://lp.solo.io/request-trial)，Solo.io 将在 3 月 23 日至 25 日的 SoloCon 2021 开幕式上提供围绕该产品和其他产品的会议和研讨会，届时 Levine 表示该公司还将发布一些公告。

凯西·霍纳在 [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>