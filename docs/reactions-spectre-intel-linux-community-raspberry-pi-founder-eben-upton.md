# 为什么树莓派不会受到熔毁和幽灵的攻击

> 原文：<https://thenewstack.io/reactions-spectre-intel-linux-community-raspberry-pi-founder-eben-upton/>

树莓派基金会创始人 T2 埃本厄普顿自己写博客是一种难得的享受。他的最后一封信是在近一年前— [庆祝树莓派的五岁生日，并宣布推出树莓派 Zero W，这是一款 10 美元的变种，配有无线局域网和蓝牙。](https://www.raspberrypi.org/blog/raspberry-pi-zero-w-joins-family/)

这次[把他带回键盘的原因是需要解释](https://www.raspberrypi.org/blog/why-raspberry-pi-isnt-vulnerable-to-spectre-or-meltdown/)重大 Meltdown/Spectre 漏洞的发现，以及为什么它们不会影响 Raspberry Pi 主板。

厄普顿写道:“现代处理器竭尽全力保持它们是直接访问内存的有序标量机器的抽象，而事实上，它们使用了包括缓存、指令重新排序和推测在内的一系列技术，来提供比简单处理器希望实现的性能高得多的性能。”。“Raspberry Pi 中使用的 ARM1176、Cortex-A7 和 Cortex-A53 内核缺乏推测性，使我们对这种攻击免疫。”

## 熔毁沉降物

如果厄普顿本周享受了一段相对无忧无虑的时光，他可能是科技行业领导者中的一个。

在拉斯维加斯的消费电子展(CES)上，英特尔首席执行官[布莱恩·科兹安尼克](https://twitter.com/bkrunner)在周一的主题演讲中承诺，他们最关心的是[每个人的数据](http://www.eweek.com/security/intel-s-krzanich-covers-cpu-flaws-quantum-computing-in-ces-keynote)的安全，并补充说“到目前为止，我们还没有收到任何关于这些攻击被用来获取客户数据的信息。”他敦促他的观众在更新可用时应用它们，并承诺英特尔将在本周末之前发布 90%的更新，其余的将在 1 月底发布。

Krzanich 还感谢该行业“齐心协力”解决熔毁漏洞。他说:“这么多公司合作解决跨几种不同处理器架构的这一行业范围的问题，真是了不起。”

[https://www.youtube.com/embed/RlJ9zB74G_U?start=3544&feature=oembed](https://www.youtube.com/embed/RlJ9zB74G_U?start=3544&feature=oembed)

视频

当然，该行业没有太多的选择，一些人一直在抱怨它是如何处理的。 [OpenBSD 项目](https://www.openbsd.org/)的负责人 Theo de Raadt 抱怨说，最初是第一批“选择性披露”给一级公司的漏洞，并补充说低于这个级别的每个人“都被骗了”对于内核开发人员来说，“突然之间，内核中最棘手的部分需要做后空翻来处理微观架构中的深层问题，”[他告诉 ITWire](https://www.itwire.com/security/81338-handling-of-cpu-bug-disclosure-incredibly-bad-openbsd-s-de-raadt.html) 。本周晚些时候，Ubuntu 16.04 的第二次更新不得不发布，此前第一次更新显然[阻止了一些用户启动他们的机器](https://www.zdnet.com/article/linux-vs-meltdown-ubuntu-gets-second-update-after-first-one-fails-to-boot/)。

[已经有三起集体诉讼](https://www.theguardian.com/technology/2018/jan/05/intel-class-action-lawsuits-meltdown-spectre-bugs-computer)代表消费者提起，而[还有四起](http://appleinsider.com/articles/18/01/11/intel-faces-more-class-action-suits-over-share-price-hits-caused-by-spectre-and-meltdown-flaws)代表英特尔投资者提起。在 [Linux 内核邮件列表](https://lkml.org/lkml/2018/1/3/797)上， [Linus Torvalds](https://github.com/torvalds) 抱怨道，“我认为英特尔内部的某些人需要认真审视一下他们的 CPU，并真正承认他们有问题。”

但至少有一位科技公司的首席执行官并不担心自己的产品。

## 为什么树莓皮不易受伤

![EbenUpton by Jim Killock (cropped](img/e9aef7fdc9ce043e3384843a605c3f22.png)

为了解释为什么 Raspberry Pi 不容易受到 Spectre 和 Meltdown 的攻击，Upton 提供了关于现代处理器设计概念的“初级读本”。一些处理器试图一次执行多条指令，尽管它们至少是按顺序执行的。但是为了提高性能，芯片设计者走得更远。

“对顺序指令进行重新排序是恢复更多指令级并行性的一种强有力的方法，但随着处理器变得更宽(能够发出三倍或四倍的指令)，让所有这些管道保持忙碌变得更加困难，”他说。所以下一个创新是“推测”——根据代码的执行分支，运行甚至可能不需要的指令。

随着时间的推移，处理器也变得比内存快得多，所以芯片制造商很快就采取新的措施来减少检索存储数据的时间。“程序倾向于以相对可预测的方式访问内存，”Upton 写道，“表现出时间局部性(如果我访问一个位置，我可能很快会再次访问它)和空间局部性(如果我访问一个位置，我可能很快会访问附近的位置)。”芯片开始包括一个靠近处理器的小型片上存储器，用来存储最近使用过的位置的数据副本。

缓存为绕过主处理器安全性的“旁路攻击”留下了额外的信息。在内核中执行所谓的“非法读取”地址的程序可以通过对响应进行计时，计算出哪些地址存在于缓存中(意味着它们最近被执行过)。

## 在线反应

Upton 的帖子吸引了超过 150 条评论，Eben 自己回复了一些评论，提供了一些更多的背景信息。“你真的需要在机器语言水平下来操纵这个…”他[在某一点上](https://www.raspberrypi.org/blog/why-raspberry-pi-isnt-vulnerable-to-spectre-or-meltdown/#comment-1375404)补充道。

很快就可以看出，这是一个对微处理器有强烈感情的人。在回答一个关于早期超标量 CPU[摩托罗拉 68060](http://lowendmac.com/2016/cpus-motorola-68060/) 的问题时，厄普顿[深情地回忆道](https://www.raspberrypi.org/blog/why-raspberry-pi-isnt-vulnerable-to-spectre-or-meltdown/#comment-1375451)“在 90 年代初，我有三年时间是 68000 迷。美丽的建筑:在一个更公正的世界里，它或它的后代会胜出。”

厄普顿的言论也在黑客新闻上引起了积极的反应，其中[一条评论](https://news.ycombinator.com/item?id=16080449)称该帖子是“我读过的最好的解释，它帮助我最终理解了这些攻击。”

甚至有一个评论者暗示厄普顿的帖子给了他们一个爱他们的树莓派的理由。

“想到我在一个小角落里做各种后台任务的小 Pi 也很有趣，它已经是我拥有的最无故障的机器，也可能是最安全的。”

* * *

# WebReduce

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>