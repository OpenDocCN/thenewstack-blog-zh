# 量子计算机上的算法加速蒙特卡罗预测

> 原文：<https://thenewstack.io/algorithm-speeds-monte-carlo-predictions-on-quantum-computers/>

在一个不确定的气候变化幽灵和全球疫情占据头条新闻的世界，能够准确预测潜在结果可以帮助我们更好地确定在任何给定场景下哪一条是最佳前进道路。虽然预测的实践从古代就开始了，但只是在最近几十年，计算机才通过推动数据驱动的预测分析方法在该领域留下了自己的印记。

处理这种预测的最著名的一类计算算法是[蒙特卡罗方法](https://www.investopedia.com/terms/m/montecarlosimulation.asp)，当随机变量起作用时，这种方法用于模拟不同结果的概率。但是运行这些模型可能是计算密集型的，并对今天基于二进制的“经典”计算机的计算极限提出了挑战。因此，下一个合乎逻辑的步骤是过渡到使用更强大的[量子计算机](https://thenewstack.io/quantum-computings-challenging-liftoff-to-commercialization/)，以便更快和更准确地模拟当今最紧迫问题中固有的复杂全谱。

## 量子加速

总部位于英国的初创公司[Cambridge Quantum Computing](https://cambridgequantum.com/)开发了一种新的算法，展示了如何大幅加快这些预测的执行速度，这将推动新兴的量子计算行业的发展，这在最近的预印论文[中有详细介绍。](https://arxiv.org/pdf/2105.09100.pdf)

“蒙特卡罗方法在科学和商业中非常普遍——基本上，任何时候在面对不确定性时必须做出一些合理的决定，蒙特卡罗方法都有可能被部署，”CQC 的高级研究科学家 Steven Herbert 博士解释道。“这包括从天气预报到在大型强子对撞机中设计粒子物理实验，到在一场缩减的体育赛事中决定谁获胜(例如，在板球比赛中使用[杜克沃斯-路易斯方法](https://www.espncricinfo.com/story/a-simple-explanation-of-the-duckworth-lewis-method-117058))——以及体育博彩市场的定价。”

特别是，赫伯特的工作集中在一种被称为[蒙特卡罗积分](https://www.scratchapixel.com/lessons/mathematics-physics-for-computer-graphics/monte-carlo-methods-in-practice/monte-carlo-integration)的技术上，这种技术被银行、资产管理公司、对冲基金和财务规划师用来做类似[期权定价](https://www.investopedia.com/terms/o/optionpricingtheory.asp)和[风险分析](https://www.investopedia.com/terms/r/risk-analysis.asp)的事情。

“‘蒙特卡洛积分’实际上只是一个冠冕堂皇的名称，用于从一些概率分布中取样(例如，当我们掷骰子时，我们均匀地‘取样’一个介于 1 和 6 之间的数字)，然后平均这些样本以接近平均值，”赫伯特说。“然而，这个简单的过程是非常计算密集型的，因此存在二次量子加速的事实(二次意味着量子算法将在经典时间的平方根左右完成)使它成为最先看到真正有用的量子优势的应用程序之一，这是一个非常有吸引力的前景。”

> 相比之下，剑桥量子计算的新算法利用量子计算的能力，在模拟中模拟更多的随机值，从而增加预测的规模和准确性。

通常，在“经典”计算机系统上运行的蒙特卡洛模拟可能需要几个小时——有时甚至是一夜——才能完成。到那时，模拟的结果可能已经过时了。虽然基于过时的结果做出重要决策可能不会对优化供应链中的交付时间等事情产生巨大影响，但在疫情这样的关键事件中制定战略时，这有时可能意味着生死之别。

相比之下，CQC 的新算法利用量子计算的能力，在模拟中模拟更多的随机值，从而增加预测的规模和准确性。它通过使用混合方法来实现这一点，其中一部分模拟在传统计算系统上运行，另一部分使用量子计算机执行，从而在经典系统的运营成本效益与量子系统的更高精度和可观的计算能力之间取得平衡。

“量子蒙特卡罗积分的每一种方法都比经典蒙特卡罗具有理论上的‘二次’量子优势，”赫伯特说。“然而，在这一突破之前，为了进行量子蒙特卡罗积分，你还必须在量子计算机上执行‘算术’操作，如反正弦和平方根。然而，这样做并没有内在的量子优势，也没有人知道如何将这些运算卸载到经典计算机上。这就是我所做的，如果我们要在' [NISQ](https://medium.com/quantum-london/nisq-noisy-intermediate-scale-quantum-7ea1bc3981df) 时代'看到有用的量子优势(也就是说，虽然量子计算机仍然是'[噪音](https://thenewstack.io/new-protocol-allows-noisy-quantum-computers-to-auto-assess-their-accuracy/)'和资源受限的)，那么将量子计算机仅用于它提供计算优势的精确运算是绝对关键的。否则，在计算完成之前，量子态将[分解](https://blogs.scientificamerican.com/observations/decoherence-is-a-problem-for-quantum-computing-but/)，导致结果不可靠。”

从广义上讲，这种结合经典和量子系统的混合方法[在行业内并不新鲜](https://www.microcontrollertips.com/merging-quantum-classical-computing-hybrid-system-faq/)，像微软和 IBM 这样的公司[提供他们自己的](https://www.ibm.com/cloud?utm_content=inline-mention)[复合平台](https://thenewstack.io/ibm-launches-new-tools-to-ease-quantum-computing-development/)。虽然量子计算可以在解决最复杂的计算方面比经典计算机提供显著的提升，但在某些情况下，经典计算机仍然可以超越更容易出错的量子计算机。从这个意义上说，CQC 的混合技术为一个难题提供了一个双赢的解决方案，这在以前是没有的。

赫伯特说:“这个提出的算法是量子蒙特卡罗积分中最先进的。”“它可以解决任何具有完全二次量子优势的蒙特卡罗积分，而将量子计算机仅用于那些具有量子优势的操作。其他方法都无法实现所有这些目标。”

Herbert 补充说，最近宣布的 CQC 和霍尼韦尔量子解决方案(HQS)之间的合作伙伴关系将意味着未来量子硬件和软件开发的更紧密协调的改进，特别是在加强量子蒙特卡罗集成的实施方面。

“我期待着与实验学家和硬件工程师合作，找出并纠正算法在实际量子硬件上执行时受到‘资源限制’的精确方式，从而消除量子优势道路上的障碍。原则上，这种方法确实是“世界上最好的”，然而，在实践中，仍然可以进行特定于应用程序的改进。这是我们的下一项工作:寻找那些热衷于探索量子蒙特卡罗集成将对与其业务相关的问题产生的变革性影响的合作伙伴，并设计量身定制的解决方案。”

在[报纸](https://arxiv.org/pdf/2105.09100.pdf)上阅读更多信息。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>