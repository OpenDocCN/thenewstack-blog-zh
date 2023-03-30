# Gravity 克隆集群以简化 Kubernetes 管理

> 原文：<https://thenewstack.io/gravity-clones-clusters-to-simplify-kubernetes-management/>

Gravity 的一款名为 [Gravity](https://gravitational.com/gravity/) 的新工具借鉴了虚拟化的快照概念，允许用户创建数千个相同的集群，以减轻设置和管理 Kubernetes 的痛苦。

“问题是 Kubernetes 的管理和 15 或 20 年前的服务器管理一样复杂，”gravity 首席执行官 [Ev Kontsevoy](https://github.com/kontsevoy) 说。

“Gravity 允许您拍摄群集的快照并创建数以千计的其他群集…它允许您创建群集、销毁它们并重新创建它们，每次群集启动时，安全性已经配置好，它已经强制执行了您公司的合规性…并且所有群集都是自我修复的，因此管理一个群集的成本等于管理一千个群集的成本。”

Gravity 允许用户拍摄 Kubernetes 集群的快照，包括所有应用程序和依赖项，并将其打包到一个文件中，该文件可以轻松安装到任何环境中。Gravity 还包括流行的开源特权访问管理解决方案 [Teleport](https://gravitational.com/teleport/) ，该解决方案整合了访问和记录整个集群活动的安全最佳实践，以满足企业合规性要求。

“你可以把它放在亚马逊、谷歌、你的私人数据中心、你的绝密实验室的地下室里。Kontsevoy 说:“你可以把它放在一个连互联网都没有的服务器房间里，叫做空气间隙。

“我们有运行 Gravity 的用户，他们需要在极度受限、极度封闭、高度合规、高度安全的环境中运行 Kubernetes。”

他说，公司倾向于使用内部拼凑的解决方案来解决跨不同环境运行许多 Kubernetes 集群的复杂问题，这既耗时又不安全。

Gravity 创建了跨部署的一致性，并允许团队远程管理集群的许多实例，即使这些实例位于防火墙之后。

Gravity 是开源的，有社区版和企业版。社区版可以从[引力网站](https://gravitational.com/gravity/benefits/cloud-native-applications/)下载。企业版允许您将 Gravity 与您的企业安全集成，包括基于角色的访问控制和跨许多集群的安全同步。它为您提供了跨多个集群的访问管理聚合。

在快照过程中，它:

*   提供完整的应用程序自省。
*   查找所有容器并删除其层的重复项。
*   打包所有必需的二进制文件。
*   添加具有基础架构要求的群集元数据。
*   将嵌入式 Docker 注册表添加到输出中。
*   重写所有要在嵌入式注册表外托管的图像。
*   输出包括用于远程管理的 SSH bastion 和 Kubernetes 网关。

输出是一个 tarball 形式的自包含映像，可以加载到 USB 驱动器上，并带到一个有空气间隙的服务器机房，以重新创建原始集群的完整副本。

它还通过特定于应用程序的挂钩自动升级，并提供回滚能力，具有全自动、逐步或手动模式。

虽然有些商店使用 SSH 安全协议，而其他商店只依赖 Kubernetes 协议，但 Gravity 允许您同时使用这两种协议，并使它们同步。

Kontsevoy 说，gravity 为甚至没有经验的 Kubernetes 用户提供简单性的方法可能不适合每个公司的口味。

“当我们提供一个集群的快照时，它以一种非常固执己见的方式提供，这是我们与 Kubernetes 一起使用的网络类型，也是一种安全措施。这些是我们认为的最佳实践。我们不允许用户调整每一个可用的配置设置。

“我们说，‘如果您信任我们的技术，开箱即用，就按原样使用它。’但是深层次的配置变化，他们是根本不允许的。…您得到的是完全自主的配置。集群可以自我运行、自我修复、自我管理。这对一些公司来说行得通，但最终对其他公司可能行不通，”他说。

“有一些不同的网络拓扑，不同的部署方式。…我们以牺牲灵活性为代价来实现简单性。”

专题图片:[安德鲁·马龙](https://www.flickr.com/photos/andrewmalone/)的[玉米糖排](https://www.flickr.com/photos/andrewmalone/2995097315/in/photolist-5yEE5T-9jhVFR-9jhTT4-9jm4iY-6bAHer-ds7iys-Tb8Bot-6E7mrg-2fDPvW-dLEjfa-cQwvUy-3wHsWs-7sbQLi-T5E167-5JBMbc-3fUVK-6514A5-5JC96t-23kdYEa-23sPtWb-23sPpD3-6cwZ85-sUidh-o7DAg4-23sPmLE-c8XhTb-nfnwyE-nQ3NbF-9MWaJV-6EbvM1-b4SEh8-7sfBQW-8Xt9Wo-7sbw9i-9UUBUf-UQXWh8-X3voyD-4UBfsR-VTXdgq-N4M72-8fEuzg-TBpo4Z-23j4C9b-258EuJo-ETwLgZ-9jm3xA-WamcWu-2aZnLwv-pCrasQ-eaEHcf)。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>