# 使用集群插件增强核心域名

> 原文：<https://thenewstack.io/supercharge-coredns-with-cluster-addons/>

Infoblox 赞助了这篇文章。

 [桑迪普·拉詹

Sandeep 是 Infoblox 的一名软件工程师，专注于对云本地计算基金会(CNCF)项目 CoreDNS 和 Kubernetes 的开源贡献。](https://www.linkedin.com/in/sandeep18/) 

用户越来越要求能够管理健康、状态、首次展示、回滚等。Kubernetes 集群中的 CoreDNS 而不仅仅依赖由集群管理工具管理的核心域名。由于在 Kubernetes 中使用操作符现在已被普遍接受，[集群插件项目](https://github.com/kubernetes-sigs/cluster-addons)的目标是将操作符的好处带给所有插件。

插件扩展了 Kubernetes 的功能。有些插件，如 CoreDNS 和 kube-proxy，被认为是 Kubernetes 集群的基本功能，与 Kubeadm、Kops 等集群管理工具一起提供。还有其他插件可以作为一个选项安装，但并不重要，但可以帮助用户管理他们的集群——例如 Calico、Kubernetes Dashboard 和 NodelocalDNS。

cluster-addons 项目的目的是让你在运营商的帮助下，以更好的方式管理插件。

操作符是一种打包、部署和管理 Kubernetes 应用程序的方法。

每个运营商都有自己的[自定义资源定义](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/) (CRD)，用户可以在这里管理插件——在安装、升级、选择版本等方面。—通过修改 CRD，而不依赖群集管理工具。

## 对集群加载运算符的需求

如今，像 Kubeadm、Kops、Cluster API 等集群管理工具。与 CoreDNS 和 kube-proxy 等基本插件捆绑在一起。

面临的一些挑战是:

*   用户希望在管理集群中安装的插件时有更大的灵活性。目前，插件是随着集群的生命周期自动管理的。例如，如果用户升级或降级他们的 Kubernetes 版本，插件的版本也会随之升级或降级。
*   由于插件变得越来越复杂，管理集群管理工具变得越来越困难。

在过去，曾有人试图通过 bash 版本的插件管理器来解决这些问题。然而，这并不成功，也没有被广泛采用。

cluster-addons 项目致力于通过引入运营商来解决这些挑战。运营商允许用户将插件的生命周期与集群的生命周期分离。

每个运算符都由一个 CRD 定义。用户将能够通过 CRD 以有限的方式定制插件(例如，安装、升级)。每个操作员都有自己的控制器。控制器是一个控制回路，它监视你的插件资源的状态，并在需要的地方做出或请求改变。控制器试图将附加资源的当前状态移动到更接近期望的状态。

## CoreDNS 运营商

CoreDNS 从 Kubernetes v1.11 开始就是默认的 DNS 插件，是拥有一个功能性 Kubernetes 集群的最重要的插件之一。

CoreDNS 操作符在这里被特别强调，因为 CoreDNS 是最复杂的插件之一。这是第一个实施的运营商，展示了运营商的力量及其使 CoreDNS 更易于在集群上管理的能力。

作为其基本功能的一部分，CoreDNS 运营商能够安装 CoreDNS，升级 CoreDNS 版本，并在升级期间自动迁移`Corefile`,以确保它是最新的并与 CoreDNS 的任何版本兼容，从而为用户提供无缝体验。

运营商持续监控核心 DNS 资源(部署、配置图、服务等)。)在控制器的帮助下。

可以通过 CustomResource (CR)修改 CoreDNS 规范。CoreDNS CR 的一个例子如下:

```
apiVersion:  addons.x-k8s.io/v1alpha1
kind:  CoreDNS
metadata:
  name:  coredns-operator
  namespace:  kube-system
spec:
  version:  1.7.0
  dnsDomain:  cluster.local
  dnsIP:  10.96.0.10
  corefile:  |
  .:53  {
 errors
 health  {
 lameduck  5s
 }
 ready
 kubernetes cluster.local in-addr.arpa ip6.arpa  {
 pods insecure
 fallthrough in-addr.arpa ip6.arpa
 ttl  30
 }
 prometheus  :9153
 forward  .  /etc/resolv.conf  {
 max_concurrent  1000
 }
 cache  30
 loop
 reload
 loadbalance
  }

```

如上所示，可以通过修改 CR 规范来修改 CoreDNS 版本、DNS 域、DNS IP 和 Corefile。控制器将登记应用于 CR 的改变，并将与核心 DNS 资源协调以反映这些改变。

要了解如何在您的集群上安装 CoreDNS 操作器，您可以遵循这里的说明[。](https://github.com/kubernetes-sigs/cluster-addons/tree/master/coredns#running-the-operator-locally)

## 创建您自己的操作员

cluster-addon 操作符是在 Kubebuilder 的帮助下创建的，kube builder 是一个使用 CRDs 创建自己的 Kubernetes APIs 的框架。如果您对创建自己的操作员感兴趣，请查看这些关于如何创建和部署您的操作员的分步说明。

## 项目的状态

今天，cluster-addon 存储库包含了许多操作符——如 CoreDNS、NodelocalDNS、kube-proxy 等。—它可以被安装并使用户能够在他们的 Kubernetes 集群上管理这些插件。

cluster-addon 项目还包含[addon-installer 库](https://github.com/kubernetes-sigs/cluster-addons/tree/master/installer)，它是一个小的实现，使用 kubectl 和 [Kustomize](https://kustomize.io/) 将 addon 操作符应用到 Kubernetes 集群。

### 未来的工作

我们正致力于将运营商集成到集群管理工具中，如 Kubeadm、Kops 和 Cluster API。

## 伸手

如果你对 cluster-addons 项目感兴趣，想要探索运营商，想要讨论插件或新功能，或者你需要帮助，你可以通过 [#cluster-addons Slack](https://kubernetes.slack.com/messages/cluster-addons) 和 [SIG 集群生命周期组](https://groups.google.com/forum/#!forum/kubernetes-sig-cluster-lifecycle)联系我们。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>