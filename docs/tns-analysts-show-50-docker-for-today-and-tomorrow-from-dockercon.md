# 今天和明天的 Docker 来自 DockerCon 2015

> 原文：<https://thenewstack.io/tns-analysts-show-50-docker-for-today-and-tomorrow-from-dockercon/>

[DramaFever](http://www.dramafever.com/) 于 2013 年 10 月开始运行 Docker。这使他们成为第一批，特别是考虑到所罗门·海克斯在那年 4 月才与世界共享 Docker。这也使得 DramaFever 的 Bridget Kromhout 和 Tim Gross 成为我们本周在 DockerCon 录制的这一集《新堆栈分析师》的嘉宾。两人在最后的精彩演示后加入了我们:

斯科特富尔顿，谁写的新堆栈覆盖码头，特别是，加入了作为该节目的共同主持人。更多剧集，请查看新堆栈的播客部分[。](https://thenewstack.io/podcasts/)

[# 50:Docker con 2015](https://thenewstack.simplecast.com/episodes/50-docker-for-today-and-tomorrow-from-dockercon-2015)今天和明天的 Docker

这个播客也可以在 YouTube 上找到。

## 码头工人和戏剧狂热

DramaFever 团队讨论了他们在将一个版本投入生产时遇到的问题。他们需要一个在开发服务器上与生产环境中完全相同的解决方案。Docker 脱颖而出。他们知道这是有风险的，因为它是 0.6 版本，但是他们知道他们会回到 Linux 容器。在他们开始使用 Docker 之前，可能需要一整天或更长时间才能让开发人员跟上速度。今天，他们可以在第一天工作的午餐前让新的开发人员开始工作。DramaFever 团队现在正在寻找服务发现工具。有很多新工具，但是很难知道哪些工具适合这个用例。一些真正脱颖而出的东西是华特·迪士尼在先进技术赛道 DockerCon 上展示的 Mesos 和马拉松配对。

目前，DramaFever 将一个容器映射到一个主机。这是他们想要改变的事情之一。这将意味着一个更复杂的编排环境。

但是在展会上宣布作为通用格式和运行时的 RunC 呢？那有影响吗？不是直接的。它将使生态系统比现在成熟得多，但开发工具制造商比“水管工”受影响更大，所罗门用这个术语来描述管理运营的人。但这可能会扩大贡献者的范围。

## 技术堆栈

DramaFever 在 AWS 上使用 Ubuntu Linux。它有一个遗留的单片 Django 应用程序，但一直在从中抽取片段来制作用 go 编写的微服务。他们还使用 AWS 来管理持久层的存储和缓存。它们会根据流量模式积极地自动伸缩。应用程序主要以无状态的方式运行。

在 AWS 上，弹性容器服务作为一个原型很有趣。它在发布时似乎还不够成熟。从那时起，他们已经做出了改变，所以情况正在好转。它是 DramaFever 的潜在候选，因为它更深入地研究了他们用 Docker 构建的管理环境。

另一个注意事项:AWS 对于某些术语的含义是不透明的，例如什么是“高”或“中等”，或者在比较性能方面。要弄清楚事情是如何运作的可能需要一些摆弄。

DramaFever 在 Docker 投入生产后又增加了其他工具。他们增加了厨师来定义形象，就像迪士尼正在做的那样。你必须控制宿主基底，才能知道容器外部发生了什么。他们开始注意工具，比如 Hashicorp 提供的工具。然后是 Mesos 和马拉松式的产品。

Cobb 说，Docker Machine 和 Docker Swarm 有兴趣一起弥合供应和主机之间的差距。这可能意味着使用 Compose，进行适当的扩展，并通过 EC2 provisioner 为机器应用它。对于戏剧热来说，这可能是一个强大的组合。

DramaFever 就不必像现在这样使用 Boot2Docker 了。这将消除在 EC2 中启动自己的实例的一些摩擦，并且非常适合前端开发人员。他们将使用 Docker Machine，而不是使用 fab 命令来启动 EC2 实例。

Scott 和我讨论了 Docker 开放容器格式及其对市场的意义，并以此结束了这次展览。

斯科特说，Docker 通过解决一些争议做了一些大事，巩固了自己在市场上的基础。它的 DNA 现在无处不在。

最能说明问题的例子之一是架构是如何发展的。Scott 说，RunC 将为容器带来新的智能，正如 Quake 演示中展示的实时迁移能力所示。RunC 是大会的重大架构新闻。

Docker 是新堆栈的赞助商。

通过推特上的 [@professoruss](https://twitter.com/professoruss/status/613500502601396224/photo/1) 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>