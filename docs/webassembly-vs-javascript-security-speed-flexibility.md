# WebAssembly 与 JavaScript:安全性、速度、灵活性

> 原文：<https://thenewstack.io/webassembly-vs-javascript-security-speed-flexibility/>

在众所周知的万维网出现之前，有 JavaScript。JavaScript 在 1995 年就已经存在了，当时 Brendan Eich 创造了这种语言来支持 Netscape，这是一种在当时具有革命性的网络浏览器，可惜现在已经不存在了。从那时起，ECMAScript 标准就成为了 web 开发的基础，代表了运行在 web 浏览器中的绝大多数应用程序。

最近，web assembly(Wasm)——实际上已经存在了一段时间——出现了。2019 年万维网联盟(W3C)将其命名为 web 标准后，它也因此成为与 HTML、CSS、JavaScript 并列的第四个 Web 标准。但是，虽然 web [浏览器应用](https://thenewstack.io/wasm-for-the-frontend-a-look-at-developer-uses/)代表了 Wasm 的核心和历史用例，但重点是它被设计为在正确配置的 CPU 上的任何地方运行——这就是 Wasm 和 JavaScript 在某些用例中分叉并变得更加集成的地方。

Wasm 和 JavaScript 仍然保持着紧密的联系，但是 Wasm 除了 JavaScript 之外，还有很多其他的东西。简而言之，Wasm 最初的目的是帮助 JavaScript 在 web 浏览器中更有效地运行，这仍然是他们集成的关键组成部分。这种集成现在已经超出了 web 浏览器的范围，扩展到了边缘和服务器应用程序，对于这些应用程序来说，单独使用 JavaScript 并不是最合适的。

这是由于 Wasm 在 CPU 级别上以二进制格式运行。别忘了，与 JavaScript 不同，Wasm 不是一种编程语言。Wasm 的一个主要优点是，它的功能使它能够容纳除 JavaScript 之外的许多不同的语言，包括 Python、Rust，当然还有 Go。NET，C++，Java 和 PHP。

因此，WebAssembly 可以在需要时集成 JavaScript，但当然不仅限于集成 JavaScript。这种与 JavaScript 的集成和使用是 WebAssembly 和 JavaScript 之间共生的基石，尤其是在 web 应用程序领域。

这是因为 Wasm 可以通过将解释语言及其运行时编译成 Wasm 模块来提高 JavaScript 的性能， [Torsten Volk](https://www.linkedin.com/in/torstenvolk) ，企业管理协会(EMA) 的分析师告诉新堆栈。他说，已经编译过的代码通常会比运行时仍需解释的代码(如 JavaScript)运行得更快。

Wasm 和 JavaScript 集成适用于广泛的应用程序。沃尔克说，它们包括边缘位置基于浏览器的机器学习、性能密集型浏览器游戏、需要低延迟执行的增强和虚拟现实应用，以及通常需要能够快速启动的应用。

此外，虽然 JavaScript 是一种伟大的通用语言，但有时“能够发挥另一种语言的优势”是有意义的， [Fermyon Technologies](https://www.fermyon.com/) 首席执行官[和联合创始人马特·布彻](https://www.linkedin.com/in/mattbutcher/)告诉 New Stack。“用 C++或 Rust 实现繁重的数字运算可能更有效。Python 中的一个包可能已经完全满足了你的需求，”Butcher 说。或者你可能背负着一段复杂的遗留代码，你真的需要在浏览器中运行。WebAssembly 解锁这些用例。”

## 共同的历史

Volk 说，事实上，JavaScript 和 WebAssembly 的历史共同发展是互补的，因为 Wasm 是在 JavaScript 之后大约 20 年才产生的——旨在将 JavaScript 用例扩展到更高性能要求的应用程序工作负载。

“对于纯粹的计算性能，以及图像处理等任务，WebAssembly 无疑表现出了比 JavaScript 快得多的优势。但可以说，背景要比这复杂得多，”沃尔克说。“对于更快的计算时间是否同样重要，这并不是一个真正的问题，例如对于移动和 Web 应用程序的较轻编码任务，需要 JavaScript 代码。”

Butcher 说，虽然 WebAssembly 交互模型的历史重要性可能是为基于浏览器的 JavaScript 代码创建了一种与其他语言编写的库进行交互的方式，但事实证明，WebAssembly 的最终设计才是最重要的。“WebAssembly 对外部环境几乎不做任何假设。重要的是，它没有假设 JavaScript，”他说。"这使得 Wasm 很容易超越浏览器环境."

新的组件模型规范就是一个恰当的例子。Butcher 说，这是因为它描述了任何 WebAssembly 二进制文件如何导入和导出由任何其他 WebAssembly 二进制文件消费的函数。“不需要 JavaScript 这远远超出了 WebAssembly 的原始范围，但由于原始规范的编写方式，这是可以实现的，”Butcher 说。

## 我们能说 WASM 更好吗？

对于纯粹的计算性能，以及像图像处理这样的任务，WebAssembly 已经证明了它的优点，即[比 JavaScript 快得多。但可以说，背景要比这复杂得多。对于更快的计算时间是否同样重要，这并不是一个真正的问题，例如对于移动和 Web 应用程序的较轻编码任务的 JavaScript 代码的需求。](https://thenewstack.io/javascript-vs-wasm-which-is-more-energy-efficient-and-faster/)

“在浏览器中，我认为 WebAssembly 最大的好处是可以使用其他语言的库。性能很好，对 Figma 这样的 web 应用程序很有帮助。但是代码重用广泛适用于许多 web 应用程序，”Butcher 说。

“对于浏览器生态系统，我不认为我们会看到 WebAssembly 超越其辅助性质，它将为 JavaScript 提供附加优势，而不是取代 JavaScript，”他说。“WebAssembly 的真正潜力不仅仅在于浏览器，它的安全沙箱、性能配置文件和易于开发的特性使它非常适合云创新。”

因为 JavaScript 是一种几乎任何人都可以访问的语言，并且提供了许多社区支持的库，这些库“支持大量的用例，而不需要重新发明轮子，”Volk 指出。“Wasm 可以与 ReactJS 和其他流行的 JavaScript 框架相结合，这一事实进一步扩大了 JavaScript 的用例范围，允许开发人员以简单和响应迅速的方式交付成熟的企业应用，”Volk 说。

## 安全材料

与仅部署在 JavaScript 中的代码相比，Wasm 提供了安全优势。当 Wasm 被用作可以部署 JavaScript 应用程序的“类固醇编译器”时，Wasm 可以使 JavaScript 代码更加安全。例如，Wasm 将 JavaScript 与浏览器隔离，确保内存安全，并实现比 JavaScript 的动态类型变量更难利用的强类型变量。“总而言之，在 Wasm 上运行 JavaScript 为整个应用程序提供了一个很好的‘安全升级’，”Volk 说。

事实上，Wasm 在许多方面提供了安全优势。这是因为，正如网络资产管理和治理解决方案提供商 [JupiterOne](https://www.jupiterone.com/) 的首席信息安全官 [Sounil Yu 所说:](https://www.linkedin.com/in/sounil/)

*   Wasm 作为 JavaScript 的编译器，可以通过减少漏洞攻击面、提供更好的内存安全性、隐藏代码、沙箱化执行环境和利用现有的安全生态系统来提高应用的安全性。Wasm 具有有限的指令集和更好的内存管理，这有助于减少漏洞的攻击面，并防止一些常见类型的漏洞，如缓冲区溢出。
*   Wasm 代码通过不可读的晦涩提供了一点安全性，使攻击者更难对代码进行逆向工程，从而更难发现和利用漏洞。
*   Wasm 还可以在沙盒环境中运行，这有助于将代码与系统的其余部分隔离开来，以防止它访问敏感信息或执行非法操作。
*   Wasm 框架，如 CNCF 的 wasmCloud，通过提供更高级别的抽象，进一步扩展了 Wasm 的安全性，减少了开发人员嵌入每个应用程序的代码量。wasmCloud 还减轻了开发人员的安全负担，使签署工件、启用内置监控和自动修补应用程序变得更加容易。

但是我们不要说 JavaScript 天生就不安全。事实上，Javascript“可以变得非常安全，”微软 Azure Core Upstream 的首席项目经理 Ralph Squillace 在电子邮件回复中说。“浏览器是地球上最受攻击的表面之一。然而，WebAssembly 更容易通过数学上可证明的沙盒模型进行深度防御，像 [Veriwasm](https://github.com/plsyssec/veriwasm) 这样的工具就利用了这一点。

“此外，你可以使用即将到来的组件模型来限制攻击面——例如，主机可能甚至不提供文件系统 API——在未来的世界中，这些类型的限制将被证明是至关重要的，”Squillace 说。"但是不要被愚弄了:主机仍然会犯配置错误，给模块太多的权力！"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>