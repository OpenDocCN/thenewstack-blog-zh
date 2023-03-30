# 库伯内特和 CNI:下一步是什么——让编写网络插件变得更容易

> 原文：<https://thenewstack.io/kubernetes-and-cni-whats-next-making-it-easier-to-write-networking-plugins/>

[](https://www.openshift.com/)

 [Casey Callendrello，Red Hat 高级软件工程师

Casey Callendrello 是 Red Hat 的一名开发人员，从事容器网络接口(CNI)的工作，这是 Kubernetes 广泛采用的容器网络接口。他之前曾在 Weebly 和 Akamai 工作，前者负责构建可扩展的基础设施，后者帮助公司发展到数十万台服务器。在业余时间，他学习德语，并制造嵌入式设备来实现日常生活的自动化。他认为世界会变得更好，我们都将转向 IPv6。他住在德国柏林。他被勉强选为 Noisebridge hackerspace 的总裁。](https://www.openshift.com/) [](https://www.openshift.com/)

Linux 容器改变了我们对应用程序架构的思考方式，以及我们满足业务需求的速度。它们提供了跨环境的一致性和可移植性，并允许开发人员专注于应用程序创新，而不是底层的执行细节。然而，一个容器本身只是打包应用程序的一种有用方式；许多容器协同工作并大规模运行，可以改变一个企业。这就是 Kubernetes 的用武之地，它提供了部署和编排 Linux 容器的能力，以驱动真正的业务成果和推动创新。

虽然容器提供了应用程序打包，而 Kubernetes 提供了从简单的容器化组件编织大型复杂应用程序的能力，但这两种技术本身缺乏一种在特定堆栈之外进行通信的通用方法。但是这个挑战有一个答案:容器网络接口(Container Networking Interface，CNI ),它为网络供应商和项目提供了一个与 Kubernetes 集成的标准方法。

最初由 CoreOS(现在是 [Red Hat](https://www.openshift.com/) 的一部分)提出来定义网络插件和容器执行之间的公共接口， [CNI 专注于网络连接和当容器被删除时移除分配的资源](https://www.cncf.io/blog/2017/05/23/cncf-hosts-container-networking-interface-cni/)。CNI 于 2016 年发布，[云原生计算基金会](https://www.cncf.io/) (CNCF)技术监督委员会去年 5 月投票接受 CNI 作为托管项目。

CNI 提供的最重要的事情之一是选择:CNI 有一个蓬勃发展的第三方网络解决方案社区，这些解决方案插入到 Kubernetes 容器基础设施中，包括第三层虚拟网络 Calico 项目、Contiv 网络、各种用例的策略网络等等。让管理员知道他们有这些选择是很重要的，这样他们就可以为工作负载选择合适的插件。

事实上，网络世界是极其多样和复杂的。Kubernetes 的[价值在于它从普通开发人员那里抽象出这种复杂性，并呈现出一个干净的插件接口。反过来，CNI 提供插件，支持在网络中添加和删除容器网络接口。****](https://coreos.com/resources/index.html#ufh-i-339012759-kubernetes-primer)

## 此时此地

由 JSON 模式定义的 CNI 最初来自于 [rkt 容器运行时引擎](https://github.com/rkt/rkt)，它被设计成具有非常具体和可访问的集成点。CNI 最初不是为库伯内特开发的。事实上，它是一个在其他容器运行时系统中使用的多供应商系统，但它被 Kubernetes 社区采用，因为它提供了一种简单但强大的网络标准化形式。

典型的例子:[根据 GitHub](https://github.com/containernetworking/cni/blob/master/SPEC.md#overview-1) ，每个 CNI 插件都是一个简单的可执行文件，由容器管理系统调用。该插件负责将网络接口插入容器网络名称空间，并在主机上进行任何必要的更改。作为其中的一部分，插件被期望分配他们自己的 IP 地址或者委托分配给一个单独的 IPAM 插件。

CNI 插件被要求做的事情表面上很简单:

*   将容器添加到网络
*   从网络中删除容器

这种简单性——加上它是一种厂商中立的规范——导致了 CNI 的广泛采用，甚至被 Kubernetes 生态系统之外的容器编排者采用，如 Mesos 和 Cloud Foundry。然而，寻求与 Kubernetes 更深层次集成的插件，比如那些实现 NetworkPolicy 的插件，将需要在 CNI 的范围之外这样做。

但是有一些问题。例如，使用一些 CNI 插件，数据包直接发送到网络，在出去的时候跳过主机的路由表和防火墙规则。这提高了性能，但也有代价。Kubernetes 的关键功能，如网络策略和服务 IP，通常是在所有容器流量都经过主机的情况下实现的。决定使用哪个 CNI 插件的用户需要知道这些权衡。

管理员经常使用 Kubernetes 的特性，比如 DaemonSets 来安装和管理他们的插件。当插件包含一个需要对 Kubernetes API 进行认证访问和 RBAC 权限的组件时，这尤其有用。然而，当这样做时，插件作者和管理员都必须考虑灾难恢复。因此，在采取这一行动之前，管理员需要问自己:如果控制平面丢失，您的安装是否会有循环依赖，使您无法将其恢复？

## 未来的道路

当谈到与 Kubernetes API 对话时，编写 CNI 插件将变得容易得多。CNI 规范 v0.4.0 将包含更多来自运行时的动态信息，包括带宽限制和 IP 范围。这意味着插件作者应该能够在不依赖 API 可访问性的情况下打开一个容器。一如既往，最佳实践是尽可能在本地缓存信息，减少 API 服务器的负载。

但是还有什么呢？在 CNI v0.4.0 中，我们计划添加 GET 命令，这需要做大量的工作才能实现。挑战在于定义它时不要对插件是如何实现的做任何假设。该规范不应该妨碍现有用户，也不应该实现起来过于复杂。不过，这是值得的；这将允许容器运行时的无缝重启，使管理员的工作更加容易。拥有一个庞大而充满活力的生态系统是一件好事，但这可能会使衡量一个地方的变化是否会对另一个地方的某人(或某物)产生负面影响变得很困难。

这就是我们前进时的困难所在。我们如何继续改善和扩大 CNI 而不损害其简单性？这是我最近在 KubeCon 的[会议上讨论的事情之一——观看了解更多:](https://www.youtube.com/watch?v=Vn6KYkNevBQ)

[https://www.youtube.com/embed/Vn6KYkNevBQ?feature=oembed](https://www.youtube.com/embed/Vn6KYkNevBQ?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>