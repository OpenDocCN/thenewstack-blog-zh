# 面向前端的 Wasm:看看开发者用例

> 原文：<https://thenewstack.io/wasm-for-the-frontend-a-look-at-developer-uses/>

当 Second State 在 2019 年开始时，WebAssembly 的主要用例是在区块链，用于运行智能合同。

“你真的需要一个轻量级的环境，一个运行它们(区块链)的沙箱，而 Docker——或一般的容器——对那来说太重了，因为在 6 秒钟的时间里，你必须做 1000 次这样的操作，”Second State 的首席执行官 Michael Yuan 说。

相反，这家总部位于奥斯汀的初创公司专注于为 [WasmEdge](https://github.com/WasmEdge/WasmEdge) 提供支持，这是一个针对云原生、边缘和分散应用的 WebAssembly 运行时。WasmEdge 是一个开源的官方沙盒项目，由[云本地计算基金会(CNCF)](https://cncf.io/?utm_content=inline-mention) 主持，这是一个开源的、厂商中立的中心。WasmEdge 源自与 [WasmTime](https://wasmtime.dev/) 相同的标准，是一个[字节码联盟](https://bytecodealliance.org/)项目。基本上，他们是一样的，袁告诉新的堆栈。

“然而，我认为我们独特的产品或功能是围绕它的开发工具和 API，”Yeon 说。“例如，我们被嵌入到 Docker 桌面中，因此每个 [Docker 用户都会得到 WasmEdge](https://thenewstack.io/when-wasm-and-docker-work-and-do-not-work-together/) 实例的副本。”

他补充说，应用程序可以用 Rust 或 JavaScript 编写，并运行在 Wasm 容器中，而不是更传统的 Linux 容器中。Kubernetes 可以管理这两种类型的容器。

## Wasm 用于前端

然而，当在前端使用 Wasm 时，它最常用于支持无服务器功能，袁解释道。例如，抖音已经为无服务器部署了 Wasm。在那个用例中，Wasm 在浏览器中运行。他说，另一个更广泛部署的用例是从后端向前端提供动态内容。

“后端可以有服务，或者现在，更常见的是使用无服务器功能或微服务，”他告诉新堆栈。

袁补充说，Wasm 和 JavaScript 之间的关系很复杂。他说，当 Wasm 第一次在浏览器中启动时，它被广泛认为是 JavaScript 的补充。JavaScript 对于某些功能来说太慢了，它的替代品，浏览器中的 [C++](https://thenewstack.io/c-23-standard-wont-have-a-key-parallelism-feature/) 应用程序，也太不安全了。

“这就是 WebAssembly 的来源，”他说。“有很多公司都这么做，比如 T2 的 fig ma T3。所有主流浏览器都有 WebAssembly 运行时，但这些都是由比如说[谷歌](https://thenewstack.io/google-brings-rust-into-chromium-project/)和[苹果](https://thenewstack.io/apple-plans-to-run-most-of-its-compute-management-on-kubernetes/)编写的 WebAssembly 运行时。这是事情的一个方面——Wasm 与 JavaScript 并行运行。”

当程序需要做计算工作，JavaScript 的处理时间太慢，或者开发人员想要使用 C++库时，可以使用 Wasm。该库可以传递给位于浏览器中的 WebAssembly 运行时。在 2019 年之前，这是最常见的用例，今天仍在广泛使用。

## BFF —前端的后端

他说，前端开发者应该了解 WasmEdge 和其他 Wasm 运行时的另一个原因是前端开发者正在做更多的后端工作。有很多[BFF](https://thenewstack.io/secure-the-web-with-an-api-driven-backend-for-frontend/)——前端的后端。

“前端开发人员过去只关心前端，但自从出现了 [Vercel](https://thenewstack.io/vercels-frontend-and-the-rise-of-the-hybrid-developer/) 、 [Netlify](https://thenewstack.io/netlify-ceo-on-why-netlify-edge-functions-was-built-on-deno/) 和类似的公司，我认为他们正在做更多传统上被称为后端的工作，”他说。“现在，他们称之为无服务器功能或边缘功能，这意味着服务功能可以做各种不同的事情。它可以做数据库的事情，虽然不太常见，但在 Vercel 的上下文中，它做了很多服务器端的渲染，所以我们没有在浏览器中渲染机架组件，而是在服务器上渲染它们。我们称之为云原生 WebAssembly 运行时，运行在浏览器之外。”

他补充道, [Rust](https://thenewstack.io/key-concepts/rust/) 可能是编译成 Wasm 最常见的语言。Typescript 也编译成 Wasm。

“WasmEdge 的一个独特之处在于，我们将 JavaScript 运行时及其整个 [Node.js 堆栈](https://thenewstack.io/why-netflix-rolled-its-own-node-js-functions-as-a-service-runtime/)移植到了 WasmEdge 中。所以你可以在 WasmEdge 内部的服务器上运行 Node.js，在前端，你有一个常规的 React.js 应用程序。

他说，在 Linux 容器中运行所有的 JS 需要几百兆字节。相比之下，在 Wasm 容器或 WasmEdge 中运行 Node.js 只有 510 兆字节。这种大小上的差异在人工智能推理中尤为重要，人工智能推理是使用一个模型来预测，比如说，面部识别。

“它节省了十倍的空间，而且在性能上也是如此，”他说。"这就是 JavaScript 人对此更感兴趣的主要原因."

他说，后端支持前端的另一个用例是在数据库或数据处理管道中部署 Wasm，与 Kafka 消息队列相连。

“对我来说，这确实是过去五年中出现的一个大趋势:前端开发人员正在转向后端？”袁说。“许多公司和许多工具都是围绕这个想法建立的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>