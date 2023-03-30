# Rancher 的 K3S 作为第一个 Kubernetes 发行版加入 CNCF 沙盒

> 原文：<https://thenewstack.io/ranchers-k3s-joins-cncf-sandbox-as-first-kubernetes-distribution/>

Rancher 的 [K3S](https://k3s.io/) ，一个精简的 Kubernetes 发行版，用于边缘部署等资源受限的环境，今天在沙盒级别加入了[云本地计算基金会](https://www.cncf.io) (CNCF)。K3S 于 2019 年 2 月推出，已经被下载了超过一百万次，目前每周的安装次数超过 2 万次。 [Shannon Williams](https://www.linkedin.com/in/smw355/) ， [Rancher Labs](https://rancher.com/) 的联合创始人兼总裁在一次采访中解释说，它的易用性和简单的包装真正导致了它的迅速流行。

“当我们第一次构建 K3S 时，我们的想法是，您可以构建一个完全兼容、完全认证的 Kubernetes 发行版，该发行版重量轻、体积小，足以在单节点类型的部署(边缘设备和人们的笔记本电脑)上运行。Kubernetes 非常强大，但大规模建造起来也相当复杂。如果您构建一个可以运行 5000 个节点的系统，它会比您想要在单台机器上运行的系统复杂一些，因此我们真的构建了一个具有许多非常合理的默认设置和简单部署的系统。当人们发现它时，就像是，'终于，这使得 Kubernetes 真的很容易，Kubernetes 可以由任何人运行，并且只需要很少的开销和成本。'K3S 刚刚从那里起飞，”威廉姆斯说。

该项目成为第一个加入 CNCF 的 Kubernetes 发行版，这一点在[提交提案](https://github.com/cncf/toc/pull/447)期间引发了一些争论，有人质疑 K3S 是否应该成为 Kubernetes 的子项目。最终，K3S 被 CNCF 的沙盒所接受，它的分类问题被搁置到未来可能的辩论中。 [K3S 库](https://github.com/rancher/k3s)简洁地将该项目总结为一个轻量级的 Kubernetes，它“生产就绪，易于安装，一半的内存，所有都在小于 100MB 的二进制文件中”，Williams 将此与 Kubernetes 的默认预期进行了比较。

“历史上，我们认为 Kubernetes 是平衡工作负载、最大化利用率和处理基础设施故障的好方法，但随着我们的标准化，它变成了运行单台机器的好方法，”Williams 说。“你当然可以在没有 Kubernetes 的单台机器上运行容器，但通过使用 Kubernetes，我可以在那台机器上运行一系列服务，我可以更容易地升级它们，我可以更容易地连接它们。我可以采用微服务架构和组件化软件，将它缩小到几乎最小的尺寸:一台机器，一个节点。”

K3S 将所有非容器化的 Kubernetes 组件打包到一个 40MB 的二进制文件中，唯一的依赖关系是“需要一个 sane 内核和 cgroup 挂载”，并添加了对 sqlite3 作为默认存储后端的支持，支持 Etcd3、MySQL 和 Postgres。虽然默认情况下 K3S 在单个集群上以单个节点启动，但 Williams 强调，如果需要，它可以在更大的规模上运行，一些云提供商实际上使用 K3S 作为他们首选的 Kubernetes 发行版。它还具有较小的内存占用，并且能够在多种硬件上运行，这使它脱颖而出。

“它还在如何实现联网、负载平衡和其他服务方面进行了优化，占用空间更小。它不仅占用空间优化，而且针对嵌入式设备、笔记本电脑、边缘位置以及任何需要简单、易于部署的 Kubernetes 的地方进行了用例优化，”Williams 说。“如果 Kubernetes 运行在冰箱上、电信网络上、数据中心中、云中，其通用性允许更容易的开发、更容易的软件分发，从而实现通用控制。这几乎就像在所有笔记本电脑上都安装了浏览器。它给了我一个通用的东西，我可以为它编写应用程序，也可以用它来编写应用程序。”

对于通用控制器，威廉姆斯不仅提到了 Rancher 本身，还提到了 Rancher 的另一个开源项目， [Fleet](https://github.com/rancher/fleet) ，它描述为“一个 Kubernetes 集群车队控制器，专门用于解决运行世界各地数千到数百万个集群的挑战。”

精简 Kubernetes 的想法似乎对 Kubernetes 的确切构成提出了质疑，对此 Williams 将 Kubernetes API 称为核心组件。

Williams 说:“CNCF 为 Kubernetes 发行版建立认证程序的方式非常清楚地表明，技术的实现很重要，但远不如 API 中的功能重要。“如果它走起来像库伯内特，听起来像库伯内特，跑起来像库伯内特，而你展示了库伯内特的能力，你就是库伯内特。这是一种面向 API 的方法，认为功能是关键。

云计算原生计算基金会是新堆栈的赞助商。

来自 Pixabay 的 lauralucia 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>