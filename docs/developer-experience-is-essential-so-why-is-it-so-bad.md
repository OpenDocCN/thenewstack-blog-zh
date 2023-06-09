# 开发者经验必不可少。那么为什么会如此糟糕呢？

> 原文：<https://thenewstack.io/developer-experience-is-essential-so-why-is-it-so-bad/>

[](https://www.codesee.io/)

[Shanea Leven](https://www.codesee.io/)

[Shanea Leven 是 CodeSee 的联合创始人兼首席执行官，CodeSee 是一个帮助开发者和开发团队更好地理解代码库的开发者平台。](https://www.codesee.io/)

[](https://www.codesee.io/)[](https://www.codesee.io/)

“经验”是最近流行的一个词。我们生活在体验经济中。消费者期望获得出色的客户体验。员工需要卓越的员工体验。这些只是这个术语无处不在的用法的几个例子。

但是，如果你是美国 450 万软件开发人员中的一员，用一个技术术语来说，很可能你的大部分经历都很糟糕。

我显然不是在谈论工作本身，这可能是有益和快乐的——有趣的技术挑战，肾上腺素刺激的与你的部落建立联系的日日夜夜，以及建造一些以前从未存在过的东西带来的独特满足感。

我说的是尝试用今天的工具链完成工作的经历。通常，这些工具链——虽然包含一些出色的单个产品——集成不良或不完整，无法让开发人员像今天的超快速、DevOps 驱动的持续交付管道所要求的那样快速高效。

开发人员的常见形象是某人在为他们组织的最新应用程序项目做贡献时疯狂地键入代码。这个形象是真实的。有时候。在其余的大部分时间里，他们试图在拼凑的工具中导航，同时也陷入了试图充分理解代码以继续进行的混乱中。

专注于开发者的分析公司 RedMonk 称之为“开发者体验差距”RedMonk 联合创始人 Stephen O ' grady[写道](https://redmonk.com/sogrady/2020/10/06/developer-experience-gap/) “大多数工具链，从编写第一行代码开始，经过测试、构建、集成和部署，一直到生产，都是由不同供应商的产品和服务拼凑而成的。

根据 O'Grady 的说法，由于这种碎片化，“开发人员被迫从编写代码中借用时间，并将其重定向到管理与高度复杂、多因素的开发人员工具链相关的问题，这些工具链通过胶带和打包线连接在一起。”

一方面，世界从未对开发者和工程师提出过更多的要求。数字化正以超高速发展。计算已经成为我们生活和每个行业中至关重要的一部分，以至于“每个公司现在都是软件公司”已经成为一句常用的格言。像 DevOps 和 DevSecOps 这样的运动不断将更多的责任推给开发人员。

另一方面，虽然业界提供了大量优秀的编辑、测试、调试和其他自动化工具来让开发人员的生活变得更加轻松，但结果却是一个难以消化的大杂烩。市场已经把这一切留给了开发商去解决。

困扰软件组织的巨大绊脚石之一涉及到开发人员在每个项目开始时需要但一直缺失的关键部分。

随着代码库变得越来越复杂，团队能够熟悉代码并理解关键信息是很重要的，比如文件和功能如何相互映射，代码变化如何适应更大的架构，等等。

但是这对于现代代码库来说非常困难。几乎总是缺少文档，存在大量令人困惑的相互依赖关系，编写代码的人可能不再在那里工作。大局是模糊的或完全看不见的。

想象一下，试图在没有蓝图的情况下建造一座摩天大楼。这基本上就是软件工程师和开发人员被要求做的事情。他们得到了一本手册，上面有单独的说明——走五步，拿着这块板，垂直地钉在另一块板上，拿着另一块板，水平地钉在那块板上——对一个动作如何影响另一个动作以及它们如何与更宽的楼层或高层建筑相结合的知识不足。

DevOps 的八个阶段——计划、编码、构建、测试、发布、部署、操作、监控——需要增加一项内容:代码库理解。

为了弥补它的缺失，开发人员求助于“即时”认知——手动梳理代码库(总是一行一行！)来学习前进所需的最低要求，祈祷没有什么会破碎。这是一项单调乏味、令人沮丧且耗时的工作，让开发人员非常恼火。

> 如果你是美国 450 万软件开发人员中的一员，用一个技术术语来说，很可能你的大部分经历都很糟糕。

不仅如此，整个努力经常被证明是徒劳的。如果一个开发人员正在阅读代码，他们很少真正知道为什么以前的开发人员做他们所做的事情。我不知道有哪个开发人员会一直在注释中解释每一个动作。即使他们这样做了，代码库变化如此之快——想想所有的拉请求——这样的信息很快就过时了。

最终发生的是，每个开发人员或工程师建立了他们自己对代码库如何工作的理解…然后当他们转到新的工作时，这些知识就离开了。

用另一个类比来说，我们今天对待代码就好像它驻留在一个大黑盒中。我们有各种优秀的工具来观察黑匣子，当它有问题时接收警报，测试它，看看它是否会以我们认为的方式运行。但真正需要的是能够打开黑盒，抓住里面的东西。

这不是一个新问题。早在 1979 年，马文·泽尔科维茨(Marvin Zelkowitz)在[](https://www.amazon.com/Principles-software-engineering-design-Prentice-Hall/dp/013710202X)的《软件工程与设计原理》中写道，“程序理解”消耗了花在软件维护上一半以上的时间。

所以，这个问题已经存在 50 多年了——在互联网出现之前。是时候解决它了。更好的代码可观察性需要与 DevOps 推动开发的所有其他功能一起“左移”。这肯定会对改善开发人员的体验大有帮助。

*<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*