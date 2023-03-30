# 麻省理工学院的新人工智能解决了“假新闻”检测工具的漏洞

> 原文：<https://thenewstack.io/mits-new-ai-tackles-loopholes-in-fake-news-detection-tools/>

近年来，虚假信息的传播已经成为一股无处不在的力量——扰乱选举，破坏民主社会，并进一步将人们分成难以驾驭的群体，顽固地植根于破坏性的“我们对他们”的意识形态。据估计，社交媒体平台上分享的新闻故事有 20%到 38%被认为是假的，不幸的是，[假消息](https://en.wikipedia.org/wiki/Disinformation)已经成为新的规范，从四处传播的[假消息](https://thenewstack.io/frauds-behind-fake-facebook-news-feeds/)中辨别真相变得越来越难——无论是在书面文字中读到的，还是在照片中看到的[活动图像](https://thenewstack.io/deep-learning-ai-generates-convincing-deepfake-videos-of-mona-lisa/)。

为了解决这个问题，专家们已经提出了各种人工智能驱动的“假新闻”探测器。其中一些工具通过分析[新闻来源本身是否被认为是一贯真实的](https://thenewstack.io/mit-algorithm-sniffs-out-sites-dedicated-to-fake-news/)来识别欺骗性新闻文章，而其他工具通过[首先生成虚假信息，然后从中学习](https://thenewstack.io/grover-ai-detects-machine-generated-neural-fake-news-by-also-generating-it/)来学习如何嗅出机器生成的虚假信息。当然，这些方法仍然存在许多漏洞，因为它们不会评估一篇文章的潜在真实性，或者错误地认为所有机器生成的文本都是自动错误的——即使生成的文本包含真实的事实。

面对现有“假新闻”检测器中的这些明显缺陷，来自麻省理工学院[计算机科学和人工智能实验室](https://www.csail.mit.edu) (CSAIL)的一组研究人员开发了一种新算法，该算法实际上根据外部来源对新闻进行事实检查，此外还解决了可能导致算法错误地将真实陈述标记为虚假的隐藏偏见。

正如这项研究的主要作者和 CSAIL 博士生 Tal Schuster 向新堆栈解释的那样:“目前的一些检测器依赖于识别文本的来源来确定它是真是假。然而，这种方法有两个问题:[第一]，同一个来源，无论是人类记者还是自动文本生成器，都可能产生真实和错误的误导性文章。识别文本的来源不会有助于区分这两者。其次，想要制造假新闻的用户可以模仿其他来源，以避免被发现。”

## 改进自动事实核查

该团队在他们的第一篇[论文](https://arxiv.org/pdf/1908.09805.pdf)中指出，这些假设也忽略了这种自动文本生成器的合法用途，例如自动完成、文本修改、问答、文本简化和摘要。在这种情况下，机器生成的文本会被检测器自动标记为假，即使它们的内容是真的。

为了证明他们的观点，该团队使用自动文本生成器创建了一篇关于美国宇航局科学家收集日冕物质抛射数据的文章摘要。尽管生成的摘要具有事实准确性，但一个“假新闻”检测器将其标记为提供虚假信息，表明它无法分辨机器生成的文本是传递真实数据还是虚假数据。

在表明这个漏洞存在后，该团队随后将注意力转向分析在[狂热](http://fever.ai/)(事实提取和验证)中可能存在的任何潜在偏见，这是一个由人类注释的真假语句组成的数据集，与维基百科文章中的数据进行交叉检查，经常被机器学习研究人员使用。该团队的分析表明，许多由人类标注的虚假陈述包含“泄露”短语，如“没有”和“还没有”因此，在 FEVER 数据集上训练的模型最终有时会错误地将包含这些单词的语句标记为错误——即使它们实际上是正确的——因为它们只评估文本的措辞，而不是通过外部来源检查语句的真实性。

因此，为了进一步测试这一点，该团队随后基于发烧创建了一组去偏差的数据。当运行假新闻检测模型时，他们惊讶地发现，其准确率从 86%下降到 58%，研究人员认为这是由于模型的初始训练。

“事实核查数据集很难找到，”CSAIL 博士生兼论文合著者 Darsh Shah 解释道。“那些存在的和人工创造的，比如发烧，是极端偏颇的。因此，在这种数据集上训练的模型也是有偏见的，不能应用于现实世界。这些模型很脆弱，很容易被愚弄。”

我们知道[隐藏的偏见](/removing-bias-from-ai-is-a-human-endeavor/)可以影响机器学习模型[深刻影响人类生活](https://thenewstack.io/hidden-gender-racial-biases-algorithms-can-big-deal/)，所以可以理解为什么无偏见的事实验证在大众媒体中越来越迫切。为了解决这个问题，该团队随后创建了一种新的事实核查算法，在他们的去偏差数据集上进行训练，这在他们的[第二篇论文](https://arxiv.org/pdf/1908.05267.pdf)中有所描述。Shah 说:“(我们的)去偏差算法……对数据集实例进行重新加权，从而降低了赠品短语的影响。”。"使用这种方法训练，模型始终优于以前的方法，特别是在现实环境中."

该团队建议，未来需要更大、无偏见的训练数据集来帮助专家开发更好、更强大的自动“假新闻”检测模型，最好是能够适应不同语言和主题的模型，并使用来自维基百科以外的广泛知名来源的证据。目前，该团队已经将他们的人工智能模型在网上公开，希望其他研究人员将把它纳入他们的项目。

“这项工作是一个大开眼界的所有其他工作在事实检查，”沙阿说。“数据集上的高性能不一定意味着现实世界的适用性。除了我们的工作指出的这种必要的重新评估之外，我们的去偏差算法也可以减少潜在偏差的影响，以确保最终的模型可以在野外很好地执行事实检查。”

*看团队的[第一篇论文](https://arxiv.org/pdf/1908.09805.pdf)和[第二篇论文](https://arxiv.org/pdf/1908.05267.pdf)，在这里找到他们的型号[。](https://github.com/TalSchuster/FeverSymmetric)*

图片:[马库斯 P.](https://unsplash.com/@marcusp?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 通过 [Unsplash](https://unsplash.com/s/photos/facts-matter?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>