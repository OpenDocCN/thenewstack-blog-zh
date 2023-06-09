# 新协议允许“嘈杂的”量子计算机自动评估其准确性

> 原文：<https://thenewstack.io/new-protocol-allows-noisy-quantum-computers-to-auto-assess-their-accuracy/>

在过去的几年里，量子计算的承诺已经逐渐渗透到我们的集体意识中。专家们预计，这些速度更快、功能更强大的计算机将完成传统或所谓的“经典”计算机无法完成的任务——如[建模复杂系统](/quantum-computings-challenging-liftoff-to-commercialization/)或[构建不可破解的网络](https://thenewstack.io/scientists-adapt-1930s-radio-tech-help-build-unhackable-quantum-internet/)。

量子计算机的[巨大潜力在于，它们的计算利用了亚原子粒子同时存在于多个状态的能力，这与经典计算机执行的更有限的基于二进制的计算相反。这意味着与传统计算机相比，量子计算机能够更快、更有效地进行复杂的计算。虽然量子计算的概念已经存在了三十多年，但在它能够更广泛地实施之前，仍然有一些障碍需要克服，例如开发一些方法来确保量子计算机给出的答案实际上是正确的。](/quantum-computings-challenging-liftoff-to-commercialization/)

## 量子可信度

来自英国华威大学的一组研究人员最近开发了这样一种技术，它允许量子计算机进行自我测试，而不必依赖效率较低的经典超级计算机来交叉检查结果，也不必大幅增加所需的量子位或“T8”量子位的数量。这意味着这种新协议在计算资源方面需要更少的“开销”,使其在更大规模的应用中更加实用。

“如果量子计算机被用于解决困难的计算问题，比如设计新的化学物质、药物和材料，我们必须有一种方法来决定它们的输出是否可信，”华威大学理论物理学助理教授和最近发表在《新物理学杂志》上的论文的合著者之一解释道。

“没有这种保证，我们永远无法将量子计算机用于任何重要的事情。我们的工作表明，这种保证是可以得到的。换句话说，它提供了一种方式来决定量子计算机对于关键应用是否足够可信。”

该团队的新认证协议的一个主要方面是，它让一台量子计算机运行几个简单的计算，除了其余的操作，答案已经知道。通过确定量子计算机在这些更简单的计算方面的正确程度，用户还可以发现量子计算机距离正在运行的整体操作的正确答案有多近或多远。这种方法受到了一种类似方法的启发，即软件程序员将小的数学函数(答案是已知的)插入到大型计算机程序中。如果程序正确地回答了这些函数中的大部分，那么用户就可以确信程序很可能也运行正常。

此外，该协议量化了所谓的“噪声”——具体来说，就是由温度波动等因素产生的输出变化，这些因素会影响量子计算机的敏感硬件。验证协议生成两个百分比——一个估计量子计算机与实际结果的接近程度，以及用户对该估计的确信程度。

“挑战在于选择这些简单的计算，”达塔说。“它们必须被挑选出来，以便测试量子计算机的所有部分，并找出它的大部分缺陷(通常被称为‘噪音’)。如果不是这样，我们可能会得到简单计算的正确输出，但对于困难的计算是不正确的。我们挑选的简单计算叫做 [Clifford 电路](https://en.wikipedia.org/wiki/Gottesman%E2%80%93Knill_theorem)。他们已经认识大约 20 年了。”

## 验证量子云

除了他们的认证协议，该团队的论文还提出了他们所谓的“中介验证协议”，这可能在未来量子计算机更加普及时有用。

“中介验证协议是我们的认证技术向潜在的客户端-服务器量子网络应用的扩展，”论文合著者 Theodoros Kapourniotis 解释道，他是华威大学量子信息科学小组的研究员。在那里，客户机周期性地接收服务器的量子位，并应用一些特殊的操作来有效地测试服务器在提供答案方面的诚实性。我们不认为这种量子信息的交换在当前的技术下是可行的，但当我们最终进入量子网络和“量子云”的时代时，它肯定是相关的。"

该团队目前正在努力进一步开发他们的认证协议，以便纳入 [量子纠错](https://en.wikipedia.org/wiki/Quantum_error_correction)——一种[容错](https://en.wikipedia.org/wiki/Fault_tolerance)，这将保护量子信息免受噪声、有缺陷的量子门或错误测量的影响。这一点尤其重要，因为像 IBM 和谷歌这样的大型行业参与者现在正在竞争建立所谓的[量子优势](https://en.wikipedia.org/wiki/Quantum_supremacy)，在这种情况下，量子设备成功地解决了一个经典计算机在实践中无法解决的问题(即，这将花费太长时间)。在这种情况下，这种量子设备的准确性对于证明量子优势至关重要。

Kapourniotis 说:“以目前对量子技术的投资速度，以及像我们这样的认证计划的发展，我们乐观地认为量子计算机将很快能够解决非常有用的问题。”。“量子计算最初的愿望仍然存在，那就是模拟依赖于量子力学本身的系统的能力。这种在基本分子水平上对复杂物理系统的理解是我们必须克服的障碍，以解决地球未来的紧迫问题，如太阳能采集。”

更多阅读团队[论文](https://iopscience.iop.org/article/10.1088/1367-2630/ab4fd6)。

图片:[拉斯·普鲁格曼](https://www.flickr.com/photos/criminalintent/ "Go to Lars Plougmann's photostream") ( [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) )

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>