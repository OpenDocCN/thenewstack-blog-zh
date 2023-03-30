# KubeCon EU:特使期待 WebAssembly 扩展微服务监控

> 原文：<https://thenewstack.io/kubecon-eu-envoy-looks-to-webassembly-to-extend-microservices-monitoring/>

整个敏捷走向自主开发的过程很好地包容了单个团队，甚至工程师的偏好。然而，毫无疑问，这给治理带来了困难。很难监控、观察和学习不同的工具。

[Envoy](https://www.envoyproxy.io/) 是一个开源的网络代理，它与应用程序一起运行，以平台无关的方式为应用程序提供通用特性。特使贡献者和软件工程师在 [Tetrate.io](http://tetrate.io) ，[Yaroslav Skopets](https://github.com/yskopets)在[kube con+CloudNativeCon Europe](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)虚拟版上提供，一个新的特使扩展作为这些多种语言的单一解释。

他这样开始:“特使的一个基本目的是它能够看到你的应用程序收到或发出的每一个请求。”

Skopets 表示，下一步是扩展 Envoy，以一种高效、灵活和简单的方式从实际交通中学习。这通常包括在 C++中本地开发 Envoy，并静态链接到 Envoy 二进制文件中。他说，这涉及到特使的许多定制构建，导致“大量的投资和前期承诺。”

Skopets 建议使用 [WebAssembly](https://webassembly.org/) ，它起源于浏览器，使应用程序具有他所谓的“接近本地的网络性能”他说，在 WebAssembly 的低级代码格式中，它能够在沙盒环境中安全、高效地执行。

在这个编码语言分散的世界里，有趣的是，应用程序仍然可以使用常规编程语言来开发——如 Rust、AssemblyScript、TinyGo、C、c++——但随后它会被编译成 WebAssembly 代码，这些代码可以动态部署和回滚。

Skopets 提供了一个他认为是普通特使用户的例子——一个拥有基于微服务的架构和使用 RESTful APIs 和 OpenAPI 规范的契约优先或设计优先 API 开发的组织。

两个需要持续回答的常见问题是:

*   API 规范是完整的和最新的吗？
*   实现与 API 规范匹配吗？

这个 Envoy 扩展允许您根据 API 规范验证请求，并通过指标标记违规。

“这是一个特别的，实验性的，一次性的扩展，”Skopets 说。

![](img/b8b4d243e5a808ebef1eb8ed4844c052.png)

这个扩展使用了 [AssemblyScript](https://github.com/AssemblyScript) ，它是 [TypeScript](https://www.typescriptlang.org/) 语法的一个子集，它是静态类型化的，被垃圾收集——内存被自动管理——并被编译成 WebAssembly 代码。

然而 Skopets 澄清说“这不是真正的 JavaScript ”,因为它不能重用 JavaScript 库，尽管它可以重用一些类型脚本库。

总的来说，他说选择 TypeScript 和 AssemblyScript 是因为他说“我们希望解决方案的复杂性与问题的复杂性相匹配”，这意味着寻找熟悉的语法和 NPM 工具箱，以及有助于更高效的开发周期的东西。

对于 Envoy 扩展模型，对于 Envoy 处理的每个 HTTP 请求，都会创建一个单独的 HTTP 过滤器扩展实例。

最后，Skopets 指出，许多分享他的 Java 背景的开发人员认为“filter”一定是无状态的，但他说这正是 Envoy 的独特之处。他在演讲后向新堆栈解释说，当 Envoy 处理单个 HTTP 请求时，它会对自定义 HTTP 过滤器扩展进行多次回调。这可能是对请求头的一次调用，也可能是对请求体的多次调用，再加上对请求头的调用，这取决于请求的大小。

Skopets 说，“因此，如果您的扩展逻辑需要来自请求处理的早期阶段的信息，它必须将其信息持久存储在某个地方(比如)记住‘请求头’，以便能够在处理‘响应头’时使用它们。”"

那么你把这些信息存储在哪里呢？由于 HTTP 过滤器扩展只对应一个请求，他建议所有这些辅助信息都应该存储在 Envoy 扩展本身中。例如:

```
class  ApiValidator  extends  HttpFilter  {
private requestPath:  string;
private requestMethod:  string;
}

```

Skopets 在他的 KubeCon 演讲的最后呼吁通过为各种语言构建惯用的特使 SDK 来为特使开源代码做出贡献。

[在 Github 上分叉这个实例的代码。](https://github.com/yskopets/kubecon2020)

KubeCon + CloudNativeCon 是新堆栈的赞助商。

来自 Pixabay 的 Arek Socha 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>