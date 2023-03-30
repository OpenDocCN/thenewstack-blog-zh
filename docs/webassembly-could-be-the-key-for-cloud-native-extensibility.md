# WebAssembly 可能是云本地可扩展性的关键

> 原文：<https://thenewstack.io/webassembly-could-be-the-key-for-cloud-native-extensibility/>

尽管 [WebAssembly](https://webassembly.org/) 是为[将高级编程](/ready-web-assembly-revolution/)引入浏览器而创建的， [Solo.io](https://www.solo.io/) 的创始人/首席执行官 [Idit Levine](https://github.com/ilevine) 一直是使用便携设备的快速开源运行时来扩展[服务网格](/category/service-mesh/)的直言不讳的支持者——引用 Solo.io 自己在提供工具和服务以支持商业服务网格操作方面的工作。她认为，事实上，WASM，也就是众所周知的，可以被用来为各种各样的云原生项目带来可扩展性。

在本周的 [The New Stack Context](/podcasts/context) 播客中，我们询问 Levine 关于 WebAssembly 的兴奋度、它在 Envoy 代理中的使用，以及 Solo.io 关于以[Open Container Initiative](https://opencontainers.org/)格式打包 WASM 模块的新提议。TNS 编辑和营销总监 [Libby Clark](/author/libby/) 主持这一集，TNS 高级编辑 [Richard MacManus](/author/richard/) 和 TNS 执行主编 [Joab Jackson](/author/joab/) 提供帮助。

[第 135 集:WebAssembly 可能是云原生扩展性的关键](https://thenewstack.simplecast.com/episodes/episode-135-webassembly-could-be-the-key-for-cloud-native-extensibility)

很早的时候，[特使](https://www.envoyproxy.io/)服务代理背后的开发人员发现几乎每个服务网格用户都需要以某种方式定制控制平面。所以他们通过添加一个[过滤器链](https://www.oracle.com/java/technologies/intercepting-filter.html)来增加可扩展性。这是一个好主意，尽管最初在 Envoy 中添加定制过滤器是一项艰巨的任务，涉及 C++和重新编译 Envoy 本身。

谷歌一直倡导让 WebAssembly 成为 Envoy 的公共运行时，以此来帮助自己的 Istio 服务网，Envoy 是其中的一个主要组件。WASM 比 JavaScript 更快，因为它运行在沙箱(虚拟机)中，所以它是安全的和可移植的。也许最棒的是，因为编写类似汇编的 WASM 代码非常困难，所以许多方面为其他语言创建了翻译器——允许开发人员使用他们喜欢的语言，如 C 和 C++、Python、Go、Rust、Java 和 PHP。

谷歌和 Envoy 社区还围绕构建一个 WebAssembly 系统接口(WASI)团结起来，该接口[充当 WASM 和 Envoy 过滤器链之间的转换层](/mozilla-extends-webassembly-beyond-the-browser-with-wasi/)。

不过，Levine 当时认为，构建 Envoy 模块的体验并不是为开发人员打包的。仍然有许多管道需要添加，Istio 的设置等等。”“谷歌真的很擅长制作基础设施工具。但我认为他们在创造用户体验方面做得不太好，”莱文说。莱文认为，就像 Docker 定制 Linux LXC——很大程度上是由谷歌开创的——向更多的开发者开放容器技术一样，WASM/WASI 也可以为 Envoy 做同样的事情。

第一步是建立一个注册中心:12 月，Solo.io 推出了 [WebAssembly Hub](https://www.solo.io/products/webassembly-hub/) ，开发者可以在这里共享和重用 WebAssembly 模块。这些模块将与适当的元数据打包在一起，以便可以轻松、一致地下载、分发和加载到 Envoy 中。

Solo.io 团队没有从零开始，而是使用一个现有的规范来封装模块，其中可以定义每一层。所以它使用了 OCI 格式，最初是为包装容器图像而创建的。Solo.io 希望分享其从运行该中心中获得的经验，发布了[web assembly(WASM)Open Container Initiative(OCI)映像规范](https://github.com/solo-io/wasm)，称将“定义如何将 WASM 模块捆绑为 OCI 映像，以使其易于构建、提取、发布和执行。”

“WASM 映像规范定义了一个由 WASM 二进制文件和配置文件组成的映像，配置文件由一个 JSON 对象组成，该对象指定了模块的预期运行时、模块的运行时 ABI 兼容性和不透明的运行时特定配置，”[Mike Melanson 在最近的一篇文章中写道。](/solo-io-borrows-oci-spec-to-bundle-webassembly-modules/)

Levine 在播客中认为，通过中间 WASM 层创建扩展的模式，因此它们可以跨平台使用，并像 Docker 容器一样自动投入运营，这种模式不会仅限于服务网格技术。云本地计算基金会的开放政策代理背后的人，以及 CNCF 的 NATS 通讯软件背后的人，也在考虑使用 WASM。

“我认为这将是云计算的未来，”莱文说。“我觉得这将是未来扩展一切的基本方式。”

本周播客中讨论的其他故事:

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>