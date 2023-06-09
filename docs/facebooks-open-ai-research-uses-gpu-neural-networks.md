# 脸书的开放人工智能研究如何使用 GPU 神经网络

> 原文：<https://thenewstack.io/facebooks-open-ai-research-uses-gpu-neural-networks/>

如何处理大数据是一个令人着迷的问题。虽然当前对大规模数据集的兴趣主要集中在从历史数据中提取价值的能力上，但它也是构建训练数据的重要工具，让我们可以创建和使用机器学习系统来处理来自传感器、用户和不断增长的社交网络的不断增长的数据流。

毫不奇怪，脸书有一个人工智能研究小组，FAIR，专注于这些问题——它的成立也是为了分享它开发的工具和技术。论文发表在开放访问网站上，如 [arXiv、](http://arxiv.org/)，FAIR 开发的工具和软件都是开源的。

脸书人工智能研究的核心是[，一个名为 Torch](http://torch.ch/) 的开源数字计算工具。Torch 由脸书、谷歌和 Twitter 的科学家以及学术界和工业界的贡献者开发，使用 [Lua 脚本语言](http://www.lua.org/)来驱动 C 代码——支持 NVIDIA 的 CUDA 通用 GPU 编程环境。

最有趣的是 Torch 的 CUDA 支持，因为它允许您使用现代 GPU 中内置的并行处理工具作为运行大规模机器学习系统的结构。Torch 不必构建大规模的计算机或虚拟机集群，而是可以针对集群 GPU 工作，为研究人员提供桌面超级计算能力。您也不会受限于 GPU 的能力，因为您可以使用 Torch 驱动定制的 FPGA 系统来解决更复杂的问题。

Torch 旨在使快速构建科学计算算法变得容易，使测试新想法和新工作方式变得更容易。你也可以使用由 Torch 社区开发的广泛可用的软件包；其中包括用于计算机视觉、信号处理和神经网络的工具。正是这种神经网络支持使 Torch 成为机器学习的理想选择，因为您可以使用它来构建可以在 CPU 和 GPU 上并行运行的神经网络。

FAIR 最近开源了一系列用于处理深度学习的 Torch 模块，其中许多模块旨在与 NVIDIA GPUs 一起工作。几个新模块旨在帮助建立自然语言处理工具——这一研究领域应该有助于脸书理解用户内容，并使其能够访问新一代的自然用户界面。

也许这次代码发布最重要的部分是一个新的[快速傅立叶变换](https://en.wikipedia.org/wiki/Fast_Fourier_transform)卷积层。卷积是一个复杂的数学过程，其中两个函数用于创建第三个函数，通常从一个域转换到另一个域。快速傅立叶变换是一种常用的卷积算法，用于将时间转换为频率(反之亦然)，从而可以轻松分析复杂信号，如图片或语音。

训练神经网络处理卷积可能很慢，因此加快训练过程很有意义，因为它让研究人员尝试更多的算法和更多的代码。FAIR 的新 FFT 算法比其他代码快得多，其博客文章声称与最快的公共代码相比，速度提高了 23 倍以上。像这样加速 FFT 和神经网络将使研究人员更容易尝试新算法。类似地，通过跨多个 GPU 自动部署来简化神经网络使用的工具将加快复杂数据集的处理速度。

通过像这样开源其机器学习工具，并通过使用数字计算的开放框架，脸书使人工智能研究人员更容易分享和改进技术和工艺。随着更快的神经网络、更好的信号处理和更好的自然语言处理技术，人工智能研究人员可以利用很多优势，脸书可以将更多优势融入其服务中。

拥有超过 10 亿的用户，服务器上有数十亿字节的数据，脸书在人工智能研究上投入巨资是有道理的。使用人工智能来理解社交网络的行为是在用户的时间表中浮现相关内容的关键——特别是在使用它来识别图像和视频流中的内容时，以及在从移动设备转向语音输入的过程中使用自然语言处理时。与研究社区分享其工具和技术应该会加快开发速度，并使脸书更容易在其面向公众的服务中部署这些技术。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>