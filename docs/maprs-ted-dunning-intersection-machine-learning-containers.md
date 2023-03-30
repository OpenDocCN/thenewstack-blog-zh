# MapR 的 Ted Dunning:机器学习和容器的交集

> 原文：<https://thenewstack.io/maprs-ted-dunning-intersection-machine-learning-containers/>

[MapR 的 Ted 催款:机器学习与容器的交集](https://thenewstack.simplecast.com/episodes/maprs-ted-dunning-the-intersection-of-machine-learning-and-containers)

你将如何编排一个集装箱化的建筑，它的目的不仅仅是*保留*状态，而是实际上一个街区一个街区地建造，就像埃及金字塔或总统的借口？

在最新一期的[播客中，](https://thenewstack.io/podcasts/makers) [MapR](https://mapr.com/) 的首席应用架构师， [Ted Dunning](https://twitter.com/ted_dunning) 提出了一个有趣的想法:一种“反向负载平衡”架构，其中无状态容器被赋予适用于机器学习的构造任务，但在有限的时间内要么完成工作，要么放下工具回家。他称之为*会合架构*。

如果世界上的每一个应用程序都可以很容易地用自动化过程来容器化，这可能已经发生了。我们以前在新的堆栈中讨论过许多维护状态的方法——在一个不那么深奥、听起来更诚实的世界中，这与“拥有自己的数据库”是一回事对于无状态系统，有状态构造是一个非常巧妙的技巧。或者至少现在，你可以选择几个非常好的技巧，也许还有一些不那么好的。

但是[机器学习](/category/machine-learning/)是不同阶的野兽。言下之意，你学到的东西就是你记住的东西。如果你可以接受机器可以“学习”任何东西的观点，那么如果机器也能够在每次迭代中把自己的历史一笔勾销，那么这个观点就毫无意义。除非保留同样的美德，否则即使是虚拟的东西也不可能是真实的。

“这不是一个可以处理所有机器学习部署问题的通用架构，”邓宁在接受 New Stack Makers 播客采访时说。“它处理一类特殊的、广泛使用的决策系统，你问一个问题，给它一些请求，然后你得到一个有限大小的回应。”

该架构解决了邓宁警告的机器学习的“无聊”方面——具体来说，就是物流。在一个典型的学术人工智能系统中，一个程序被赋予一个要解决的任务，它在指定的时间内尽最大努力返回一个解决方案。Rendezvous 将以类似的方式工作，除了在给定的时间间隔内有多个容器参与响应。容器所能提供的解决方案被交付给一种代理，不管它是否准备好了。这个代理过滤掉好的输出和坏的输出，并把结果——也许还有一个可信度指数——呈现给调用它的函数。

### 在这个版本中:

[2:08:](https://thenewstack.simplecast.com/episodes/maprs-ted-dunning-the-intersection-of-machine-learning-and-containers?t=2:08) 邓宁关于机器学习应该如何融入容器化环境的想法。
[9:08:](https://thenewstack.simplecast.com/episodes/maprs-ted-dunning-the-intersection-of-machine-learning-and-containers?t=9:08) 将学习框架转变为容器化
[14:32:](https://thenewstack.simplecast.com/episodes/maprs-ted-dunning-the-intersection-of-machine-learning-and-containers?t=14:32) 探索数据专家、数据操作员和数据科学家之间的技能差异。
[21:41:](https://thenewstack.simplecast.com/episodes/maprs-ted-dunning-the-intersection-of-machine-learning-and-containers?t=21:41) 讨论演示容器及其背后的数学是用来做什么的教育和培训。
[25:46:](https://thenewstack.simplecast.com/episodes/maprs-ted-dunning-the-intersection-of-machine-learning-and-containers?t=25:46) 教育如何激励人们以一种直接而富有成效的方式利用个人所学。
[33:57:](https://thenewstack.simplecast.com/episodes/maprs-ted-dunning-the-intersection-of-machine-learning-and-containers?t=33:57) 机器学习系统如何处理 SLA 式契约以及置信度指标的可能性。

专题图片:艺术家描绘的由詹姆斯·赫德伯格创作的单个原子厚的合成石墨烯片，在知识共享 3.0 下获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>