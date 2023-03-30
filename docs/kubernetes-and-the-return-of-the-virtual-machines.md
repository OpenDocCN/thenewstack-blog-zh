# Kubernetes 和虚拟机的回归

> 原文：<https://thenewstack.io/kubernetes-and-the-return-of-the-virtual-machines/>

[#174:库伯内特和虚拟机的回归](https://thenewstack.simplecast.com/episodes/174-kubernetes-and-the-return-of-the-virtual-machines)

在本周新的 Stack Analysts 播客中，我们将进一步探讨在 Kubernetes 环境中使用虚拟机的吸引力。

这场讨论是由 Pivotal 首席技术专家 Paul Czarkowski 上个月撰写的热门博客文章引发的。基本 Docker 风格的容器的问题是它们不能在多租户环境中提供足够的安全性，在多租户环境中，多个部署混合在同一组 Kubernetes 控制的服务器上。因此，我们采访了 Czarkowski，以了解他更多的想法。

Linux 容器都依赖于来自内核的共享内核，内核通过名称空间提供隔离。然而，Kubernetes API 并不安全，大多数 K8s 组件并不知道租户。Czarkowski 认为，这迫使服务提供商将 Kubernetes 的工作负载作为单独的集群提供给不同的客户，而没有充分利用 Kubernetes 通过将工作负载集中在同一个集群上所能提供的全部节省。

他建议说，虚拟机——过去十年的尖端技术——确实提供了足够的隔离，以防止一个客户端占用另一个客户端的工作负载。主要的云提供商提供嵌套在虚拟机中用于隔离的容器服务(参见[亚马逊网络服务的 Fargate](/aws-fargate-the-beginning-of-the-end-for-infrastructure-management/) )。Google 的 gVisor 和 [Kata containers](https://thenewstack.io/kata-containers-secure-lightweight-virtual-machines-container-environments/) 是为使用精简虚拟机的容器提供隔离的两个努力。

在本播客的后半部分(单独录制)，我们采访了红帽云平台副总裁 [Joe Fernandes](https://www.linkedin.com/in/joefernandes1/) ，探讨了这种回归虚拟机的商业意义。他谈到了 Red Hat 的 open shift——Red Hat 的 Kubernetes 商业分发——给容器带来的安全好处，以及 gVisor 等技术的采用。我们还谈到了 Kubernetes 越来越多地用于管理虚拟机等非容器资源，或者通过 [KNative](/with-knative-google-brings-multicloud-serverless-to-the-enterprise/) 等技术管理无服务器工作负载。

## 在这个版本中:

[3:39:](https://thenewstack.simplecast.com/episodes/174-kubernetes-and-the-return-of-the-virtual-machines?t=3:39) 当你谈到多租户时，你指的是共享的 Kubernetes 服务吗？
[10:29:](https://thenewstack.simplecast.com/episodes/174-kubernetes-and-the-return-of-the-virtual-machines?t=10:29) 探索 Kubernetes 中的工作组来解决这个问题。
[15:04:](https://thenewstack.simplecast.com/episodes/174-kubernetes-and-the-return-of-the-virtual-machines?t=15:04) 从用户角度比较虚拟机、隔离和控制与使用容器。
[22:45:](https://thenewstack.simplecast.com/episodes/174-kubernetes-and-the-return-of-the-virtual-machines?t=22:45)VMs 是 Kubernetes 的未来吗？这里的核心问题是什么？
[30:00:](https://thenewstack.simplecast.com/episodes/174-kubernetes-and-the-return-of-the-virtual-machines?t=30:00)open shift 是否支持其中一些微虚拟机？最终，Kubernetes 将能够像在容器中一样在虚拟机上运行。对于尚未迁移到容器的公司来说，这样做的价值主张是什么？

TNS 编辑部主任 [Libby Clark](https://twitter.com/libbymclark?lang=en) 在 TNS 执行主编 [Joab Jackson](https://github.com/joabj) 的帮助下主持了这一集的 TNS 分析师。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>