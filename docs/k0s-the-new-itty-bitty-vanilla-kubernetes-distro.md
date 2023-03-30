# K0s:新的小不点，香草 Kubernetes 发行版

> 原文：<https://thenewstack.io/k0s-the-new-itty-bitty-vanilla-kubernetes-distro/>

在给 Lens Kubernetes IDE 添加扩展的同时，Mirantis [Lens IDE](https://k8slens.dev/) 开发团队决定他们需要一个超轻量的 Kubernetes 发行版。所以，程序员归程序员，他们自己做了一个: [k0s](https://k0sproject.io/) 。

“我们希望为 Kubernetes 的各种使用案例创建一个现代、强大、多功能的基础层。k0s 联合创始人、 [Jussi Nummelin、](https://twitter.com/jnummelin)[Mirantis’](https://www.mirantis.com/)高级首席工程师表示:“它利用了传统的上游 Kubernetes，并且足够灵活，可以涵盖从典型的基于云的部署到各种边缘/物联网类型的用例。“利用我们以前的经验，我们真的不想开始维护各种操作系统发行版的设置和打包。因此，单个二进制文件的打包模型使我们能够更专注于核心问题，而不是不同风格的打包，如 deb、RPMs 等等。”

顺便说一下，那是个零，不是大写字母 o。为什么是零？因为这意味着将开发者的摩擦减少到零。K0s 作为单个二进制文件分发，除了内核之外，它不依赖于任何主机操作系统。它不需要特定的主机操作系统发行版，也不需要额外安装的软件包。展望未来，k0s 发行版将直接修复任何漏洞或性能问题。

其特点包括:

*   单一静态二进制
*   Kubernetes 1.19
*   [集装箱](https://containerd.io/)
*   控制平面存储选项:
    *   SQLite(集群内)
    *   etcd(集群内、托管、默认)
    *   MySQL(外部)
    *   PostgreSQL(外部)
*   CNI 供应商
    *   Calico 3.16(默认)
    *   定制(自带)
*   控制平面隔离:
    *   完全隔离(默认)
    *   受污染的工人
*   控制平面—节点通信
*   [核心域名](https://coredns.io/)
*   指标-服务器 0.3
*   工作节点的自定义角色\配置文件

它的开发者说 k0s 极大地降低了安装和运行完全兼容的 Kubernetes 发行版的复杂性。新的 Kube 集群可以在几分钟内启动。他们声称，没有特殊技能或专业知识的任何人都可以轻松上手。

对于那些不是初学者的人来说，它也可以像你所期望的那样，和镜头一起使用。这有助于有经验的开发人员使用丰富的图形化 IDE 进行可视化和 Kubernetes 集群控制。

K0s 的目标受众是需要随时随地轻松运行生产级 Kubernetes 的任何人。从在桌面上快速尝试的开发人员，到部署大规模生产集群的开发人员。使用相同的发行版可以确保您的代码在从开发到生产的过程中始终以相同的方式工作

当然还有其他轻量级的 Kubernetes 发行版。我很快想到了 Canonical 的 [MicroK8](https://microk8s.io/) s。但是，它的团队认为 k0s 脱颖而出，因为它是唯一一个不依赖主机操作系统的发行版，可以从本地开发集群扩展到大规模部署。

Nummelin 认为 k0s 是从笔记本电脑到私有数据中心集群(在裸机或虚拟机上)混合云集群所需的唯一开源 Kubernetes 发行版。 [Natanael Copa](https://github.com/ncopa) ，Alpine Linux 创始人兼 Mirantis 工程师补充道，“k0s 使得在你自己的笔记本电脑上运行相同的 Kubernetes 发行版变得非常简单，就像你在云中运行生产一样。”

当然，现在还为时尚早。这些目标中有一些是远大于现实的。正如程序员在 k0s GitHub 网站上所说，“我们仍然在 0.x.y 发布版本上，所以事情还没有 100%稳定。这包括不同 API 和配置结构的稳定性以及 k0s 本身的稳定性。虽然我们确实进行了一些基本的冒烟测试，但我们仍然缺乏更多针对基于 k0s 的集群的长期运行稳定性测试。当然，我们只测试一些已知的配置组合。”

也就是说，“在社区的帮助下，我们希望在 2021 年初推出 1.0.0 版本。”如果那只是一群普通的随机开发者，我会倾向于祝他们好运，然后继续我的路。但是，镜头团队，Nummelin 和 Copa 知道他们的东西。这个 Kubernetes 发行版值得你关注。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>