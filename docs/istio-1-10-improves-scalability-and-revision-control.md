# Istio 1.10 改进了可伸缩性和修订控制

> 原文：<https://thenewstack.io/istio-1-10-improves-scalability-and-revision-control/>

[](https://www.linkedin.com/in/zhihan-zhang-840176169/)

 [张志涵

韩志是 Istio 1.10 的发布经理，也是 Tetrate 的软件工程师。他主要关注云原生开源开发。他是 Tetrate Istio 发行版的维护者和 Istio 贡献者。](https://www.linkedin.com/in/zhihan-zhang-840176169/) [](https://www.linkedin.com/in/zhihan-zhang-840176169/)

Istio 继续致力于改善用户体验，最近发布了正式版 1.10。它增强了 Istio 的可伸缩性，并引入了修订标签以实现更流畅的控制。

1.10 版有以下主要更新:

*   使用发现选择器，支持监视一组选定的名称空间以获得更好的可伸缩性
*   在 Istio canary 升级期间，新的修订标签功能可避免重复的名称空间重新标记
*   更改了边车网络接口
*   Istio 网站的全新外观，istio.io
*   为每个人开放设计和规划文档
*   贬低 Kubernetes 第一方 JWT 支持

## 增强 Istio 的可扩展性

以前，Istio 控制平面会监视集群中所有命名空间的服务、端点和 pod。但是，由于 pod 和服务的规模不断增加，此功能可能会影响性能。

企业可能不需要 istiod 来监视所有名称空间。Istio 监视一些名称空间可能不太明智，比如包含一组 Spark 作业单元的名称空间，因为快速变动的资源会导致 Istio 控制平面的性能问题。

在 1.10 版本中，发现选择器存在于支持任意名称空间标签选择器的 meshConfig 部分中，允许用户基于表达式包含或排除名称空间。

例如，下面的命令将安装带有发现选择器的 Istio，并让 Istio 观察带有标签`istio-discovery: enabled`和`region: us-east1`的名称空间，或者带有标签`app`等于`cassandra`或`spark`的名称空间。

```
istioctl install  --skip-confirmation  -f  -  <<EOF
apiVersion:  install.istio.io/v1alpha1
kind:  IstioOperator
metadata:
namespace:  istio-system
spec:
meshConfig:
discoverySelectors:
 -  matchLabels:
      istio-discovery:  enabled
      region:  us-east1
 -  matchExpressions:
 -  key:  app
    operator:  In
    values:
 -  cassandra
 -  spark
EOF

```

要了解更多关于 discovery selector 的信息，并将其与 Sidecar 资源进行比较，请查看[这篇博文](https://istio.io/latest/blog/2021/discovery-selectors/)。

## 引入修订标签，使金丝雀更新更加顺畅

Istio 从 1.6 开始支持金丝雀升级。但是在 1.10 版本之前，如果您想为给定的名称空间采用一个试验性的新版本，您可以将名称空间标记为金丝雀修订版(如`istio.io/rev=canary`)，并在该名称空间中重启应用程序。从金丝雀版本迁移到生产版本需要在名称空间中重新标记，从像`istio.io/rev=canary`这样的金丝雀标签到像`istio.io/rev=prod`这样的生产标签，这引入了许多多余的工作。在 Istio 1.10 版本中，我们通过采用修订标签来简化升级。

例如，如果您安装了两个修订，比如 1-7-6 用于生产，1-8-0 用于 canary 安装，我们可以创建两个修订标记，如下所示:。

```
```bash
istioctl  x  revision tag set prod  --revision  1-7-6
istioctl  x  revision tag set canary  --revision  1-8-0
```

```

在我们验证了 canary 版本运行良好之后，我们可以使用下面的命令将 prod 标签迁移到新的版本:

```
```bash
istioctl  x  revision tag set prod  --revision  1-8-0
```

```

prod 标签下的名称空间也将迁移到新版本，注入的工作负载将使用新的控制平面重新启动。

有关更多信息，请查看更新的 [canary 更新文档](https://istio.io/latest/docs/setup/upgrade/canary/#stable-revision-labels-experimental)。

## 边车网络接口变化

正如我们所知，Kubernetes 为每个 pod 提供了一个单独的网络名称空间，对于 pod 通信，有两个网络接口。应用程序可以绑定到环回接口`lo`以允许 pod 内的呼叫，绑定到 pod ip `eth0`以允许 pod 到 pod 的通信，或者绑定到两者(通常绑定到 0.0.0.0)。

在 Istio 1.10 之前，Istio 数据平面将拦截来自`eth0`接口的 pod 入站流量，并将其重定向到`lo`，这可能会让应用程序仅绑定在`lo`接口上以接收来自其他 pod 的流量，或者禁止仅绑定到`eth0`接口的 pod 接收其他 pod 的流量。

从 Istio 1.10 开始，Istio 数据平面不再进行重定向，只会通过`eth0`转发流量。这种方法保留了 Kubernetes 的标准网络行为，避免了无意中暴露给只绑定到`lo`网络接口的应用程序单元。

值得注意的是，这个特性可能会影响从 Istio 1.9 到 Istio 1.10 的升级。

要检查您当前的部署是否会受到影响，请运行 precheck 命令:`istioctl experimental precheck`。

precheck 命令可以检测任何绑定到本地主机(lo 接口)的 pod，并报告错误 [IST0143](https://istio.io/latest/docs/reference/config/analysis/ist0143/) 。

如果您仍然不确定是否要迁移，您可以通过在 Istio 控制平面中采用以下环境变量`PILOT_ENABLE_INBOUND_PASSTHROUGH=false`来禁用此更改。

关于网络接口变化的更多细节，请查看这篇博文。

## 结论

总之，Istio 社区已经在 Istio 1.10 版本中解决了用户体验和性能优化问题。Istio 1.10 版本的行为更接近 Kubernetes 的标准行为，并为可伸缩性、微调和修订控制提供了更多功能。我们期待 Istio 社区在 2021 年推出更多功能和进步！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>