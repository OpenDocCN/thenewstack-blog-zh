# WebAssembly 要考虑的 6 个安全风险

> 原文：<https://thenewstack.io/6-security-risks-to-consider-with-webassembly/>

程序和应用程序是数字形式的思想表现。如果你能用其他语言梦想它，WebAssembly 可以把它交付给浏览器。从 Unity 移植的游戏到 web 上的 PDF 编辑，以及利用 Jupyter 和 Rust 的[交互数据](https://www.youtube.com/watch?v=5dl_m_6T2bU)，WebAssembly 的用例数不胜数。

WebAssembly (Wasm)正在获得交付高性能客户端代码的动力，这些代码通常不能由 JavaScript 创建或执行，至少不能以高性能的方式执行。这种复杂性通常超出了 JavaScript 有效处理它的能力，更适合 C#和 Rust 等其他编程语言。作为一个可移植的编译目标，Wasm 使得 C#和 [Rust](https://thenewstack.io/adoption-of-rust-whos-using-it-and-how/) 能够用于 web 应用。

WebAssembly 已经被像 [Figma 和 Google Earth](https://madewithwebassembly.com/) 这样的高流量、高容量和高知名度的公司所使用，并且许多公司也在寻求开始使用它。你可以在网上找到一些很棒的 Wasm 入门指南，帮助你构建第一个基于 Wasm 的应用。然而，尽管它越来越受欢迎，但没有一项技术不存在安全风险。因此，如果你对开始使用 [Wasm](https://thenewstack.io/what-makes-wasm-different/) 感到兴奋，你需要使用一些护栏，这篇文章将指导你记住一些安全注意事项。

## **什么是 WebAssembly？**

WebAssembly 是用于在 web 上执行代码的低级二进制格式。它旨在用作编译目标，运行起来高效而快速。Wasm 通过压缩成二进制格式的类似汇编的低级语言，使其他编程语言在浏览器中可用。

## **WebAssembly 的目标**

Wasm 旨在提供广泛的 JavaScript web 应用程序无法与之竞争的性能水平。WebAssembly 的创建并不是为了取代 [JavaScript](https://thenewstack.io/javascript-developers-on-what-matters-and-whats-next/) ，而是通过为 web 应用提供一个安全高效的执行环境，作为其他语言和浏览器之间的编译桥梁。

此外，Wasm 旨在使 web 开发人员能够轻松地将代码从其他平台移植到 web 上。代码可以通过浏览器在网上访问，而不是依赖于平台。

## **web assembly 如何工作**

WebAssembly 是一个 web 标准，它定义了二进制格式和相应的类似汇编的文本格式，以便在 web 上执行。它被设计为高级语言(如 C/C++/Rust)编译的可移植目标，支持客户端和服务器应用程序在 web 上的部署。

web 标准定义了一组核心指令、相应的类似汇编程序的文本格式以及用于加载和运行 Wasm 代码的 JavaScript API。它还建立了一个运行时环境，包括内存模型、垃圾收集和异常。二进制格式旨在以最小的占用空间高效、快速地解析。

Wasm 的未编译文本格式是以人为中心的方法创建的，更易于阅读和调试。表面上看， [WebAssembly](https://thenewstack.io/the-latest-milestones-on-webassemblys-road-to-maturity/) 程序看起来像 TypeScript，它也有 JavaScript 没有的额外功能，比如强类型和垃圾收集原语。JavaScript API 提供了一种加载 WebAssembly 代码、实例化和运行它以及访问其导出的方法。API 还提供了一种创建和操作核心指令所使用的 WebAssembly 内存和表格的方法。

## 【WebAssembly 需要考虑的 6 个安全风险

WebAssembly 是编译和运行 web 应用程序的一种安全高效的格式。然而，在使用这种技术时，需要记住一些限制。让我们来看看其中的一些。

## **WebAssembly 沙盒**

当谈到网络浏览器时，在安全性和功能性之间有一场持续的战斗。一方面，浏览器必须是安全的，以保护用户免受恶意行为者的侵害。另一方面，浏览器需要能够让用户在网上做他们需要做的事情。

与 WebAssembly 相关的最大风险之一是它限制了漏洞的可见性。WebAssembly 必须在沙箱环境中运行，通常与 JavaScript 沙箱相同。

这可能会有问题，因为 WebAssembly 在一定程度上仍然依赖 JavaScript 来执行它需要做的事情。与 JavaScript 的混合意味着它也继承了[基于 JavaScript 的漏洞](https://www.forcepoint.com/blog/x-labs/webassembly-potentials-and-pitfalls)。一个好的做法是对 Wasm 使用与保护 Javascript 代码相同的安全预防措施和措施。

## **内存管理**

WebAssembly 的内存管理问题主要是因为它是一个虚拟机。Wasm 没有专用的物理内存。相反，它依赖于主机的内存。像内存泄漏这样的问题更成问题，因为 JavaScript 通常会自动清理，而静态语言要求这个过程是显式的。

如果 Wasm 程序超出了声明的最大值或达到了浏览器的限制，程序可能会崩溃，给用户带来不愉快的体验。为了防止这种情况，C++程序有像 [emscripten](https://emscripten.org/docs/introducing_emscripten/index.html) 这样的工具链，它带有[杀毒软件](https://emscripten.org/docs/debugging/Sanitizers.html)，可以帮助调试。

## **线性记忆**

虽然 JavaScript 和 WebAssembly 都在浏览器中运行，但这并不意味着这两种语言可以无缝地相互交流。从 JavaScript 调用 WebAssembly 会导致巨大的内存开销，因为这两种语言在不同的内存模型下运行。

JavaScript 使用垃圾收集堆，而 WebAssembly 使用线性内存空间。这意味着当从 JavaScript 调用 WebAssembly 时，需要将 WebAssembly 线性内存空间复制到 JavaScript 堆中，导致内存使用量增加。

## **堆栈管理**

当执行 WebAssembly 程序时，代码被下载并存储在内存中。这个内存分为两部分:堆栈和堆。堆栈用于存储局部变量和函数参数，而堆用于存储全局变量和动态数据结构。

该堆栈由 WebAssembly 运行时自动管理。当一个函数被调用时，一个新的堆栈框架被创建在堆栈的顶部。这个堆栈框架包含函数的局部变量和参数。当函数返回时，堆栈帧被销毁，先前的堆栈帧再次变为活动状态。

另一方面，堆是由程序员手工管理的。当不再需要堆分配的对象时，必须显式释放它们，否则会发生内存泄漏。确保堆分配的对象在被释放后不被访问也是程序员的责任。

## **代码混淆**

WebAssembly 可用于创建难以理解或逆向工程的代码。代码被编译成二进制格式，然后由虚拟机执行，所以它不是人类可读的，也很难调试。

如果恶意参与者可以将代码注入 WebAssembly 模块，他们就可以控制执行代码的机器。他们可以窃取敏感数据，甚至接管整个机器。通过 WebAssembly 增加代码注入的[案例导致机器接管以挖掘加密货币。](https://thehackernews.com/2022/07/hackers-increasingly-using-webassembly.html)

当扫描漏洞时，最好的方法是直接进入源代码本身。这意味着在编译和部署之前检查问题、错误、潜在的内存泄漏、安全漏洞和标准的 [OWASP 十大](https://www.jit.io/blog/the-in-depth-guide-to-owasps-top-10-vulnerabilities)问题。

## **缺乏完整性检查**

[完整性检查](https://www.jit.io/blog/6-essential-steps-to-use-owasp-zap-for-penetration-testing)是确保数据不被篡改的安全措施。有几种方法可以执行完整性检查，但最常用的是使用校验和。校验和是根据文件中的数据计算的值。如果文件的数据发生变化，校验和也会发生变化。通过将文件的校验和与唯一值进行比较，可以检测出文件是否被修改过。

完整性检查对于安全性至关重要，因为它们有助于检测攻击者是否篡改了文件。例如，攻击者可能会修改文件以绕过安全检查或添加恶意代码。完整性检查还可以检测文件是否意外损坏。

WebAssembly 没有内置的完整性检查方法。然而，使用 JavaScript 在 WebAssembly 模块上执行完整性检查是可能的，这就是像 Jit 这样的[安全集成工具](https://www.jit.io/security-tools)可以提供帮助的地方。不对 WebAssembly 模块执行完整性检查的风险包括被篡改的模块在未被检测到的情况下被执行，以及损坏的模块导致意外行为的可能性。

能够在浏览器中运行非基于 JavaScript 的语言是一个令人兴奋的前景。WebAssembly 很棒，但是它不是没有风险的。因此，如果您的团队使用 Wasm，那么您的应用程序很有可能容易受到攻击。Jit 通过构建在开源工具上的易于实现的持续安全计划，帮助您确保您的 WebAssembly 应用程序和云编排能够抵御不良因素。你可以[试试这里](https://platform.jit.io/login?distinctID=182f4433453df9-018717c8be199b-26021d51-e1000-182f4433454d52&items=)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>