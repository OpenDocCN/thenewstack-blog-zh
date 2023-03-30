# 本周编程:黑客马拉松解决新冠肺炎

> 原文：<https://thenewstack.io/this-week-in-programming-hackathons-tackle-covid-19/>

这一个月真是糟糕透了。有时候感觉就像是一天又一天的坏消息。就在上个月，我们看到股市暴跌，失业率飙升，我们能想到的每一件有趣的事情都被取消，越来越多的人死去。事实上，这似乎只是冰山一角。

我不知道你怎么样，但我需要一些好消息。

为此，我们想，这一次我们可以看看一些解决方案，而不仅仅是问题。之前，我们研究过[开发者如何帮助击败新冠肺炎·疫情](/this-week-in-programming-how-devs-can-help-beat-the-covid-19-pandemic/)，不仅关注资源，也关注作为回应涌现的各种黑客马拉松。好了，一段时间过去了，thons 被黑了，也有一些结果需要探索。事不宜迟，三个新冠肺炎黑客马拉松已经宣布了他们的获胜者，我们今天在这里向你们展示他们，作为技术可以在我们当前的情况下做些什么的例子。

首先，疫情响应黑客马拉松最近结束了，[宣布了获胜项目](https://medium.com/@travismay/results-from-the-pandemic-response-hackathon-a756e84d8c5e)，这些项目是从 2000 多名参与者的 230 份提交材料中挑选出来的，并沿着四个轨道组织起来——公共卫生信息、流行病学和跟踪、卫生工作者安全以及疫情的次级效应。这个特别的黑客马拉松为每个类别选择了四个获胜者，这可能有点太多了，但他们从基于聊天机器人的热线 [Cov2words](https://datavant.us19.list-manage.com/track/click?u=0fd0995ce1abd5bca33291772&id=079517d045&e=09d537cf0f) ，建议你是否接受新冠肺炎病毒测试，到 [Airspar 充气野战医院](https://datavant.us19.list-manage.com/track/click?u=0fd0995ce1abd5bca33291772&id=765c289f4e&e=09d537cf0f)，一种可用于快速扩大医院病床容量的充气负压帐篷的设计，到 [WhatsInStock](https://datavant.us19.list-manage.com/track/click?u=0fd0995ce1abd5bca33291772&id=f149200f18&e=09d537cf0f) ， 它向纽约人展示了(目前)他们在哪里可以在附近的商店找到像卫生纸这样的东西，以减少他们需要旅行的次数。

接下来， [CodeVsCOVID19 黑客马拉松以另外四个获奖项目结束了](https://codevscovid19.devpost.com/submissions)(包括疫情响应黑客马拉松中 Cov2words 的重复)。例如， [doctor@home](https://devpost.com/software/doctor-home-6k7dyq) 为居家的新冠肺炎患者提供自我监测和智能医疗分诊，而 [WeTrace](https://devpost.com/software/wetrace-g9ocyi) 提供了查明你是否与测试呈阳性的人接触的可能性，以及 [Detect Now](https://devpost.com/software/detect-now) 使用深度学习从记录中检测与新冠肺炎有关的咳嗽。

最后，CODEVID-19 每周黑客马拉松宣布了一个获胜者，由来自 50 个国家的 1500 名开发者提交。第一周(就像一年前的疫情时间)是一个名为 covid19.pink 的新冠肺炎仪表板，该团队设法在黑客马拉松开始后的几天内推出了它。接下来，WeHaveWeNeed.com 提供了一个市场，将有需求的人和能够提供帮助的人聚集在一起，而本周的赢家是慈善商店交换，它提供书籍和 DVD 订阅服务，以消除孤立，同时与当地慈善机构合作。

[https://www.youtube.com/embed/BxV14h0kFs0?feature=oembed](https://www.youtube.com/embed/BxV14h0kFs0?feature=oembed)

视频

## 本周的节目中

*   **在 Kubernetes 上部署 WebAssembly:**首先，随着由 Deis Labs 和[微软](https://cloudblogs.microsoft.com/opensource/2020/04/07/announcing-krustlet-kubernetes-rust-kubelet-webassembly-wasm/)发布的[Krustlet，WebAssembly Kubelet](https://deislabs.io/posts/introducing-krustlet/) 的引入，在 Kubernetes 上运行 web assembly 变得更加容易。这个名字暗示了该项目的构成，即它是一个用铁锈写成的 Kubernetes kubelet。Deis Labs 将 WebAssembly 二进制文件与 Linux 容器进行了比较，web assembly 二进制文件“可以在任何地方运行，而不管底层硬件如何”, Linux 容器“旨在提供操作系统级别的沙盒环境”,但不能在不同的硬件上运行，称这两种技术是互补的一对。“Krustlet 并不打算取代 Kubelet，”他们写道。“当一起运行时，客户端可以在同一个集群中运行传统的 Linux 容器工作负载和 WebAssembly 工作负载。用 WebAssembly 编写的应用程序可以与在 Linux 容器中编译的应用程序进行通信，这两种类型的工作负载可以以类似的方式与集群的其余部分进行交互。”现在，[开源项目](https://github.com/deislabs/krustlet)正处于早期阶段，但请继续关注。
*   **Rust 考虑 GitHub 动作与 Azure 管道:**Rust 编程语言团队一直在评估 GitHub 动作在 Azure 管道上的使用，并提供了关于其 GitHub 动作评估的[更新，报告称他们预计在未来几个月内做出决定。虽然该团队仍在评估其中一个，但他们表示，他们希望 GitHub 的行动能够大大加快 CI 流程。“我们的贡献者将会注意到的主要区别是我们的 CI 时间大大减少了。他们写道:“在当前的 Azure Pipelines 中，安装构建通常需要三个多小时才能完成(使用 60 个并行的双核虚拟机)，而我们预计新的 GitHub Actions 安装只需不到一半的时间即可完成构建，这要归功于 GitHub 为我们慷慨准备的八核虚拟机专用池。”如果你碰巧在考虑这两种服务的区别，为什么不让别人替你做研究呢？](https://blog.rust-lang.org/inside-rust/2020/04/07/update-on-the-github-actions-evaluation.html)
*   **Scratch 进入 TIOBE 指数前 20 名:**通过跟踪每月发布的编程语言流行指数(根据搜索)，DevClass 注意到低代码[儿童编程语言 Scratch 已经进入前 20 名](https://devclass.com/2020/04/06/kids-programming-language-scratch-nails-top-20-in-latest-dev-rankings/)。该指数的保罗·詹森[给出了这样的解释](https://www.tiobe.com/tiobe-index/)“Scratch 中‘编写’的项目总数超过 5000 万个，而且每个月都有 100 万个新的 Scratch 项目加入进来，Scratch 受欢迎的事实是不可否认的，”而 DevClass 提出，孩子们呆在家里不去上学也可能是这种视觉语言突然流行起来的罪魁祸首。

*   **寻找 COBOL 开发人员:**虽然 COBOL 可能是一种有 60 年历史的编程语言，但它在 TIOBE 索引中排名第 25 位，仅比 Rust 稍受欢迎，本周它成为关注的焦点，因为[美国失业激增凸显了对 COBOL 技能的迫切需求](https://thenewstack.io/u-s-unemployment-surge-highlights-dire-need-for-cobol-skills/)。根据 Lawrence Hecht 在 New Stack 上的一篇报道，当面临 1600%的使用率增长时，新泽西州的失业系统根本无法承受负荷，州长发出了求救信号。如果你认为解决办法只是继续前进，赫克特写道，“仅仅因为一些东西是古老的，并不意味着它应该被安乐死。事实上，根据一项正在进行的对 500 多名 COBOL 系统相关人员的调查[来看，最常见的 COBOL 应用方法是现代化，而不是退休。](https://www.brighttalk.com/webcast/16907/376805)

*   受新冠肺炎影响的 Node.js 发布时间表:几乎没有什么是不受疫情影响的，发布时间表也不例外。最近，谷歌 Chrome 和微软 Edge 团队[宣布推迟他们的发布时间表](https://www.cnet.com/news/google-pauses-chrome-updates-because-of-coronavirus-disruptions/)，现在 Node.js 正在[做同样的事情](https://medium.com/@nodejs/changes-to-release-schedule-fe597dcd4691?source=rss-96cd9a1fb56------2)，称它“将根据调整后的工作时间表调整其发布节奏。”所以，如果你是那种把发布日期同步在日历上的人，你可能想看一看。
*   **关于面包制作:**当我们在做的时候，我们看到你和其他人都喜欢上了面包制作。我们明白这一点——我们自己已经做了一段时间，因为它便宜、有趣，并且可以让你在制作面包时不使用任何防腐剂或商店购买的高果糖玉米糖浆。因此，在这一点上，我们认为我们应该提供一个我们本周遇到的工具，这个工具[可以帮助你安排制作酸奶面包的时间](http://www.breadscheduler.com/#/)。它配有食谱(按重量，唯一的出路)，并提供了一个调度程序，有闹钟和一切。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>