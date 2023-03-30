# Istio 1.5 为 Envoy 带来了一个基于 WASM 的二进制安装程序可扩展性

> 原文：<https://thenewstack.io/istio-1-5-brings-a-binary-installer-wasm-based-extensibility-for-envoy/>

开源的最新版本 [Istio service mesh](https://istio.io/) 、[版本 1.5](https://istio.io/news/releases/1.5.x/announcing-1.5/) ，带有一个全新的安装程序来简化部署过程，以及一个基于 [WebAssembly](https://thenewstack.io/ready-web-assembly-revolution/) (WASM)的新扩展模型，来帮助代理服务器更好地过滤流量。

Istio 背后的开发团队将 [1.5 版本](https://istio.io/news/releases/1.5.x/announcing-1.5/change-notes/)标记为该项目的主要版本，并展示了他们季度发布节奏的成功。这是第五个符合该计划期限的版本。

新的安装程序得益于将 Istio 重新架构成一个更加单一的代码库，允许控制平面作为一个二进制文件安装。名为 Istiod 的新安装程序与现有的 API 和运行时组件保持一致。这一特性为通过 Kubernetes 运营商安装 Istio 铺平了道路。

通过引入 WASM，Istio 可以将自己已经相当可观的可扩展性模型与 Istio 最常用的数据层 [Envoy](https://www.envoyproxy.io/) 集成在一起。“WASM 将使开发者能够在特使代理中安全地分发和执行代码——与遥测系统、策略系统集成，控制路由，甚至转换消息的主体，”宣布新版本的网页[承诺。这种方法对开发人员来说也应该更有效。](https://istio.io/news/releases/1.5.x/announcing-1.5/)

随着越来越多的组织转向 Kubernetes 并发现需要更复杂的网络和策略管理，服务网格技术继续获得用户的采用。由谷歌以开源形式发布的 Istio，[仍然是最受欢迎的选择，](https://thenewstack.io/istio-and-the-service-mesh-horse-race/)尽管其他进入者，如 bubbly 的 [Linkerd](https://linkerd.io/) 和 HashiCorp 的 [Consul](https://www.consul.io/) 也仍然是可行的选择。

其他新特性包括期待已久的命令行安装，通过 [istioctl](https://istio.io/docs/reference/commands/istioctl/) 配置工具。通过支持 auto mTLS(测试版)以及改进对安全策略的支持，安全性得到了增强。遥测技术在这个版本中也得到了很大的提升。现在正在捕获原始 TCP 连接(除 HTTP 之外)的指标，并且 gRPC 工作负载现在受到更密切的监控。

由[凯尔·格伦](https://unsplash.com/@kylejglenn?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/extend?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>