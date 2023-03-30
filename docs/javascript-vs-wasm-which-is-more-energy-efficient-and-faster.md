# JavaScript 和 WebAssembly:哪个更节能更快？

> 原文：<https://thenewstack.io/javascript-vs-wasm-which-is-more-energy-efficient-and-faster/>

哪个运行更快更节能: [JavaScript](https://thenewstack.io/javascript-developers-on-what-matters-and-whats-next/) 和 [WebAssembly](https://thenewstack.io/key-concepts/wasm/) ？葡萄牙米尼奥大学研究了这个问题，并得出结论:虽然在实验室微基准测试中，JavaScript 可能比 Wasm 更节能、更快，但在实际应用中，Wasm 在速度和能效方面比 JavaScript 更出色——有时平均高出 30%。

这还是在 [Wasm](https://thenewstack.io/wasm-for-the-frontend-a-look-at-developer-uses/) 还处于早期的时候。

“Wasm 仍处于起步阶段，只有时间能告诉我们它将如何发展，”该研究的作者软件工程师 joo De Macedo 通过电子邮件告诉新的堆栈。“在我们最大胆的预测中，我们看到 Wasm 完全将本地应用从操作系统中挤出，并使网络浏览器成为 21 世纪的操作系统。”

## 微基准测试与真实应用

这项研究于 2022 年发表，研究了真实世界的基准和微观基准。

“微基准是一个程序，它跟踪和测量单个明确定义的任务的性能，如运行时间、运行速率、带宽等。，”德马塞多解释道。“微基准测试是衡量软件系统性能的主要方法之一，因此，Wasm 也不例外。

他补充说，由于 Wasm 的主要目标之一是提高 Web 应用程序的性能，“比较 Wasm 和 JS 的运行时间和[能源性能](https://thenewstack.io/reduce-co2-emissions-and-cost-by-increasing-software-efficiency/)尤其重要”。

说到微基准，在某些情况下，JavaScript 可能比 Wasm 更节能、更快。虽然 Wasm 更节能，在谷歌 Chrome 和微软 Edge 上的表现优于 JavaScript，但 JavaScript 在 Mozilla Firefox 上的表现确实优于 Wasm，“大多数时候都有显著差异”。

也就是说，最终 Wasm 仍然在现实世界的应用程序中占据主导地位。

“初步结果显示，WebAssembly 虽然仍处于起步阶段，但已经开始超越 JavaScript，还有更大的增长空间，”报告称。"统计分析表明，与 JavaScript 相比，WebAssembly 产生了显著的性能差异."

## JavaScript 与 Wasm 研究的工作原理

这项研究通过 [Wasmboy 基准](https://wasmboy.app/benchmark/)来观察 Wasm 和 JavaScript 在现实世界应用中的表现，这是一个 Gameboy/Gameboy 颜色仿真器，用[类型脚本](https://thenewstack.io/key-concepts/typescript/)编写，以基准测试 Wasm。Wasmboy 是用 JavaScript/TypeScript 编写的，创建它的主要目的是比较 AssemblyScript 编译器产生的 Wasm 和 TypeScript 编译器产生的 JavaScript 的 [ES6 最新版本之间的运行时性能。](https://www.w3schools.com/js/js_versions.asp)

“这款游戏控制台包括六款不同的开源游戏，可以通过该控制台运行，”报告称。“我们更新了 WasmBoy 源代码，以便指定游戏必须在哪个浏览器中执行。”

因此，在三种浏览器上运行的六款游戏——Chrome、Edge 和 Firefox——使用两种语言，该团队总共有 36 个独特的样本。

他们还使用了[PSP PDF kit 基准](https://pspdfkit.com/blog/2018/a-real-world-webassembly-benchmark/)，它使用的软件支持在任何平台上查看、注释和填写 PDF 文档中的表单。该报告指出，创建开源基准是为了评估将软件移植到 Wasm 生态系统的可能性，并将 Wasm 与 JavaScript 实现进行比较。该团队对应用程序的源代码进行了修改，以两种语言(was 和 asm.js)执行几个输入。为了使用真实的输入来执行基准测试，该团队考虑了五个不同的 pdf 文档，包括一本分为三个部分的书、一篇科学论文和一个包含 20 张幻灯片的幻灯片演示。

报告称，“类似于 Wasmboy 基准测试，我们开发了 makefiles 来自动化不同浏览器中的执行”，结果在三种浏览器中的每种语言中产生了五个样本，用于 30 个不同的程序执行。

它还研究了各种微观基准；这些程序最初是用 C 编写的，并使用 Emscripten 编译器编译成 Wasm 和 JavaScript。其他可以用来编译 Wasm 的语言有 C/ [C++](https://thenewstack.io/google-launches-carbon-an-experimental-replacement-for-c/) ， [Rust](https://thenewstack.io/what-rust-brings-to-frontend-and-web-development/) ，Go，Python 和 [AssemblyScript](https://thenewstack.io/webassembly-developers-lust-for-rust-and-assemblyscript-but-not-go/) ，一种类型脚本的形式。

有关微基准和研究其他方面的详细信息，请阅读若昂·德马塞多(joo De Macedo)、鲁伊·阿布雷乌(Rui Abreu)、鲁伊·佩雷拉(Rui Pereira)和若昂·萨拉瓦(joo Sara iva)撰写的“[web assembly vs JavaScript:Energy and Runtime Performance](https://ieeexplore.ieee.org/document/9830108)”一文，德马塞多(De Macedo)的硕士论文可在 Engineers.org 电气与电子研究所(Institute of Electrical and Electronics)或[免费订阅。](https://drive.google.com/file/d/1a4rYPiXdumL3ZMaBsPgiaBLKtzFPdg2A/view?usp=sharing)

然而，总而言之，这种方法允许团队查看，例如，JS 和 Wasm 如何不同地处理规模和输入大小。之前的一项研究使用了这种方法，但只研究了虚拟机的性能。德马塞多的研究希望着眼于现实世界的应用，因此该团队开发了一个框架来衡量基于浏览器的环境中的性能。

## Wasm 作为 JavaScript 的替代品？

我问德马塞多 Wasm 最终会不会取代 JavaScript。

“也许永远不会，因为 JS 对不需要超性能的网页更有意义，”他回应道。“目前，Wasm 是 JS 的补充，而不是替代。然而，如果 Wasm 得到进一步开发，它可能会在一些应用程序中取代 JS，因为它的加载时间更快，资源利用更有效。”

德马塞多预测，从长远来看，Wasm 将是破坏性的。

“Wasm 不仅会彻底改变网络，”他说。“WebAssembly 的承诺有可能颠覆技术市场的多个领域，包括云，云最近越来越多地转向容器模型，而容器模型并不总是满足每个组织的需求。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>