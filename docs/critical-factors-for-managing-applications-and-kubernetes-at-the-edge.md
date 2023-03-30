# 管理边缘应用和 Kubernetes 的关键因素

> 原文：<https://thenewstack.io/critical-factors-for-managing-applications-and-kubernetes-at-the-edge/>

[](https://rafay.co/)

 [莫汉·阿特雷亚

莫汉·阿特雷亚是拉法系统公司产品和解决方案副总裁。他是一位经验丰富的产品专家，拥有 20 多年的经验。在 Rafay 之前，他曾在 Okta、Neustar、McAfee 和 RSA 担任高级产品管理职务。他获得了新加坡国立大学的工程硕士学位。闲暇时，莫汉喜欢和家人在一起，摆弄他的望远镜。](https://rafay.co/) [](https://rafay.co/)

由于网络提供的几个优势，商业正被推向网络的边缘。自动驾驶汽车、远程资产监控、医院内患者监控和工厂实时缺陷检测只是利用网络边缘的响应性能、可扩展性和降低延迟的业务应用的几个例子。

随着 5G 无线无处不在，以及越来越多的物联网(IoT)设备开始使用无线通信，数据量和数据速率也在不断增加。虽然这两个因素在某种程度上是独立的，但它们共同增加了对边缘应用程序的需求。

这种对速度的需求意味着，旧的中央数据库模型对来自各种来源的应用程序查询反应缓慢，现在正在被位于网络边缘的应用程序和数据所取代，在网络边缘，应用程序和数据可以快速响应大量的输入。支持这种流动的容器化的微服务应用必须在它们能够处理它的地方，这意味着它们也必须在边缘。

Kubernetes 是业界用于容器编排的首选工具，但是，当将容器移动到边缘时，会出现额外的 Kubernetes 管理复杂性。鉴于现在需要管理的集群数量以数百计，部署、安全性和设备管理流程都变得更加复杂。

考虑到这些限制和挑战，在边缘操作时，有几个 Kubernetes 管理注意事项非常重要，以确保您的应用程序确实是最先进的，而不是最前沿的:

*   **自动化部署:**手动将应用程序部署到数十或数百个位置是不可行的。自动化是一个需求，因为它是部署潜在的数千个应用程序以及分布式 Kubernetes 集群的唯一有效手段。GitOps 正在接管世界，它对 edge 来说也很棒。
*   **利用零信任安全:**边缘集群本质上是迷你云。计划在整个操作中使用零信任安全概念，以便使用标准的身份验证和授权过程来访问它们。如果操作得当，您可以利用公司的中央目录进行身份验证。此外，所有数据流都必须加密，以确保复杂的 Kubernetes 基础设施各部分之间的安全通信。
*   **实施集群蓝图:**考虑到需要管理的集群数量，以集中的方式创建和管理标准化的集群配置非常重要。否则，群集配置会随着时间的推移而变化，很快变得过于繁重而难以支持，或者不再符合内部策略和行业法规。
*   **操作“车队”而不是单个集群:**考虑到边缘集群的数量，一次执行一个集群的操作是不切实际的。组织应该能够为集群分配标签，并被允许跨整个集群执行批量操作。例如，(a)升级标签为“欧洲”的所有集群，或者(b)将工作负载部署到标签为“加利福尼亚”的所有集群
*   **利用多租户:**在一个扁平、单一的层次结构中管理数百个集群可能不切实际且操作繁琐。请考虑将集群组织到逻辑上隔离的操作域中。例如，美国西部的所有集群位于一个专用项目中，而美国东部的所有集群位于一个逻辑上独立的项目中。
*   **职责分离**:要运营具有数百种不同工作负载的大型集群，使用基于角色的细粒度访问控制实现明确的职责分离至关重要，这样开发人员就可以不受约束地(但经过审核)访问开发环境，而运营团队则可以管理整个集群。
*   **消费 Kubernetes 管理即服务**:管理集群很难；管理帮助您管理这些集群的解决方案也不容易。将 Kubernetes 管理产品作为一项服务来使用将会减轻您的团队的负担，否则他们将不得不承担仅仅是启动和运行支持基础设施的负担。

edge 通常被认为是一个“无服务器”的计算环境，但这种想法并不反映现实。让边缘变得有效的是，它将服务器和应用程序移动到更靠近需要的地方。将服务器及其应用和数据放在边缘也是一个纯粹的效率问题，可以带来更好的性能和更好的用户体验，我们尤其在零售和制造垂直行业看到了这种趋势。

考虑到需要管理的容器和集群的数量，这种效率带来了更高水平的管理开销。采取上述步骤可以使复杂的环境变得高效和安全，并释放 edge 应用程序所带来的所有希望。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>