# 英特尔 GPU 的 CUDA ZLUDA 需要一个新的维护者

> 原文：<https://thenewstack.io/zluda-a-cuda-for-intel-gpus-needs-a-new-maintainer/>

一个开源项目的工作已经停止，该项目将帮助为英伟达专有 CUDA 平台编写的程序在英特尔 GPU 上运行，因为该项目的前维护者正在寻找其他人来领导这项工作。

早在 2020 年，[在波兰格但斯克工作的英特尔软件工程经理 Andrezej Janik](https://www.linkedin.com/in/andrzej-janik-6b84b4113/) 就开始着手 ZLUDA 项目，该项目旨在替代基于英特尔 GPU 技术的 CUDA(计算统一设备架构)。

ZLUDA(用 C++和 Rust 编写)将是一件大事，因为它提供了 Nvidia 专有 CUDA 的开源替代方案。即便如此，ZLUDA 还是提供了一个概念证明，可以在非 Nvidia 硬件上运行未经修改的基于 CUDA 的应用程序。

正如该项目的 [GitHub 页面](https://github.com/vosen/ZLUDA)所解释的:

*ZLUDA 是英特尔 GPU 上 CUDA 的替代产品。ZLUDA 允许使用英特尔 GPU 运行未经修改的 CUDA 应用，性能接近本机。它可与当前的集成英特尔 UHD GPU 配合使用，并将与未来的英特尔 Xe GPUs 配合使用*

ZLUDA 是基于英特尔的 oneAPI 零级规格构建的，即使在早期，它看起来也非常有前途。鉴于它将如何使在英特尔硬件上运行 CUDA 软件成为可能，这一前景是巨大的。

不过，在 ZLUDA 轰动之后不久，Janik 更新了 README。md 文件中包含以下语句:

*由于私人原因，我目前无法继续开发这个项目。想接手的话叉一下联系我 vosen@vosen.pl*

至少据一位匿名的英特尔员工称，由于担心许可问题，英特尔自己可能要求停止开发。至少，Janik 在 CUDA 上的工作可能代表了英特尔的利益冲突(即使该项目不是英特尔的官方项目)。

当然，自从 2006 年推出 CUDA 以来，Nvidia 一直保持该软件的专利性。显然，如果 Nvidia 想让其他业务实现 CUDA，早就开源了。但事实并非如此。

## 什么是 CUDA？

对于那些不知道的人，CUDA 库允许软件开发人员使用支持 CUDA 的 GPU 进行通用处理，也称为 GPGPU(图形处理单元上的通用计算)。CUDA 提供的层可以直接访问 Nvidia GPU 的虚拟指令集和并行计算元素，从而使执行计算内核成为可能，并且是大多数高性能 AI/ML 框架用来访问 GPU 的。

简而言之，CUDA 使 GPU 资源可用于并行编程，这意味着开发人员可以通过将 GPU 资源用于计算的任何可并行化部分来加速计算密集型应用。这是巨大的，特别是在云原生开发中，可伸缩性可能需要尽可能多的计算能力。

## 开源版在哪里？

早在 2009 年，苹果和 Khronos 集团推出了 OpenCL，试图为异构计算提供一个标准，而不限于英特尔/AMD CPU 和英伟达 GPU 的组合。换句话说，这是一个可以在任何硬件上实现的 CUDA 版本。

不幸的是，OpenCL 永远达不到 CUDA 的性能水平。部分问题是 OpenLS 只能利用 1 个 GPU，而 CUDA 可以利用 2 个 GPU。这是一个显著的区别(也许也是为什么 OpenCL 还没有获得很大的吸引力)。

## 为什么 CUDA 对云很重要？

如前所述，使用 CUDA，您可以通过在 CPU 中添加 GPU 来获得额外的计算能力。有了云原生应用，你需要你能得到的每一点力量。当您部署的容器将受到大量需求的冲击时，尤其如此。事实上，当使用 CUDA 和多个 P100 服务器 GPU 时，您可以看到高达 50 倍的性能提升(相对于标准 CPU)。

回到 2020 年， [Folding@Home 获得 CUDA 支持](https://www.overclock3d.net/news/gpu_displays/folding_home_gains_cuda_support_to_deliver_significant_performance_boosts/1)。通过这一增加，该项目在大多数基于 GPU 的项目中实现了 15-30%的性能提升，在特定工作负载中甚至实现了更大的提升。一个恰当的例子是，在 COVID Moonshot 项目中使用 CUDA Core22，该项目的性能提升了 50-100%。使用 Nvidia P106-100 GPU，Folding@Home 发现 COVID Moonshot 短跑的性能提高了 400%。

考虑到这项工作的重要性，每一项性能提升都至关重要。CUDA 提供了这种水平的收益，很容易理解为什么这个库变得如此重要。

## 向前

Janik 的项目受到了来自 [HackerNews](https://news.ycombinator.com/item?id=26262038) 和 [Phoronix](https://www.phoronix.com/scan.php?page=news_item&px=ZLUDA-v2-Released) 的严肃报道，并迅速在 AI/ML/HPC 社区中传播开来。兹鲁达将会改变游戏规则。

没有了 Janik，是不是意味着这个项目已经胎死腹中了？不。正如 Janik 所说，如果有人想把它作为一个叉子，他愿意交出这个项目。

我联系了 Janik 寻求评论，但一直没有回音。Nvidia 也没有对新堆栈的最后一分钟询问做出回应。

然而，ZLUDA 是一个重要的项目，它可能会对云原生开发产生重大影响。因此，如果你(或你认识的人)准备分叉这个项目，尽快联系 Janik。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>