# 2023 年边缘计算项目的 7 种硬件设备

> 原文：<https://thenewstack.io/7-hardware-devices-for-edge-computing-projects-in-2023/>

如果你对边缘计算或物联网项目感兴趣，但不知道从哪里开始，这篇文章将帮助你了解项目所需的硬件。

## 边缘计算概述

“边缘”实际上是什么，根据你的参考框架可能会有很大的不同。边缘可以像内容交付网络(CDN)一样简单，提供静态文件以降低加载时间，将您的应用部署在多个区域数据中心，使用现代的[无服务器](https://thenewstack.io/serverless/)框架和服务将处理转移到离用户更近的硬件，甚至将功能直接推送到用户的设备上。

使用边缘计算的主要原因归结为延迟、成本和可靠性之间的权衡。延迟让用户感到沮丧，因此开发人员希望尽可能减少延迟。如果您在现场使用手机或卫星数据，带宽也会很昂贵，因此对于数据密集型任务，尽可能尝试在设备上完成任务是有意义的。

对于可靠性极其重要且网络连接无法保证的关键应用，[边缘计算](https://thenewstack.io/edge-computing/)可以通过在本地完成工作而不是依赖云中的处理能力来确保事情保持正常运行。

以下是一些常见的边缘计算示例:

*   安全摄像机图像识别
*   无人驾驶汽车
*   工业制造异常检测
*   工业监控

## Nvidia Jetson

Nvidia 制造的 [Jetson](https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/) 系列芯片是为边缘计算工作负载设计的，这些工作负载需要在边缘[上执行人工智能任务的能力，而不是依赖于数据中心 GPU。示例用例包括具有人工智能视觉的机械臂、](https://thenewstack.io/the-challenge-of-scaling-the-intelligent-edge/)[可以执行流式分析的相机](https://www.influxdata.com/blog/nvidia-jetson-series-part-2-vision-ai-pipeline/?utm_source=vendor&utm_medium=referral&utm_campaign=2023-03_spnsr-ctn_7-hardware-for-edge_tns)以及在收集的传感器数据上运行的高级机器学习模型。

Nvidia 通过提供各种软件工具与 Jetson 硬件一起使用来创建统一的开发堆栈，从而使开发变得更加容易。Jetson 有原型或爱好项目可用的开发工具包，如果你计划将你建造的东西商业化，还可以批量购买芯片。

## 颗粒

对于 WiFi 或以太网不可用的边缘或物联网项目， [Particle](https://www.particle.io/) 系列是一个很好的选择。Particle 提供全球可用的 SIM 卡，可让您的设备使用蜂窝数据传输数据。

在硬件之外使用 Particle 的另一个好处是，Particle 提供了一个完整的[物联网](https://www.influxdata.com/use-cases/iot/?utm_source=vendor&utm_medium=referral&utm_campaign=2023-03_spnsr-ctn_7-hardware-for-edge_tns)云平台，这使得将不同的系统集成在一起比试图自己构建要容易得多。Particle 还提供了许多 API、软件开发工具包(SDK)以及与第三方工具的集成。

## 谷歌珊瑚

如果你的项目涉及任何类型的机器学习，谷歌生产的 [Coral](https://coral.ai/) 芯片是一个很好的选择。所有 Coral 设备都由谷歌定制的张量处理单元(TPUs)提供支持，这些单元专门用于机器学习工作负载。Coral 提供专为快速原型制作而设计的器件，以及针对您希望将使用原型板制作的产品商业化的情况而设计的生产就绪型器件。

Coral 制造的一个非常酷的设备是 USB 加速器，它可以与本文中讨论的其他一些设备结合使用，为它们提供额外的能力，以有效地运行机器学习模型。

## 树莓派

当开始物联网或边缘计算类型的项目时， [Raspberry Pi](https://www.raspberrypi.org/) 可能是最知名的产品。Raspberry Pi 的主要卖点是它对初学者、生态系统和社区的可用性。几乎任何您想要尝试的任务都可能有指南或教程来帮助您，并且有许多库和第三方硬件来加速开发。

在过去几年里，树莓派唯一真正的缺点是，由于芯片短缺，几乎不可能找到它。[据](https://www.raspberrypi.com/news/supply-chain-update-its-good-news/)公司称，这个问题应该会在 2023 年下半年得到解决。

## 橙色圆周率

顾名思义，[橙皮](http://www.orangepi.org/)设备与树莓皮有相当多的重叠。Orange Pi 的主要好处是，与 Raspberry Pi 相比，你将以相同或更低的价格获得更好的硬件性能。

缺点是 Orange Pi 没有那么大的社区或第三方生态系统。这些问题可以通过使用某些 Orange Pi 器件模型来缓解，这些器件模型与许多为 Raspberry Pi 板设计的外设兼容。

## Odroid

[Odroid](https://www.hardkernel.com/) 是 Hardkernal 打造的一系列单板电脑，非常适合边缘计算。就使用它们的意义而言，Odroids 被认为类似于 Raspberry Pis。与 Raspberry Pi 相比，使用 Odroid 的一些好处是，您可以为某些 Odroid 型号添加外部 RAM，并且一般来说，在处理能力和配置方面有更多的选择。

一个典型的缺点是，与 Raspberry Pi 的用户友好的生态系统相比，Odroids 在设置和使用外设时被认为更难使用。

## 英特尔 NUC 公司

[英特尔 nuc](https://www.intel.com/content/www/us/en/products/details/nuc.html)本质上是迷你电脑，由于外形小巧，是边缘计算的绝佳选择。这些设备将大量计算能力集成到一个小封装中，非常适合空间受限的环境。

它们易于扩展和升级，可以轻松访问 RAM 和存储等组件。NUCs 也可以配置为运行各种操作系统，包括 Windows 和 Linux。nuc 在边缘计算方面的另一个优势是功耗相对较低，这在担心功耗的情况下非常重要。一个潜在的缺点是，与本文中的一些其他设备相比，它们往往没有那么多的端口或对外围设备的支持。这是否是一个问题将取决于您的用例。

Chick-Fil-A 是英特尔 NUCs 大规模用于边缘计算的一个例子，它有一系列受欢迎的博客帖子，介绍他们如何在每个商店使用英特尔 NUCs 硬件部署 Kubernetes。

## 后续步骤

除了本文涵盖的设备之外，物联网或边缘计算还有许多其他选择，它们都有自己的权衡。您选择哪一个将取决于您的特定项目的需求，以及您希望在多大程度上优化成本而不是便利性和开发速度。

查看以下链接，了解更多信息和教程，帮助您完成物联网或边缘计算项目:

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>