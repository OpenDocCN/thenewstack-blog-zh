# 英特尔为可扩展深度学习奠定了基础

> 原文：<https://thenewstack.io/intel-sets-base-scalable-deep-learning/>

“人工智能在我们身边无处不在。英特尔执行副总裁兼数据中心集团总经理黛安·布莱恩特在本周于三藩市举行的英特尔开发者论坛上发表主题演讲时说。

在活动中，该公司用虚拟现实、物联网和环境计算的高级应用承诺来戏弄开发者，当然，所有这些都需要大量的处理能力，对该公司来说，最好是英特尔类型的处理能力。今年，英特尔也推广了人工智能和[机器学习](/category/machine-learning/) (ML)。

她说，自动照片标记、语音转文本、欺诈检测、精准医疗、自动驾驶汽车都受益于人工智能。

人工智能的主要驱动力之一是机器学习。去年大约有 7%的服务器是为机器学习而部署的。而且这个数字还在增长。到 2020 年，运行人工智能驱动的分析工作负载的服务器将超过任何其他工作负载。“机器学习及其子集技术，深度学习，是扩展人工智能领域的关键方法，”她说。

她指出，机器学习本质上是一种分布式并行高性能工作负载。数学并不新鲜，甚至也不难。这是简单的线性代数。但这确实需要规模。

“你能计算的数据越多，模型就越准确，你能对模型进行的计算越多，模型训练和收敛的速度就越快，”布莱恩特说。

目前，[英特尔至强](http://www.intel.com/content/www/us/en/processors/xeon/xeon-processor-e7-family.html)处理器是最广泛部署的 ML 芯片。该公司正在宣传将于 2017 年推出的下一代至强融核芯片，被称为“[骑士登陆](http://www.forbes.com/sites/aarontilley/2016/08/17/intel-takes-aim-at-nvidia-again-with-new-ai-chip-and-baidu-partnership/#142f82094f5a)，[是机器学习的真正主力](http://www.nextplatform.com/2016/06/20/intel-knights-landing-yields-big-bang-buck-jump/)。芯片组将包括可变精度浮点的新指令。“至强和至强融核本质上是可扩展的架构，”Bryant 说(尽管 Nvidia 最近指控英特尔搞砸了一些 Phi 性能数据)。

该公司在这一领域有很多竞争对手，特别是来自 Nvidia 等 GPU 公司的竞争。Bryant 认为，使用 ML，您希望在处理生产工作的同一个处理器上进行开发，因此一旦投入生产，训练模型将是准确的。“一旦你训练了一个算法，你就不想重新编码和优化它，”她说。她认为，加速器(比如说 GPU)也会增加编程的复杂性。

为了进一步启动 ML，英特尔正在优化许多广泛使用的 ML 框架，以便它们能够在英特尔处理器上更高效地运行。有英特尔优化版本的 [Caffe](https://github.com/intelcaffe) 和 Theano，不久公司将发布优化版本的 [TensorFlow](https://thenewstack.io/look-inside-tensorflow-googles-open-source-deep-learning-framework/) 、 [CNTK](https://github.com/Microsoft/CNTK) 和 [Torch](http://torch.ch/) 。

“我们正在投资，以确保所有这些框架在单个至强或至强融核上运行出色，同时确保它们在规模上运行，”Bryant 说。

这些框架通过将它们连接到英特尔创建的许多库中进行优化，以尽可能最有效的方式与其处理器进行交互。这些库包括[英特尔数学内核库](https://software.intel.com/en-us/intel-mkl) (MKL)和[英特尔数据分析加速库](https://software.intel.com/en-us/blogs/daal) (DAAL)。今年晚些时候，该公司还将发布一个用于神经网络训练的库，名为[深度神经网络数学内核库](https://software.intel.com/en-us/articles/deep-neural-network-technical-preview-for-intel-math-kernel-library-intel-mkl) (MKL-DNN)，以及一个用于深度学习的[软件开发工具包](https://software.intel.com/en-us/machine-learning/deep-learning/sdk-signup)。

布莱恩特还提到了英特尔计划以 4 亿美元收购深度学习初创公司 [Nervana Systems](https://www.nervanasys.com/) 、。

“他们的知识产权，以及他们在加速深度学习算法方面的深厚专业知识，将直接应用于我们在人工智能方面的进步，”她说。“他们有芯片级、库级和框架级的解决方案。”

[英特尔](https://www.intel.com/content/www/us/en/it-management/intel-it/it-managers.html)是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>