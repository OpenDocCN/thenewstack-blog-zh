# 为什么集装箱安全没有简单的答案

> 原文：<https://thenewstack.io/why-container-security-has-no-easy-answers/>

[VMware](https://www.vmware.com/company.html) 赞助了这次播客。

关于您的组织必须做什么——或者购买什么——来确保容器环境是安全的，有许多观点。但是退一步说，容器站在开源的肩膀上，团队在过去几十年中学到的安全性和遵从性过程在许多情况下仍然适用。

[为什么集装箱安检没有简单的答案](https://thenewstack.simplecast.com/episodes/why-container-security-has-no-easy-answers)

同时，容器安全有其自己的一套规则和最佳实践，这些规则和实践往往不太明显。更糟糕的是，围绕开源安全的许多困惑仍然存在，进一步加剧了挑战。

[VMware](https://www.linkedin.com/in/dirkhohndel)副总裁兼首席开源官 [Dirk Hohndel](https://www.linkedin.com/in/dirkhohndel) 说:“如果我看一下容器环境，我们好像回到了糟糕的旧时代，容器 Docker 文件可能有一个许可证，但它几乎总是不是容器中包含的所有软件的许可证，容器通常包含许多组件。霍恩德尔说，最重要的问题是，你如何找到安全的容器，并“确保你现有的容器确实是安全的？”

在最新一集的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中，主持人 Alex Williams 讨论了容器正在成为开放基础设施的核心部分后，合规性和安全性的现状。加入他的还有 VMware 的霍恩德尔和安德鲁·威尔逊，后者是英特尔的长期首席开源合规官。

Wilson 利用他在该主题上的丰富经验，展示了历史背景以及开源安全的许多缺点是如何继续困扰容器安全的。

“我总是遇到一种普遍的误解，认为开源和公共领域是一回事。或者，如果这段代码没有明确的版权声明，那么它一定是公共领域，因此，我可以对它做任何我想做的事情，不存在合规问题——这完全是错误的……你真的应该假设你找到的任何代码都是由某人版权所有的，”威尔逊说。“您对该许可证的要求可能非常低，而许可许可证可能是最高的，它们可能由类似 GPL 系列许可证的东西定义，其中有一些模糊的情况。”

对于容器来说，从 Docker Hub 下载二进制文件是非常常见的标准做法，“然后可能在它们上面添加层，并在生产环境中运行它们，”Hohndel 说。“在这个基础设施中，几乎没有什么可以帮助你识别这些二进制文件的实际内容。”

“我是否知道集装箱里有什么，或者是否有任何后门，或者是否有任何间谍软件？”霍恩德尔说。这些问题“通常在容器环境中得不到答案，这也是我几年来一直试图谈论这个话题的真正原因。”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>