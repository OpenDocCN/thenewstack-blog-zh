# Etcd 可能是云计算基金会的下一个项目

> 原文：<https://thenewstack.io/etcd-may-next-project-cloud-native-computing-foundation/>

etcd key-value store 是 Google Kubernetes container orchestrator 的一个重要组件，可能是云计算原生计算基金会(CNCF)旗下的下一个项目。

临时 [CNCF](https://cncf.io/) 执行董事[克里斯·阿尼斯奇克](https://twitter.com/cra)在本周于加州太浩湖附近举行的 Linux 基金会 Linux 协作峰会的一次谈话中提到了 etcd 的考虑。

“Etcd 是下一条线，”Aniszczyk 承诺。技术委员会目前正在考虑接受这项技术，开源技术的现任管理者 CoreOS 似乎对这个想法很友好。CNCF 的技术监督委员会于本月早些时候成立，Kubernetes [很快成为第一个项目](http://blogs.cisco.com/cloud/cloud-native-computing-foundation-accepts-kubernetes-as-first-project)。

“像 [ZooKeeper、etcd 和 consult](http://technologyconversations.com/2015/09/08/service-discovery-zookeeper-vs-etcd-vs-consul/)这样的技术正在这个领域获得发展。这是一种常见的模式，这就是为什么我们认为 CNCF 应该有一个分布式键值存储，”CNCF 技术监督委员会负责人 Alexis Richardson 在 TNS 播客录制期间说道。

“而且咱们不要拐弯抹角。Kubernetes 依赖于 etcd，”理查森补充道。"如果 Kubernetes 在基金会，etcd 也应该在基金会."

[etcd 技术](https://thenewstack.io/about-etcd-the-distributed-key-value-store-used-for-kubernetes-googles-cluster-container-manager/)是一个[分布式键值存储](https://thenewstack.io/about-etcd-the-distributed-key-value-store-used-for-kubernetes-googles-cluster-container-manager/)。存储在 etcd 上的运营数据在多台服务器之间传播，因此如果一台服务器离线，etcd 集群中的其他服务器可以快速响应查询。“整个想法是要有一个关键的价值商店，是有弹性的机器故障，”飞利浦说。

飞利浦说，Etcd 旨在存储“真正重要的集群配置信息”。弹性键值存储是运行云原生应用所必需的。调度、DNS 查找、负载平衡或服务发现的信息对于集群来说非常重要，“您不希望一个人失败，也不希望这些信息不可读或不可写。”

飞利浦的 etcd 基于一份谷歌白皮书，描述了谷歌自己的、从未公开发布的、名为 [Chubby](https://research.google.com/archive/chubby.html) 的键值存储。etcd 随后被集成到 Kubernetes 中，以及由 Docker、CoreOS 和其他人开发的许多其他基于容器的技术中。 [etcd](https://github.com/coreos/etcd) 项目现在有超过 400 名贡献者和一些维护者。

“Etcd 是一个高质量的项目。写得不好的东西并不是全新的东西。它已经经历了多次迭代，并在战斗中证明了自己，”理查森说。

[CNCF](https://thenewstack.io/cloud-native-computing-foundation-seeks-clarity-world-container-confusion/) 于去年成立，旨在通过帮助协调正在开发的不同方法来减少云容器领域的[技术混乱](https://twitter.com/joyent/status/697549725319483392)。成员包括面向容器的创业公司，如 CoreOS 和 Docker，以及较大的 IT 公司，如 IBM、Red Hat 和 Cisco。

飞利浦指出，将 etcd 赠送给 CNCF 等第三方在很多方面都是有利的。一个组织将会是一个中立的牧羊人，这将有助于消除软件被一个有偏见的党派控制的疑虑。“竞争对手的参与并没有那么令人不快，”飞利浦说，并指出当该项目被接受时，Kubernetes 的版权就从谷歌转移到了 CNCF。

一个组织还可以处理所有的日常管理职责，如执行版权和注册域名。

CNCF 将给 etcd 带来的另一个好处是，它拥有由英特尔捐赠的 10，000 节点集群，可用于测试软件的新版本。理查森说，拥有这种资源“将大大降低测试成本”。

etcd 开发团队当然可以使用这个集群来帮助完成他们正在开发的新 API，通过更有效地使用 CPU 和内存来帮助已经非常快速的 etcd 更快地工作。飞利浦表示，需要一种新的 API，以便 etcd 可以使用谷歌开发的 gRPC(谷歌远程过程调用)，这是一种基于 HTTP/2 和协议缓冲区的新协议。Kubernetes 使用相当冗长的 JSON 来交换关键信息，所以这个新协议将大大加快交付。

思科、CoreOS、Docker、IBM、英特尔和 Red Hat 都是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>