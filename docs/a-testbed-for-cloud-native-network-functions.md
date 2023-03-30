# 云本地网络功能测试平台

> 原文：<https://thenewstack.io/a-testbed-for-cloud-native-network-functions/>

在一个充斥着首字母缩略词的公告中，一个新的测试平台可用，用户可以在 Kubernetes 上比较云本地网络功能(CNF)和 OpenStack 上的虚拟网络功能(vnf)。

这是云本地计算基金会(CNCF)和 Linux 基金会的 [LF 联网](https://c212.net/c/link/?t=0&l=en&o=2383771-1&h=1756977902&u=https%3A%2F%2Fwww.linuxfoundation.org%2Fprojects%2Fnetworking%2F&a=LF+Networking) (LFN)项目之间的合作。

Linux 基金会去年 9 月宣布，LFN 正式与 CNCF 合作，支持将 VNFs 迁移到 CNFs。(看到了吗？)

“CNFs 正在成为未来的网络架构，其原因与 containers 和 Kubernetes 正在成为企业计算的标准平台一样，”CNCF 执行董事[丹·科恩](https://twitter.com/dankohn1?lang=en)在一份声明中说。“我们很高兴能继续与 LF Networking 合作，为电信公司及其供应商提供一种在 VNFs 和 CNFs 之间进行可复制比较的方法。”

它坚持认为，用户将发现 CNFs 在成本、弹性和开发速度方面提供了好处，并且由于虚拟化开销较低而带来了性能改进。

在下面的视频中，Kohn 表示，讲述 Kubernetes 如何在电信世界中发挥作用的故事将是 2019 年 CNCF 的一个主要焦点。

[https://www.youtube.com/embed/5qMiR7HO5bQ?feature=oembed](https://www.youtube.com/embed/5qMiR7HO5bQ?feature=oembed)

视频

CNF 测试平台不是 CNCF 主办的[项目](https://www.cncf.io/projects/)，它的 [GitHub](https://github.com/cncf/cnf-testbed) 页面解释说，而是“创建可重复的点对点测试平台的倡议，电信公司和电信供应商可以用它来评估 CNF 架构与更传统的 VNF 架构相比如何。”

它补充说，CNF 试验台仍处于原型阶段。到目前为止，有四个测试案例，但更多的将被添加。

用户可以从 [ONAP](https://c212.net/c/link/?t=0&l=en&o=2383771-1&h=2422011997&u=https%3A%2F%2Fwww.onap.org%2F&a=ONAP) (开放网络自动化平台)或者自己的联网代码中测试网络功能，看看打包成容器或者虚拟机的相同代码和运行在相同硬件上的区别。

ONAP 是 LF 网络体系下的一个项目，提供策略驱动的物理和虚拟网络功能的协调和自动化。它参与了 cncf.ci 项目，该项目专注于在裸机上运行的 Kubernetes 上集成、测试和部署 cncf 和 LF 项目。

CNF 测试床使用了来自 ONAP 虚拟客户驻地设备(vCPE)用例的几个开源 vnf，同时还将代码重新打包成容器，成为 CNF。

测试床将在 [CNCF 社区基础设施实验室](https://thenewstack.io/cncf-packet-team-provide-free-infrastructure-cloud-developers/)运行，使用 [Packet](https://www.packet.com/) 捐赠的裸机服务器，其中包括位于超过 15 个全球位置的高性能计算和存储节点。

据 FierceTelecom 称，虽然[对集装箱和 Kubernetes](https://thenewstack.io/add-it-up-enterprise-adoption-of-kubernetes-is-growing/) 的采用持续增长，但电信行业仍在摸索这些新技术。

“容器化将堆栈向上移动到 VNFs 中，但是这意味着将 VNF 移动到云原生环境中吗？”Linux 基金会网络和协调总经理 Arpit Joshipura 告诉 FierceTelecom。

“我们想说的是，就分层架构而言，有一个明确的旅程。魔鬼显然在细节中。”

CNCF、Linux 基金会和 OpenStack 是这个新堆栈的赞助商。

专题图片:大卫·斯潘塞的《环球旅行》。根据 CC BY-SA 2.0 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>