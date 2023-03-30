# NASA 和 IBM 用新的基础模型加速人工智能创造

> 原文：<https://thenewstack.io/nasa-and-ibm-to-speed-ai-creation-with-new-foundation-models/>

NASA 和 IBM 正在合作，基于 NASA 的数据集——包括地理空间数据——创建基础模型，目标是加速 AI 模型的创建。

基础模型在大型、广泛的数据集上进行训练，然后通过使用有针对性的较小数据集来训练其他人工智能模型。基础模型可以用于不同的任务，并且可以将关于一种情况的信息应用于另一种情况。一个实际的基础模型的例子是 ChatGPT3，它是用基础模型 GPT3 构建的。

负责监督 IBM 混合云平台和开发人员生产力研究战略的 Priya Nagpurkar 表示，这种方法加快了人工智能模型的创建。

Nagpurkar 说:“我们很高兴这是一个关键的证据，也是我们 IBM 首次将基础模型技术应用于科学，特别是这种规模的数据。”“基础模型是 IBM Research 的一大推动力的一部分，让我们兴奋的是基础模型这一新兴的人工智能技术，它可以摄取大量未标记的数据并进行传输，在一个领域学习并将其应用于其他领域，[这]大大简化了下游任务和人工智能应用，也消除了对大量劳动力数据的需求。”

## NASA 和 IBM 的两个人工智能模型目标

[基础模型](https://research.ibm.com/blog/what-are-foundation-models)可能很强大:最初 IBM 花了 7 年时间训练沃森掌握 12 种语言。通过使用基础模型，IBM 在大约一年的时间里将沃森的语言能力提高到了 25 种语言。

位于阿拉巴马州亨茨维尔的美国宇航局马歇尔太空飞行中心的高级研究科学家[拉胡尔·拉马钱德兰](https://www.linkedin.com/in/rramachandran05/)说:“这里的关键是，它将在建立和解决具体科学问题方面扩大和加速科学进程。“人们不必从收集大量训练数据开始构建自己的个人机器学习管道，而是可以从基础模型开始，通过一些有限或精心策划的训练样本，你应该能够构建满足你的科学或应用需求的应用程序。”

联合新闻稿称，这项联合工作的目标是促进科学理解，以及对自然灾害和气温变暖等地球和气候相关问题的回应。合作将在两个领域应用基础模型:

1.  第一个模型将在超过 300，000 份地球科学出版物上进行培训，以按主题组织文献，并使其更容易搜索和发现新知识。
2.  第二个模型将在美国地质勘探局和美国宇航局广受欢迎的[协调的陆地感知 2 (HLS2)](https://hls.gsfc.nasa.gov/) 卫星数据集上进行训练，其用途从检测自然灾害到跟踪植被和野生动物栖息地的变化。例如，它可以通过检测损坏的屋顶、确定洪水的边界、帮助草原管理和估计生物量来估计龙卷风的破坏。

## 地理空间数据的技术挑战

2020 年，NASA 举办了一场关于整合 [AI](https://thenewstack.io/key-concepts/artificial-intelligence/) 和[机器学习](https://thenewstack.io/key-concepts/machine-learning/)的研讨会，NASA 在会上确定了两个挑战:首先，缺乏训练深度学习模型所需的训练数据集 Ramachandran 称之为“一个主要的科学瓶颈”第二，现有的人工智能模型不能跨越空间和时间进行概括。

IBM 和 NASA 官员在周二的新闻发布会上承认，虽然第一语言模型项目已经有了概念验证——IBM 和 NASA 推测可能在年中准备就绪——但第二个目标面临技术挑战。

“我们正在寻找新的、创新的解决方案来解决这些问题……我认为基金会模式有潜力解决这些挑战，”Ramachandran 说。

IBM 首席研究员 Raghu Ganti 进一步解释说，HLS2 数据集的遥感器带来了独特的挑战，因为它记录了地球物理空间数据，其中包括时间和空间信息。

“为了在这些数据的基础上训练一个模型，建立基础模型的变压器技术必须改变，”他说。“这些是我们正在探索的问题。”

Transformer 技术是一种深度学习模型，主要用于自然语言处理和计算机视觉领域。转换器设计用于处理顺序输入数据，包括自然语言，以进行翻译和汇总。与像递归神经网络这样的老方法不同，变压器一次处理全部输入——因此，变压器技术可以处理一个句子，而不是一次消化一个单词。这种方法减少了培训时间。

还有一个事实是 [NASA 的档案数据](https://thenewstack.io/artemis-mission-telescopes-present-data-challenges-for-nasa/)目前为 70pb，预计随着高数据速率任务的启动，几年内将增长到 250，如 12 月启动的 [SWOT](https://swot.jpl.nasa.gov/) 和计划于 2024 年启动的 [NISAR](https://nisar.jpl.nasa.gov/) 。

“我们所有的数据都是公开的，我们支持全球 70 亿用户访问我们的数据进行研究和应用，”Ramachandran 说。“我们的目标是让我们的数据，即美国宇航局的数据——这对科学界来说真的很有价值——可被发现、可访问并可用于全球范围内的广泛科学用途和应用。”

他说，这些项目的一个目标是降低最终用户使用这些数据的门槛。

## NASA 和 IBM 将使用 PyTorch

Ganti 说，这些模型将对公众开放，并将利用 PyTorch。

“我们的培训平台利用 PyTorch，我们完全依赖 PyTorch 来培训我们所有的基础模型，我们也与 PyTorch 合作，推动所有这些模型的培训，”Ganti 说。“PyTorch 是所有开源开发人员的首选深度学习框架[,我们只想确保我们所有的基础模型、培训技术和我们培训的模型都在 PyTorch 中，并回馈给社区。”](https://www.dominodatalab.com/blog/tensorflow-pytorch-or-keras-for-deep-learning)

基础模型平台构建在 [Red Hat OpenShift](https://thenewstack.io/red-hat-openshift-presses-outward-to-the-edge-enhances-developer-experience/) 之上，支持在公共或私有云中的任何超级缩放器上运行。Ganti 说，Red Hat OpenShift 将“让你用现成的食谱更快地训练这些模型”。

例如，利用 NASA 数据建立的模型，他们利用了大约 10 亿个令牌。根据 ML 工程师和 AI 博客 [Vaclav Kosar](https://vaclavkosar.com/ml/Tokenization-in-Machine-Learning-Explained) 的说法，标记化是将输入数据分割成一系列有意义的部分。

“给你一个比较，一个开源模型，这是一个非常高质量的模型，有 500 亿个令牌，”Ganti 说。“这个特别的程序需要……在 32 个 GPU 上大约需要 6 个小时——这差不多就是它现在正在做的事情。因此，你会看到速度的显著提高，因为我们正在采取的所有训练方法都得到简化。”

他指出，这对开发人员的生产力是一个很大的提高，并补充说，将这一点交给开发人员是“我们在战略上感兴趣的事情”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>