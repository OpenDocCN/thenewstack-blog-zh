# 奇偶校验:生产中的容器使用

> 原文：<https://thenewstack.io/parity-check-no-one-really-grasped-uses-docker-containers/>

奇偶校验是 TNS 分析师的专栏文章

[Lawrence Hecht](https://thenewstack.io/author/lawrence-hecht/)

他将研究 IT 行业的各种调查和研究，提炼更深刻的真理，揭穿没有根据的假设。

调查很棒！调查是最糟糕的！我对调查又爱又恨。新的堆栈已经解析了许多关于容器和 Docker 使用的报告。他们提供了巨大的洞察力，但他们回答的每一个问题都会引发更多的问题。“使用”容器是什么意思？Docker 实际上是正在使用的主流容器类型吗？人们实际上是如何安排容器的使用的？

这些问题将会在 Docker 和容器生态系统的电子书系列中继续得到解答。同时，本专栏将帮助你解读你在新闻中读到的数字。

# 容器的使用

一年前 Docker 风靡一时，一份 stacken engine(Oracle)调查报告称[70%的 IT 专业人士正在使用或考虑使用容器。然而，除了大肆宣传之外，该数字的三分之二(49%)处于评估阶段，实际用户的部署有限。经过一年的信息收集和试验，我们更加了解容器在其技术采用生命周期中的位置。](http://www.stackengine.com/infographic-state-containers-2015-docker-adoption/)

最近的一项 451 研究调查表明，从 2015 年上半年到下半年，处于“发现和评估”阶段的云计算用户从 56%下降到 32%。

好消息是，几乎一半的评估者已经转向试点项目、测试/开发或生产用途。坏消息是，略多于一半的评估者(13%的样本)已经从他们的路线图中放弃了容器，因此只有 64%的人现在正在使用或计划使用容器。这种不切实际的兴趣下降是意料之中的，并且由于营销宣传和现实之间的差距而经常发生。

我曾与 451 合作，并信任其数据团队，但乍一看，这些数字与其他已公布的调查不符。例如，Robin Systems 最近的一项调查显示，95%的受访者正在使用、计划或评估使用容器，而 Dynatrace 和 O'Reilly 的一项为期六个月的研究也报告了超过 90%的数字。

451 和其他研究相差 30 个百分点。只看容器的非测试/开发生产使用，451 报告了 14%的水平，Ruxit 26 和 Robin Systems 36。同样，高值和低值之间有 20%以上的差异。哪项研究是正确的，研究结果应该如何解释？为了回答这些问题，我们比较了上述所有调查的结果。这些研究发现差异的原因与语义和样本有关。

每份问卷都以明显不同的方式定义了容器的使用和考虑。在最初询问他们对容器的一般用途或计划后，大多数研究试图阐明更多的信息。询问容器是否用于“生产”是一种流行的方法。换句话说，真正的业务应用程序是在它们之上运行的吗？如果是，有多少 IT 基础设施在使用它们？

找到此信息的另一种方法是询问它在什么类型的环境中使用(例如，测试、开发、生产)。例如，StackEngine 和 Ruxit 允许用户在询问容器是否用于测试、开发或生产时提供多个回答。

这种方法的问题是许多调查者说他们在多种环境中使用容器。虽然在许多情况下这可能是真的，但也可能 QA、测试和开发之间的区别并不总是很清楚。例如，451 调查将测试和开发环境合并为一个类别，一些受访者可能正在测试容器解决方案，而不是在软件开发生命周期的一个步骤中使用它们。

另一个不同点是，451 询问的是试验和试点，而罗宾系统询问的是计划和是否有人在“玩”集装箱。总的来说，我们对未来调查的建议是更好地区分那些为了将容器投入生产而测试容器使用的人和那些经常使用容器作为持续集成过程一部分的人。

除了问卷的措辞，谁被问到这些问题也会影响结果。451 研究基于一组 IT 决策者，而 Robin Systems 调查则是从一个在线出版物网络中征集的。Ruxit 和 StackEngine 的调查也是基于自选的受访者。这种类型的调查方法可能会导致对容器早期采用者的偏见，并容易受到第三方运动的影响，以填补调查的“选票”。然而，通过观察目前在生产中使用容器的受访者，我们仍然可以学到很多东西。

通过 Pixabay 的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>