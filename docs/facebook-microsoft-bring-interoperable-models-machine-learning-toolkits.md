# 脸书和微软将互操作模型引入机器学习工具包

> 原文：<https://thenewstack.io/facebook-microsoft-bring-interoperable-models-machine-learning-toolkits/>

越来越多的机器学习工具包，尤其是深度学习工具包，最近已经可供开发者使用；谷歌、微软、亚马逊、脸书、三星、英特尔和百度都发布了自己的框架，此外还有一些关键的框架，如 [Torch](http://torch.ch/) 、 [Caffe2](https://github.com/caffe2/caffe2) 和 Theano，以及来自学术团体的更新的框架，如 [Marvin](http://marvinproject.sourceforge.net/en/index.html) 。

不同的机器学习团队使用不同的框架，尤其是因为它们都有不同的优缺点，但直到现在，在不完全重建数据模型的情况下，从一个框架转移到另一个框架的选项并不多。

对于希望比较和复制由使用不同工具或编程语言的其他团队发布的结果的研究人员，以及希望在一个框架中构建数据模型原型，然后在生产系统中使用不同工具包的开发人员来说，可重复性非常重要。这通常意味着扔掉已经完成的工作，并在新的框架中重新创建它，这在研究人员准备推出你的机器学习系统时减慢了他们的速度。

解决这个问题的一种方法是使用 [Keras](https://keras.io/) ，这是一个 Python 库，提供了使用 [TensorFlow](https://www.tensorflow.org/) 、Theano、Deeplearning4j 和[微软认知工具包](https://github.com/Microsoft/CNTK) (CNTK)开发深度学习模型的高级构建模块；同一个模型可以通过设置标志用于不同的框架，而不需要修改任何代码。用早期版本的 CNTK 集成进行测试表明，不同的框架在不同的领域给出了更好的结果。Keras 的设计比框架本身更加用户友好，非常适合原型和实验。

虽然它不擅长超越单节点机器，但这正日益成为深度学习的方向(向外扩展更大、更深的网络)；你必须添加其他工具，如 [Elephas](https://github.com/maxpumperla/elephas/pulse) 来有效地做到这一点。如果不调整 Keras 框架本身，让 Keras API 充当抽象并不总是提供对底层工具包中更强大选项的访问。

脸书和微软合作的[开放神经网络交换](https://github.com/onnx/onnx) (ONNX)格式采取了不同的方法。这是一个表示深度学习模型的开源标准，可以让你在 CNTK、Caffe2 和 [PyTorch](http://pytorch.org/) 之间转移它们。

与 Keras 不同，ONNX 只是标准化了数据模型的表示方式。每个框架都可以直接使用，但是模型可以跨不同的框架重用。

机器学习项目在不同的开发阶段使用多个框架是很常见的；一个框架可能针对快速培训进行了优化，非常适合原型设计，而另一个框架适用于不同的网络架构，因此更适合构建最终产品。现在智能手机的片上系统通常都有一个“人工智能核心”，更多的学习可以在设备上完成，所以像 Caffe2 这样的框架将是一个选择，因为它已经为手机上的推理进行了优化。ONNX 使得从一个移动到另一个更加容易。

## 断开

“微软和脸书在 ONNX 上工作的主要意图是解决和(希望)修复当人工智能项目从开发/测试进入生产时可能出现的脱节，” [Pund-IT](http://www.pund-it.com/) 首席分析师[查尔斯·金](https://twitter.com/punditinc)告诉新堆栈。“对数据/模型可互换性的支持对于希望为多个平台创建应用程序的开发人员来说至关重要，因为主要供应商也在推进他们自己的专有人工智能框架(苹果的 [Core ML](https://developer.apple.com/machine-learning/) 就是一个很好的例子)，”King 指出。

“这是一个很好的方法，将不同的框架结合在一起，这样我们就可以交换模型，因为每个框架都有自己的优点和缺点，这将使人们摆脱对一个框架的束缚，”微软技术人员黄表示同意。

“CNTK 非常适合大规模深度学习；如果你有大量的数据，这是最快的。Caffe2 非常适合为计算机视觉工作负载创建小型模型。PyTorch 非常善于给你在研究中所需要的灵活性；它很慢，但是很灵活。例如，当你从早期研究转向大规模工业研究时，你可能需要从 PyTorch 转向 CNTK，现在有了 ONNX，你可以轻松做到这一点。”

ONNX 也方便了那些越来越多地添加优化来加速神经网络的硅供应商； [Nvidia 的深度学习 SDK](http://developer.nvidia.com/deep-learning-frameworks) 覆盖了广泛的框架，但越多的框架共享相同的数据模型表示，为它们优化的工作就越少。

## ONNX 内部

最新版本的 Caffe2 和 PyTorch 已经支持 ONNX，下一个版本的 CNTK 将会添加它。微软和脸书也在研究参考实现、工具和模型配置的“模型动物园”，你可以用它们来快速开始机器学习项目。

许多深度学习工具包使用计算图来表示神经网络，但它们一直都有自己的图形格式。ONNX 有一个所有三个框架都可以使用的可扩展计算图模型的定义，以及标准数据类型和内置操作符的定义。ONNX 计算图是具有输入和输出的节点列表。每个节点调用一个操作员；操作符没有存储在图中，但是每个支持 ONNX 的框架都将为标准支持的数据类型实现操作符。

第一个版本集中在用于推理的操作符和[类型上，但是递归神经网络是 PyTorch 团队在 ONNX 支持上的一个高优先级。](http://pytorch.org/docs/master/onnx.html)

King 指出，ONNX 并不是简化任务的唯一尝试，而是使用多种框架。[预测模型标记语言](https://sourceforge.net/projects/pmml/) (PMML)支持传统神经网络中的模型互操作性，如反向传播。包括亚马逊、IBM 和谷歌在内的许多公司都支持和使用 PMML。创建 PMML 的团队目前正在开发一种更灵活的后续技术[Portable Format for Analytics](http://dmg.org/pfa/index.html)(PFA )(使用 JSON 而不是 XML ),并处理模型本身的数据准备。

“ONNX 应该有利于一系列人工智能和相关的机器学习(ML 和深度学习(DL)过程，特别是如果它超出了最初的支持，”金说。“微软和脸书的 ONNX 是否最终成为公认的标准还有待观察，但这两家公司正朝着正确的方向前进。”

微软是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>