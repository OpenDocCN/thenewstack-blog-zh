# IBM 和英特尔重新思考处理器设计以适应人工智能工作负载

> 原文：<https://thenewstack.io/ibm-power9-fundamental-changes-computer-design/>

人工智能正在给处理器带来新的需求。算法数据处理不同于早期的数据处理模型，这些模型是由像 [LINPACK](https://www.top500.org/project/linpack/) 这样的基准测试所强调的。它还通过降低 CPU 的重要性和利用协处理器更快的计算能力来改变计算架构。CPU 只是一个推动者，大量的深度学习是在 GPU、FPGAs 和谷歌的[张量处理单元](https://cloud.google.com/blog/big-data/2017/05/an-in-depth-look-at-googles-first-tensor-processing-unit-tpu)等加速器芯片上完成的。

像 IBM、Intel、Nvidia 和 AMD 这样的主要硬件公司正在接受架构和调整硬件方面的变化，这种变化鼓励了人工神经网络的创建，正如研究人员在 20 世纪 60 年代所设想的那样。IBM 的新 POWER9 系统，[于 12 月初](https://www.ibm.com/it-infrastructure/us-en/resources/power/enterprise-ai/?S_PKG=-&cm_mmc=Search_Google-_-IBM+Systems_WW_Always+On+Digital_Power-_-WW_NA-_-+power9_Broad_-&cm_mmca1=000018TL&cm_mmca2=10005033&cm_mmca7=9004372&cm_mmca8=kwd-391819439491&cm_mmca9=7ec65f8e-ccee-44ab-ab53-e0179eaf8ab8&cm_mmca10=238525787476&cm_mmca11=b&mkwid=7ec65f8e-ccee-44ab-ab53-e0179eaf8ab8%7C503%7C148154&cvosrc=ppc.google.%2Bpower9&cvo_campaign=000018TL&cvo_crid=238525787476&Matchtype=b)发布，依靠超快速管道——它称之为“软管”而不是“吸管”——将数据传输到具有机器学习能力的协处理器。计算机的学习能力与互连吞吐量直接相关，因为移动数据意味着更快的结果。

数据中心的大部分深度学习都以英伟达 GPU 为中心，IBM 的 POWER9 服务器家族通过专用的下一代 [NVLink](http://www.nvidia.com/object/nvlink.html) 路径提供了到英伟达最新 Volta GPUs 的最快路径，比 x86 芯片中当前的 PCI-Express 3.0 每通道快 7 到 10 倍。Nvidia [为其 GPU 提供了自己基于](https://developer.nvidia.com/cuda-gpus)CUDA 编程工具包的深度学习框架，IBM 提供了支持流行深度学习工具的 [PowerAI](https://www.ibm.com/us-en/marketplace/deep-learning-platform) 软件。

Nvidia 的 GPU 之所以受欢迎，是因为它能够跨数千个内核进行低级浮点处理，可以共同提供一只猫在图像中是否真的是一只猫的近似值，这是一个典型的 AI 问题。这很像大脑的运作方式，其中一个神经元网络共同处理可用信息，以识别可能正在查看的内容。

IBM 认为 POWER9 的快速吞吐量将使 x86 系统黯然失色，但人工智能有许多方法，正如英特尔正在研究的那样。英特尔围绕包括 FPGAs 和 ASICs 在内的芯片堡垒建立了自己的人工智能产品组合，希望有些东西能够坚持下去。这家芯片制造商正试图将在人工智能趋势中失败的风险降至最低，就像它在移动设备和电视中因产品延迟或失败而失败的风险一样。

或许是受到英伟达成功的刺激，英特尔也在构建自己的 GPU(在 2009 年放弃了一个代号为 Larrabee 的 GPU 之后)，将 Nervana 芯片集成到服务器中(它也有一个附带的深度学习框架)，并提供 Altera FPGAs。它有 [Saffron 编程框架](http://saffrontech.com/)，专门从多个来源获取和统一数据。英特尔的 Altera FPGAs 将进入汽车，模仿与图像识别相关的类似 GPU 的功能。英特尔最近废弃了其 Knights Hill 超级计算芯片，以制造一种围绕人工智能构建的新型芯片。

但是 IBM 有一个早期的优势，比如像 [PCI-Express 4.0](https://www.anandtech.com/show/11967/pcisig-finalizes-and-releasees-pcie-40-spec) (比 PCIeE 3.0 快两倍)，以及一个叫做 [OpenCAPI](http://opencapi.org/about/) 的开放互连，不同的协处理器、存储器和内存可以连接到这个互连上。除了 AMD GPUs，POWER9 还可以连接专门的深度学习协处理器，如谷歌 TPU 和 Wave Computing 和 Graphcore 等公司的其他处理器。协同处理器公司有责任为 OpenCAPI 添加兼容性。

对于 IBM 和英特尔来说，对[现场可编程门阵列](https://www.altera.com/products/fpga/overview.html)(FPGA)的支持可能是关键，因为这些芯片可能会蚕食人工智能的 GPU 优势。例如，在深度学习中，FPGA 可以加载专用于图像识别、金融建模或国家语言处理的代码。可以很容易地修改代码以重新调整 FPGA 的用途。长期以来，FPGAs 被用来通过代码模拟芯片或测试操作系统。苹果、英特尔、高通、微软和其他公司通过 FPGAss 测试软件和硬件，当以最高速度运行时，FPGA 可能会很耗电，但越来越省电。与 CPU 不同，FPGAs 不能作为通用芯片来执行各种运算。

展望未来，IBM 的 POWER9 系统可以被视为 IBM Research 正在开发的量子计算机和神经形态芯片的前奏。两者都专注于人工智能，但有不同的编程模型。人工智能还处于早期阶段，但决策者面临的挑战是采用一种计算机设计——无论是在 GPU、FPGAs 还是 ASICs 上——并在考虑长期 It 投资时坚持使用它。

[谷歌](https://cloud.google.com/kubernetes-engine)是新堆栈的赞助商。

由[克里斯·劳顿](https://unsplash.com/photos/5IHz5WhosQE?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)通过 [Unsplash](https://unsplash.com/search/photos/change?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>