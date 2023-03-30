# 演示:“小妖精自由”让混沌工程变得简单

> 原文：<https://thenewstack.io/demo-gremlin-free-and-easy-chaos-engineering/>

混沌工程的概念是作为一种在停机发生之前检测系统中问题区域的方法出现的。网飞在 2010 年创造了这个概念的变体，称为[混沌猴子](https://github.com/netflix/simianarmy)，以帮助确保亚马逊网络服务(AWS)上运行的实例的任何中断都不会对其流媒体服务产生影响。

但对于那些缺乏带宽来实现类似网飞的混沌猴子过程来测试他们的系统的组织来说，2 月份推出的 [Gremlin Free](https://www.gremlin.com/blog/introducing-gremlin-free/) 允许组织或个人开始使用混沌工程，而不必使用信用卡来查看它是如何工作的。

在新堆栈的演示过程中； [Lorne Kligerman](https://www.linkedin.com/in/lorne-kligerman) ，Gremlin[的产品总监](https://www.gremlin.com/)详细描述了混沌工程的概念以及如何通过使用 Gremlin Free 来工作。

Kligerman 说:“停机代价高昂，而且会损害客户的信任。“Gremlin 让您能够安全可靠地找到系统中的弱点，以免它们成为问题。”

[https://www.youtube.com/embed/yCdJ5MSLkAc?feature=oembed](https://www.youtube.com/embed/yCdJ5MSLkAc?feature=oembed)

视频

Kligerman 说，除此之外，混沌工程允许组织以一种有计划、有控制的方式将失败引入他们的系统。Kligerman 说:“你可以在这些问题导致现实世界中的中断之前，在它们真正伤害到你的最终用户体验之前，自己发现这些问题——这正是我们希望防止的。”。

破解并观察你的监控软件和其他系统如何反应是 Gremlin 的联合创始人兼首席执行官 Kolton Andrus 熟悉的事情，因为他也是网飞的混沌工程师。Kligerman 还表示，他在谷歌担任产品经理和解决方案工程师时，能够观察到混沌工程是如何工作的。Kligerman 说“真正创造一个真正有弹性的系统的唯一方法是尝试用你自己的方式打破它。”

Kligerman 说，Gremlin Free 的想法是“让它进入社区，这样每个人都可以尝试一下，并扩展混沌猴的概念”。“当你随机关闭服务器中的实例时，这更像是一件随机的事情，”Kligerman 说。"我们真的在以一种深思熟虑的可控方式实践混沌工程."

个人或组织通过首先在服务器上安装 Gremlin 客户端开始使用 Gremlin Free，服务器可以是物理主机、虚拟机或容器，可以包含在 Kubernetes 部署中。Kligerman 说，Gremlin Free 引入了两种不同的攻击:CPU 和状态攻击，这是一种关闭攻击，类似于混沌猴子所做的。

在演示过程中，Kligerman 展示了峰值上升时在 [Datadog](https://www.datadoghq.com/) 仪表盘监视器上看到的情况。作为混沌工程过程的一部分，还可以看到指示攻击何时开始和停止的事件。

Kligerman 说，例如，当你发起 CPU 攻击时，它允许你观察你的实例，并确保你的监控工具正常工作，通过查看你是否能看到峰值，以及当峰值发生时，你的工具是否向你发送警报。对于 CPU 攻击，您可以选择希望攻击持续多少秒，以及希望影响多少个 CPU 核心。攻击可以现在进行，也可以安排在以后进行，甚至可以在某个时间内随机进行。

当运行一个简单的 CPU 或关机攻击时，“你可以看到当你的自动缩放实例消失时会发生什么，”Kligerman 说。“这是一种不需要信用卡的方式，你可以在自己的时间安装它，运行一次攻击，看看会发生什么，”Kligerman 说。“我们认为你会看到一些影响，你会让你的系统变得更好，你的客户也会因此更高兴。”

这个想法是让业界通过实践直接了解混沌工程是如何工作的。“我们认为行业已经真正理解了它是什么，以及为什么你应该这样做，”Kligerman 说。“现在，这一切都是关于我如何开始，我如何看待混沌工程对我的系统的影响，无论你是一家小型初创公司还是一家拥有数百或数千个团队的非常大的公司。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>