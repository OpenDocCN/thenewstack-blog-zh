# WebAssembly 的 Wasmtime 1.0 改进了安全性和性能

> 原文：<https://thenewstack.io/webassemblys-wasmtime-1-0-revamps-security-performance/>

WebAssembly 运行时 Wasmtime 1.0 版已经发布，其中的更新改进了 [Wasmtime](https://wasmtime.dev/) 的安全状态和性能。这是一个酝酿了一年的更新。

更新的一个原因是平台开发者将 WebAssembly 带到了浏览器之外。这意味着它也在浏览器的沙盒环境之外， [Lin Clark](https://github.com/linclark) 说，他是 Fastly 的高级首席软件工程师，也是 [WebAssembly 系统接口(WASI)](https://thenewstack.io/mozilla-extends-webassembly-beyond-the-browser-with-wasi/) 小组和[字节码联盟](https://bytecodealliance.org/)的主席。该联盟是一个开源联盟，致力于构建 WebAssembly 和 WASI 等标准。Mozilla、Fastly、Intel 和 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 都是创始成员。

Clark 在关于新版本的博客[中指出，浏览器外的用例是运行时发挥作用的地方，允许 WebAssembly 在浏览器外安全运行。](https://bytecodealliance.org/articles/wasmtime-1-0-fast-safe-and-production-ready)

“他们……认为你只需下载 WebAssembly 代码，在你的计算机上运行，并拥有对文件系统的完全权限，这是非常危险的，”林周四在发布前告诉新堆栈。“这就是我们成立字节码联盟的原因之一——确保当 WebAssembly 从浏览器使用案例中转移到浏览器使用案例之外时，我们能确保保持强大的安全性。”

## 运行时性能提高

字节码联盟已经在测试新运行时的公司中看到了改进的性能结果。Clark 在她的文章和 TNS 中强调了几个例子:

*   去年 7 月，Shopify 切换到了 Wasmtime ，执行性能平均提高了大约 50%。
*   Fastly 在今年 3 月切换到 Wasmtime，发现执行时间提高了约 50%，每秒可服务的 eqests 增加了 72%至 163%。
*   DFINITY 于 2021 年 5 月使用 Wasmtime 推出了其[区块链](https://thenewstack.io/are-application-specific-chains-the-future-of-blockchain/)，自那以来，已经为超过 150，000 份智能合同执行了超过 1，000 亿条指令，没有出现任何生产问题。

在一篇关于联盟如何实现性能提升的[帖子中，Fastly 软件工程师兼字节码联盟成员](https://bytecodealliance.org/articles/wasmtime-10-performance) [Chris Fallin](https://github.com/cfallin) 解释了它是如何工作的，以及他们如何专注于优化运行时和编译器。

“当 Wasmtime 执行 Wasm 程序时，CPU 既执行从 Wasm 字节码编译的本机指令，也执行‘Wasmtime 运行时’的一部分，Wasmtime 运行时是 Wasmtime 的一部分，它维护数据结构以帮助实现 Wasm 语义，”他说。对于这两个执行阶段中的每一个，都有两个阶段:启动/初始化(Wasm 代码的编译和运行时的初始化)，以及稳态执行

为了提高速度，团队专注于优化每个阶段，特别是:

*   是时候在联盟的编译器 [Cranelift](https://github.com/bytecodealliance/wasmtime/tree/main/cranelift) 中编译代码了。
*   Cranelift 中生成代码的速度。
*   在 Wasmtime 中实例化 Wasm 模块的时间。
*   Wasmtime 中运行时原语的速度。

## Wasm 中的安全性

使 WebAssembly 既安全又快速的一个原因是事件之间的隔离。每个 Wasm 模块都有自己的状态，不会影响其他模块的状态，这在由[尼克·菲茨杰拉德](https://github.com/fitzgen)撰写的[字节码联盟文章](https://bytecodealliance.org/articles/security-and-correctness-in-wasmtime)中有详细说明。

文章指出，这使得运行不受信任的 WebAssembly 程序变得安全，因为程序“不能读写内存的外部区域，不能将控制权转移给进程中的任意代码，也不能自由访问网络和文件系统”。该程序无法逃离沙箱，从其他系统窃取私人数据或在服务器上运行僵尸网络。

“但是这些安全属性只有在 WebAssembly 运行时的实现是正确的情况下才成立，”文章警告说。

Wasmtime 是在 [Rust](https://thenewstack.io/bryan-cantrill-on-rust-and-the-future-of-low-latency-systems/) 中实现的，这有助于它避免“一整类错误，而不牺牲我们有效实现语言运行时所需的底层控制，”这篇文章说。然而，Rust 并没有让 Wasmtime 免受其他问题的困扰，例如编译器中“由于逻辑错误而导致的错误编译”可能会从沙箱中逃脱。

这篇文章的其余部分致力于解释新的更新如何通过以下方式解决这些问题:

*   使用 cargo vet，这是一个 Mozilla 开发的工具，可以确保 Firefox 中使用的所有第三方 Rust 库都经过可信的审计员的手动审查。
*   提供任务之间的隔离，这样一个 bug 就不会自动感染所有其他后续任务，这是可能的，因为 Wasmtime 的快速实例化。
*   不断起毛。“ [Fuzzing 是一种软件测试技术](https://thenewstack.io/developers-are-buzzing-on-fuzzing/)，它通过将伪随机数据输入到你正在测试的系统中来发现安全性和正确性问题，”文章指出。"我们每天 24 小时不间断地在后台进行模糊处理."它继续解释了联盟接受“模糊驱动开发”的所有方式
*   Wasmtime 和 Cranelift 的形式验证。
*   缓解[幽灵袭击的步骤](https://www.malwarebytes.com/blog/news/2021/05/spectre-attacks-come-back-from-the-dead)。

## WebAssembly 的用例

Clark 说，WebAssembly 的好处和用途通常分为四个方面。第一，速度快。Clark 说，虽然虚拟机、容器或 JavaScript isolate 可以执行一些相同的启动和拆卸，但 WebAssembly 可以做得更快。例如，Fastly 使用 WebAssembly 为 edge 运行无服务器功能。

克拉克告诉 TNS:“JavaScript 隔离是所有隔离中最快的，启动一个 JavaScript 隔离需要 5 毫秒，而 WebAssembly 实例需要 5 微秒。”“有了 WebAssembly，启动和拆卸速度可以提高几个数量级。”

Clark 说，WebAssembly 还为开发人员提供了语言中立性，因为它使开发人员能够在一个无服务器的功能中运行许多不同种类的语言。

WebAssembly 还可以用在数据库、分析和事件流用例中。

“当你有一个数据库，你有很多代码和数据之间的通信，来来回回，你做一个查询，你得到一些数据给代码，然后代码处理它，然后根据结果向数据库请求更多的数据，它只是不停地来来回回，来来回回，来来回回，”克拉克说。“如果您只是让这些处理代码在数据库内部运行，速度会快很多……但如果没有安全保障，您就无法做到这一点。WebAssembly 可以给你那些在数据库内运行的安全保证。”

她补充说，WebAssembly 的另一个类似用途是第三方插件系统，并以 Shopify 在商务中的应用为例。

“以前，Shopify 基本上会在主要的 Shopify 代码库之外运行这个插件，有很多延迟，当他们有 flash 销售时，它就会崩溃，”Clark 解释说。“他们使用 WebAssembly 在代码库中运行第三方代码，以便能够保持极短的延迟，并根据需要进行扩展，而不会危及用户流的安全。”

另外两个小众用例是便携式客户端，如 [BBC 的 iPlayer](https://www.bbc.co.uk/iplayer) 和[可信执行环境](https://www.trustonic.com/technical-articles/what-is-a-trusted-execution-environment-tee/)，用于高安全性的情况。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>