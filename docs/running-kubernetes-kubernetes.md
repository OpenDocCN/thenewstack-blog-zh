# 在 Kubernetes 运行 Kubernetes

> 原文：<https://thenewstack.io/running-kubernetes-kubernetes/>

[](https://www.kubermatic.com/)

 [塞巴斯蒂安·舍勒

塞巴斯蒂安是 Loodse 的首席执行官和联合创始人，Loodse 是一家软件公司，开发了 Kubermatic——一个用于多个 Kubernetes 集群的容器引擎。在 Loodse 之前，Sebastian 在企业部门工作了十多年。他的职业生涯始于软件生产商 SAP，在那里他参与了 SAP Hana 的开发，并担任主要国际客户的顾问。](https://www.kubermatic.com/) [](https://www.kubermatic.com/)

开源的 [Kubernetes](/category/kubernetes/) 容器编排引擎绝对有一些魔力。几年来，容器一直是一个很酷的概念，但广泛的部署被证明是困难的。手动管理容器间的网络、持久存储和数百个容器的自动扩展是不可能的，并且看不到真正好的容器平台。

当 Google [在 2014 年向开源社区发布](https://github.com/kubernetes)Kubernetes 项目时，这种情况发生了变化。很快，网络、存储、自动扩展、警报和许多其他容器的标准基础设施功能现在可以在 Kubernetes 集群中自动管理，同时具有极低的停机时间和出色的性能。对许多公司来说，大规模运行容器并利用分布式基础设施成为一种可行的选择。

巧合的是，云原生应用程序的想法引发了宠物与牛的讨论，在讨论中，您开始将基础架构的每个组件视为群体中可任意使用的一部分，而不再是不可替代的宠物。根据这种新的思维方式，每个组件都必须能够在没有影响的情况下发生故障:服务器、机架、数据中心……一切。然而，具有讽刺意味的是，许多公司现在像对待宠物一样对待他们的 Kubernetes 集群，并在它的护理和健康上花费大量时间和资源。

对我们来说，这似乎很奇怪，不应该是这样，因为它违背了云原生应用程序的基本概念。因此，我们的任务很明确:我们希望 Kubernetes 集群成为低维护的牛:完全可管理的、可伸缩的、多租户的，并且在任何时候都是可处置的。此外，我们希望所有集群都有一个 API。

如果 Kubernetes 提供了运行自动化容器集群的完美工具，为什么不使用 Kubernetes 自托管多个 Kubernetes 集群呢？为什么不建立一个 Kubernetes-as-a-Service 来将重心从运行 Kubernetes 重新转移到运行您的服务上呢？事实上，这就是我们过去和现在所做的，我们仍然认为这是一个非常好的想法。

## 但是在 Kubernetes 中运行 Kubernetes 是如何工作的呢？

首先要做的是建立一个外部 Kubernetes 集群，它运行多个独立客户集群的主组件。与任何其他 Kubernetes 集群一样，主集群由四个主组件组成:API 服务器、 [etcd](https://github.com/coreos/etcd) 键值存储、调度器和控制器。为了防止停机，我们创建了一个高可用性设置，每个组件都有几个实体。

![](img/4919232db24fb71529ef796bef9a86bb.png)

图表:主集群的高可用性设置。

然后，为了启动内部集群，我们创建一个名称空间，生成证书、令牌和 SSH 密钥，并部署主组件。随后，我们添加一个入口，使 API 服务器和 etcd 可以从外部访问。最后，我们安装基本插件，如 [Heapster](https://github.com/kubernetes/heapster) 、 [kube-proxy](https://kubernetes.io/docs/admin/kube-proxy/) 、 [Kube-dns](https://kubernetes.io/docs/admin/dns/) 和仪表板。

之后，我们想知道内部集群中发生了什么，因为这是节点和 pod 实际运行的地方。不幸的是，在标准的 Kubernetes 设置中没有这样的机会，在这里您只能与主集群的 API 进行通信。让事情变得更复杂的是，我们想要设置 N 个集群，N 个 API 服务器和 N 个 etcd 实例都拥有主集群的 IP。因此，我们需要提供一个具有 HTTP 和 TCP 代理的服务，该服务能够通过 SSH 隧道将对客户 API 服务器 3 的加密请求传输到客户 API 服务器 3。

![](img/63b2a43ff0ad8a2a830cec6c8f19f422.png)

图表:网络解决方案。

## 摘要

我们展示了通过在 Kubernetes 中运行 Kubernetes，您可以提供多个自托管和完全管理的内部集群。这使您可以轻松地创建、更新、删除和重新安排集群，而不会影响功能。此外，这种架构确保了更高的隔离性和安全性，同时也极大地方便了多租户。

虽然这一概念仍处于早期，但我们相信 Kubernetes-in-Kubernetes 是再次摆脱宠物范式的重要一步。这一概念使公司能够大规模运行多个集群，并追求真正的云原生战略，在这种战略中，您只需关注您的应用程序，而不再关注您的基础架构。

*欲了解更多关于 Kubernetes 网络和相关主题的信息，请参加 3 月 29 日至 30 日在德国柏林举行的[CloudNativeCon+kube con Europe](http://cloudnativeconeu.org/)2017。*

![](img/1b40d1b19a04f3913288c3753dcf90e7.png)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>