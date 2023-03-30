# Google I/O 展示了 TensorFlow 的机器学习优势

> 原文：<https://thenewstack.io/tensorflow-grows-google-io/>

随着谷歌大举押注其机器学习和分析能力将成为其谷歌云平台的巨大优势，难怪该公司在今年的谷歌 I/O 活动上花了大量时间展示其各种[机器学习](/category/machine-learning/)和人工智能工具，包括更新的 [TensorFlow](https://www.tensorflow.org/) 。

虽然谷歌提供了 [BigQuery](https://cloud.google.com/bigquery/) 和其他大数据分析工具，但 TensorFlow 机器学习建模库仍然是谷歌在该领域的独特价值主张。当许多其他人工智能和机器学习工作专注于服务器时，TensorFlow 不仅专注于服务器端，还专注于边缘设备。

本周早些时候，谷歌推出了[谷歌云平台](https://cloud.google.com/) [物联网核心](https://cloud.google.com/iot-core/)，这是一套用于处理大量物联网设备及其产生的数据的工具和分析工具。TensorFlow 也是这一平台战略的一部分，谷歌的物联网战略重点关注将 TensorFlow 模型推向边缘设备的能力。这使得单个设备能够执行面部识别、语音识别和图像识别等操作，而不必连接到核心应用。

谷歌内部已经将 TensorFlow 应用于 1000 多个内部项目，从 Gmail 到 Google Photos。在 Google 之外， [GitHub](https://github.com/tensorflow/tensorflow) 上的 TensorFlow 知识库是这项服务上最受欢迎的开源 ML 项目。

为了继续推动该项目的发展，谷歌 I/O 主办了许多 TensorFlow 演示，包括第二版 [TensorFlow 处理器单元](http://www.tomshardware.com/news/google-tensor-processing-unit-machine-learning,31834.html) (TPUs)，这是为矢量计算定制的专用集成电路。谷歌高级硬件工程师 Andy Swing 表示，TPU 版本可以处理 TensorFlow 模型的训练和执行。

TPU 2 是专门为帮助训练张量流模型而设计的。Swing 说，与 TPU 版本 1 不同，TPU 版本 2 是从头开始设计的，专门用于加快 TensorFlow 模型的训练时间。

“最初的第一版仍在大量使用，但它们是专门为一项任务设计的:推理。这个版本是针对培训的。它可以扩展到 64 个单元，这对训练很有好处，因为现在没有那么大的模型，”Swing 说。

当一名谷歌工程师意识到如果每个拥有安卓手机的人每天只使用语音识别三分钟，那么谷歌将不得不将其数据中心的数量增加一倍时，第一台 TPU 首次被开发出来。

TPU 2 提供 180TFLOPS 的浮点运算性能。它拥有 64GB 的高带宽内存，以及定制的网络功能，可以承载多个 TPU。谷歌团队目前正在征集机器学习项目的开发者，以便在他们的 1000 台设备集群上运行。

在展会的其他地方，[谷歌的 Magenta 团队](https://magenta.tensorflow.org/welcome-to-magenta)正在展示其与 TensorFlow 的合作。Magenta 是[谷歌大脑](https://research.google.com/teams/brain/)项目中的一个子团队，其任务是将机器学习和艺术结合起来，创造有趣的体验。在谷歌 I/O，这采取了[人工智能二重奏](https://aiexperiments.withgoogle.com/ai-duet)的形式。

Kory Matheson 是 Magenta 人工智能二重奏团队的开发人员之一，他说该项目试图在音乐键盘上与人工智能进行有趣的互动。当你弹奏钢琴时，AI-Duets 会发出自己的音符，即兴表演各种二重奏:

[https://www.youtube.com/embed/0ZE1bfPtvZo?feature=oembed](https://www.youtube.com/embed/0ZE1bfPtvZo?feature=oembed)

视频

Matheson 说，为了训练这个应用程序，TensorFlow 项目分析了大量的 MIDI 文件和流行歌曲的假书备忘单。马西森说，该模型相当深入和庞大，并通过基于网络的界面在线托管。

在 Google I/O 上围绕 TensorFlow 反复出现的一个话题是被称为 [Keras](https://keras.io/) 的高级神经网络 API。这个深度学习库被谷歌开发者反复提及，事实上，这个开源的深度学习库是 GitHub 上第二受欢迎的机器学习项目。尽管 Keras 来自谷歌之外，但该团队已经接受并支持了这个项目。

针对 Google I/O，发布了 TensorFlow 的[版本 1.2](https://github.com/tensorflow/tensorflow/blob/r1.2/RELEASE.md) 的发布候选。[这个版本中的变化](https://github.com/tensorflow/tensorflow/blob/r1.2/RELEASE.md)包括许多重大修复，Windows 上 C 库的可用性，以及一个新的调用，以更少的开销反复运行类似的步骤。

**专题图片**:谷歌首席执行官桑德尔·皮帅在 2017 年谷歌 I/O 大会上赞美人工智能的优点(亚历克斯·汉迪)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>