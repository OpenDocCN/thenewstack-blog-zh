# 解开计算机先驱查尔斯·萨克尔的丰富遗产

> 原文：<https://thenewstack.io/charting-legacy-charles-p-thacker/>

本周，查尔斯·萨克尔去世的消息迅速传遍了 T2 的互联网。然而，稍慢一点的是对撒克的生活和他的遗产的完整描述。事实上，我写的这篇文章和你读的这篇文章都是 Thacker 遗产的直接产物:台式电脑。事实上，人们甚至可以认为电话和其他触摸屏设备也是他的遗产。

他还在以太网和分时硬件的开发以及其他创新中发挥了关键作用。

在我们进一步深入之前，应该注意的是，在 Thacker 工作的几十年里讨论计算机和技术导致了一系列错综复杂的故事:这是一个非常小的世界，在一个地方工作不可避免地会在其他地方工作。因此，要讲述查尔斯·萨克尔的故事，我们必须转向一些次要的旅行路线，去了解到底是什么激发了撒克去追求他所承担的项目类型。

[https://www.youtube.com/embed/U8WppDOVfUc?feature=oembed](https://www.youtube.com/embed/U8WppDOVfUc?feature=oembed)

视频

20 世纪 60 年代末，萨克在加州大学伯克利分校开始了他的计算机生涯，当时他刚刚获得物理学学位。1968 年，他加入了 Genie 项目的团队，该项目继续开发伯克利分时系统。当时，分时是一件大事，尽管在 1957 年已经在 PDP-1 上被发明出来，但它仍然是模糊的前沿。

奇怪的是，在 Thacker 的时代，讨论的要点之一就是如何在一个大型网络中分配一台计算机使用。这里的工作是由传奇人物 J. C. R. Licklider 促成的，他作为 [Bolt Beranek and Newman，Inc](http://www.xconomy.com/boston/2009/09/02/bbns-long-search-for-a-home-endsat-home/2/) (BBN)的副总裁购买了第一台 DEC PDP-1。Licklider 的团队将在同一个 PDP-1 上演示[时间共享](http://www.computerhistory.org/revolution/mainframe-computers/7/181):分割计算机处理时间以分配给多个用户的行为。

Licklider 接着在 DARPA 获得了一个职位，首先是信息处理技术办公室的负责人，然后是行为科学指挥和控制研究主任。正是以这种身份，他在 1963 年发布了一份备忘录，详细说明了设计分时系统网络的相关困难。当时的软件根本无法应对这一挑战，但那份备忘录为后来成为互联网前身的阿帕网(ARPAnet)描绘了一幅愿景。

第二年，Multics 操作系统的工作开始了，这是你从未听说过的最重要的操作系统。1969 年，当贝尔实验室退出这个项目，把它留在通用电气手中，通用电气随后把整个项目卖给霍尼韦尔时，Multics 开始分崩离析。在接下来的三十年里，霍尼韦尔继续制造 Multics 机器。

Multics 开创了数据访问单级存储的概念，这意味着操作系统本身处理所有文件的写入和读取，并且该过程只使用简单的 CPU 指令。Multics 还支持动态链接和共享库。

很自然，你会觉得“Multics”这个名字听起来有点耳熟。这是因为当贝尔实验室退出这个项目时，是因为公司已经在内部构建了 UNIX 和 T11。

但是 UNIX 不仅仅是 UNIX。UNIX 也是 C 编程语言。当时，构建操作系统是创建新的编程环境和语言的一部分。

在这个世界上，萨克获得了他刚刚获得的物理学学位。的确，这是一个竞争的世界。麻省理工学院的 Licklider 团队已经生产出了与[兼容的分时系统](http://multicians.org/thvv/compatible-time-sharing-system.pdf)，[达特茅斯学院有自己的分时系统](http://dtss.dartmouth.edu/timeline.php)，曼切斯特大学已经生产出了 [Atlas Supervisor](http://www.chilton-computing.org.uk/acl/technology/atlas/p019.htm) 。

1968 年萨克到达时，伯克利分时系统已经有了 2.0 版本，并与科学数据系统 940 一起发布，后者是更常见的 SDS 930 的变体。940 有一个主要由集成电路构成的 24 位 CPU，是第一台本身支持分时系统的 SDS 机器。

因为 SDS 940 基本上是由于在伯克利的工作，尽管 SDS 的上层管理人员持怀疑态度，但萨克尔和伯克利分时系统团队的其他人看到了在这里创办公司的机会。他们成立了伯克利计算机公司:萨克和艾德·麦克赖特负责设计硬件，巴特勒·兰普森和彼得·多伊奇负责软件。

BCC 不是一家成功的公司。该公司生产的单个 BCC-500 最终在夏威夷大学完成，在那里它形成了其 Aloha 分时系统的主干。本手册解释了这台双 CPU、多处理器机器背后的一些细节。它很古怪，灵感来自巴勒斯 B-5000 架构和多镜头。

尽管失败了，伯克利计算机公司继续取得了一些崇高的成就，尽管这些是在不同的旗帜下完成的。在被认为是跨海湾合作的终极中，[施乐 PARC](http://www.computerworld.com/article/2515874/computer-hardware/timeline--parc-milestones.html) 抓住了 BCC 的创始人并雇佣他们来领导一个新的计算机系统的开发；个人电脑系统。

在 BCC 团队在 PARC 形成了计算机系统实验室的核心之后，Thacker 成为了施乐 Alto 项目的负责人。许多人认为 Alto 是第一台个人电脑 T3 的原型[。](https://www.nytimes.com/2017/06/14/technology/charles-thacker-dead-personal-computing-pioneer.html)

当他开始在 PARC 施乐公司工作时，组装史上最具革命性的个人电脑所需的所有零件都在那里。事实上，1972 年，拉加经委会的 PDS-1 已经是第一台个人电脑。虽然 PARC 无疑是许多现代计算范式的鼻祖，但其中许多“发明”在 PARC 成立时就已经存在了。然而，它们都没有得到很好的实施或推广。

虽然 PARC 并没有使施乐成为世界上最大的计算机公司，但它所产生的影响今天仍然伴随着我们。例如，Thacker 和他的团队发明了以太网，并一直沿用至今。他们也是发明激光打印机、[所见即所得](https://foldoc.org/WYSIWYG)文本编辑器以及最终 [Postscript](http://www.adobe.com/products/postscript.html) 的人。

Thacker 的工作使那些系统变得可用、可理解，最重要的是:现实。Thacker 是一位不可思议的硬件工程师，他能够理解复杂的计算概念，并以可复制的方式实现它们。

Thacker 继续与 PARC 计算机科学实验室的其他人一起创建了 DEC 系统研究中心。在那里，团队能够重新开始许多主要项目。特别是，PARC 的团队一直在构建 [Mesa](http://www.softwarepreservation.org/projects/lang/mesa) ，一种专为施乐 Alto 构建的类似 Algol 的语言。PARC 团队又一次构建了一种语言和一个操作系统。

到了 12 月，这个想法已经失宠，团队开始着手制作 [Modula-2](https://www.modula2.org/) ，这是一个新的开始。事实上，在计算领域，有些事情永远不会改变:有机会重新开始总是修复过去项目中积累的错误的好方法。

兰普森在一次采访中说，“当我们离开 PARC 去 DEC 的时候，我们能够摆脱梅萨所有的传统服饰，重新开始。我们说过，我们不想花五年时间来设计和实现一种编程语言。我们能做什么；Modula 对我们来说是一个非常舒适的起点，因为首先，它并不复杂，其次，它拥有我们熟悉的所有传统。所以我们问自己，我们可以添加什么；我们认为当前对严肃编程语言的需求是什么？”

最终，Thacker 于 1997 年进入微软研究院，为微软的平板电脑设计硬件。尽管很早就参加了那个派对，但 Thacker 对便携式屏幕界面电脑的想法并不陌生。他已经在 PARC 看到并研究过这样一个想法:[艾伦·凯](http://www.i-programmer.info/history/8-people/438-alan-kay.html?start=1)的概念计算机，被称为 [Dynabook](http://history-computer.com/ModernComputer/Personal/Dynabook.html) 。他已经试图在十二月建造这个代号为 [Lectrice](http://tabletuniten.weebly.com/history.html) 的东西。

[https://www.youtube.com/embed/tQg4LquY0uU?feature=oembed](https://www.youtube.com/embed/tQg4LquY0uU?feature=oembed)

视频

虽然许多其他有影响力的开发人员和设计师能够声称拥有创新技术和想法，但他们中的许多人也是被剥头皮的先驱:即使对施乐 PARC 公司的工作进行最仁慈的评估，也不得不承认那里设计的创新在其他地方完全货币化了。

但这忽略了在任何人之前将新技术推向市场并付诸实施的难以置信的困难。这是查尔斯·泰克绝对能够做到的事情。虽然他的工作不像他同时代的一些人那样浮华或知名，但如果没有它，我们今天认为理所当然的许多创新可能不会在没有萨克的情况下从实验室里出来并付诸实践。

[https://www.youtube.com/embed/A9n2J24Jg2Y?feature=oembed](https://www.youtube.com/embed/A9n2J24Jg2Y?feature=oembed)

视频

Marcin Wichary 通过 cc [2.0 许可证](https://commons.wikimedia.org/w/index.php?curid=59912013)制作的 Charles Thacker 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>