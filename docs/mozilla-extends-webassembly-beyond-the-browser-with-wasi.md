# Mozilla 通过 WASI 将 WebAssembly 扩展到了浏览器之外

> 原文：<https://thenewstack.io/mozilla-extends-webassembly-beyond-the-browser-with-wasi/>

Mozilla 的 [WebAssembly](https://webassembly.org/) 一开始是一个实验，几乎是一个问题:有没有可能在不破坏浏览器沙盒的情况下在浏览器中运行任意代码？一个附带的好处是更快的 web 应用程序将超越当前的 web 技术，允许开发人员将现有的桌面应用程序带到 web 上。

这是一个适时到来的实验。微软放弃了它的 ActiveX 插件模型，谷歌也放弃了它的 NaCl 工具。旧的 web 开发模式正在迅速消失，被大量的安全漏洞和缺乏跨平台兼容性所冲刷。

自最初推出以来，WebAssembly 已经被所有主流浏览器采用，并得到了 Mozilla、Google、Microsoft 和 Apple 的支持，它们都贡献了代码。

WebAssembly 被认为是虚拟机的定义，它与浏览器的 JavaScript 引擎一起工作，以与本机代码相当的速度运行代码。与 JavaScript 的字节码方法不同，它采用 C 和 C#等熟悉语言编写的代码，在最终编译为二进制之前，先将其转换为类似汇编语言的字节码。WebAssembly 可执行文件在被[交付给浏览器](https://thenewstack.io/ready-web-assembly-revolution/)之前被编译，这使得它们成为向 web 应用程序添加复杂功能的一种紧凑而高效的方式。

WebAssembly 有很多值得喜欢的地方，并且它已经开始影响关于流行 web 框架的想法。微软正在试验将其作为 ASP.NET 核心应用平台的浏览器内扩展 [Blazor](https://blazor.net/) 的基础。

其他公司一直在考虑将它完全从浏览器中移除。随着 Node.js 等基于 JavaScript 的工具在无服务器和其他云架构中的使用越来越多，这是一个有意义的举动——即使只是将熟悉的开发环境引入新的工作方式。

在浏览器之外进行 WebAssembly 的实验非常好，但是如果它要成为一个支持跨平台和跨浏览器开发的工具，它需要围绕它建立新的标准。Mozilla 最近宣布了这一努力的开始，发布了第一个 WASI:web assembly 系统接口。

> 您也许可以将 WASI 视为运行在主机平台上的系统级代码和运行在用户模式下的应用程序之间的界限。

WebAssembly 是虚拟处理器的实现， [WASI](https://wasi.dev/) 更进一步，为开发者提供了一个完整的概念操作系统。对于虚拟处理器，只有一个目标架构，JavaScript 引擎可以处理其实现与 ARM、Intel、Power 或您拥有的任何硬件之间的转换。WASI 也做了同样的事情，为 WebAssembly 程序提供自己的通用操作系统功能的底层实现，然后通过主机 JavaScript 引擎将其转换为操作系统调用。在你的代码中以 WASI 为目标，你就能够开发出在 macOS、Windows、UNIX 等平台上运行完全相同的应用程序，甚至可以在移动操作系统上运行。

像 WASI 这样的系统界面是一个基本的操作系统概念。这就是我们的应用程序使用系统调用的方式，例如以受保护的方式读写文件。操作系统不会出现内存错误，应用程序可以保证读取或写入不会被另一个应用程序破坏，或者一个调用的结果不会被传递给进行相同调用的另一个应用程序。您也许可以将 WASI 视为运行在主机平台上的系统级代码和运行在用户模式下的应用程序之间的界限。

同样重要的是要注意，您不会编写直接访问 WASI 接口的代码。相反，这些将是在 WebAssembly 中实现的，相当于我们在大多数通用语言中使用的标准库。这样我们就知道，如果我们通过 WASI 在 WebAssembly 中运行一个 C 应用程序，一个 **printf** 命令将会写入一个控制台，不管它是在 Windows 还是 UNIX 上。WASI 实现了 WebAssembly 编译器的接口，底层的 JavaScript 引擎处理对它运行的任何操作系统的实际系统调用。您不需要为代码的每个目标操作系统安装合适的标准库，您只需要编译一次。

使用 WASI 作为编译器和运行时的提前组合的一部分将减少与当前 JavaScript 引擎相关的开销。代码可以根据需要发送到服务器，由支持 WASI 的 WebAssembly 编译器编译，然后在实现 WASI 系统接口的 JavaScript 运行时上运行。当调用代码时，不需要调用 JIT 编译器:WebAssembly 二进制文件将被加载并准备运行。

已经有三个 WASI 的实现，Mozilla 自己的实现和一个允许任何人在浏览器中体验 WASI 的 polyfill。从开发者的角度来看，最有趣的可能是来自 edge delivery network Fastly。它的 [Lucet WebAssembly](https://www.fastly.com/blog/announcing-lucet-fastly-native-webassembly-compiler-runtime) 编译器现在也是一个运行时，在 GitHub 上有一个[开源版本](https://github.com/fastly/lucet)。目前，它被用于 Fastly 的实验性边缘服务 Terrarium，被视为运行在谷歌 V8 引擎上的 JavaScript 的快速替代品。

在一篇博客文章中， [Pat Hickey](https://www.fastly.com/blog/pat-hickey) ，Fastly 的高级软件工程师，描述 Lucet 能够“在不到 50 微秒的时间内实例化 WebAssembly 模块，只需要几千字节的内存开销。相比之下，Chromium 的 V8 引擎实例化 JavaScript 或 WebAssembly 程序需要大约 5 毫秒和数十兆字节的内存开销。

像 Lucet 这样服务是边缘计算的重要工具。开发人员可以用他们选择的语言编写代码，编译成 WebAssembly，然后以接近本机的速度运行，而不必了解底层边缘服务的架构。它还允许服务提供商使用异构硬件来部署适当的计算服务器以满足位置和负载需求。例如，ARM 服务器可以部署在电源有问题的地方，而英特尔或 AMD 服务器可以处理更繁重的工作负载。服务提供商也有机会使用它来试验替代平台，如 RISC-V 或 Power，而不会中断工作负载。

很容易看到 WASI 在网络边缘的用途，为云服务处理卸载计算，或为物联网或无服务器服务(如 [CloudFlare 的 Workers](https://www.cloudflare.com/products/cloudflare-workers/) )加速消息路由。WASI 有很多值得喜欢的地方，像 Lucet 这样的开源实现应该会大大加快人们的接受速度。通过向虚拟机添加一个新的抽象层，它避免了在可移植代码中支持本机系统接口的陷阱，在它们所属的 JavaScript 运行时处理它们。在接下来的几年里，看看在它的基础上构建了什么将会是一件有趣的事情——也许更有趣的是，谁来构建它。

来自 Pixabay 的 Peter H 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>