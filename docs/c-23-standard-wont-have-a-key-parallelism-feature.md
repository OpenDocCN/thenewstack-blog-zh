# C++ 23 标准没有关键的并行特性

> 原文：<https://thenewstack.io/c-23-standard-wont-have-a-key-parallelism-feature/>

明年即将到来的下一个版本的 C++ 标准将不会有一个关键的特性，使得编写在[并行计算](https://thenewstack.io/introducing-tigergraph-native-parallel-graph-database/)环境中执行的代码变得更加容易。

C++ 2023 标准不会有称为发送者和接收者的异步算法功能，这将允许在具有多个芯片(如 CPU 和 GPU)的系统上同时执行代码。

“我们的目标可能是尝试将其纳入明年的工作草案——[ c++ 26]工作草案——这样一旦它出现，人们就会更加认真地对待它，”阿贡国家实验室高级领导设施的计算机科学家、 [C++](https://thenewstack.io/google-launches-carbon-an-experimental-replacement-for-c/) 委员会成员[内文·利伯](https://www.linkedin.com/in/nevinliber/)在上个月的[超级计算 2022](https://sc22.supercomputing.org/) 大会的分组会议上说。

## 根本性的变化

用 C++编写的软件应用正在经历根本性的变化，PC、服务器和移动设备在多个芯片上同时执行代码。发送方和接收方的目标是更新标准 C++框架，以便程序员可以更容易地编写利用新执行环境的应用程序。

程序员越来越多地为 CPU 和加速器(如 GPU 和 AI 芯片)编写代码，这对更快地执行应用程序很重要。

“虽然 C++标准库有丰富的并发原语集…和较低级别的构建块…但我们缺乏 C++程序员迫切需要的异步和并行的标准词汇和框架，”一份描绘该提案的文档说。

## 发送者和接收者

目前，C++代码必须针对特定的硬件进行优化。但是发送方和接收方将为标准 C++代码添加一个抽象层，以便在多个并行环境中运行。目标是增加可移植性，这样代码可以在不同的安装环境下工作。

“我们当然知道如何将它与算法联系起来。我希望对于 C++ 26 我们可以做到这一点。桑迪亚国家实验室的主要工作人员，同时也是 C++标准委员会成员的克里斯蒂安·特罗特说。

异步通信功能很大程度上是由 Nvidia 推动的，其 [CUDA](https://thenewstack.io/cuda-12-harnesses-a-nvidias-speedier-gpu-architecture/) 并行编程框架广泛应用于机器学习，依靠 CPU 和 GPU 的并发性来减少训练时间。

Nvidia 已经开源了它的 [libcu++ C++库](https://nvidia.github.io/libcudacxx/)。该公司上周还发布了 CUDA 12.0 并行编程框架，该框架支持 C++20 标准，并支持 GCC 10、Clang 11 和 ArmC/C++ 22.x 等主机编译器。

Nvidia 的 CUDA 架构师[斯黛芬·琼斯](https://www.linkedin.com/in/stephen-jones-profile/)告诉新的堆栈，发送者/接收者可能无法实现 C++ 23，但它将使未来的编码者生活更容易。

“我对 2026 年很有信心，但是发送者/接收者——这是 C++中的一个重大转变。琼斯说:“对他们来说，尝试采用异步流水线执行是一件非常新鲜的事情。

## 需要成熟的技术

虽然一个关键特性的延迟在理论上可能不太好，但 C++委员会成员表示，最好等到技术成熟后再将其作为标准添加。随着芯片设计、内存和存储需求的不断变化，使用加速器进行计算还处于早期阶段。

“我认为我们需要看到更多的加速器，”英特尔软件工程师 James Reinders 说，“我认为这需要更多的时间来完成。"

英特尔提供了一个名为 [SYCLomatic](https://thenewstack.io/intel-invokes-linus-torvalds-to-push-software-tools/) 的工具，通过剥离将应用限制在 Nvidia GPUs 上的 CUDA 代码，使代码可以跨硬件移植。Reinders 表示，GPU 不会是唯一可用的加速器。

Reinders 还指出了一场激烈的争论，即在标准 C++中是否需要像远程内存这样的钩子技术。他说，有些是更好的扩展。

“给它一些时间让它发挥出来，我们会看到这是否是放入 C++的正确选择，或者作为一个扩展是否更好， [OpenMP](https://thenewstack.io/intel-pushes-cross-architecture-support-in-oneapi-toolkits/) 长期以来一直非常强大。它从未被整合到 Fortran 或 c 语言中，不要把核心语言过度复杂化是合适的，”Reinders 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>