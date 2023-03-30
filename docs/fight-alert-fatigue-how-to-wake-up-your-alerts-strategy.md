# 对抗警报疲劳:如何唤醒你的警报策略

> 原文：<https://thenewstack.io/fight-alert-fatigue-how-to-wake-up-your-alerts-strategy/>

[](http://scalyr.com/)

 [Steven Czerwinski，Scalyr 工程主管

Steven Czerwinski 是 Scalyr 的联合创始人兼工程主管。在 Scalyr 之前，他在 Google 工作了 8 年，专门为消费者应用程序构建分布式数据库系统。他是 Picasa 网络相册的后端技术负责人，Cosmo 的技术负责人，以及 Stratus 的技术负责人，Stratus 是 Cosmo 的替代者，推动了包括 Google Plus 在内的进一步统一。在加入谷歌之前，Steven 在加州大学伯克利分校攻读博士学位，专攻分布式和移动系统。他成功地通过了论文答辩，但离开了 ABD，开始了他在谷歌的工作。](http://scalyr.com/) [](http://scalyr.com/)

如今，工程团队面临着保持系统平稳运行的日益增长的需求。这是因为业务和数字客户体验之间的界限正在缩小，当应用程序成为业务时，任何不完美的用户体验都意味着对收入的影响。

在这种背景下，健全的警报策略对于几乎每个工程团队来说都是至关重要的。根据最近的一项调查，58%的 DevOps 专业人员报告依赖五个或更多的可观察性工具来确定性能问题的根本原因，这意味着对于每个问题，他们都要在多个位置的数千个警报中进行分类，以便找到答案。由于不可能始终监控系统健康的各个方面，智能警报策略可以帮助团队更有效地运营，并将注意力集中在最需要的地方，从而保持业务平稳运行。

但是设置警报并不总是像看起来那么简单。为了做好这件事，团队不仅要应对隐藏在表面之下的不断蔓延的复杂性，还要对抗“警报疲劳”，即当通知变得过于频繁时忽略通知的倾向。这两种情况下的关键是在节奏和紧迫性之间找到合适的平衡。为了帮助您的团队建立一个更好的警报策略(并在晚上睡得更好)，这里介绍了我们如何在 [Scalyr](http://scalyr.com/) 应对挑战:

## 警报结构

首先，说一下结构。在最高级别，警报围绕三个关键支柱设计:指标(您要监视的性能度量)、比较语句(即“大于”、“小于”、“等于”)和阈值(您要与指标进行比较的关键值)。

例如，要监视 CPU 使用率的意外峰值，您可以设置以下警报:如果过去 15 分钟的平均 CPU 使用率大于过去 24 小时的平均值，则触发警报。

## 阈值

创建警报时，首先建立阈值通常会有所帮助。有三种类型可以应用于警报:固定的、基于状态的和历史的。

顾名思义，固定阈值会在性能水平超过某个静态的预定水平时触发警报。这些是最容易设置的阈值，在测量具有硬性限制的性能指标时效果最佳，例如 CPU 使用率或硬盘空间。

基于状态的阈值也简单明了。它们识别系统状态的变化，例如，“运行”或“停止”，主要用于监控应用程序进程的意外停机时间。

历史阈值稍微复杂一些。也称为“滑动窗口”，这些阈值将指标的当前值与其过去值进行比较。换句话说，监视一个特定的时间段(比如 15 分钟的窗口),这个时间段随着时钟的滴答声而持续移动。例如，基于历史阈值的警报可能会显示:如果 15 分钟平均 CPU 使用率大于 24 小时前 15 分钟平均 CPU 使用率的 120 %,则触发警报。这里的想法是在过滤噪声的同时识别给定指标中的突然峰值。

在这个主题上，在设置警报时包含“宽限期”也是有用的。换句话说，添加一条规则，防止警报触发，除非它被触发了一段持续的时间。这有助于过滤掉微小的偏差，识别长期活动。

## 韵律学

一旦制定了阈值，就该确定支持您的警报的指标了。每个警报策略都需要涵盖五类关键指标:容量、带宽、状态、速率和事件参数指标。

容量指标监控具有固定和已知容量的系统组件，如磁盘空间和可用内存。如果某样东西可以“填满”或“用完”，通常用容量度量来衡量。当达到容量时，系统崩溃，这意味着阈值应该设置在最大容量以下。当达到容量的后果具有严重破坏性时，阈值应该设置得特别低。

带宽度量测量系统内的流量。例如，网络利用率、CPU 使用率和磁盘吞吐量。这种类型的系统活动本质上经常是高度可变的，因此考虑根据移动平均值发出警报。例如，不是通过查看最新的测量来监控网络使用情况，而是将它设置为测量 30 分钟窗口内的平均使用情况。

状态指标具有不同的值，用于监控系统状态的变化，如“运行”或“停止”这些系统状态指标通常与基于状态的阈值挂钩。

速率指标用于测量特定事件发生的速率。换句话说，在一定时间内发生的事件的数量。例如，“每秒请求数”、“每秒错误数”、“每分钟登录尝试次数”等等。对于可预测的指标，历史阈值是最好的。对于不太可预测的，基于历史高点或低点的阈值通常是一个合理的方法。

事件参数度量基于事件的一些可测量属性，如响应时间或请求大小。该指标通常用于监控和报告一段时间内所有相关事件的平均值。为事件参数度量设置的阈值类似于为速率度量设置的阈值，对可预测的度量使用历史阈值，对不太可预测的度量使用固定阈值。

## 通知

有了正确的警报阈值和度量标准，下一步就是构建一个系统，以便在出现问题时接收通知。这一步至关重要。你可以拥有世界上最好的警报参数，但是如果你没有收到警报，它们就没有任何用处。

现代 DevOps 环境提供了多种选择。例如，现在可以将警报存储在数据库中，并通过电子邮件每天批量发送，立即通过电子邮件发送，通过短信或电话发送，或以某种组合方式发送。诀窍是找出最适合你的团队的交互模式。

一般来说，紧急警报应该是可中断的。他们需要立即抓住你的注意力，传达问题的紧迫性。因此，将相同指标、不同阈值和不同通知方法的警报“堆叠”在一起通常也是有意义的。这里的想法是当问题变得更加紧急时，升级警报。

提醒远比看上去要多得多。设置一个合理的警报策略需要考虑三个关键支柱:阈值、指标和通知。随着应用程序正常运行时间对每个企业来说都变得至关重要，现在就花点时间为您的应用程序环境和团队找出正确的组合可以让一切变得不同。

戴维·克洛德在 [Unsplash](https://unsplash.com/search/photos/wild?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>