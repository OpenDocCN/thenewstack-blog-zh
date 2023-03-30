# 异构处理需要数据并行化:SYCL 和 DPC++是一个很好的开始

> 原文：<https://thenewstack.io/heterogeneous-processing-requires-data-parallelization-tools-sycl-and-dpc-are-a-good-start/>

[](https://www.linkedin.com/in/jamesreinders/)

[James Reinders](https://www.linkedin.com/in/jamesreinders/)

[James Reinders，英特尔工程师，拥有三十多年的并行计算经验，是十本与并行编程相关的技术书籍的作者/合著者/编辑。James 在英特尔工作，致力于促进异构(XPU)世界中的并行编程。](https://www.linkedin.com/in/jamesreinders/)

[](https://www.linkedin.com/in/jamesreinders/)[](https://www.linkedin.com/in/jamesreinders/)

我喜欢说“这都是关于 XPUs 的。”

我们正处于一个美好的时代，硬件创新正在导致 CPU、GPU、FPGAs、DSP、ASICs 等产品的爆炸式增长，我只是将其简称为 XPUs。XPUs 是任何类型的“处理单元”的简称——任何可以帮助我的应用程序计算的硬件。

作为开发人员，XPUs 的冲击意味着我们越来越多地面临为更多不同的处理单元编写代码的挑战。我们的任务是考虑额外的时间和资金，重新编写和测试代码，以提高新架构的应用性能。比以往任何时候，为了保持我们的理智和代码的可维护性，最重要的是我们编写的代码适用于尽可能多的 xpu。移动到跨架构模型进行应用程序开发已经表明，它可以为组织节省大量的时间和金钱，随着异构计算的流行，这成为一个更加紧迫的问题。

今天正在进行的是一场反思，因为我们的世界正在迅速变成一个 XPUs 的世界，这将最终改变所有的计算。

## XPUs:重塑软件加速计算

CUDA 是一个广泛使用的专有软件编程系统，它是为 Nvidia GPUs 设计的，并且非常有效。OpenCL 采用了开放的方法，并获得了一定程度的多厂商支持。OpenCL 有自己的缺点——最明显的是以 C 为中心，不能很好地满足 C++的需求。

CUDA 和 OpenCL 很好地实现了它们的目的。展望未来，开发人员需要一个真正开放的多厂商方法来帮助实现 XPUs 的承诺。

## 为什么 SYCL 和数据并行 C++ (DPC++)提供了最佳的前进道路

CUDA 和 OpenCL 的经验为基于 C++的异构系统数据并行性的真正流行和开放的解决方案的出现奠定了基础。这个解决方案就是 SYCL，它是一个更高级的编程模型，可以提高在多个硬件加速器上的编程效率。它很快获得了广泛的多供应商支持、广泛的兴趣和多个重要编译器项目的支持。

SYCL 很重要，因为在我们日益多样化的世界中，有效的编程要求我们为所有的 xpu 提供高性能的访问。只有真正开放的方法才能做到这一点。

SYCL 是异构硬件的单源 C++数据并行编程(XPUs)的开放标准。SYCL 允许用 C++进行单源编译，以系统上的多个设备为目标，而不是对主机使用 C++和对设备使用特定于域的内核语言。

SYCL 给 C++带来了内核风格的编程和在系统中定位、查询和使用加速器的机制。基于内核的编程是利用数据并行性的一种重要编程方式，OpenCL 和 CUDA 也支持这种方式。OpenCL 以前引入了以标准方式枚举和访问加速器的能力。

还可以看看 DPC++(数据并行 C++)，它为 LLVM 社区提供了一个开放的实现，目标是将所有东西都移植到 LLVM C++编译器中。DPC++的目标是用一些扩展实现 SYCL。DPC++开创了许多现在出现在 SYCL 2020 中的特性，因此甚至在标准尚未成熟之前，就已经在 SYCL 2020 的大部分实现上领先一步。与整个 SYCL 2020 规范完全一致的工作仍有待完成；所有的工作都很容易在非常活跃的[开源库](https://github.com/intel/llvm)中观察到。DPC++被[英特尔](https://software.intel.com/content/www/us/en/develop/tools/oneapi/base-toolkit.html)用来针对英特尔 CPU、GPU 和 FPGAs。DPC++也被 [Codeplay](https://www.hpcwire.com/2020/02/04/codeplay-open-sources-a-version-of-computecpp-for-nvidia-gpus/) 用来针对 Nvidia GPUs。另一款 SYCL 编译器 [hipSYCL](https://github.com/illuhad/hipSYCL) ，通过连接 AMD 的 HIP/ROCm，支持 AMD 的 CPU 和 GPU。为 SYCL 提供多种开源编译器对社区来说太棒了，这表明 SYCL 拥有广泛、多样和开放的支持。

在 2019 年和 2020 年期间，我与一个专门的小团队合作，创作了第一本关于 SYCL 和 DPC++的书。你可以从[新闻网站](https://www.apress.com/us/book/9781484255735)下载一份免费的。发布后不久，Khronos 宣布了最终确定的 SYCL 2020 规格。

最近 SYCL 2020 规范的批准是一个重要的里程碑。它确实是一个开放的规范，有着光明的未来；该规范是行业内许多敬业的个人多年来规范开发的产物。SYCL 2020 基于 C++17，能够更轻松地加速标准 C++应用，并推动与 ISO C++路线图更加一致。Khronos Group 在他们的 SYCL 2020 公告中强调了 SYCL 2020 的许多功能，包括支持统一共享内存、内置缩减、广泛使用 CTAD 和符合标准 C++原子的原子操作。

## XPU 是未来，为了 XPU 多样性和编程健全性的好处，让我们保持开放

SYCL 和 DPC++将帮助我们有效地使用 XPUs。它们是对 XPUs 支持的更广泛推动的一部分，扩展到库和所有软件开发工具，建立在 SYCL 及其编译器的雄心之上。这就是 oneAPI 行业计划的由来，我对这个计划充满热情，当我重新加入英特尔时，我很高兴成为其中的一员。对这个主题的支持——减轻开放使用所有 xpu 的挑战——正在推动人们对 SYCL 和 oneAPI 的兴趣。一个坚实的例子是 oneAPI 深度神经网络库(oneDNN)的使用，最初针对英特尔处理器进行了高度优化，加速了世界上最快的计算机(采用 Arm 处理器)。因此，oneDNN 现在也有了强有力支持。SYCL 和 oneAPI 库和工具的开放性有助于开创一个开放和性能的新时代，使我们能够对所有 xpu 进行有用的编程访问。

总之，软件开发人员社区有机会创建服务于整个行业的标准，包括 SYCL，并强烈支持异构编程(XPUs)和现代 C++的采用，因为它包含并行性。

SYCL 提供了一个开放标准，具有广泛的支持、大量的参与能力、多种开源实现和看似无限的可能性。DPC++提供了一个开放的基于 LLVM 的编译器来减少支持 SYCL 的工作量，并鼓励跨 XPUs 的强兼容性。oneAPI 提供了一个论坛来讨论和推动 XPUs 在软件开发的各个方面的开放和高性能访问。

我希望你能抓住机会了解 SYCL、DPC++和 oneAPI，因为 XPUs 是计算的未来。我们应该在开放的环境中共同塑造对 xpu 的支持，享受 xpu 巨大多样性的好处，以便我们有效地编程。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>