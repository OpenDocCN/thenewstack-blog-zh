# 移动机器学习:人工智能卸载引擎

> 原文：<https://thenewstack.io/mobile-machine-learning-ai-offload-engines/>

英特尔正在推广这样一种观点，即其新的 CPU 是运行机器学习和其他人工智能工作负载的最具成本效益的硬件，因为你也可以将它们用于其他计算——使它们比主要用于高性能机器学习的 GPU 更灵活。但是从手机到云服务，我们看到了大量既不是 CPU 也不是 GPU 的人工智能专用硬件。

正如微软杰出的工程师道格·伯格(Doug Burger)在谈到 Azure 如何使用[FPGA](https://thenewstack.io/developers-fpgas-cloud/)来加速机器学习时向新堆栈解释的那样，“现在有一场关于什么是正确的架构的大辩论？是软逻辑吗，是硬逻辑吗，数据类型和运算符是什么，应该在 CPU 上运行什么，应该在这套加速器上运行什么，系统架构是什么？这都是可以争取的。”

## 移动机器学习

加速器正在手机中出现，以加速运行训练有素的数据模型，从人脸识别到提高照片质量。苹果 iOS 的核心 ML 框架包括许多预训练的模型，这些模型运行在 A11 的仿生神经引擎上，以及用于从 TensorFlow 和 Apache MXNet 等框架转换模型的工具。

ARM 即将推出的[机器学习和物体检测处理器](https://thenewstack.io/arms-project-trillium-brings-dedicated-machine-learning-hardware-smart-devices/)类似于苹果的仿生神经芯片。ARM 不是通用处理器或重新设计的 DSP 芯片，而是专门设计来运行精度降低的整数和矩阵乘法累加器算法，这些算法构成了机器学习的大部分工作负载，特别是推理——运行经过训练的机器学习模型，而不是训练它。

开发人员可以在 Linux 上使用 [ARM NN SDK](https://developer.arm.com/products/processors/machine-learning/arm-nn) 来翻译 Caffe 模型(以及最终用于其他机器学习框架的模型)，以便在使用 ARM 硬件的设备上运行，如果有 ARM ML 处理器，代码将针对它进行优化。

高通的[神经处理引擎 SDK](https://developer.qualcomm.com/software/qualcomm-neural-processing-SDK) 涵盖了更多的框架，尽管在高通拥有包括 ARM ML 处理器的平台之前，它针对语音检测等工作负载的 Hexagon DSP 和用于对象检测和风格转换的 Adreno GPU，使用 Caffe、Caffe2、TensorFlow、ONNX、CNTK 和 MxNet 训练的模型。

谷歌有一个定制的神经处理单元，它在 [Pixel 2](https://www.blog.google/products/pixel/pixel-visual-core-image-processing-and-machine-learning-pixel-2/) 的相机应用中使用它来代替 Hexagon DSP 进行机器学习，华为也创建了自己的 NPU(事实上其最新的手机拥有双 NPU)。第三方应用程序也将能够利用这些 npu，但在花费大量时间支持它们之前，有必要研究一下它们能带来多大的性能提升。

ARM 的 ML 处理器不仅仅用于手机；它们将出现在特定的硬件设备中，如智能监控摄像头和平板电脑。VA 的 NeuPro AI 处理器也是为物联网设备、可穿戴、无人机和 AR/VR 头戴设备设计的；他们有专门的矩阵乘法引擎和可编程矢量 DSP(CEVA 称之为矢量处理单元)，可以用新的神经网络算法进行更新。Imagination Technology 的 PowerVR Series2NX 是一款神经网络加速器，专为智能手机、智能相机和自动驾驶汽车设计，针对处理卷积、激活、轮询和归一化等张量运算进行了优化。它与 Android 神经网络 API (NNAPI)一起工作，开发人员可以使用[想象力神经网络 SDK](https://www.imgtec.com/developers/neural-network-sdk/) 来转换来自 Caffe 等框架的模型。

## 服务器和云

Nvidia 也一直在为其一些[显卡](https://www.nvidia.com/en-us/data-center/volta-gpu-architecture/)添加张量处理器，以加速深度学习。在云中，谷歌有一个定制的 ASIC 张量处理单元，使用 8 位简化精度计算浮点和整数张量。

降低精度(或微软称之为窄精度)每次运算使用更少的晶体管，使其更有效地计算较低精度的数字，深度神经网络使用较低精度的权重来提高速度。Burger 告诉我们:“当你进行推理时，你的效率会有一个超线性的飞跃。”

用于训练向 16 位整数和浮点数精度发展的神经网络，但用于在运行从 32 或 16 位浮点表示向 8 位整数发展的训练模型时进行推理，因为它提高了指令吞吐量，减少了内存消耗，而没有太多的精度损失。

正如英特尔人工智能产品事业部总经理 Naveen Rao 所解释的那样，“更低的精度允许芯片上有更多的并行性，因为更多的这些操作同时发生，功耗更低，并且在不降低分类率或语音翻译成文本的效果等算法性能的情况下做得更多。这并没有降低性能，同时还能以更低的功耗实现更高水平的并行性。”混合使用数字精度来实现性能和准确性也变得越来越普遍。

英特尔已经在高级向量扩展中添加了矩阵运算，以补充最新至强处理器中的 x86 指令集。今年出货的 Cascade Lake Xeon 增加了新的向量神经网络指令， [DL Boost](https://simplecore.intel.com/nervana/wp-content/uploads/sites/53/2018/05/IntelAIDC18_Formenko_Theatre_052418_final.pdf) (PDF)，可以用更少的指令处理深度学习推理中常见的 8 位整数卷积。2019 铜湖至强 CPU 将拥有新版本的 DL Boost，使用谷歌的 bfloat16 16 位浮点格式来训练工作负载，以及支持 8 位乘法和 32 位累加的向量神经网络指令(VNNI)集扩展。

英特尔即将推出的“神经处理器”Nervana NNP-L1000 神经处理器将于 2019 年底上市，它拥有自己的新混合精度数字格式，称为 Flexpoint，可以将标量计算转换为定点乘法和加法。

微软在 Azure 的每台服务器上都安装了 FPGA 来运行机器学习服务，现在客户可以在这些服务器上运行 [ResNet](https://github.com/azure/aml-real-time-ai) ，并与 HPE 和戴尔合作，提供配备 FPGA 的服务器来在边缘运行其认知服务。这些项目脑电波系统有一个[专用指令集](https://www.slideshare.net/albertspijkers/brain-wave-hotchips2017)，针对密集矩阵乘法、向量运算和张量运算(如卷积、非线性激活和嵌入)进行了优化，使用微软自己的窄精度浮点格式 ms-fp8 和 ms-fp9，包装在 float16 接口中。

但是，与所有这些人工智能加速器和卸载硬件一样，开发人员不会在指令集的层面上工作；他们将继续使用 TensorFlow、MXnet 和 CNTK 之类的框架，这些框架将利用更有效的数字格式和指令。

## 不要忘记基准测试

硬件供应商声称特定于人工智能的硬件可以快多少，但在市场的早期阶段，开发人员可能希望自己做更多的测试，以找出这些有多重要，以及哪些加速器对他们使用的模型最有好处。

当与一家 OEM 合作时，微软被要求移植其 Azure 认知服务 API 之一，以使用 OEM 设备上的 NPU 运行。完成这项工作后，团队在设备上对服务进行了基准测试。“我们真的发现，我们在 CPU 上做得和在他们的神经处理器上一样好，”微软首席小组项目经理 Andy Hickl 告诉我们。

最后，他们把这个问题留给了原始设备制造商来决定。“我们说，我们的算法可以在你提供的任何计算平台上运行，”Hickl 说。这类似于 Rao 的说法，即推断“通用计算和 GPU 等特定计算之间的性能差距不是 100 倍，而是 3 倍”。

越来越多的工具将试图为可用的硬件优化机器学习模型和系统，但这些工具中有许多来自 ARM 和英特尔等硬件供应商，而不是跨平台的。英特尔的开源 [nGraph 编译器](https://ai.intel.com/ngraph-a-new-open-source-compiler-for-deep-learning-systems/)承诺优化模型 TensorFlow、MXNet、neon 和 ONNX(增加了对 CNTK、PyTorch 和 Caffe2 的支持)，以在 Xeon、Nervana、Movidius(专用视觉处理芯片)、Stratix FPGA 和 GPU 上运行。如果你需要在移动设备上运行相同的机器学习模型，或者甚至在 AMD CPU 上运行，那就没有帮助了，所以我们期待看到它变得更加跨平台，以真正帮助开发人员，或者看到一个通用的处理管道，可以根据目标硬件使用 nGraph 或其他优化器。

这是一个快速发展的空间。随着如此广泛的人工智能卸载硬件和加速采用如此多的不同方法，开发人员可以预期必须采用更广泛的工具来利用它们，在投资时间支持特定硬件之前做一些基准测试是值得的。

微软是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>