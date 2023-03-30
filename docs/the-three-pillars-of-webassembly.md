# WebAssembly 的三大支柱

> 原文：<https://thenewstack.io/the-three-pillars-of-webassembly/>

围绕 [WebAssembly](https://webassembly.org/) 的软件业正在兴起。这项技术通常被称为 WASM，它正在改变我们的代码在网络浏览器、边缘云、物联网设备等环境中的执行方式。我在过去写过关于 WebAssembly 不同方面的文章，所以如果你想了解更多的上下文，那么[给](https://thenewstack.io/why-webassembly-modules-could-be-the-new-de-facto-unit-of-compute/) [那些](https://blog.suborbital.dev/building-for-a-future-based-on-webassembly)一个[阅读](https://blog.suborbital.dev/get-started-with-webassembly-using-typescript-part-1)。

今天，我将从更高的层面谈论 WASM 的特别之处，为什么您应该关注它，以及为什么我相信它将在未来几年推动新一代软件的发展。我将阐述 WebAssembly 的三大支柱——安全性、便携性和性能——并概述为什么它们使 WASM 成为一股不可忽视的力量。

## 安全性

 [康纳·希克斯

Connor 是加拿大渥太华的一名开发人员，从事安全和分布式系统项目。他在 1Password 领导产品开发，并建立亚轨道开源项目。Connor 坚信将安全性和隐私构建到所有软件的核心中，并正在利用 WebAssembly 等技术探索下一代 web 服务开发。](https://suborbital.dev) 

先说安全。如今，随着供应链问题、密码劫持和数据泄露成为常见的新闻故事，它成为了许多人关注的焦点。WebAssembly 从其安全沙箱开始，以多种方式为安全之战带来了一些重要武器。

当 WASM 被执行时，代码不能访问任何东西，包括网络、文件系统或任何现成的东西。这就是所谓的默认拒绝安全模型，它不是由 Docker 等容器技术实现的。为了让运行在 WASM 沙箱中的代码与外部世界进行交互，必须显式授予它访问宿主函数的权限。

web 浏览器可以授予 WASM 模块某些能力，比如`fetch` API 和对 DOM 的访问。云环境等其他主机可以使用 WASI(web assembly 系统接口)来授予模块对文件系统、随机性(如`/dev/urandom`)和系统时间等常见事物的访问权限。所有这些确保了 WASM 模块中的代码只能访问它运行所需的资源，仅此而已。

为了对抗供应链攻击的增加，也有[努力](https://github.com/WebAssembly/design/issues/1413)使 WebAssembly 模块的加密签名成为规范的标准部分。使用可信密钥对模块进行签名并在系统试图运行该模块时验证签名的能力将是一大优势，并有助于在使用 WebAssembly 构建应用程序时巩固“深度防御”的思想。

当软件供应商开始将他们的 API 库作为 WASM 模块分发时，这将变得尤其重要；我们将能够利用跨语言模块链接(由不同语言构建的模块共享内存和功能的能力)，还可以验证模块是由供应商生产的，并且没有被篡改。

## 轻便

链接模块的想法将我们带到了第二个支柱，可移植性。我喜欢从两个方面考虑 WASM 的可移植性:语言可移植性和平台可移植性。语言可移植性是用一种语言编写的模块(如 Rust)在用另一种语言编写的系统(如 Go)中运行的能力。因为 WASM 运行时可以嵌入到其他软件中，所以它们可以用来引入在团队的主要语言中不可能实现的特殊组件。这一概念也可以应用于通过将用不同语言编写的多个 WASM 模块组合在一起以形成一个软件的应用程序，例如由我们的公司[亚轨道](https://suborbital.dev)维护的 [Atmo](https://github.com/suborbital/atmo) 框架。

关于平台可移植性，WebAssembly 不依赖于任何硬件架构，因此它可以在几个不同的平台上执行，而无需重新编译。例如，这将允许您生成单个 WASM 文件，并在物联网设备和云虚拟机上运行它。当 WASM 模块被执行时，它被提前(AOT)或实时(JIT)编译成机器本机代码。

Chrome 的 V8、Wasmtime 或 Wasmer 等 WASM 运行时会自动执行这种编译，这使得运行任何模块都非常简单。例如，当流量峰值导致某个模块受到传入请求的冲击时，我可以看到这在您的代码自动从中央云实例移动到边缘计算网络的场景中变得非常有用。

## 表演

这就给我们留下了最后一个支柱，性能。WebAssembly 旨在以本机或接近本机的速度执行代码。影响任何应用程序性能的因素有很多，包括语言、硬件、垃圾收集、虚拟化等等。

WebAssembly 是代码的一种表示形式，通过在运行时针对每个平台优化自身，可以轻松地以高性能的方式执行。我们仍然处于 WebAssembly 的早期，但它已经可以与 V8 JavaScript 引擎的性能相媲美，后者已经优化了无数年。所有编译到 WebAssembly 的语言都将受益于 WASM 运行时未来带来的任何性能改进，这对每个人来说都是一大胜利。

我邀请您思考您正在构建的软件，并问自己开发平台的哪些方面对您最重要。我敢打赌，我在这里讨论的三个支柱中至少有两个是您的业务的关键因素，并且您将能够通过采用 WebAssembly 作为一种技术来改进代码的关键属性。人们希望 WASM 将成为一种底层技术，为软件工作流提供动力，而开发人员根本不需要太关心它，就像大多数开发人员不关心他们语言的编译器生成的汇编代码一样。

主要的区别在于，WebAssembly 从一开始就内置了这些很棒的属性，以确保您的代码在默认情况下是安全的、可移植的和高性能的，这对于今天的软件工具来说是不可能的。

[https://www.youtube.com/embed/Qu1CEdbLDRs?feature=oembed](https://www.youtube.com/embed/Qu1CEdbLDRs?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>