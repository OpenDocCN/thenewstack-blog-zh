# CNCF、Eclipse 探索 Kubernetes 驱动的物联网/边缘计算

> 原文：<https://thenewstack.io/cncf-eclipse-explore-kubernetes-driven-internet-of-things-edge-computing/>

Eclipse 基金会和云本地计算基金会[已经合作](https://blogs.eclipse.org/post/mike-milinkovich/k8s-edge-%E2%80%93-some-context-new-kubernetes-iot-working-group)创建了一个 [Kubernetes 物联网(IoT)/边缘计算工作组](https://github.com/kubernetes/community/tree/master/wg-iot-edge)。

随着物联网技术越来越多地被考虑用于工业云， [Eclipse Foundation](https://www.eclipse.org/org/foundation/) 的执行董事[迈克·米林科维奇](https://twitter.com/mmilinkov)说，“与 Kubernetes 合作的想法对双方都变得越来越有兴趣”。“随着时间的推移，人们有兴趣了解这一堆栈如何发挥作用。”

CNCF 有 29 个项目处于不同的成熟阶段，VMware 和 Siemens 等成员有兴趣研究 K8S 与物联网和边缘计算的协同作用。

[Eclipse 物联网工作组](https://iot.eclipse.org/working-group/)已经存在了六年，已经积累了跨越 [36 个项目](http://iot.eclipse.org/projects)的近 300 万行代码，得到了博世、红帽等 42 家公司的支持。米林科维奇说，这些组织的目标是成为“物联网的开源重心”。

例如，Eclipse 成员 Bosch 有超过 300 家工厂希望以云友好的方式进行管理，并且还希望将这项工作扩展到公司自己的客户。

博世正在领导的一个项目是 [Eclipse Hono](https://www.eclipse.org/hono/) ，该项目从可能多达数百万的终端设备进行大规模 MQTT 数据输入，将其转换为 AMQP，然后将其路由到关注来自该特定设备的数据的应用程序。Hono 跑在 Kubernetes 上面。

[![](img/5f98d0a77431b2c8998a76797ccbc41a.png)](https://www.eclipse.org/hono/)

“历史上，Kubernetes 一直非常关注请求-响应传输层的 HTTP 和 TLS，但当我们有数百万台设备”不运行这些协议时，我们该怎么办？米林科维奇问道。

在这种水平扩展的情况下，Kubernetes 可以提供一个标准化的控制平面，并管理边缘和混合云操作的应用。它可以用于管理一个或多个边缘计算部署。K8s 还可以管理多个物联网网关。

“当你开始谈论物联网的全部范围时，有如此多的用例和用户需求，以至于没有一种方法可以做到这一点，”米林科维奇说。

该小组将开展的第一项工作是确定一些通用术语，如“物联网网关”，以及对一些用户需求的共同理解。记录用例并建立一些参考架构也在待办事项列表中。

米林科维奇说:“为了实现我们需要的分布式计算基础设施，我们还需要一套通用的工具和一套通用的基础设施来帮助我们实现这一目标。”该工作组最初将着眼于核心 CNCF 技术，如 Kubernetes，但也扩展到其他潜在有用的技术，如 Linkerd 服务网格或 Prometheus 监视器。

该小组计划定期举行在线会议，在 Kubecon 等活动中举行会议，并促进对邮件列表的持续讨论。

云计算原生计算基金会和 Red Hat 是新堆栈的赞助商。

特征图片: [Imgflip 热图生成器](https://imgflip.com/memegenerator/135256802/Epic-Handshake)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>