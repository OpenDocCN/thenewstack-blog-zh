# Google TensorFlow 击败 Caffe 的五种方式

> 原文：<https://thenewstack.io/three-ways-google-tensorflow-beats-caffe/>

弗吉尼亚州阿灵顿数据科学公司深度学习分析的高级数据科学家 [Aaron Schumacher](https://www.linkedin.com/in/ajschumacher/) 认为，在使用软件框架训练机器学习任务的模型方面，谷歌的 [TensorFlow](https://www.tensorflow.org/) 在许多重要方面击败了加州大学伯克利分校的 [Caffe](http://caffe.berkeleyvision.org/) 图书馆。

简而言之，TensorFlow 更容易部署，具有更灵活的 API，以及其他有利的属性，Schumacher 断言，他在上周于奥斯丁举行的 [OSCON 开源会议](https://conferences.oreilly.com/oscon/oscon-tx/public/schedule/full/tensorflow-day)上提出了他的理由。对于那些试图在快速扩张的机器学习领域获得立足点的人来说，他的洞察力可能是有价值的。

根据 Schumacher 的说法，与 Caffe 相比，Tensorflow 在以下几个方面对开发者更友好:

**1:更容易部署:**Caffe 的一个缺点就是没有安装的简易机制，比如 Tensorflow 部署的 Python **[pip](https://github.com/pypa/pip)** 包管理器。“你总是需要从源代码编译它，”舒马赫说。

**2。一个使用和共享 API 的高级 API:**Caffe 是第一个通过 [Caffe Model Zoo](http://caffe.berkeleyvision.org/model_zoo.html) 提供开发者已经构建和共享的模型库的机器学习框架之一。然而，Caffe 缺少的一点是“用于构建模型的高级 API”，这是 TensorFlow 提供的(事实上，Schumacher [也将在 5 月 24 日举行关于新 TensorFlow APIs 的网络研讨会](https://www.altoros.com/blog/event/more-and-better-the-new-tensorflow-apis/))。

使用 TensorFlow，研究人员可以使用一行 Python([" TF . contrib . keras "](https://www.tensorflow.org/api_docs/python/tf/contrib/keras))来获取预先训练好的模型。“你指定你想从一个模型中得到什么，它就准备好接受训练，”舒马赫说。TensorFlow 还提供了一个类似 scikit 的包(“tf.contrib.learn”)来评估一系列模型。

**3。开发人员的生命周期管理**:“API 的水平在这里很重要。有了高级别的 API，你可以快速进行实验，但有时你会希望有一个低级别的 API，以一种非标准的方式获得配置东西的螺母和螺栓，”Schumacher 说。

按照 Schumacher 的估计，Caffe 的方法是“中低 API ”,它提供的高层支持很少，但深度配置也有限。“它并不总是像你希望的那样低，如果你想变得更高，你必须建立自己的，”他说。

例如，深度学习分析必须为 [PyCaffe](https://github.com/BVLC/caffe/blob/master/python/caffe/pycaffe.py) 接口构建一个包装器，以便使其更易于使用。虽然 TensorFlow 和 PyCaffe 都是用 C++编写的，但 Tensorflow 有一个更适合 Python 的接口，Python 正日益成为数据科学家的首选语言。Caffe 的界面更加以 C++为中心，要求用户为每个新的机器学习任务创建配置文件并将其植入磁盘。

**4。更好的支持 GPU**:Caffe 对运行在 GPU 上的作业有一些支持，其矢量处理能力支持并行操作。但是 Caffe 的文档隐藏在它的 GitHub 知识库中。目前，GPU 支持没有为 Python 提供工具——所有的训练都必须通过基于 C++的命令行界面来完成。还有，Caffe 只支持单一风格的多 GPU 配置。“这不是一般的多 GPU 支持，”他说。

相比之下，TensorFlow“非常简单，令人惊叹，”Schumacher 说。所有必要的调整都是通过 **tf.device()，**完成的，其中指定使用 GPU。不需要额外的文档，也不需要对 API 进行任何更改。此外，TensorFlow 在架构方面更加灵活:您可以在两个 GPU 上运行一个模型的两个副本，或者在两个 GPU 上运行一个大模型。

**5。更好地支持多机配置:**使用 TensorFlow 支持多机也同样容易，Schumacher 断言。使用 Caffe，必须使用 [MPI 库](https://www.open-mpi.org/)。MPI 最初是为在大型多节点超级计算机上分解应用程序而开发的。因此，“对许多人来说，实现一个运行 Caffe 训练过程的 MPI 版本并不容易，”Shumacher 说。

TensorFlow 再次提供了一种为多节点作业配置作业的简单方法，只需将 **tf.device()** 设置为作业可以运行的机器数量。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>