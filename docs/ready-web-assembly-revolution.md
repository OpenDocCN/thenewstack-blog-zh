# 你准备好迎接网络组装革命了吗？

> 原文：<https://thenewstack.io/ready-web-assembly-revolution/>

想象有一天你可以用你选择的任何语言(静态类型)编写一个 web 应用程序。不再摆弄 JavaScript，甚至 HTML 或 CSS。你开发的应用程序也会运行得更快。

这是 [WebAssembly](http://webassembly.org/) (WASM)背后的开发者的梦想，这是一个新的项目，将 web 应用程序打包成低级字节码，由 web 浏览器运行。我们通过网飞高级软件工程师[杰伊·菲尔普斯](https://twitter.com/_jayphelps)了解了 WASM，他上个月在北卡罗莱纳州罗利的[万物开放](https://allthingsopen.org)会议上做了一个关于 WASM 的演讲。

今天， [JavaScript](/tag/javascript/) 是用于构建 web 应用程序的主要语言。所有的浏览器都支持它；它是用来学习的。但是不能保证它将永远是默认语言。

“我认为我们最终会使用一种今天甚至不存在的语言，”菲尔普斯说。相反，可能演变的将是一种专门针对 web 应用程序而设计的全新语言。

有了 WASM，开发人员可以用 C、C++或 Rust 编写他们的程序——将来还会支持其他静态类型的语言——然后编译成低级字节码，浏览器可以在虚拟机中执行。

通过将应用程序逻辑转换成字节码，它的加载和执行应该会更快，至少与 JavaScript 相比是这样，JavaScript 仍然需要浏览器花费相当多的时间来执行。“它从一开始就被设计得很快，”菲尔普斯谈到 WASM 时说。此外，因为它实际上是在沙箱中运行，所以它也更安全，因为恶意代码不会接触到主机(尽管[有些人对这种方法表示担心](https://news.ycombinator.com/item?id=10487713)最终用户无法访问源代码，就像传统的 Web 情况一样)。

至少从 20 年前的 Java 小程序开始，就有人试图将二进制代码带到网络上，Java 小程序笨重且加载缓慢，主要是因为它们完全在浏览器环境之外运行。最近，谷歌尝试了此类工作，如原生客户端(Native Client )( T10 )( T11 ),该客户端因 WASM 而被终止。

有些类似的是 [ASM.js](http://asmjs.org/) ，它提供了一种编译 JavaScript 优化子集的方法。然而，Phelps 警告说，JavaScript 并不是一种真正适合编译的语言，因为它是动态类型的，在代码中提供了太多的变化，很容易被编译器消化。

然而，与早期的尝试不同，WASM 似乎实际上是一种势头。菲尔普斯说:“这是第一次所有的浏览器制造商，甚至 Edge，都参与进来并制定规范。”对浏览器制造商的部分吸引力在于，他们不必从头开始生成新的虚拟机来运行字节码；他们可以使用他们的 JavaScript 虚拟机来代替。

WebAssembly 现在的最佳用途是那些需要大量 CPU 的 web 应用程序。较小的程序从浏览器调用它们的时间会滞后。菲尔普斯说:“只有当你有一些繁重计算任务时，你才会想要跨越这个界限。”。视频编码或游戏是主要的潜在用途。游戏引擎提供商 [Unity](https://unity3d.com/) 组装了一个演示游戏，其中包括围绕虚拟沙箱驾驶坦克。

[以太坊](https://ethereum.org/)区块链平台甚至正在研究在服务器上运行 WebAssembly 的可能性(这项工作提出了 WebAssembly 不仅用于浏览器，甚至作为独立的跨平台开发环境的有趣可能性，费尔普斯指出)。

首先，下载 [WebAssembly](https://mbebenita.github.io/WasmExplorer/) Explorer，它提供了一种输入 C 或 C++并返回 WebAssembly 代码的方法。编写 WebAssembly 最常见的方式是通过 [Emscripten](http://kripken.github.io/emscripten-site/) ，通过[底层虚拟机](http://llvm.org/) (LLVM)编译的 C 和 C++代码生成 JavaScript。一个独立的 JavaScript 文件将挂载 WebAssembly，或者，如果是一个完整的页面应用程序，它可以直接挂载到 HTML。

得益于 Mozilla 基金会的资助，[web pack JavaScript](https://webpack.js.org/)dependency bundler 增加了对 WebAssembly 的一级支持。这将允许开发人员将他们的 C++或 Rust 代码自动编译成 JavaScript 项目。

由 Mozilla、微软和谷歌于 2015 年推出的 WebAssembly 仍有一些工作要做。今年早些时候发布了最低可行产品(MVP)。但是除了通过 JavaScript 接口之外，仍然不能直接访问任何 web APIs 来实现系统调用等功能。最终，计划将是让 WebAssembly 直接与浏览器对话。需要某种形式的垃圾收集来回收不再使用的内存。还有多线程能力方面的工作，尽管现在这在某种程度上通过 [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers) 得到支持。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>