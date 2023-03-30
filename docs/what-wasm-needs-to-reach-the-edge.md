# Wasm 需要什么才能到达边缘

> 原文：<https://thenewstack.io/what-wasm-needs-to-reach-the-edge/>

一次编写，随处运行。这句口头禅仍然适用于 [WebAssembly](https://thenewstack.io/is-webassembly-really-the-future/) (WASM)的承诺——但关键词是“承诺”，因为我们还没有到那一步，特别是对于边缘应用，或者至少还没有完全做到。当然，随着供应商开始支持不同的语言，如 TypeScript、Python 或 C#，WebAssembly 适应 JavaScript 和 Rust 之外的不同语言的能力已经取得了很大进步。

到今天为止，WASM 已经在浏览器中出现了。它也迅速用于后端服务器应用程序。然而，要达到应用程序可以到达边缘的阶段，还有许多工作要做。开发人员可能并不太关心这些——他们只是希望他们的应用程序在任何地方都能运行良好和安全，而不是想太多为什么 edge 还没有准备好，而是什么时候会准备好。

事实上，开发人员可能希望设计一个通过 WebAssembly 模块部署的应用程序，该应用程序将分布在各种边缘设备上。与过去几年不同的是，为特定设备设计应用程序可能需要大量时间来为每种设备类型重新发明轮子，WASM 的一个美妙之处是——一旦标准化到位——开发人员可以创建一个语音转录应用程序，不仅可以在智能手机或 PC 上运行，还可以在一个可以在执行任务时藏在特工衣服里的微型边缘设备上运行。换句话说，应用程序可以跨不同的边缘环境同时无缝地部署在任何地方。

在巴塞罗纳举行的 [WASM I/O 会议](https://thenewstack.io/vmware-and-other-wasm-players-want-webassembly/)期间，一些会谈讨论了实现边缘的成功以及在此之前需要完成的其他事情，即为边缘设备准备标准化组件。

## 完整事物中缺少的一个环节

边缘是[其中一个可能被误用甚至误解的流行语。对于电信公司，这可能意味着服务器或不同的电话设备。工业设备可能包括物联网设备，适用于需要带 CPU 的互联设备的用户的任何行业或消费用途。](https://thenewstack.io/what-the-heck-is-the-edge-and-why-should-you-care/)

组织可能希望通过 Kubernetes 集群部署 WASM 模块，以便在边缘设备上部署和管理应用程序。这样一个 WASM 用例是微软技术项目经理 Francisco Cabrera Lieutier 和微软边缘与平台产品经理金宥真虚拟演讲和演示“使用 AKS Edge Essentials 和 Akri on WASMs 以最小的占用空间连接边缘设备”的主题。

Lieutier 和 Kim 展示了如何通过 Kubernetes 环境使用 WASM 模块来部署和管理摄像设备。这是通过 AKS Edge Essentials 和 Akr 完成的。WASM 低功耗的主要好处之一是能够远程管理相机设备，像其他边缘设备一样，如温度计或其他传感器类型，将缺乏运行 Kubernetes 的 CPU 能力，否则如果没有 WASM，这将是一个要求。

“我们如何从集群中协调和管理这些设备？”金说。Kim 解释说，演示中使用的解决方案是 Akri，这是一个 Kubernetes 功能接口，用于连接 WASM 的物联网设备。

然而，虽然不同的边缘设备可以通过 AKS Edge Essentials 和 Akri 与 WASM 连接和管理，但边缘设备网络尚不兼容，比如说，在 AWS 集群下从云运行或直接从内部环境分布的边缘网络。

同样，问题是互操作性。“我们知道 WebAssembly 已经开始工作了。它做你需要做的事情，WASM 的功能集已经在浏览器和服务器上得到验证，” [Ralph Squillace，](https://twitter.com/ralph_squillace?s=20&t=rIXfGJMDDFoAk4LdqDJJFw)微软 Azure Core Upstream 的主要项目经理在会议间隙告诉新堆栈。

“缺少的是我们没有互操作性，我们称之为可移植性，即在重建不同的云之后采用相同的模块并部署它的能力，但你需要通用的界面、通用的运行时体验和专业化。这就是组件模型为互操作性提供的。

并不是说没有取得进展，所以希望在不久的将来，互操作性问题将得到解决，边缘设备将采用标准化的组件模型。目前，WASI 已经成为将 Wasm 延伸到浏览器之外的最佳候选人。被描述为 WebAssembly 的[模块化系统接口](https://wasi.dev/)，它被证明有助于解决在任何有适当配置的 CPU 的地方运行 Wasm 运行时的复杂性——这是 WebAssembly 自创建以来的主要卖点之一。通过标准化，Wasi 层最终应该能够将所有不同的 Wasm 模块运行到任何和所有带 CPU 的边缘设备上的组件中。

在“wasi-cloud:使用 WebAssembly 的云计算的未来”的演讲中，[字节码联盟](https://bytecodealliance.org/)技术标准委员会的主任贝利·海斯(Bailey Hayes)和 Cosmonic 的主任 Dan Chiarlone (virtually)在一个工作演示中展示了 wasi-cloud 如何为在云上运行 WASM 代码提供标准化的接口。

“对于如何编写一个可以跨云在任何地方运行的应用程序的问题，我们的答案是 wasi-cloud，”Hayes 说。“你可以想象，使用标准 API，一个应用程序可以在任何地方或任何架构、云或平台上运行。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>