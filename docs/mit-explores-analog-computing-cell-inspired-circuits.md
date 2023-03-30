# 麻省理工学院研究人员利用细胞启发电路探索模拟计算

> 原文：<https://thenewstack.io/mit-explores-analog-computing-cell-inspired-circuits/>

我们对现代计算的概念与数字计算机密切相关。但是，数字计算机所依赖的 1 和 0 的二进制系统是一种很差的方法，无法准确地模拟在活细胞和有机体中发现的生物系统的无限复杂性。

在新兴的生物信息学领域，模拟计算机变得不可或缺，科学家和工程师正在开发方法和软件工具，以更好地理解生物数据。

与用单独的[离散值](https://en.wikipedia.org/wiki/Continuous_and_discrete_variables#Discrete_variables)表示数据的数字计算机相比，模拟计算机能够将数据表示为一个跨越[连续](https://en.wikipedia.org/wiki/Continuous_and_discrete_variables#Continuous_variables)值范围的变量，这使它们在涉及实时连续变化的相互依赖的参数的情况下更加有效，例如生物系统中的参数。

> “‘数字’在今天几乎是‘计算机’的同义词，但这实际上是一种耻辱”——阿德里安·桑普森。

但是今天的大多数模拟计算机都是手动编程的，这是一个费力的过程，现在可能会被稍微容易一点的东西所取代，这要归功于[麻省理工学院 CSAIL](https://www.csail.mit.edu/) 研究生 [Sara Achour](https://people.csail.mit.edu/sachour/) ，他与顾问兼麻省理工学院教授 [Martin Rinard](http://people.csail.mit.edu/rinard/) 和达特茅斯大学教授 [Rahul Sarpeshkar](https://engineering.dartmouth.edu/people/faculty/rahul-sarpeshkar) 合作创建了 Arco，一个编译器，它采用我们人类可以理解的语言编写的高级指令，并将这些指令翻译成模拟计算机的低级电路规格

“模拟”这个词听起来可能像是回到了某个黑暗的前数字时代，或许这种描述是有点准确的:模拟计算机的初级版本至少已经存在了两千年，从著名的[安蒂基希拉机械装置](https://en.wikipedia.org/wiki/Antikythera_mechanism "Antikythera mechanism")到今天仍在使用的[计算尺](https://en.wikipedia.org/wiki/Slide_rule)。但是有些人认为，计算的未来将是模拟的，因为今天不断缩小的微芯片将不会为明天科学和医学研究中的复杂应用提供足够的计算能力。

## 细胞启发的模拟电路

该团队的论文最近在[计算机械协会](http://www.acm.org/)关于[编程语言设计和实现](http://conf.researchr.org/home/pldi-2016)的会议上发表。在这篇文章中，他们解释了 Arco 如何采用微分方程，并将其转换为流经模拟电路的实际电压，微分方程通常用于描述细胞生物学的复杂动力学。该编译器可以与任何可编程模拟设备一起工作，但特别是，该团队专注于 Sarpeshkar 已经在开发的模拟芯片，该芯片利用微分方程和模拟常见蜂窝系统的电路。

模拟方法的表现明显优于数字工具。在该团队的实验中，编译器使用五组与生物学研究最相关的微分方程进行了测试。响应时间从不到一分钟解决最简单的集合到几乎一个小时解决最复杂的集合(有 75 个微分方程)不等，与手动或数字方式设计模拟实现相比，这实际上是非常好的。

Sarpeshkar 在麻省理工学院的[新闻稿](http://news.mit.edu/2016/analog-computing-organs-organisms-0620)中说:“用几个晶体管，细胞形态[“细胞启发”]模拟电路可以解决复杂的微分方程——包括噪声的影响——这将需要数百万个数字晶体管和数百万个数字时钟周期。

此外，这项技术可以扩大规模，以解决更大的问题，如模拟整个器官，甚至是有机体，而不仅仅是一个细胞。

“‘数字’在今天几乎是‘计算机’的同义词，但这实际上是一种耻辱，”[艾德里安·桑普森](http://adriansampson.net/)说，他是康乃尔大学计算机科学的助理教授，在团队的论文中对他的帮助表示感谢。“每个人都知道，如果我们能够有效地利用模拟硬件，它会非常高效。这篇论文是我所记得的最有前途的编译器作品，可以让普通人编写模拟计算机程序。他们做的聪明的事情是针对模拟计算已经被认为是一个很好的匹配的一种问题——生物模拟——并建立一个专门针对这种情况的编译器。”

那么这对我们意味着什么呢？似乎有一场[模拟复兴](https://thenewstack.io/sound-geeks-resurrecting-analog-synthesizer/)正在进行，随着模拟计算在未来几年继续朝着未知的方向发展，我们可能会看到它支撑着[人工智能](http://21stcenturywire.com/2015/05/12/the-new-a-i-brain-has-arrived-and-its-analogue-not-digital/)、模拟计算机辅助药物设计和生物研究新时代等意想不到的发展。未来正在快速逼近，它很可能是模拟的，而不是数字的。

特征图片:[沃尔夫冈·斯蒂夫](https://www.flickr.com/photos/stiefkind/ "Go to Wolfgang Stief's photostream") (CC BY 2.0)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>