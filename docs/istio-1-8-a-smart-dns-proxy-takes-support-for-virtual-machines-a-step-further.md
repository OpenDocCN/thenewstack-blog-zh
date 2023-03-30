# Istio 1.8:智能 DNS 代理进一步支持虚拟机

> 原文：<https://thenewstack.io/istio-1-8-a-smart-dns-proxy-takes-support-for-virtual-machines-a-step-further/>

[Tetrate](https://www.tetrate.io/) 赞助本帖。

 [吉米·宋

Jimmy 是 Tetrate 的开发者倡导者，CNCF 大使，ServiceMesher 和 Cloud Native Community(中国)的联合创始人。他主要关注 Kubernetes、Istio 和云原生架构。](https://www.linkedin.com/in/jimmysongio/) 

1.8 是将于 2020 年发布的 Istio 的最后一个版本，它有以下主要更新:

*   支持使用 Helm 3 进行安装和升级。
*   混合器被正式移除。
*   添加了 Istio DNS 代理以透明地拦截来自应用程序的 DNS 查询。
*   添加了 WorkloadGroup 以简化虚拟机的集成。

WorkloadGroup 是一个新的 API 对象。它旨在用于虚拟机等非 Kubernetes 工作负载，旨在模拟用于 Kubernetes 工作负载的现有 sidecar 注入和部署规范模型，以引导 Istio 代理。

## 安装和升级

Istio 开始正式支持使用[头盔](https://istio.io/latest/docs/setup/install/helm/) v3 进行安装和升级。在以前的版本中，安装是通过 istioctl 命令行工具或操作符完成的。在 1.8 版本中，Istio 支持使用 Helm 进行就地升级和金丝雀升级。

## 增强 Istio 的可用性

istioctl 命令行工具有一个新的错误报告特性( [istioctl 错误报告](https://istio.io/latest/docs/reference/commands/istioctl/#istioctl-bug-report))，可以用来收集调试信息和获取集群状态。

安装[附加](https://istio.io/latest/blog/2020/addon-rework/)的方式有所改变:1.7 istioctl 不再推荐，在 1.8 中已被移除，以帮助解决附加滞后上游的问题，并使其更易于维护。

负责策略控制和遥测收集的 Istio 组件 Mixer 已被删除。其功能现在由特使代理人提供服务。对于扩展性，服务网格专家推荐使用 [WebAssembly](https://istio.io/latest/blog/2020/wasm-announce/) (Wasm)来扩展 Envoy 你也可以试试 [GetEnvoy Toolkit](https://www.getenvoy.io/reference/getenvoy_extension_toolkit_reference/) ，它让开发者更容易为 Envoy 创建 Wasm 扩展。如果你还想使用混音器，你必须使用 1.7 或更高版本。在 Istio 1.7 之前，Mixer 一直在接收错误修复和安全修复。Mixer 支持的许多功能都有替代方案，如 [Mixer 弃用](https://tinyurl.com/mixer-deprecation)文档中所指定的，包括基于 Wasm 沙盒 API 的 [in-proxy 扩展](https://github.com/istio/proxy/tree/master/extensions)。

## 支持虚拟机

Istio 最近的升级稳步专注于让虚拟机成为网格中的一等公民。 [Istio 1.7 在支持虚拟机](https://thenewstack.io/how-to-integrate-virtual-machines-into-istio-service-mesh/)方面取得了进展，Istio 1.8 增加了一个[智能 DNS 代理](https://istio.io/latest/blog/2020/dns-proxy/)，这是一个用 Go 编写的 Istio sidecar 代理。sidecar 上的 Istio 代理将带有一个由 Istiod DNS 代理动态编程的缓存。来自应用程序的 DNS 查询被 pod 或 VM 中的 Istio 代理透明地拦截和服务，该代理智能地响应 DNS 查询请求，实现从虚拟机到服务网格的无缝多集群访问。

Istio 1.8 增加了一个[工作负载组](https://istio.io/latest/docs/reference/config/networking/workload-group/)，它描述了一个工作负载实例的集合。它提供了一个规范，工作负载实例可以使用它来引导它们的代理，包括元数据和身份。它仅用于虚拟机等非 k8s 工作负载，旨在模拟用于 Kubernetes 工作负载的现有 sidecar 注入和部署规范模型，以引导 Istio 代理。通过使用工作负载组，Istio 已经开始使用 [istioctl 实验工作负载组](https://istio.io/latest/docs/setup/install/virtual-machine/#create-files-to-transfer-to-the-virtual-machine)来帮助自动化虚拟机注册。

[Tetrate](https://www.tetrate.io) ，企业服务网格公司，在客户的多集群部署中广泛使用这些 [VM 特性](https://www.tetrate.io/blog/whats-new-in-istio-1-8-dns-proxy-helps-expand-mesh-to-vms-and-multicluster/)，使 sidecars 能够为网格中所有集群的入口网关处暴露的主机解析 DNS 并通过相互 TLS 访问它们。

## 结论

总而言之，Istio 团队保持了年初做出的承诺，自 2018 年 1.1 版本以来，保持了每三个月发布一次的常规发布节奏，并在性能和用户体验方面进行了持续优化，以在 Istio 上实现棕色地带和绿色地带应用的无缝体验。我们期待 Istio 在 2021 年取得更多进展。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>