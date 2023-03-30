# Etcd 数据库加入了云本地计算基金会

> 原文：<https://thenewstack.io/the-etcd-database-joins-the-cloud-native-computing-foundation/>

为世界上每一个 Kubernetes 集群提供动力的分布式键值数据库已经加入了 Kubernetes，成为由[云本地计算基金会](https://www.cncf.io/) (CNCF)管理的开源项目。

根据 CNCF， [etcd](https://coreos.com/etcd/) 将获得真正的厂商中立的自由，以及资金来采取额外的增强措施，如安全和成熟度审计，指出 etcd 的联合创始人[布兰登飞利浦](https://www.linkedin.com/in/brandonphilips/)，他是红帽的技术人员，也是 CoreOS 的前首席技术官，CoreOS[红帽今年早些时候收购了](/red-hat-will-acquire-coreos-greater-kubernetes-presence/)。

CNCF 在本周于西雅图举行的[kube con+CloudNativeCon 2018](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2018/schedule/)用户大会上宣布了这一最新项目。这是该组织承担的第 33 个项目。

CoreOS [在 2013 年首次发布了](https://coreos.com/blog/distributed-configuration-with-etcd.html) etcd，在 Apache 开源许可下，帮助该公司实现恢复能力和自动更新的总体目标，而不停机到关键的基础设施组件。etcd 是用 Go 编写的，基于谷歌对 Chubby 的规范，该规范是谷歌为管理自己的内部基础设施而创建的。使用 Raft 共识算法，Etcd 是一个分布式数据库，确保即使一个节点宕机，数据也将保持一致。

在 etcd 推出两年后，创建 Kubernetes 开源容器编排软件的谷歌工程师选择 etcd 作为集群信息的数据存储，使其成为云原生操作新兴架构的重要组成部分。谷歌在 2015 年向当时新成立的 CNCF 捐赠了 Kubernetes，以及该组织的种子资金，并在 8 月份完成了分离[。](https://techcrunch.com/2018/08/29/google-steps-back-from-running-the-kubernetes-infrastructure/)

经过 Kubernetes 在全球的部署，etcd 已经久经沙场，目前是 3.3 版本。自推出以来，[已经发布了 157 个版本](https://github.com/etcd-io/etcd/releases)，提交了近 15000 个，核心贡献来自超过 466 个人，包括来自所有主要云提供商的贡献，如亚马逊网络服务、谷歌和阿里巴巴。

飞利浦指出，除了 Kubernetes，etcd 还发现了其他用途。优步正在使用软件[存储普罗米修斯](https://eng.uber.com/m3/)收集的大规模配置数据。谷歌 Chrome 团队使用该软件来跟踪和管理来自各个证书颁发机构的证书。YouTube 的 [Vitess](/cncf-host-vitess/) ，也是 CNCF 的一个项目，使用该软件跟踪 MySQL 实例的多个碎片。

在这些情况下，用户希望“横向扩展他们的计算机基础设施，但是仍然有一些关键的信息需要集中托管。他们不想在一台机器停机时让自己的系统面临风险，所以这就是为什么你不使用 MySQL 或 Redis 来保存这些数据，”Philips 说。

CNCF 的母公司 Linux 基金会将管理及其[商标使用指南](https://www.linuxfoundation.org/trademark-usage/)，域名和账户将由 CNCF 管理。

核心开发小组已经在致力于 etcd 的未来增强，包括降级到早期版本的能力。Philips 指出，这是目前很少有数据库提供的功能，当在新升级版本的部署中发现错误时，这一功能非常有用。还将创建额外的工具来安装专门用于 Kubernetes 部署的 etcd 版本。红帽本身也将继续致力于 etcd 增强，飞利浦，如 [etcd 操作器](https://github.com/coreos/etcd-operator)协助安装。

云原生计算基金会、Kubecon + CloudNativeCon、Linux 基金会和 Red Hat 是新堆栈的赞助商。

特色图片:红帽的布兰登·菲利普斯。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>