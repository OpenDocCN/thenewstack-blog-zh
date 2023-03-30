# 什么是 WebAssembly，为什么需要它？

> 原文：<https://thenewstack.io/what-is-webassembly-and-why-do-you-need-it/>

这篇文章开始了一系列的教程来帮助开发者和其他好奇的人理解 WebAssembly 的基础知识，作者是 TNS 开源记者 Jack Wallen。请经常回来查看更新。

[WebAssembly](https://thenewstack.io/what-is-webassembly/) (也称为 WASM)于 2017 年推出，作为基于堆栈的虚拟机的二进制指令格式，开发用于在现代网络浏览器中运行，以在现代处理器(包括网络浏览器)上提供代码的“[高效执行和紧凑表示。](https://www.w3.org/2019/12/pressrelease-wasm-rec.html.en)

有了 [WebAssembly](https://webassembly.org/) 你可以使用开放的 web 平台技术和各种语言开发高性能的 web 应用程序。WebAssembly 使创建视频、音频、图形、3D 环境、多媒体游戏、加密计算甚至可移植语言实现成为可能。最重要的是，与标准工具相比，WebAssembly [提供了显著的性能提升](https://thenewstack.io/what-is-webassembly/)。它本身并不是作为一种语言来使用的，而是作为 C、C++和 Rust(所有这些语言都设计得非常快)等语言的有效编译目标。

WebAssembly 是一个开放标准，其创建目标如下:

*   以接近本地的速度执行。
*   可读性强，易于调试。
*   注意安全。
*   不要断网。

## 但是为什么是 WebAssembly 呢？

传统上，人们认为网络有两个组成部分:

*   一台虚拟机
*   一组 Web APIs

很长一段时间以来，JavaScript 一直是虚拟机中运行的主要语言，它在这方面做得很好。然而，现代用例已经说明了 JavaScript 最大的问题之一——性能。当运行资源密集型应用程序时，如 3D 游戏、VR 和增强现实以及视频编辑，我们看到 JavaScript 无法提供接近原生的性能。再加上下载、解析和编译更大的基于 JavaScript 的应用程序的计算成本，这个问题变得更加突出。

尽管 WebAssembly 是一种与 JavaScript 完全不同的语言，但它并不打算取代 JavaScript，而是与 JavaScript 并行运行。这样，开发人员可以为他们的应用程序获得两全其美的效果。而且，与 JavaScript 不同，WebAssembly 是一种低级的、类似汇编的语言，具有紧凑的二进制格式。这使得 WebAssembly 能够提供接近原生的性能。

随着越来越多的云原生、移动优先开发的进行，接近原生的性能对于一些应用程序以对消费者可行的方式运行变得至关重要。

使用 WebAssembly 的主要好处是:

*   近乎自然的表现。
*   安全。
*   调试简单。
*   开源。
*   独立于硬件、语言和平台。
*   轻量级。

WebAssembly 有八个关键对象。这些对象是:

*   WebAssembly。模块–该对象包含已经由浏览器预编译的无状态 WebAssembly 代码。
*   **网络组装。global**–该对象表示一个全局变量实例，可从 JavaScript 访问，并可跨 WebAssembly.Module 的一个或多个实例导入/导出。
*   **网络大会。instance**–这个对象是 WebAssembly.Module 的一个有状态的可执行实例。
*   WebAssembly。memory–这个对象是一个可调整大小的 ArrayBuffer 或 SharedArrayBuffer，它保存 WebAssembly.Instance 访问的原始内存字节。
*   **web 组装。table**–这个对象是一个存储函数引用的 JavaScript 包装器。
*   **web 汇编。compile error**–该对象指示解码或验证过程中的错误。
*   **web 汇编。link error**–该对象指示模块实例化过程中的错误。
*   **web 汇编。runtime error**–该对象是当 WebAssembly 指定陷阱时抛出的错误。

## 在钻研 WebAssembly 之前，你应该知道些什么？

在开始使用 WebAssembly 进行开发之前，您至少应该了解 JavaScript 如何在浏览器环境中运行。您还应该能够自如地使用命令行界面。了解 C 和 C++知识也是一个重要的优势。

## WebAssembly 是如何工作的？

简而言之，使用 WebAssembly 创建有五个步骤:

1.  安装 [Emscripten](https://github.com/emscripten-core/emsdk) 核心(一个基于 LLVM/Clang 的编译器，将 C 和 C++源代码编译成 WebAssembly)和所需的工具链。
2.  用 C、C++或 Rust 编写代码。
3.  用 Emscripten 将代码编译成 WebAssembly。
4.  将编译后的 WebAssembly 代码(通过粘合代码)转换成 HTML 页面。
5.  通过 HTTP 为您的新应用提供服务。

## WebAssembly 用例

WebAssembly 有很多用例。一些可能性包括:

*   绿地/多平台开发。
*   从纯桌面迁移到基于桌面和浏览器的应用。
*   更新用 Silverlight 编写的旧应用程序。
*   与旧平台的向后兼容性。
*   渐进式网络应用。
*   移动应用。

你还会发现很多用 WebAssembly 构建的网站。像这样的网站:

你还会发现任何运行 [Unity](https://unity.com) 游戏的网站都使用 WebAssembly。WebAssembly 也完全能够构建基于网络的应用程序，用于文字处理、电子表格、演示、幻灯片、照片/视频编辑等等。尽管 WebAssembly 可能不是目前使用最广泛的技术，但它正在逐渐普及。[截至 2020 年](https://www.sec.cs.tu-bs.de/pubs/2019a-dimva.pdf)，绝大多数 WebAssembly 被用于加密挖掘和游戏。然而，考虑到 web 和移动应用程序发展的本质，我预计在不久的将来会有越来越多的 WebAssembly 被部署。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>