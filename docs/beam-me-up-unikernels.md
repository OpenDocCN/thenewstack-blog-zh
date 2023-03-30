# 传送我上去，单核

> 原文：<https://thenewstack.io/beam-me-up-unikernels/>

“整个单核运动真正重要的部分与容器和虚拟化无关。对于单核，它是关于图书馆化的。所有的依赖都变成了库。如果你看整个应用级的东西，人们倾向于构建小的库并重用它们。我们试图让人们相信系统代码可以变成库。你不必每次都重建，”Unikernel Systems 的创始人 Anil Madhavapeddy 说，他现在是 Docker 技术团队的一员(Docker 在今年早些时候收购了 Unikernel)。

毫无疑问，单核的黄金时代正在迅速到来。最初，开发者认为在产品中使用单核是[五年后的事情](https://thenewstack.io/good-luck-debugging-unikernels-joyents-chief-technology-says/)，但是现在公司已经[开始在产品中使用它们](https://thenewstack.io/dockers-unikernel-experiment-begins-paying-off-mac-os-libraries/)。在本期[The New Stack Makers](https://thenewstack.io/podcasts/)embedded below 中，New Stack 创始人 Alex Williams 与三位单核专家进行了对话: [Ian Eyberg](https://github.com/eyberg) 单核平台提供商的创始人 [Defer Panic](https://deferpanic.com/) ，Docker 的 Madhavapeddy，以及 [EMC](http://www.emc.com/) 的技术副总裁 Joshua Bernstein。

[关于单核:伊恩·埃伯格，约书亚·伯恩斯坦，安尼尔·马达瓦佩迪在奥斯丁 OSCON](https://thenewstack.simplecast.com/episodes/on-unikernels-ian-eyberg-joshua-bernstein-anil-madhavapeddy-at-oscon-in-austin)

讨论[也可以在 YouTube 上观看](https://youtu.be/oDT86HWbF3M)。

随着容器应用的持续升温，人们发现有些东西根本不适合容器。问题是，单核是否更适合这些任务？对埃伯格来说，答案是明确的:“是的。”

Eyberg 还提供了一些关于提供容器作为他们自己的 SaaS 的公司的精选词:“容器是内核的一部分，而内核就是问题。有许多事情是容器不能做或不愿做的。整个[容器即服务](https://thenewstack.io/the-year-ahead-ops-and-the-rise-of-container-as-a-service/)的事情都是营销扯淡。“除非你能用容器完全取代谷歌云(Google Cloud)或亚马逊(Amazon)，否则这完全是胡扯。”

让应用程序更容易部署和管理是 unikernels 可以做到的。EMC 和 Defer Panic 等公司已经在采取措施，通过使用单核来帮助将复杂的工作流任务分解为更易于管理的任务。“工程师喜欢复杂，但老实说，这是一种可怕的生活方式。你需要把事情简单化。这就是我们所有的安全和配置管理问题的来源。开发人员可以比普通工程师赚更多的钱，这是一个糟糕的问题。“这都是因为我们有一个自 20 世纪 60 年代以来就存在的内核。”。

Bernstein 继续解释说，根本没有足够的时间向开发人员和运营团队解释如何配置他们的基础设施来支持单核。“无论我们如何部署应用程序，无论是在谷歌还是亚马逊，它都必须在某个地方运行。基础设施不仅仅存在于云中；它必须真实存在。我认为我们没有充分讨论如何构建这个基础设施来支持这些技术。每个人都喜欢，“哦，这取决于开发人员，”而可怜的运营人员坐在那里，拿着服务器和锤子说，“我不知道该怎么办！”"

Madhavapeddy 继续解释说，无论中央云提供商有多快，单核通过解决物理服务器层的问题而脱颖而出。“如果您想在 10 毫秒内做出响应，Compute 需要在这里运行。中央云提供商不可能做到这一点。有生理上的限制。我们要么成为《星际迷航》，要么构建更好的 API。”

第一资本公司和 T2 码头公司是新堆栈的赞助商。

专题图片:伦纳德·尼莫伊和威廉·夏特纳，via Pixabay。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>