# KubeCon EU: WebAssembly 不仅仅是 JavaScript 的替代品

> 原文：<https://thenewstack.io/kubecon-eu-why-webassembly-is-more-than-a-javascript-replacement/>

虚拟机语言 [WebAssembly (Wasm)](https://webassembly.org/) 正在扩展到云本地计算的范围，并越来越多地集成到 Kubernetes 环境中。

为什么 Wasm 以及 WebAssembly runtime[wasmCloud](https://github.com/wasmCloud/wasmCloud)被认为不仅仅是 JavaScript 的替代品，这是周五[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)[kube con+CloudNativeCon EU](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)主题演讲“云原生和 web assembly:更好地在一起”的主题

Wasm 现在运行并支持云原生应用程序，并且运行在“作为嵌入在我们的应用程序中的可插拔引擎的服务器上，作为边缘平台，”微软 Azure 的首席产品经理兼 Krustlet 的 c0 创建者 Ralph Squillace 说。“它在我们的浏览器中，是的，它甚至在已经出现在我们的应用程序中的物联网 web 组件中，”Squillace 说。

换句话说，自从最初创建 WebAssembly 将 [JavaScript (JS)](https://developer.mozilla.org/fr/docs/Web/JavaScript) 、 [C++](https://fr.wikipedia.org/wiki/C%2B%2B) 和 [Rust](https://www.rust-lang.org/fr) 集成到单个运行时平台以来，它正在扩大其范围，以包括云原生平台，包括服务网格和 edge Kubernetes 支持。

在演讲中，[云治理平台提供商](https://www.linkedin.com/in/hectaman) [Stacklet](https://stacklet.io/) 的业务开发副总裁 Liam Randall 还介绍了 Wasm 现在如何用于 Envoy、Istio 和 Istio.io Gloo 服务网格，以及用于 [Kubewarden](https://docs.kubewarden.io/) 。它用于支持微软飞行模拟器和电子商务平台 [Shopify](https://www.shopify.com) 的 Kubernetes 集群。[快速](https://www.fastly.com/)依赖 Wasm 进行计算边缘应用。

Squillace 说:“已经是云原生的，就像任何好的技术一样，它很无聊，因为它很有效。”“即将到来的未来可能会给董事会增添一点趣味。”

今年早些时候，在 SoloCon 2021 期间的演示演讲[“使用 Web Assembly 扩展 Istio 和 Gloo Mesh”](https://sched.co/i7e4)中，Solo.io 软件工程师[沙恩·安东内尔](https://www.linkedin.com/in/irishshane/)描述了 Wasm 如何用于配置 Gloo Edge 如何用于管理进出集群的南北流量的 API 网关。Solo.io 正在为其[网络组装中心](https://www.solo.io/products/webassembly-hub/)寻求 Wasm 集成。

兰德尔说:“Wasm 是一个围绕速度高效的尺寸和安全性的关键价值主张，使其成为一个有吸引力的嵌入式引擎选择，我们可以在其中执行来自第三方的代码。”“以前你可能会转向 JavaScript，现在我们开始[使用] Wasm，因为安全可移植性和关注点的解耦超越并成为我们云原生环境的一部分。”

“随着 web assembly 组件功能开始出现，它能够在多种架构、系统和受限环境中运行，这意味着你现在就可以开始考虑如何使用它，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>