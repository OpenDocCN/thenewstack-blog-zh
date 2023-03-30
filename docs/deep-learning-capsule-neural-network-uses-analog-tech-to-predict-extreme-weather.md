# 深度学习“胶囊神经网络”使用模拟技术来预测极端天气

> 原文：<https://thenewstack.io/deep-learning-capsule-neural-network-uses-analog-tech-to-predict-extreme-weather/>

[莱斯大学](https://www.rice.edu/)的研究人员使用一种源于二战时期的基于模拟的技术来预测天气，开发了一种[深度学习人工智能](https://www.geeksforgeeks.org/introduction-deep-learning/)，它可以“教会”自己提前五天预测恶劣天气事件，即使当前天气状况的信息不完整。

该团队的模型使用[胶囊神经网络](https://www.geeksforgeeks.org/capsule-neural-networks-ml/) (CapsNets)，使用一种模拟生物大脑的人工神经网络，以更好地识别模式。

[越来越多的科学证据](https://www.carbonbrief.org/mapped-how-climate-change-affects-extreme-weather-around-the-world)表明，洪水、干旱和热浪等极端天气事件[的频率确实在增加](https://www.sciencedaily.com/releases/2018/03/180321130859.htm)，而且很可能是由人类活动引起的[。虽然我们在全球范围内还远远没有任何一种全面的解决方案，但与此同时，我们迫切需要有效的工具来提前及时准确地预测这种极端天气事件，从而防止重大损失并有可能挽救生命。](https://www.sciencedaily.com/releases/2016/03/160311133516.htm)

## 模拟信号的返回

正如莱斯大学的团队解释的那样，过去的天气预测是由人类专家通过研究以前的天气模式目录来完成的，以便将过去的天气状况与当前的天气状况进行比较，从而找到一种模拟，或一种与现有气象状况最相似的模式。基于对过去类似天气事件后发生的事情的观察，人们可以预测几天后会发生什么。

然而今天，天气预报技术用数字方法处理这个问题，使用一种叫做[数字天气预报](https://www.ncdc.noaa.gov/data-access/model-data/model-datasets/numerical-weather-prediction) (NWP)的东西，它在 20 世纪 50 年代计算机出现后取代了模拟方法。虽然数值天气预报的准确性在过去几十年中有所提高，但它仍然不能可靠地预测更多的极端事件。

“导致中纬度地区(北美大部分地区、欧洲、亚洲大部分地区)热浪和寒流等极端事件的天气模式通常是由于急流中的异常模式:高低压系统的异常配置，”赖斯机械工程和行星科学助理教授、该研究的合著者 Pedram Hassanzadeh 说。“因此，鉴于这一点，以及基于人工智能的模式识别技术的最新进展，我们想看看我们是否可以回到模拟预测的想法，但利用人工智能。”

为了创建他们的模型，团队修改了他们解决问题的方法；他们最初使用的人工智能方法是[卷积神经网络](/deep-neural-network-ai-reconstructs-mysterious-image-hidden-in-picasso-painting/)(CNN)。然而，他们的方法很快就变成了模式识别，当时该团队发现了一种新的深度学习形式，称为胶囊神经网络。与 CNN 不同，胶囊神经网络没有“池层”，这减少了特征图的维度，因此减少了要学习的参数数量和网络中执行的计算量。CapsNets 还使用嵌套神经层的“胶囊”，使它们能够识别相对空间关系，这对预测极端天气事件至关重要。

Hassanzadeh 说:“与 CNN 不同，CapsNets 没有池层，可以跟踪要素的相对位置。”“这对我们的模拟预报框架非常重要，因为高低压系统的相对位置对于确定天气系统如何随时间演变以及地表是否会出现极端情况非常重要。”

该团队的模型通过处理数百对地图来训练自己，每一张地图都显示表面温度和气压等特征，时间间隔为几天。经过训练，该团队的模型能够提前五天预测极端天气事件，准确率达到 85%。

研究人员现在的目标是进一步推进他们的模型，使其能够提前十天做出预测。虽然该团队警告说，他们的模型不是 NWP 的替代品，但这种新方法可能有助于提高未来天气预报的准确性，同时降低计算要求。

“提高 NWP 模型的分辨率可能会提高它们的预测技能，但这将增加它们的计算成本和产生预测的时间，”Hassanzadeh 警告说。“我们负担不起一直以更高的分辨率运行 NWP 模型。因此，使用我们的框架的一个方法是训练顶网提供早期预警。如果模拟方法预测到加州的热浪，我们可以相应地提高 NWP 分辨率，这将有助于更好地预测加州的热浪。这可能会提高极端天气事件预测的准确性，而不需要更多的计算能力。”

在*地球系统建模进展杂志*上阅读更多该团队的论文。

来自 Pixabay 的 Gerhard Gellinger 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>