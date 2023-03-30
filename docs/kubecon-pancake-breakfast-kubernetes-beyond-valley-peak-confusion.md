# CloudNativeCon 煎饼早餐:Kubernetes 带我们超越“高峰困惑”

> 原文：<https://thenewstack.io/kubecon-pancake-breakfast-kubernetes-beyond-valley-peak-confusion/>

去年 12 月，Joyent 首席技术官 [Bryan Cantrill](https://twitter.com/bcantrill) 问我们是否已经在容器领域达到了“[高峰困惑](https://twitter.com/bridgetkromhout/status/766442217624010754)，提到容器技术和平台的可能组合将如何让任何对未来技术有先见之明的首席技术官完全不知所措。

将近一年后，[云本地计算基金会](https://cncf.io/)的 [Kubernetes](http://kubernetes.io/) 和它的 CNCF 项目伙伴们，能为这一困境提供解决方案吗？

在 11 月 8 日于 CloudNativeCon 2016 举行的 [TNS 分析师煎饼早餐会](https://thenewstack.io/podcasts/)上，CNCF 执行董事 [Dan Kohn](https://www.linkedin.com/in/dankohn) 与康卡斯特系统架构师 [Erik St. Martin](https://twitter.com/erikstmartin) 、CoreOS 首席执行官 [Alex Polvi](https://www.linkedin.com/in/polvi) 和 Wercker 首席技术官 [Andy Smith](https://www.linkedin.com/in/termie) 一起讨论 Kubernetes 的发展和未来。他们回答了观众关于在企业中采用该技术的问题，并强调了他们之间如何最好地规避开发人员今天使用 Kubernetes 仍然面临的一些挑战。

[# 120:CloudNativeCon 煎饼早餐——Kubernetes 带我们超越“高峰困惑”](https://thenewstack.simplecast.com/episodes/120-cloudnativecon-pancake-breakfast-kubernetes-takes-us-beyond-peak-confusion)

[https://www.youtube.com/embed/3tixhkl1Pw0?feature=oembed](https://www.youtube.com/embed/3tixhkl1Pw0?feature=oembed)

视频

在康卡斯特，圣马丁解释说，虽然该公司曾考虑从头开始构建自己的解决方案，但最终 Kubernetes 脱颖而出。这归结为重新思考 Kubernetes 的工作方式，并使用这些第三方工具来为该公司构建一个 Kubernetes 堆栈。“至于网络和实时线程约束，我们已经有了一些东西，但修复这些问题比我们从头开始要简单得多。我想你会看到高峰混乱开始结束。我想我们可能已经过了混乱的高峰期。我认为 Kubernetes 是领先的，并认为这一类别肯定是有帮助的，”圣马丁说。

“我们的使用情形非常相似。我们需要经常轻松地部署东西。你只需说，“应用部署”，一切都会自行解决。经常做每件事，这样你就知道它是有效的。如果你每天甚至每隔几分钟就做一次，你可以肯定它会起作用。“Kubernetes 消除了所有的痛苦，”史密斯说。

为了继续实现成为真正的跨平台竞争者的目标，CNCF 启动了一个类似于营销演示的新项目，目前正在 T2 的 CNCF 社区集群上运行。该项目旨在让开发者了解如何在自己的堆栈中使用 Kubernetes。“我们选择了三种工作负载，一种是 Node 中的 Google Analytics 克隆。JS、分布式计算客户机和分布式内核编译器。我们的目标是让同样的演示在 GCP Azure 或 DigitalOcean packet 上运行，并接受来自任何其他托管公司的请求。”

[![k8-book](img/6fec44c9aca417aebc9e45055954f1df.png)](https://thenewstack.io/ebooks/use-cases/use-cases-for-kubernetes/)

当观众开始质疑在裸机部署上使用 Kubernetes 时，专家组的一致意见是，这是一个最终仍需解决的绊脚石。“我认为我们的筹码有点不足。对于什么是在裸机上启动和运行集群的最佳部署，仍然缺乏共识。CNCF 的演示选择了 Ansible，但这个想法是为了展示最佳实践。科恩说:“我认为，我们对这是未来的解决方案信心不足。

“它现在也只是太空中的一片空白，”波尔维附和道。Smith 用一个关于 Wercker 如何开发软件的声明来反驳 Kohn，“Ansible 在我们办公室里几乎像一个坏词。我们想和 API 谈谈，仅此而已。那是我们现在开发软件的地方。每个人最后一次接触服务器应该是打开 Kubernetes，仅此而已。其他一切都应该通过 API。”

至于这个平台的未来，17 岁的 Kubernetes 维护者 Lucas Kaldstrom 给出了他的想法。“我希望它能更容易设置。那真的很重要。所以更多的人可以适应和使用 Kubernetes。现在，很难建立。我认为我们正在生产生命周期中努力工作，任何愿意与我们一起做出贡献的人都会很棒。”

Polvi 附和了这一说法，强调既然 Kubernetes 已经在生态圈内找到了立足之地，开发商就有了大量的可能性。“这让我想起了很多 IOS 或 Android，因为这个新平台的存在，你可以去构建或做些什么。我们正从让平台发挥作用，转向构建优步或任何因平台的存在而成为可能的东西。一两年前，你还不能建造这些东西。”

史密斯以一个可能性成熟的高调结束了讨论:“一旦人们停止为 Linux 设计，开始为 Kubernetes 设计，那才是真正的奇迹开始发生的地方。”

云原生计算基金会、CoreOS、Docker 和 Wercker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>