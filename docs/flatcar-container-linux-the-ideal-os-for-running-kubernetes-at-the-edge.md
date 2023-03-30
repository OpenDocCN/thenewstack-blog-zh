# Flatcar Container Linux:在边缘运行 Kubernetes 的理想操作系统

> 原文：<https://thenewstack.io/flatcar-container-linux-the-ideal-os-for-running-kubernetes-at-the-edge/>

编者按:这篇文章将是涵盖 Flatcar Container Linux 的系列文章的第一篇，涵盖了在边缘配置和部署操作系统所需的一切。请每周五回来查看未来的分期付款。

我一直在研究在边缘运行 Kubernetes 的优化基础设施栈。虽然牧场主的 [K3s 被认为是 edge 的最佳 Kubernetes 发行版，但对 edge 优化操作系统(OS)的追求仍在继续。](https://thenewstack.io/tutorial-install-a-highly-available-k3s-cluster-at-the-edge/)

在假期里，我有机会探索 [Flatcar Container Linux](https://www.flatcar-linux.org) ，这是一个在[红帽收购 CoreOS](https://thenewstack.io/docker-acquiring-coreos-red-hat-aims-kubernetes-company/) 时作为 CoreOS Container Linux 的[分支开始的操作系统。](https://thenewstack.io/flatcar-linux-the-coreos-operating-system-lives-on-beyond-red-hat/)

自从 2014 年推出以来，我一直是 CoreOS，Inc .项目的粉丝。Container Linux、rkt、etcd、Fleet 和法兰绒是 CoreOS staple 的一些产品。虽然 [etcd](http://etcd.io) 成为了 Kubernetes 的基础和 CNCF 的一部分，但其他项目在红帽[收购了](https://www.redhat.com/en/about/press-releases/red-hat-acquire-coreos-expanding-its-kubernetes-and-containers-leadership) CoreOS 后就不复存在了。

去年，Red Hat [宣布](https://coreos.com/os/eol/)该公司将不再开发或支持容器 Linux。尽管 Fedora CoreOS 被定位为替代产品，但它不是 CoreOS Container Linux 的替代产品。

Flatcar Linux 现在由柏林初创公司 [Kinvolk](https://kinvolk.io) 正式维护，作为一个容器原生的轻量级操作系统，继续实现最初的容器 Linux 的承诺。在收购 Red Hat 之前，Kinvolk 的人员一直与 CoreOS 的 Container Linux 开发人员密切合作。

CoreOS 提供了容器 Linux 栈作为 Docker Swarm 的替代方案，当时它还处于起步阶段。CoreOS 的 Container Linux、rkt、Fleet 和 etcd 都是在 Kubernetes 推出之前创建的。Container Linux 是这个堆栈的基础，许多人认为 rkt 是 Docker Daemon 的更好替代方案。etcd 充当分布式内存数据库，协调容器 Linux 集群的多个节点之间的通信——它仍然服务于大多数 Kubernetes 部署。Fleet 是能够部署、扩展和管理带有嵌入式容器映像的 [systemd](https://www.freedesktop.org/wiki/Software/systemd/) 单元文件的协调者。在 Kubernetes 中，每个单元文件被粗略地翻译成一个 Pod 定义。

快进到 2021 年，您会看到云原生生态系统发生了很多变化。但是，最初承诺的不可变、幂等、轻量级、容器优化的操作系统仍然很有吸引力。

通过提供定期的安全更新和补丁，Flatcar Container Linux 为 CoreOS Container Linux 注入了新的活力。它本质上使旧操作系统在不断变化的动态云原生生态系统中具有相关性。

例如，即将发布的 Flatcar Container Linux 版本将对 containerd 提供本地支持，作为 Docker 引擎的替代。这使得 kubelet 直接与容器运行时对话成为可能。

在裸机服务器上运行的边缘安装 Flatcar Container Linux 很容易。更小的占用空间、原子更新和远程管理功能使其成为边缘设备的理想选择。

Flatcar Linux 没有包管理器。systemd 单元文件构成了操作系统的构造块。每个过程，即使是短暂的，都是作为一个单元打包和部署的。这些单元文件可以作为安装过程的一部分进行配置和部署。一旦部署完毕，就可以通过标准的`systemctl`工具对其进行管理。

我最喜欢的是操作系统的声明性。基于[Ignition](https://kinvolk.io/docs/flatcar-container-linux/latest/provisioning/ignition/)——一个为配置和单元文件使用 JSON 格式定义的工具——进程可以在引导时启动。甚至 SSH 配置，包括用户名和密钥，也是安装过程中使用的点火文件的一部分。

借助 iPXE 服务器和节点的 FQDN/IP 地址，您可以远程安装 Flatcar Container Linux。升级到新版本就像重新启动节点一样简单。在 Ignition 的帮助下，可以无缝升级 Kubernetes 集群，而对工作负载的影响最小。

由于 CoreOS 构建的原始 orchestrator built 已被弃用，因此在 Flatcar Container Linux 上部署 etcd 没有硬性规定。您可以让 K3s 和 Microk8s 等发行版使用内置的 etcd 来运行高可用性集群。

Flatcar Container Linux 在 IaaS 环境中正式可用，包括 AWS、Azure、Google Cloud 和 Equinix Metal。你可以在云中或者在你的本地工作站上通过 Vagrant 启动一个 VM。

Kinvolk 围绕 Flatcar Container Linux 提供商业支持和定制工程服务。还有一个 LTS 渠道，在那里，一个版本的有效期延长至 18 个月。

我在我的实验室环境中配置了一个 PXE 引导服务器，它托管 Flatcar 内核映像和`initramfs`文件。我可以通过点火在三个节点上安装 Flatcar Container Linux，这些节点运行在由英特尔赛扬 CPU、8GB RAM 和 128GB SSD 驱动的[奥德赛迷你 PC](https://thenewstack.io/odyssey-blue-j4105-mini-pc-an-x86-device-for-edge-computing-projects/) 上。

在第一次启动时，我将 K3s 安装在多主配置中，以实现高可用性(HA)。最棒的是，我可以在不进入任何节点的情况下完成所有这些工作。Flatcar Container Linux 的这种远程管理能力使其成为 edge 的最佳操作系统之一。

在本系列的后续文章中，您将学习如何配置 PXE 引导服务器，如何使用 Ignition 在磁盘上安装操作系统，如何部署 HA K3s 集群，以及如何升级它。敬请期待！

贾纳基拉姆·MSV 的网络研讨会系列“机器智能和现代基础设施(MI2)”提供了涵盖前沿技术的信息丰富、见解深刻的会议。在 [http://mi2.live](http://mi2.live) 注册参加即将到来的 MI2 网络研讨会。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>