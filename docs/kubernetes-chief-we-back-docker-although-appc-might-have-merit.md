# Kubernetes 酋长:我们支持 Docker，虽然 appc 可能有优点

> 原文：<https://thenewstack.io/kubernetes-chief-we-back-docker-although-appc-might-have-merit/>

谷歌上周宣布支持 CoreOS 努力成为一个新兴的容器规范 appc T1 的维护者。旨在使容器能够承载多个流程，这似乎是对 [CoreOS 的大胆宣言](https://github.com/appc/spec/blob/master/SPEC.md#app-container-image)的认可，因为容器可以更紧密地与 Kubernetes 对集群的支持保持一致。

周一，Kubernetes 领导人兼谷歌集团产品经理 Craig McLuckie 的博客文章彻底抹杀了 T4 的这一表现。在这篇文章中，McLuckie 重新表述了谷歌对 appc 的支持，从“Kubernetes 项目的一个重要里程碑”(他上周称之为“T8 ”),到“我们可能会在未来的某个时候……引入”谷歌容器引擎。

“我们宣布获得 AppC 和 RKT 支持的意图是将 Kubernetes(我们的开源项目)打造成容器世界的中立阵地，”McLuckie 写道，他指的是 CoreOS 的容器系统新品牌，以前称为 Rocket。

“客户应该能够仅仅根据其技术优点来选择他们的容器运行时和格式，我们确实认为随着技术的成熟，AppC 提供了一些合理的潜在优点，”他继续说道。“不知何故，这被误解为‘a 对 b’的选择，这是完全不真实的。有了选择，世界几乎总是变得更美好，不同的工具可以用于不同的目的，这是非常自然的。”

McLuckie 最后称赞 Docker Inc .使容器技术“民主化”，并重申 Google 计划“无限期地”支持 Docker 标准。

谷歌产品经理的声明正式表明了他的观点，这一观点最早出现在[5 月 4 日，当时他在推特](https://twitter.com/cmcluck/status/595313016410738688)上写道:“很难过 rkt/Docker 在 [@kubernetesio](https://twitter.com/kubernetesio) 上的支持被视为非此即彼:

> 肯定是两者都有。rkt/appc 很有前途，但是 Docker 有真正的吸引力。

在周一的博客帖子之后，麦克卢奇补充了这条推文:

> 最近一直在为不必要的闹剧难过。

## 重置里程碑

上周，CoreOS 首席执行官 Alex Polvi 将谷歌的 Tim Hockin 与 Red Hat 的 Vincent Batts 和 Twitter 的 Charles Aylward 放在一起，不仅作为 appc 的官方维护者和合作者，而且作为 Polvi 描述的单一、通用容器标准的支持者。

Polvi 写道:“在推出 appc 后的几个月里，我们已经看到通用应用容器规范背后的采用和支持在快速增长。”“这些公司和个人正走到一起，以确保应用程序容器有一个定义良好的规范，为确保堆栈之间的安全性、开放性和模块化提供指导方针。”

但是波尔维从来没有暗示过他相信 **appc** 会在 Kubernetes 中取代 Docker 的 **libcontainer** 。所以，没有任何一个重要人物提出过这样的观点:在今天使用 Docker 的开源生态系统中， **appc** 将会取代 Docker。

也就是说，谷歌对 appc 的支持不仅仅是口头上的，确实是对 CoreOS 的一个赌注。仅仅因为你赌了不止一匹马，并不意味着你不是一个赌徒。

此外，虽然许多开源生态系统在“民主化”的前提下取得了成果，并让客户选择正确的组件，但在某种程度上，客户会遵从某人关于“正确的组件”是什么的判断。这就是为什么这个问题远远不止是一个关于规范文档语法的小冲突。

新兴的 **appc** 格式选择的分发机制将是 Quay.io，CoreOS 于去年 8 月收购了它。正如 CoreOS 的 Polvi 在本月早些时候告诉新堆栈的那样，Quay.io 不是 appc 容器的“默认注册表”,就像 Docker Hub 是 Docker 容器的默认注册表一样。尽管如此，Quay 是一个独立的生态系统，其所有者目前声称，不应该有一个单独的默认集装箱图像分发中心。

谷歌的人应该对这个观点非常熟悉。“我们选择‘市场’而不是‘商店’这个词，因为我们觉得开发者应该有一个开放和无障碍的环境来提供他们的内容，”这是谷歌的朱立伦在 2008 年提出的支持开放独立的安卓市场的论点——一个服务的名字，尽管朱棣文提出了这个论点，但还是被改成了。

在周二下午对新堆栈的一份声明中，CoreOS 首席执行官 Alex Polvi 对 McLuckie 的帖子做出了如下回应:

> 我们相信这篇文章是在说，这个世界因为有选择而变得更好，而且 appc 确实有优点。

Polvi 继续说道:“ **appc** 社区坚信，用户需要基本的安全功能，以及一个可以由各种供应商共享的标准运输容器。“我们认为这是用户想要的，也是他们成功使用容器所需要的。我们看到, **appc** 方法与各种软件社区——包括 Kubernetes 产生了牵引作用。”

## 红帽不是旁观者

对许多企业来说，技术上的“开放”并不意味着容忍不同的标准，而是坦率地讨论单一标准的可能性。由于开源开发者至少据称是*开放的*，企业客户可能会认为，如果这些开发者未能共同努力，为实现符合每个人最大利益的目标制定一个单一的、通用的标准，那么一定有一个很好的理由。

这是红帽战略高级总监 Lars Herrmann 周二在温哥华 OpenStack 峰会上的观点。

“作为一个行业，我们有机会通过集装箱化来达成一个单一的格式，并使它为每个人服务，”赫尔曼告诉新的堆栈，“而不是将其分割成不同的格式。因为这只会产生大量的冗余和多余的工作，却没有任何好处。我们已经在格式层面忍受这种分裂很久了。现在我们有机会克服这一点。”

Herrmann 指出， **appc** 和 Docker 的 **libcontainer** 之间的差异远不止语义上的，这引发了关于 Docker 的守护进程是否应该负责启动进程而不是 CoreOS 所依赖的 **systemd** 的争论。Herrmann 承认，Docker 的设计选择确实使容器更难管理，也更难利用其安全性。他说，正是因为这个原因，Red Hat 指派了一名工程师负责 appc 规范。

“理想情况下，我们真的希望让社区明白如何一起工作，而不是相互对抗，”Herrmann 说。“我们真的不认为我们需要另一种形式。”

尽管 Red Hat 是 systemd 的主要作者之一，他继续说道，“我们认为仅仅从 Docker 守护进程基础设施转换到 systemd 还不足以抛弃同质的、统一的格式。我们真的鼓励社区一起工作。这就是我们两者都参与的原因。”

在新的一期节目中，我们将会看到更多关于赫尔曼的采访。

CoreOS 和 Red Hat 是新堆栈的赞助商。

通过 Flickr Creative Commons[获取专题图片。](https://www.flickr.com/photos/photographingtravis/16359934852/in/photolist-oFMN3a-qVEWEh-oY2ctt-pWiih4-pWB3Hj)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>