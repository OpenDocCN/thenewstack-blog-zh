# Docker 收购单核系统，计划将虚拟图书馆操作系统主流化

> 原文：<https://thenewstack.io/docker-buys-unikernel-systems-plans-bring-unikernels-data-center/>

Docker 周四宣布，它已经收购了英国剑桥一家专门从事单核开发的初创公司 Unikernel Systems。

此次收购将帮助 Docker 扩大企业可以使用的虚拟化技术的范围，实际上将 Docker 转变为一个运行广泛工作负载的平台，而不仅仅是基于容器的工作负载。

Docker 创始人兼首席技术官 Solomon Hykes 说:“就像我们对容器所做的那样，我们感兴趣的是使这项技术大众化，让它对数百万开发者和 it 专业人士可用和有用。“单内核让你基本上摆脱了操作系统，取而代之的是将操作系统中真正需要的小部分编译进应用程序中。”

> 单核“是一种完全不同的部署和管理应用的方法”——Solomon Hykes

Hykes 说，作为单一用途设备的基础，unikernels 特别适合非常小的工作负载，可能在嵌入式或物联网设备上运行，它们也非常适合在数据中心运行的非常大的分布式微服务风格的工作负载。

总部位于英国剑桥的 Unikernel Systems 由许多来自 [Xen 项目](http://www.xenproject.org/)的先驱组成，因此他们在公共云工作负载和操作系统方面拥有丰富的经验。

粗略地说，你可以把[单核](https://thenewstack.io/defining-a-unikernel-and-how-it-works/)看作是精简的容器，只包含运行手头特定工作负载所需的功能。他们借用了在构建模块化操作系统和库操作系统(LibOS)的工作中萌发的思想，这些思想已经存在了几十年。

Hykes 说，单核“是一种完全不同的部署和管理应用程序的方法”。

用 OCaml 编写的 Unikernel Systems 的 [MirageOS](https://mirage.io/) 旨在“将整个[虚拟机]——包括所有内核和用户空间代码——重组为更加模块化的组件，这些组件以库操作系统的风格灵活、安全和可重用，”MirageOS 开发人员 Anil Madhavapeddy 和 David J. Scot 在 2014 年为计算机械协会(Association for Computing Machinery)撰写的一篇论文中写道。

Hykes 说，使用单核[在很多方面都是有利的。要部署的支持代码要少得多:Hykes 估计，unikernel 甚至比最小的基本容器还要小 10 倍。这直接转化为主机上更少的内存和 CPU 使用。](https://thenewstack.io/continuum-containers-unikernels-serverless-architectures/)

更小的内存占用意味着出现安全漏洞的机会更少。他说，没有不必要的驱动程序、守护程序或库，“攻击的表面区域就更小了”。

迄今为止，单核开发[一直由热情的研究人员组成的小团体驱动](https://thenewstack.io/dockers-unikernel-purchase-changing-role-os/)，单核系统领导了大量工作。

现在，Docker 想走技术主流。“我们打算让单核技术成为 Docker 工具的标准部分，”Hykes 说。

Hykes 承认，构建单核的过程是一个复杂的过程。因为单核是离散功能的集合，开发人员必须挑选他们手头工作需要的功能。因此，Hykes 说，Docker 的主要工作是“添加润饰”，即定义使单核更容易部署的惯例和标准。

收购条款没有披露。

Docker 是新堆栈的赞助商

通过 Pixabay 获得 CC0 许可的功能图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>