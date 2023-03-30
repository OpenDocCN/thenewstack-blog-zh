# 什么是 web assembly——为什么你会听到这么多？

> 原文：<https://thenewstack.io/what-is-webassembly/>

小龙虾。云闪工人。[打开策略代理](https://www.openpolicyagent.org/)。Shopify 应用程序。微软飞行模拟器。 [Adobe](https://www.adobe.com/) Lightroom 和 [Acrobat](https://medium.com/adobetech/acrobat-on-the-web-powered-by-webassembly-782385e4947e) 的 web 应用版本。WebAssembly (或简称 WASM)开始出现在广泛的工具和平台中。

尽管 WebAssembly 为浏览器带来了 HTML、CSS 和 JavaScript 之外的语言，但它不是 JavaScript 的替代品，它采用了与 Flash、Active X 插件和其他为浏览器封装非 web 代码的技术非常不同的方法。

[https://www.youtube.com/embed/-DVcchn4T_Y](https://www.youtube.com/embed/-DVcchn4T_Y)

视频

把它想象成一个小型、快速、高效且非常安全的基于堆栈的虚拟机，它不关心它在什么 CPU 或 OS 上运行，它被设计成以接近本机的速度执行可移植的字节码——由最初用 C、C++、Rust、Python 或 Ruby 编写的代码编译而成。WebAssembly 不仅在浏览器中运行:它始于客户端，但在服务器上证明非常有用。

这是一个开放的、行业范围的合作项目，旨在将类似汇编语言的性能和安全性与高级语言的便利性结合起来。为了创建 WebAssembly 标准的共享实现而成立的[字节码联盟](https://bytecodealliance.org/)现在包括了主要的参与者，如 [Arm](https://www.arm.com/) 、[英特尔](https://www.intel.com/)、[谷歌](https://about.google/)和[微软](https://www.microsoft.com/)以及 [Mozilla](https://www.mozilla.org/) 和[Fastly](https://www.fastly.com/)——暗示了 WASM 将被广泛采用。

Gartner 的高级分析师 Fintan Ryan 告诉 New Stack 说:“前景和兴奋之处在于便携性和速度的结合。”。

“规范本身是成熟的，它在许多领域得到了应用，从微软的 Blazor 工具包到一些浏览器应用程序，”他补充道。“我们还看到它以有限的方式用于服务网格、边缘设备和一些边缘处理。”

## 安全扩展性

作为一种跨多个平台运行代码的快速、安全和强大的方式，WebAssembly 非常适合运行来自客户或合作伙伴的不受信任的代码，无论是[通过将代码注入已经运行的容器来避免冷启动](https://community.arm.com/developer/research/b/articles/posts/making-faas-awsm-an-efficient-serverless-wasm-runtime-for-the-edge)的无服务器功能，还是在数据库引擎中运行的[内联数据转换，](https://thenewstack.io/webassembly-brings-easy-inline-data-transformations-to-redpanda-kafka-streaming-platform/)[电子商务插件](https://shopify.engineering/shopify-WebAssembly)，Kubernetes 准入策略或[开放策略代理策略规则](https://www.openpolicyagent.org/docs/latest/wasm/)。Istio 和 [Envoy](https://thenewstack.io/wasm-modules-and-envoy-extensibility-explained-part-1/) 支持 WASM 作为其 LUA 运行时的轻量级和更灵活的替代，用于编写支持不同协议的过滤器。[飞行模拟器](https://docs.flightsimulator.com/html/Programming_Tools/WASM/WebAssembly.htm)甚至用 WebAssembly 模块代替 dll。

“任何有扩展机制的项目都可能会利用 WASM 来做到这一点，”[云本地计算基金会](https://www.cncf.io/)首席技术官 [Chris Aniszczyk](https://www.linkedin.com/in/caniszczyk/) 告诉我们。

[矢量化](https://www.linkedin.com/in/alexandergallego/)的创始人兼首席执行官亚历山大·加莱戈走得更远:“JavaScript 在 90 年代末为网络所做的事情，就是 WebAssembly 可以为服务器端应用所做的事情。”

> "这种前景和激动人心之处在于便携性和速度的结合."

— [高德纳公司](https://www.gartner.com/en/experts/fintan-ryan)[的高级分析师芬坦·瑞安](https://www.gartner.com/en)

WASM 的启动时间比 V8 更快，将能够在具有少量内存和存储的物联网设备上运行(潜在的是 1GB 内存和 50MB 存储)。JavaScript 运行时已经针对性能进行了积极的优化；这也将发生在 WASM。当 JavaScript 在浏览器之外运行时，在无服务器环境或不允许 JIT 编译的环境中(在 iOS 或游戏控制台上)，它将从中受益。由于没有冷启动问题，可移植性和低资源消耗将使 WebAssembly 成为 Cloudflare Workers 和 Fastly 的 Compute@edge 等服务上的 Edge 的理想选择。

这种方法是使用浏览器沙箱隔离第三方库的逻辑扩展，如可能有错误或漏洞的字体渲染引擎和图像或音频解码器。但 WebAssembly 也是为了让开发人员更容易创建安全的应用程序(并在依赖第三方代码的同时保持安全)。

因为 WebAssembly 被设计为在浏览器中运行并避免困扰 Flash 和 Active X 的安全问题，所以它被设计为在不损失性能的情况下进行隔离。浏览器需要能够在网页加载时解析、验证和编译 WASM 代码，并且这些代码总是在沙箱中运行。

WebAssembly 旨在尝试并避免各类错误和漏洞，如缓冲区溢出和控制流劫持。因为像 C 和 C++这样的语言使用指向内存中存储变量值的地址的指针，所以 WebAssembly 代码需要一种安全的方式来访问内存中非常特定的部分，而不是其他部分。WebAssembly 使用线性内存块，WebAssembly 模块只能访问分配给它的内存块；模块和之间没有共享内存(至少目前没有)，也没有垃圾收集。

WASM 将代码和数据分开。它有一个带类型检查的静态类型系统和一个非常结构化的控制流，旨在使编写编译安全的代码更容易，线性内存、全局变量和堆栈内存分别访问。这也是 WebAssembly 保持可移植性的一部分。虽然当 WASM 代码执行时，实际运行的机器代码使用寄存器，并且对于运行它的 CPU 来说是非常特定的，但是 WebAssembly 是一个堆栈机器；WebAssembly 不是使用寄存器来存储它正在操作的数据，而是从堆栈中弹出数据来进行操作，并将结果推回到堆栈中。

目前，这些数据只是数字，尽管有人提议添加引用类型——如字符串、序列、记录、变量——以使 WASM 模块更容易与运行在其他运行时或用不同语言编写的模块进行交互。另一个提议，Web IDL 绑定，将让 WASM 模块指定它需要的“胶水”来调用那些新类型将引用的外部对象上的方法。

WASM 模块不能访问操作系统中的 API 和系统调用。如果你想让它与模块外的任何东西交互，你必须显式地导入它，这样你就知道唯一运行的代码是你告诉模块的代码。

WebAssembly 中的安全保障只有沙盒那么好，字节码联盟成员之一 UCSD 已经创建了一个正式的验证器来检查沙盒实现的准确性， [Veriwasm](http://cseweb.ucsd.edu/~dstefan/pubs/johnson:2021:veriwasm.pdf) 。

字节码联盟代表[告诉我们，WASM 仍然会有漏洞。“我们当中没有人是不会犯错的。问题是你如何处理它，你在做什么来降低它的可能性，减轻它的影响？”他说，对于 WebAssembly 的许多新兴用例来说，“安全性只是入门的门票”。](https://www.linkedin.com/in/tillschneidereit/)

## 离开浏览器，进入云端

当 WebAssembly 在浏览器中运行时，浏览器处理其对操作系统功能的访问。对于在浏览器之外运行 WebAssembly，比如在服务器或物联网设备上，一些问题对于云原生开发者来说非常熟悉，比如在没有文件系统的服务上处理文件系统的概念(这是保存代码、配置和共享数据所需要的)。给予代码对操作系统的完全访问权不仅仅是打开了攻击的可能性；它还将代码绑定到特定的操作系统。

为了避免这种情况，WebAssembly 使用了 WebAssembly 系统接口(WASI)。它是一组模块化的系统接口，看起来像一个抽象的操作系统，具有 IO 等低级接口和 cryptography 等高级接口，使 WebAssembly 代码保持可移植性。

这提高了安全性，因为它隔离了模块，并且只给它们对文件系统(或其他资源)和系统调用的特定部分的细粒度权限；不同的模块相互隔离，并限制它们可以传递给任何试图提升权限的恶意代码的内容。它还可以提高性能，例如在容器之间复制数据；不需要在用户和内核空间之间移动数据，而是通过网络发送数据，然后进行反向处理，数据可以通过管道传输到 sidecar，使用更快更简单的调用机制。

正如 Docker 联合创始人 Solomon Hykes 在宣布 WASI 的时候发推文所说，“如果 WASM+WASI 在 2008 年就存在，我们就不需要创建 Docker。”

在浏览器内部，WebAssembly 使用 JavaScript 引擎，Node.js 等环境支持 WebAssembly。在浏览器之外，它需要自己的运行时来实现 WASI——目前有多种 WASM 运行时的实现和多种协议。甚至字节码联盟目前也有三个运行时，其中两个正在合并: [Wasmtime](https://github.com/bytecodealliance/wasmtime) 和 Fastly 的 [Lucet](https://github.com/bytecodealliance/lucet) 运行时，该运行时针对 edge compute 进行了优化，使用提前编译来减少延迟，并正在 Wasmtime 之上进行重写。WAMR， [WebAssembly 微运行时](https://github.com/bytecodealliance/wasm-micro-runtime)，用于资源有限的嵌入式设备；这将是一个独立的运行时。

RedHat 正在构建另一个运行时(也基于 Wasmtime)，它可以使用像 SGX 这样的可信执行环境在不可信的主机上运行敏感的工作负载，这是[机密计算联盟](https://confidentialcomputing.io/)的 [Enarx](https://enarx.io/) 项目的一部分。

其他运行时包括:

*   [Wasmer](https://wasmer.io/) ，服务器端运行时，支持包括 LLVM 在内的多种编译器。
*   [WAVM](https://wavm.github.io/) 使用 LLVM 将 WebAssembly 代码编译成机器码。
*   [Wasm3](https://github.com/wasm3/wasm3) 也专注于嵌入式 app 设备。
*   [Second State 的 WasmEdge](https://www.secondstate.io/) (在被 CNCF 沙盒接受之前被称为 SSVM)专门针对车载应用。
*   像 [Wasmcloud](https://wasmcloud.com/) 这样的平台方法，一个 actor runtime(以前称为 WaSCC)构建在 WebAssembly 之上，用于创建用 AssemblyScript、TinyGo 或 Rust 编写的分布式系统，将 WebAssembly 模块绑定到云服务。

有了这么多不同的方法，不同运行时的性能会有所不同——对 WebAssembly 越来越多的兴趣意味着我们正处于前寒武纪工具大爆发时期，新的选项不断涌现，一些旧的工具停止开发或不支持完整的规范。这些全面的基准测试有助于了解什么是最新的，以及生态系统的发展速度，但 WASI 和 WebAssembly 本身都是一项正在进行的工作。

Schneidereit 建议说:“对于 WebAssembly 生态系统来说，这种数量的实验是非常健康的，我们需要一系列不同的人来尝试不同的解决方案。我认为这对开发人员来说太棒了:他们可以混合搭配不同的方法来解决用例的不同方面，并有相当多的不同实现可供选择。”

他承认这确实给开发人员带来了决定采用哪种方法的负担，随着 W3C 标准化的继续，其中一些将被 WebAssembly 组件和[模块链接](https://github.com/WebAssembly/module-linking)等提议所取代。“我们最终会看到一些方法成为赢家，另一些逐渐消失。从长远来看，人们没有兴趣为他们可能瞄准的所有东西提供专有的利基解决方案。”

## 革新云开发

出于显而易见的原因， [WebAssembly 是结合 JavaScript 使用](https://thenewstack.io/what-is-webassembly-and-why-do-you-need-it/)的一个好选择。[彭博](https://www.bloomberg.com/company/)的 JavaScript 基础设施和工具团队的负责人[罗布·帕尔默](https://www.linkedin.com/in/robpalmer2)告诉我们:“WebAssembly 的优势在于高性能、对固定形状数据的数值计算以及类型化数据结构。”。“它允许高性能应用程序和高性能库与(开发人员)用来构建应用程序的同一 JavaScript 集成。”

当 WebAssembly 作为平台的一部分得到支持时，它是最容易使用的，就像 Wasmcloud 中的 CLI 或 [Redpanda Transforms](https://vectorized.io/blog/wasm-architecture/) 中的 rpk 工具。

> “我们最终会看到一些方法成为赢家，另一些逐渐消失。从长远来看，人们没有兴趣为他们可能瞄准的所有东西提供专有的利基解决方案。”

— [直到 Schneidereit](https://www.linkedin.com/in/tillschneidereit/) ，字节码联盟

除此之外，WASM 的开发者体验通常涉及定制绑定，可能是复杂的工具链和多步工作流。[更好的工具](https://github.com/vshymanskyy/awesome-wasm-tools)开始到来，[不仅仅是为了生锈。](https://github.com/bytecodealliance/wasm-tools)十几种语言都有可以生成 WebAssembly 二进制文件的编译器——但它们仍然是零散的。

新工具包括:

Ryan 指出:“它仍处于初期阶段，有许多(快速改进的)工具链设置工作要做，这可能会让一些人感到畏惧。”。“如果你来自一个系统背景，感觉还好；从网络背景来说，就不那么好了。尤其是 Rust 社区，在这个领域做了很多工作。我们也看到 AssemblyScript 正在进行有趣的工作。”(那是[编译成 WebAssembly 的 TypeScript](https://www.assemblyscript.org/) 的变体)。

为了让 WebAssembly 成为主流，它需要像编译任何其他二进制文件一样容易，如果工具容易集成到开发人员已经工作的方式中，并且在开发人员想要的环境中可用。

Schneidereit 说:“我们今年试图做的一件关键事情是将已经在标准化轨道上走了一段时间的东西投入生产准备。”这包括将 Rust、WASM 和 JavaScript 的易用性集成到其他语言和环境中。

“我们正在积极致力于所有这些东西的实现的生产质量，以便我们可以将它们送到开发人员手中，集成到开发人员想要的环境中。”

不过，对于一些开发人员来说，WebAssembly 看起来更像是一个功能性的打包决策。Krustlets 和 [Blazor](https://dotnet.microsoft.com/apps/aspnet/web-apps/blazor) 已经将 WASM 作为一种交付复杂环境的方式:Krustlet 是 KuberNETes 节点，Blazor 是. net。NET 运行时集成到 WebAssembly 沙箱中，所以只要应用程序需要的库都包含在内。NET 代码可以在 WASM 内部的浏览器中运行。 [WebContainers](https://blog.stackblitz.com/posts/introducing-webcontainers/) 将 Node.js 放在 WebAssembly 内部运行 Visual Studio 代码(可以把它看作 GitHub Codespaces 的替代方案)。

这种包装将给 WebAssembly 带来巨大的发展空间。 [TC39](https://github.com/tc39) 联席主席 [Brian Terlson](https://www.linkedin.com/in/brian-terlson-6822aa61) 对 WebAssembly“非常看好”,因为在 10 年后，它可能会成为云计算基础设施的基础部分，从而彻底改变可编程性模型。

“这是一种未来的可移植可执行格式，具有许多非常好的功能:非常轻量级，真正跨平台，并与 Web 组装系统接口相结合，你可以想象未来你不需要 Node 或任何东西，因为你可以只构建一个本地可执行文件，并附带 Node 或 Deno，”Terlson 告诉我们。“您可以在边缘运行小型 WebAssembly 程序，距离您的客户很近，实现超低延迟。”

## 生产率的提高

但是云开发的最大优势不仅仅是不受信任代码的安全性。Terlson 建议，这是开发者和为他们构建 SDK 的云服务提供商的生产力。

想象一下，一个开发人员正在尝试像 Azure Service Bus 这样的云消息服务；他们希望通过将消息放入队列来测试他们的代码，并且他们希望在他们使用的任何语言中这都是容易的。仅仅使用 Azure CLI 就意味着下载一个 Python 解释器，因为这是实现它的语言。如果它实现了期待已久的“编写一次，在任何地方运行”的承诺，WebAssembly 可以彻底改变这一点。

“我们没有一个简单的工具，只是在队列中抛出一个消息，开发人员真的要求将这些工具构建到他们的开发工作流程中，”Terlson 说。“Azure 支持这么多不同的语言，我们不能用每种语言反复编写相同的工具。我们需要一种技术，让我们能够将一个非常小巧、简单的工具封装在某种信封中，让我们能够将其打包，并以多种不同的语言公开。WASI 的网络组装可能就是这种技术。”(Schneidereit 告诉我们，Fastly 在构建 WebAssembly 工具时已经利用了这种可移植工具的早期版本。)

扩大这个想法，泰尔森相信 WebAssembly 可以极大地简化云编程模型。

“我认为未来 WebAssembly 与一些云原生应用的运行时相结合，将会极大地清理这个故事，”他说。“我可以带任何我想要的语言。我可以带来任何 PaaS 基础设施和 WebAssembly 运行时将它粘合在一起，只需很少的工作。我可以在云中运行我的应用程序，我可以在边缘运行我的应用程序，我可以在本地运行它。对我这个开发者来说无所谓；它只是运行。”

*更正:本文之前提到过 WaSCC，现在被称为 Wasmcloud。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>