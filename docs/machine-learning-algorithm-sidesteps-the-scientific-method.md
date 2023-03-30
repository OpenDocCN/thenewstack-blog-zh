# 机器学习算法回避科学方法

> 原文：<https://thenewstack.io/machine-learning-algorithm-sidesteps-the-scientific-method/>

几个世纪以来，科学方法——基于观察过程，提出假设，然后通过实验证明或否定该假设——一直是现代科学的基石。这是一种被许多科学领域使用的技术，因为它提供了一种使用经验证据逻辑和理性地回答问题的结构化指南——这种方法引领人类走出黑暗时代，进入今天的时代，在这个时代，物理学、天文学和现代医学的突破性发现是可能的。

但是在科学研究中有不需要科学方法的情况吗？普林斯顿大学[等离子体物理实验室](https://www.pppl.gov/) (PPPL)的一组研究人员现在提出，这确实是可能的——通过使用一种可以预测行星物理轨道的机器学习算法，而无需基于物理定律。

关于这项工作的[论文](https://www.nature.com/articles/s41598-020-76301-0)最近发表在 [*科学报告*](https://www.nature.com/articles/s41598-020-76301-0) 上，概述了该团队如何根据水星、金星、地球、火星、木星和矮行星谷神星的已知轨道数据训练机器学习算法。这种机器学习算法，再加上该团队所谓的“服务算法”，然后被用于预测其他行星的轨道——包括太阳系的抛物线和双曲线逃逸轨道——而不需要输入牛顿运动和引力定律。相反，这种方法形成了该团队所谓的离散场理论，该理论将宇宙建模为一种“黑箱”。这种方法意味着人们可以从“数据到数据”——从训练数据到预测——而不依赖于物理定律提供的中间步骤。

“值得强调的是，服务和学习算法不知道、学习或使用牛顿运动定律和万有引力，”该团队写道。“离散场理论直接将观测数据和新的预测联系起来。不需要牛顿定律。”

本质上，该团队的算法能够学习行星运动的规律，并理解任何物理系统背后的动力学，只需通过几个例子进行训练。该算法不需要依赖于求解复杂的微分方程来提供高度精确的预测。

研究人员说:“提出的方法从一组给定的训练数据中学习场论，这些数据由离散时空位置的物理场的观察值组成。”他们解释说:

*“物理定律根本上是以场论的形式表达的，而不是微分方程。因此，更重要的是尽可能学习基础领域的理论。由于场论通常比相应的微分方程更简单，因此学习场论更容易，这对人类智能和人工智能都是如此。除了观察数据受场论支配的基本假设之外，所提出的学习和服务算法不假设任何物理定律的知识，例如牛顿运动定律和[薛定谔方程](http://hyperphysics.phy-astr.gsu.edu/hbase/quantum/schr.html)【预测动态系统未来行为的波动方程】。这与物理学中大多数现有的机器学习方法论不同。”*

我们可能最熟悉机器学习算法，因为它们用于[推荐引擎](https://thenewstack.io/40-something-dude-asks-for-music-recommendation-redditors-point-to-the-algorithms/)和[面部识别](https://thenewstack.io/clearviews-controversial-facial-recognition-ai-automates-mass-surveillance/)和[自然语言处理](https://thenewstack.io/openais-gpt-3-makes-big-leap-forward-for-natural-language-processing/)应用。然而，在物理学领域，机器学习算法通常用于模拟复杂的过程，如磁聚变设备中的等离子体破裂，或模拟流体的动态运动。在普林斯顿团队的这项工作中，该算法跳过了需要用物理惯例显式编程的中间步骤。

“开发的算法对物理支配定律的变化是鲁棒的，因为该方法不需要任何物理定律的知识，除了基本假设支配定律是场论，”该团队说。“当狭义相对论或广义相对论的影响很重要时，这些算法也应该是有效的。”

## 生活在电脑模拟中？

研究人员的方法部分受到牛津哲学家尼克·博斯特罗姆的哲学思想实验的启发，他认为宇宙实际上是一个计算机模拟。博斯特罗姆的[模拟假说](https://www.simulation-argument.com/simulation.html)指出，人类可能已经进入了一个高度科技化的“后人类”阶段，在那里可以获得巨大的计算能力。博斯特罗姆接着假设，我们可能实际上生活在一个“祖先模拟”中，这个模拟是由我们的后人类后代运行的——几乎类似于某人打开游戏机玩视频游戏。

> “值得强调的是，服务和学习算法不知道、学习或使用牛顿运动定律和万有引力，”该团队写道。“离散场理论直接将观测数据和新的预测联系起来。不需要牛顿定律。”

“模拟假说指出，物理宇宙是一个计算机模拟，物理学家正在仔细研究它是否可能成为现实，”该团队说。“如果假设是真的，那么时空必然是离散的。物理学中的场论也是如此。因此，至少从理论角度来看，提出离散场理论的一些机器学习和服务算法是离散宇宙(即计算机模拟)运行以最小化行动的方法是合理的。”

虽然我们可能无法确定我们是否真的很快生活在模拟中，但该团队表示，他们的新方法可能会在预测等离子体粒子在聚变能量实验中的行为方面有一些有趣的应用。当两个或多个原子核结合形成一个或多个不同的原子核和亚原子粒子时，就会发生聚变，从而产生巨大的能量。核聚变是恒星的主要能源，如果科学家能够预测核聚变过程是如何工作的，这可能是利用它作为一种近乎无限的可再生能源的一种方式。目前，该团队正致力于通过降低噪声来提高机器学习模型的准确性，例如使用噪声消除信号或采用[生成机器学习模型](https://thenewstack.io/machines-learn-learn-like-humans-new-breakthrough-algorithm/)。

更多阅读团队[论文](https://www.nature.com/articles/s41598-020-76301-0)。

图片:Karlis Reimanis 通过 Unsplash 拍摄

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>