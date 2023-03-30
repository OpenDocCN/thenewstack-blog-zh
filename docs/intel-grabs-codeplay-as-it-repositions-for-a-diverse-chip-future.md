# 英特尔抓住 Codeplay，为多样化的芯片未来重新定位

> 原文：<https://thenewstack.io/intel-grabs-codeplay-as-it-repositions-for-a-diverse-chip-future/>

在软件制造商的收购狂潮中，英特尔又抢走了一家公司，周三同意以未披露的金额收购 Codeplay 软件。

[Codeplay](https://www.codeplay.com/) 以围绕开源 [SYCL](https://en.wikipedia.org/wiki/SYCL) 并行编程模型的开发工具而闻名，该模型包括工具、运行时和执行模型，因此标准 C++代码可以适用于跨 CPU、GPU 和其他处理器的并发执行。

### SYCL + OneAPI

英特尔打算将 Codeplay 的工具与其自主开发的 [OneAPI](https://www.intel.com/content/www/us/en/developer/tools/oneapi/overview.html) 并行编程框架配对，以便开发人员可以从异构计算环境中获取最大的计算能力。

过去，程序执行依赖于 CPU，但在过去的 15 年里，GPU、FPGAs 和 ASICs 等新型处理器在人工智能和分析等应用方面表现出色。CPU 现在将程序卸载到这些替代处理器上运行，这是由并行编程工具自动完成的，包括 OneAPI、OpenCL 和 CUDA。这些框架确保编码人员不必担心硬件。

默认情况下，标准 C++没有并行执行代码的钩子，硬件和软件公司已经用它们的库介入了。Nvidia 有一套名为 libuC++的标准 c++库，可以在 CPU、公司的 GPU 和其他芯片之间并行执行代码。但是英伟达、英特尔和其他公司正在共同研究将并行性引入标准 C++版本的提案。

英特尔的 oneAPI 已经通过一个名为 OneAPI 数据并行 C++ (DPC++) 的工具集[支持 SYCL，Codeplay 还有另一个名为](https://www.intel.com/content/www/us/en/developer/tools/oneapi/data-parallel-c-plus-plus.html#gs.2jsw8g) [ComputeCpp](https://developer.codeplay.com/home/) 的 SYCL 工具。(英特尔最近发布了 SYCLomatic，这是一款允许程序员将 Nvidia CUDA 编写的代码导出到 SYCL 的工具。)

Codeplay 赢得了美国能源部等公司的合同，为他们的前沿超级计算机实施 SYCL 开放标准，该计算机在 500 强排行榜上被评为世界上最快的超级计算机。这台超级计算机是世界上第一台亿亿亿次系统，使用 AMD 的 Epyc 芯片。Codeplay 支持 AMD、Intel 和 Nvidia 的一系列 CPU 和 GPU。

该公司发言人在一封电子邮件中表示，这笔交易将帮助英特尔进一步推进其“oneAPI 愿景，并加强我们对开放生态系统的承诺”。

## 改变航向

英特尔正在改变其 50 年的 CPU 传统，推出稳定的替代芯片来加速计算。英特尔计划在今年下半年出货用于超级计算的 Ponte Vecchio GPU，并在 2016 年斥资 167 亿美元收购 Altera，2019 年斥资 20 亿美元收购 AI 芯片公司 Habana。

英特尔还改变了其芯片设计，将 CPU 和加速器挤在一个芯片封装中，这符合其长期制造战略。英特尔已经开放了其工厂来制造基于 RISC-V 和 ARM 的芯片，因此收购 Codeplay 将有助于开发人员调整代码，以便在单个封装中结合 x86、ARM 和 RISC-V 指令集架构的芯片上并行执行。

英特尔雇佣了大约 17，000 名软件开发人员，正在寻求在其芯片产品上构建软件服务。该公司首席执行官[帕特·基尔辛格](https://www.linkedin.com/in/patgelsinger/)已经明确表示，该公司正在寻求对[进行战略性软件收购](https://thenewstack.io/intel-to-continue-buying-spree-of-saas-vendors/)。

英特尔最近的收购包括人工智能提供商[颗粒](https://www.intel.com/content/www/us/en/newsroom/news/corporate-news-march-2022.html#gs.2mc5dx)和开源软件公司 [Linutronix](https://community.intel.com/t5/Blogs/Products-and-Solutions/Software/Intel-Acquires-Linutronix/post/1362692) 。在上个月的英特尔愿景大会上，该公司展示了新的软件服务，包括在其 GPU 上运行的云游戏服务 [Project Endgame](https://www.thurrott.com/hardware/262959/intel-announces-new-project-endgame-streaming-service-powered-by-its-arc-gpus) ，以及用于云中安全通信的认证层 [Project Amber](https://www.intel.com/content/www/us/en/newsroom/news/vision-2022-project-amber-security.html) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>