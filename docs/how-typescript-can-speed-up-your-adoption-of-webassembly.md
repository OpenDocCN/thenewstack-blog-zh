# TypeScript 如何加快您对 WebAssembly 的采用

> 原文：<https://thenewstack.io/how-typescript-can-speed-up-your-adoption-of-webassembly/>

WebAssembly，也被称为 WASM，被吹捧为 2022 年值得关注的[顶级云本土趋势之一。WASM——一种快速、安全和强大的跨平台运行代码的方式——与容器运行时有着惊人的相似之处。许多项目和创业公司都在致力于加速它的采用。](https://thenewstack.io/5-cloud-native-trends-to-watch-out-for-in-2022/)

这项技术相对较新——它在不到五年前首次发布。因此，正如 Gartner 的高级分析师 [Fintan Ryan](https://www.gartner.com/en/experts/fintan-ryan) 在[之前的一篇新文章](https://thenewstack.io/what-is-webassembly/)中指出的那样，仍有许多工作要做，以改进工具链的设置。

对于那些有 web 开发背景的人来说，WASM 的新奇和围绕它的快速创新可能会令人望而生畏，然而，关于 [TypeScript](https://www.typescriptlang.org/) ，一种基于 [JavaScript](https://thenewstack.io/javascript-forecast-whats-ahead-for-ecmascript-2022/) 的强类型语言的知识，可能会让迈出第一步不那么令人生畏。

## WebAssembly 的复杂性

JavaScript 并没有被设计成 web 的编译目标。由于它的普遍性和较低的入门门槛，它最终成为了一个。但是 JavaScript 也带来了一些陷阱。

尽管可移植性强且速度快，但在复杂的 web 应用程序中，JavaScript 的性能是不可预测的。这为设计一个快速、安全、可移植、高性能的网络编译目标铺平了道路，也为这些工作的标准化铺平了道路。

输入 WebAssembly。作为编译目标，字节码格式和相关的文本代码格式几乎可以被任何平台的浏览器使用，它几乎在所有这些方面都取得了胜利。

但是看一眼编译后的代码就足以让程序员感到害怕，因为它缺少编程语言提供的所有高级抽象。虽然它的目的不是手工编写，因为它被设计成一个编译目标，但采用者确实需要学习一种可以编译成 WASM 的语言。

虽然编译器是为 C、C++和 Rust 等类型化语言开发的，但那些没有 JavaScript 等类型系统的编译器被抛在了后面，因为 WASM 本身就是静态类型的。

直到 2017 年， [AssemblyScript](https://www.assemblyscript.org/) 才进入生态系统，并消除了网络开发人员如果想利用 WASM 的好处就必须学习一门新语言的需求。

## 什么是 AssemblyScript？

作为 TypeScript 的一种变体，AssemblyScript 以 WASM 功能集为目标，并允许程序员对他们的代码进行低级别的控制。和 TypeScript 一样，AssemblyScript 也是开源的。

AssemblyScript 的[文档](https://www.assemblyscript.org/basics.html)声明，“与面向 JavaScript 环境及其所有动态特性的 TypeScript 不同，AssemblyScript 面向 WebAssembly 及其所有静态保证，因此有意避免 JavaScript 的动态性，因为它无法提前有效编译*。”*

 *与编译成 JavaScript 的 TypeScript 不同，AssemblyScript 由 [Binaryen](https://github.com/WebAssembly/binaryen) 直接编译成 WebAssembly，与更高的速度和性能相关。

## AssemblyScript 有什么帮助？

如果 JavaScript 是您首选的编程语言，那么 TypeScript 几乎就是它的超集，在保持语法相似的同时增加了可选的静态类型。如前所述，AssemblyScript 是 TypeScript 的一个更严格的变体，这意味着不需要从头开始，因此采用者能够基于现有的知识。

无服务器引擎公司 Suborbital 的创始人兼首席执行官康纳·希克斯(Connor Hicks )告诉新堆栈:“TypeScript，JavaScript 的静态类型变体，是一种广泛采用且易于理解的网络应用类型安全系统。

“由于 WebAssembly 是非常强类型的，所以使用 TypeScript 语法创建一种语言对于 web 开发人员来说很有意义，可以轻松地用 WASM 进行构建，”Hicks 说。“AssemblyScript 是开发人员使用熟悉的语言同时获得 WebAssembly 的性能和可移植性优势的最简单方法之一”

然而，即使它与 TypeScript 有一些相似之处，AssemblyScript 也不应被误认为是它的子集。需要考虑行为和特定于特性的意外，因为毕竟它们是针对两个非常不同的目标进行编译的。

快速浏览一下文档就足以理解，在开发 AssemblyScript 时，使 JavaScript(和 TypeScript)成为 web 开发人员最爱的特性已经被剥离了。

无论这意味着缺少像`any`、`void`和`undefined`这样的通用操作符，还是由于 WebAssembly 模块在沙箱中运行而缺少 DOM 访问，AssemblyScript(和 WebAssembly)的采用肯定会带来很多文化和思维方式的转变。

随着更大的成熟，TypeScript 的一些重要特性，比如对所有函数的闭包支持，[将可能被整合到 AssemblyScript](https://github.com/AssemblyScript/assemblyscript/wiki/Status-and-Roadmap) 中。然而，人们必须记住，虽然熟悉 TypeScript 可能是通过 AssemblyScript 采用 WebAssembly 的垫脚石，但请记住 AssemblyScript 不是 TypeScript 的确切子集。

因为它是为 WebAssembly 量身定制的，AssemblyScript 的发展将与 WebAssembly 规范的开发方式紧密相连。如果您了解 Typescript，那么它和 AssemblyScript 在语法上有很多相似之处，但后者是用熟悉的语言元素编写一个全新的故事。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*