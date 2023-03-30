# Krustlet 用基于 Rust 的 Kubelet 将 WebAssembly 带到了 Kubernetes

> 原文：<https://thenewstack.io/krustlet-brings-webassembly-to-kubernetes-with-a-rust-based-kubelet/>

在 Kubernetes 的世界中，大多数扩展 Kubernetes 的程序都是用 Go 编写的，而且大多数由 Kubernetes 编排的应用程序都被打包成容器。这两个东西已经变得如此常见，以至于已经成为默认，但没有一个是明确必要的，正如来自[微软的 Deis 实验室](https://deislabs.io/posts/hello-world/)的一个名为 [Krustlet](https://krustlet.dev/) 的新兴项目所证明的那样，该项目目前正在[加入](https://github.com/cncf/toc/pull/664#issuecomment-848013276)沙盒级别的[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)。

Krustlet 颠覆了 Kubernetes 的这两种习惯，首先，它是用 Rust 编写的，这是一种最初由 Mozilla 开发的内存安全语言，其次，它的目的是使 Kubernetes 能够调度 WebAssembly 模块，以代替[开放容器倡议(OCI)](https://opencontainers.org/community/certified/) 容器。虽然 Krustlet 团队在一年多前发布时小心翼翼地指出 WebAssembly 和 containers 可以作为“互补的一对”，每一个都有“自己独特的优势和劣势”，但这正是他们希望带给 Kubernetes 的优势。

“WebAssembly 可以完成许多与容器相同的任务，但它有不同的操作配置文件。Azure Core 的首席软件工程师 Matt Butcher 在一封电子邮件中解释道:“它可以用更少的权限运行，更小，而且是跨架构/跨操作系统的。“由于熟悉 Kubernetes，我们想看看是否可以构建一个在 Kubernetes 内部执行 Wasm 的工具，以说明 Wasm 和容器之间的相似之处并强调它们之间的差异。那是一个转折点。WebAssembly 比我们最初想象的更有前途。”

根据 Azure Core 的主要项目经理 Ralph Squillace 的说法，将 WebAssembly 引入 Kubernetes 还有另外一个原因。

Squillace 在一封电子邮件中写道:“Kubernetes 项目的驱动力不在于容器运行时，尽管它们引发了革命，但在于控制平面，即统一技能集和工具的 API。”。“我们想看看在这种运营模式下，使用不同的沙盒流程方法(WASM)能做些什么——结果会怎样？事实证明，一切都很顺利。”

“Krustlet”这个名字本身就说明了这里发生了什么:Krustlet 本质上是一个用 Rust 编写的 kubelet，用于运行 WebAssembly。当 Kubernetes API 接收到一个指向容器映像的创建新 pod 的请求时，kubelet 通常会响应并创建 pod 来运行容器映像。在这种情况下，当 Kubernetes API 收到一个创建新 pod 的请求，但是该请求指向一个存储在 OCI 注册表中的 WebAssembly 模块时，Krustlet 会做出响应。所有这一切都是通过一个名为“[污染和容忍](https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/)的 Kubernetes 系统发生的，Butcher 说这就是“Krustlet 的有趣之处:我们可以不加改变地使用 Kubernetes——没有补丁，没有对控制平面的特殊调整——Krustlet 只是一个替代运行时，可以放入任何 Kubernetes 集群，立即提供 Wasm 支持。”

虽然 Squillace 指出容器“在代码重用方面比 WASM 有用得多”——尽管他说 [WebAssembly 系统接口(WASI)](https://wasi.dev/) 可能会改变这一点——但 WebAssembly 还是有一些独特的优势，特别是当涉及微服务和运行在受益于小型快速二进制文件的环境中时。

“我们没有看到 WebAssembly 被用来重新打包现有的应用程序。但说到微服务架构，我们认为 WebAssembly 可能是最佳选择，”Butcher 写道。“对于微服务来说，启动速度、内存占用、安全性甚至开发的容易程度都是非常有意义的指标。而这些恰好是 WebAssembly 的强项。我们的愿景是让在 WebAssembly 中构建微服务变得简单而愉快，然后使用 Kubernetes 部署它们。”

通过启用 WebAssembly，Krustlet 提供了更高的密度、更快的启动和关闭时间、更小的网络和存储空间，所有这些功能不仅支持微服务，还支持边缘和物联网环境中的操作。此外，WebAssembly 还提供了在多种架构上运行而无需重新编译的能力，具有默认情况下不信任访客的安全模型，并且可以由解释器执行和流式传输，这意味着它可以在最小的设备上运行。

“Krustlet 可能与 SUSE/Rancher 的 k3s 等产品相结合，可以通过向 Kubernetes 集群提供小尺寸扩展来进军物联网。这表明库伯内特斯发生了翻天覆地的变化。当谷歌的一些人第一次编写 Kubernetes 时，他们考虑的是数据中心的集群。但是，为什么只考虑数据中心呢？”屠夫问道。“想象一下这样一个世界，pod 可以动态地移动到尽可能靠近用户的地方——小到恒温器、游戏机或家用路由器。然后，当这个人离开家时，这个应用程序可以和他们一起“离开”，跳到下一个最近的地方——但仍然在同一个群集中。当然，这是未来的世界，但 Krustlet 是实现这一目标的一步。”

Kubernetes 的下一个世界肯定是该项目致力于加入 CNCF 的原因之一，Squillace 解释道，他还指出，该项目的团队与 Helm，Brigade 和 Porter 的团队相同，都是 CNCF 的项目。

“我们真的希望看到 Kubernetes 在未来几十年取得成功。Krustlet 扩展了 Kubernetes 的功能:例如，Krustlet 应用程序可以由 Helm 和 Porter 打包。这些事情向我们表明，Krustlet 属于 CNCF，在那里它可以成为云本地工具不断扩大的产品组合中更有用的一部分，”Squillace 说。

目前， [Krustlet repository](https://github.com/deislabs/krustlet) 仍然显示着一个显著的横幅，宣称它是“高度实验性的”，但该项目预计将在未来几个月内达到 1.0 版。展望未来，Squillace 表示，该项目“将专注于网络和增加对 wasm 运行时的更多支持，专注于与 Akri(针对设备)等方法以及 SUSE 的 k3s 等小型发行版的合作。”

“假设 Krustlet 在 Kubernetes 生态系统中找到了自己的位置，我们希望它变得‘无聊’，它被使用，它起作用，”Squillace 在电子邮件中说。“然而，它确实巩固了 WASM 可以做的事情，特别是即将到来的 WASI 规范工作和模块链接。”

此外，Squillace 指出，从 Krustlet 及其多运行时提供者模型到字节码联盟(包括创始成员 Fastly、Intel、Mozilla 和 Red Hat)有一条直接的路径，以支持 WASM 和 WebAssembly 组件的其他功能(如链接等)的进一步工作。微软也是其中一员。

Squillace 写道:“云和 WebAssembly 世界的一些领军人物，如谷歌、Arm 和 Shopify，已经加入了最初的创始成员，我们对该社区在未来一年能够共同做些什么感到兴奋。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>