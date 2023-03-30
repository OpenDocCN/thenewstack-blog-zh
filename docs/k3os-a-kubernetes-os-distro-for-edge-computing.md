# K3OS:面向边缘计算的 Kubernetes 操作系统发行版

> 原文：<https://thenewstack.io/k3os-a-kubernetes-os-distro-for-edge-computing/>

在发布了为 edge 设计的轻量级 Kubernetes 发行版 [k3s](https://rancher.com/blog/2019/2019-02-26-introducing-k3s-the-lightweight-kubernetes-distribution-built-for-the-edge/) 之后，Rancher Labs 宣布了一个名为 k3OS 的配套操作系统。

k3OS 预览版支持 x86 和 ARM64。在 [k3OS](https://github.com/rancher/k3os) 中，Kubernetes 集群配置和底层操作系统配置使用与其他 Kubernetes 资源相同的声明性语法来定义，这意味着两者可以一起管理。

Rancher 一直在与包括风力涡轮机公司[金风智能能源](http://www.goldwindglobal.com/)在内的许多客户合作，在资源受限的环境中使用 Kubernetes。

Rancher Labs 首席执行官兼联合创始人[盛亮](https://www.linkedin.com/in/shengliang/)表示:“这些客户将 Kubernetes 更多地视为基础层，而不是应用层。

“其中一些来自 Linux，但许多实际上来自嵌入式 Windows，如 Windows XP。他们会让 Windows XP 运行一些类似嵌入式的应用程序。在能量平台上跑步之类的事情…如果你走向自动取款机或者地铁站。

“他们似乎把这两件事看成一件事:‘如果你想发布一个 Kubernetes 发行版，你最好负责操作系统。’”他说。

12 月，该公司宣布与 [Arm](https://www.arm.com/) 合作，为企业提供管理 x86 集群中的 Kubernetes 及其[物联网部署](https://thenewstack.io/how-low-can-kubernetes-go-rancher-arm-team-to-find-out/)的单一方式。

5gb 到 8GB 的边缘节点在现场处理数据，以减少发送回数据中心的数据量。用户相当频繁地更新这些节点上的应用程序。

他说，k3OS 的动力是操作系统没有与 Kubernetes 紧密集成的问题。

“人们倾向于做的只是部署操作系统，让它保持原样。然后他们会升级 Kubernetes，修补 Kubernetes，但操作系统没有改变。所以随着时间的推移，出现了各种各样的 CVE(常见的漏洞和暴露)。我们开始在 Kubernetes 集群上运行代理，我们会检测底层节点中的各种安全漏洞，然后我们会说，‘你必须修补底层操作系统。’"

事实证明这并不容易。…它实际上需要操作系统和 Kubernetes 之间的协调。

“如果你是谷歌或优步，由 SRE(网站可靠性工程师)负责这些事情，这不是问题，但(与 edge)我们谈论的是现场技术人员做这些事情，”他说。

“整个事情只需要简单得多，更有弹性。”

[K3s](https://k3s.io/) 是经过认证的生产级 Kubernetes 发行版，重量不到 40 MB。它只需要 512 MB 的内存就可以运行。它被打包成一个二进制文件，去掉了遗留的、alpha 的和非默认的特性。它使用 sqlite3 作为默认存储机制，etcd3 作为选项，但不是默认的。

“K3s 实际上是 Linux 发行版和 Kubernetes 发行版的结合体，”梁说。

“真的没有剩下多少 Linux 发行版了——它真的只是内核，加上一些实用程序。大部分东西都是库伯内特斯。现在，当人们想要更新时，他们只需到 Kubernetes 发出一些命令，Kubernetes 就会协调整个集群的升级。不仅仅是集群本身，还有底层操作系统。…

“K3s 已经让 Kubernetes 变得非常简单；我们只是把它扩展到了操作系统，所以你不必担心。操作系统也成为你不可改变的基础设施的一部分。你只要一次就搞定了。这几乎就像无人干预的操作，并且提高了安全性。人们[过去]会离开这些操作系统很多年，不去碰它们。你不只是在给 Kubernetes CVEs 打补丁，你也在给操作系统 CVEs 打补丁。”

Rancher Labs 计划在今年晚些时候发布 k3OS 的量产版。

几年前，该公司推出了管理码头集装箱的轻量级操作系统 [RancherOS](https://thenewstack.io/docker-fuels-rethinking-operating-system/) 。但是在 Kubernetes 的世界里，“你实际上不再需要 Docker 层了，”梁说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>