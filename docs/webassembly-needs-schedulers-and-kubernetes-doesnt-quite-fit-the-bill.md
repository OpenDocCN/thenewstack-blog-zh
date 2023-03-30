# WebAssembly 需要调度程序，而 Kubernetes 并不完全符合这个要求

> 原文：<https://thenewstack.io/webassembly-needs-schedulers-and-kubernetes-doesnt-quite-fit-the-bill/>

云原生计算不再仅仅意味着使用容器。

一个很好的例子是[Cosmonic web assembly Platform as a Service](https://cosmonic.com/)的架构。它是尽可能原生的云，但是对容器的依赖很小。将您的 WebAssembly 带到 Cosmonic，该平台提供了一种简单的方式来运行代码，甚至连接到其他服务。

当构建基础设施来运行这样一个潜在的高度可扩展的平台时，Cosmonic 没有选择目前看似标准的选择，即 Kubernetes，而是选择了 HashiCorp Nomad 开源 orchestrator。

平台服务发现，与 Kubernetes 相比，Nomad 的优势在于在处理非容器运行时时提供了更大的灵活性。

“应用程序并不总是容器，”Cosmonic 的工程总监 [Taylor Thomas](https://www.linkedin.com/in/oftaylor/) 在上周于洛杉机举行的 [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) 年度用户大会 HashiConf 2022 上说。

## 减少样板文件

对于开发人员来说，当前运行哪怕是最小的应用程序的云原生方法也是一件苦差事。即使是几百行的一些简单的业务逻辑也必须编译，然后打包成一个容器，然后在 Kubernetes 上调度。

Cosmonic 背后的想法是消除开发人员必须编写的所有样板代码。

Cosmonic 基本上是围绕 [WASMCloud](https://wasmcloud.com/about/) 的“企业粘性”，WASMCloud 是一个开源[云本地计算基础](https://cncf.io/?utm_content=inline-mention)平台，目前是一个沙盒项目，用于 WebAssembly。Cosmonic 是 [WASMCloud](https://github.com/wasmcloud/) 的主要维护者之一。

Cosmonic cloud 为客户应用程序运行时提供了一个空间，可进行水平和垂直扩展。

因此，每次开发者需要一个 http 服务器，或者一个 [Redis](https://redis.com/?utm_content=inline-mention) 数据库，开发者只需在代码中写一个契约，比如一个服务器或者一个键值存储，平台就会自动提供服务。

“这些功能允许我们抽象出他们不再需要管理的代码。它摆脱了样板文件。它使这种选择成为运行时的决定，像我们这样运行平台的人需要处理，”托马斯说。

服务可以被认为是可组合的参与者，它们都是“无状态和反应性的”不需要连接字符串或客户端。演员是在 WASM 写的，所以他们足迹少，速度快。要实现这一点，还需要其他一些后端，比如键值管理存储和容器化遥测。

Cosmonic 服务在 HashiCorp 的调度器和指挥器 [Nomad](https://www.nomadproject.io/) 上运行。Nomad 作为作业调度程序运行，而不是运行时。对于控制平面，Nomad 使用[哈希公司领事](https://www.consul.io/)身份网络软件和[哈希公司金库](https://www.vaultproject.io/)秘密管理器。

为了多租户安全，系统使用了[鞭炮](https://firecracker-microvm.github.io/)微管理器。泰勒说，这些非常轻量级、安全和快速的虚拟机“允许我们在相同的实际服务器上非常紧密、非常安全地运行客户主机”。

“Nomad 是这个用例的完美调度器，因为它支持混合环境。而且，它能够扩展到任何你想安装的类似结构或东西，”托马斯说。

托马斯说，这种设置不可能在 Kubernetes 下运行。

他说，有了 Nomad，“你只需要挑选你需要的特定东西，而不是像 Kubernetes 那样试图吞噬整个世界。”

更好的是，它不仅限于容器。它可以与 WASM 的 Cosmonic 一起工作，但也可以轻松支持 Java、QEMU，甚至 fork exec。它也很容易与相邻的标准一起工作，例如[容器存储接口](https://thenewstack.io/how-the-container-storage-interface-csi-boosts-cloud-native-devops/) (CSI)和[容器网络接口](https://thenewstack.io/container-networking-landscape-cni-coreos-cnm-docker/)，

Thomas 参与了 Krustlet 项目，该项目旨在扩展 Kubernetes 以支持非容器工作负载——包括 WASM。他的外卖？

“让我告诉你，Kubernetes 不喜欢不是容器的东西。他解释说，要把这两种技术联系起来需要“成千上万行代码”。

“你和诺曼德之间没有这个问题，”他继续断言道。通过 HashiCorp 自己的[任务驱动](https://www.nomadproject.io/docs/drivers)，它是非常可扩展的。任务驱动程序是执行工作负载的运行时组件。它还是一个可用于引入新类型工作负载的框架。Cosmonic 建立了自己的鞭炮任务驱动程序。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>