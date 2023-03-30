# Solo.io 借用 OCI 规范捆绑 WebAssembly 模块

> 原文：<https://thenewstack.io/solo-io-borrows-oci-spec-to-bundle-webassembly-modules/>

继去年发布其 [WebAssembly Hub](https://www.solo.io/products/webassembly-hub/) 之后， [Solo.io](https://www.solo.io/) 已经[发布了](https://www.solo.io/blog/announcing-the-webassembly-wasm-oci-image-spec/)一份新的 [WebAssembly (WASM)开放容器倡议(OCI)映像规范](https://github.com/solo-io/wasm)提案，据称该规范将“定义如何将 WASM 模块捆绑为 OCI 映像，以使其易于构建、拉取、发布和执行。”

尽管 Solo.io 正致力于使用 WASM 来扩展服务网格功能，但可移植的 WASM 包可能是简化开发的一个重大进步。“如果 WASM+(一个 WebAssembly 系统接口)在 2008 年存在，我们就不需要创建 Docker。这就是它的重要性。服务器上的 WebAssembly 是计算的未来。Docker 创始人所罗门·海克斯(Solomon Hykes)在最近的一条推文中写道。

Solo.io 于 2019 年 12 月首次推出了 WebAssembly Hub，重点是扩展特使代理，这构成了其 [Gloo](https://www.solo.io/products/gloo/) API 网关的基础。去年 3 月，在谷歌和 Istio 团队接触到 Solo.io 之后，该公司[扩展了](https://www.solo.io/blog/an-extended-and-improved-webassembly-hub-to-helps-bring-the-power-of-webassembly-to-envoy-and-istio/)web assembly Hub 的重点，包括扩展基于 Envoy 代理的 Istio 服务网格，这也[增加了 WASM 可扩展性](https://thenewstack.io/istio-1-5-brings-a-binary-installer-wasm-based-extensibility-for-envoy/)。Solo.io 将该中心描述为“为 Envoy Proxy、Gloo 和 Istio 提供构建、发布、发现和部署定制扩展所需的一切。”

“当我们在(WebAssembly Hub)工作时，我们学到了很多东西。我们学习了如何捆绑 WebAssembly。Solo.io 创始人兼首席执行官[艾迪特·莱文](https://github.com/ilevine?tab=repositories)在一次采访中说:“我们知道我们想要做一些像 Docker 体验一样的事情，我们决定最好的方式就是利用已经存在的东西，比如 OCI 规范。”。“想象一下，OCI 是一个基类。你基本上继承了 OCI 并加以扩展。OCI 规范只是非常高的层次，而不是具体的，我们希望它更具体，因为我们觉得它对工具更好，因为工具可以接受这些元数据，基本上说‘啊，这是一个特使规范！’"

WASM 映像规范定义了一个由 WASM 二进制文件和配置文件组成的映像，配置文件由指定模块的预期运行时、模块的运行时 ABI 兼容性和不透明的运行时特定配置的 JSON 对象组成。[规范库](https://github.com/solo-io/wasm/tree/master/spec)中的描述进一步阐明了“该规范可以被认为是 OCI 映像规范的扩展，专门为生产和消费 WASM 模块的应用程序而设计(与应用程序容器相对)。”

## 但这是图像吗？

在最初发布之后，开放容器倡议的一些成员[质疑](https://groups.google.com/a/opencontainers.org/g/dev/c/3_B0TkIkA7w)提议规范的命名，OCI 技术监督委员会成员 [Steve Lasker](https://www.linkedin.com/in/stevelasker/) 写道“我认为在具体的品牌中有一点混乱。如果我理解正确的话，从技术上来说，这不是一个 OCI 图像，而是一个 OCI 文物类型。它可以存储在注册表中，如奇点，头盔，OPA 等。[……]不管怎样，我都不会称之为 OCI 形象，因为它确实有特定的含义。”

WASM 规范命名的话题是本周 OCI 会议的一个话题，Levine 在会上提供了关于 Solo.io 产品的[完整背景](https://youtu.be/t-lj9PoXE0Q?t=2188)，这导致了在深入规范本身之前，关于 Solo.io 在这种情况下使用的 WebAssembly 的初级读本。

[https://www.youtube.com/embed/t-lj9PoXE0Q?start=2617&feature=oembed](https://www.youtube.com/embed/t-lj9PoXE0Q?start=2617&feature=oembed)

视频

在会议中，拉斯克似乎决定用“OCI 神器”作为更正确的术语，他说“我们试图讨论的一件事是‘OCI 图像’这个术语，而不是其他一些术语，因为它有意义。[……]从我们的角度来看，我不会调用‘OCI 映像’,因为我们认为 OCI 映像是运行时容器映像，可以说是一种平台中立的 Docker 容器。”

Levine 在讨论中解释说，Solo.io 在他们与 WebAssembly 的合作中处于领先地位，他们希望利用他们的经验提出一个规范(当前版本是 v0.0.0 ),以防止未来的潜在问题。

“在构建所有这一切的过程中，我们意识到了一件事……在云原生环境中，它往往会造成很多，政治和提供商会造成很多错位。我认为，在我看来，这种错位正在摧毁创新，”莱文说。“因此，不要让社区再经历一次这样的问题对我来说非常重要。我们曾经有过容器管理，现在又有了服务网格，我真的不认为这是健康的。”

除了命名和商标，Levine 表示，她认为这只是一个开始，随着这种扩展超越 Envoy 和 Istio，开放政策代理(OPA)T1 和 T2 NATS T3 也朝着这个方向发展。

“我个人认为，这仅仅是开始。我们需要它，这是我们在生产中与客户一起运行的东西，这就是我们需要它的原因，”Levine 说。"在我看来，这将是云原生的未来:扩展东西."

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>