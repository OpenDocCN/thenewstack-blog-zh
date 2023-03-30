# 用于自动化混沌工程的 Gremlin-Spinnaker 集成

> 原文：<https://thenewstack.io/gremlin-spinnaker-integration-for-automating-chaos-engineering/>

与开源多云连续交付平台 [Spinnaker](https://github.com/spinnaker/spinnaker) 的集成只是混沌即服务供应商 [Gremlin](http://gremlin.com/) 计划与 CI/CD 合作的第一步。

据 Gremlin 联合创始人兼首席技术官[马修·福纳奇里](https://www.linkedin.com/in/mattforni/)称，这是一个合理的起点。“这很有意义。”

Spinnaker ，一个为高度分布式和混合系统开发的平台，诞生于网飞。并非巧合的是，Gremlin 的联合创始人兼首席执行官 [Kolton Andrus](https://twitter.com/koltonandrus?lang=en) ，是网飞的一名混沌工程师，并帮助建立了其第二代混沌工程工具，称为 [FIT](https://cts.businesswire.com/ct/CT?id=smartlink&url=https%3A%2F%2Fmedium.com%2Fnetflix-techblog%2Ffit-failure-injection-testing-35d8e2a9bb2&esheet=51962544&newsitemid=20190402005098&lan=en-US&anchor=F.I.T.&index=3&md5=b1a3d05a4a1018735f69e696773bd4f9) (故障注入测试)。

Fornaciari 将混沌工程描述为“变被动为主动”它在您的系统上引入了压力条件，以发现和修复将会崩溃的东西，例如当您扩展时。

“与 CI/CD 整合的整个想法并没有走向失败。有很多活动部件。应用程序将不断变化，基础架构将不断变化，整个想法是将它们集成到您的 CI/CD 中，这样您就不会遭受两次相同的故障，”他说。

新的 Stack 已经写了关于[混沌工程如何在分布式系统中建立稳定性](https://thenewstack.io/chaos-engineering-can-give-distributed-systems-stability/)。Gremlin site 可靠性工程师 [Tammy Bütow](https://twitter.com/tammybutow) 指出了[在采用混沌工程](/gremlins-tammy-butow-on-the-business-side-of-chaos-engineering/)之前你需要做的事情，比如了解你的业务停机的成本，并进行良好的监控。

与 Gremlin 的集成意味着 Spinnaker 用户可以跨多个云提供商自动进行混沌实验，包括 AWS EC2、Kubernetes、谷歌计算引擎、谷歌 Kubernetes 引擎、谷歌应用引擎、微软 Azure、OpenStack 等。

“你注入一点点失败，这样你就能建立起一种坚韧的忍耐力。你需要从一个非常基本的故障模型开始。将 CPU 提升到 100%或类似的水平，”Fornaciari 解释道。

“然后你想增加爆炸半径，我们是这样描述的。你想从很小的规模开始，也许只有一台主机，然后你想增加。随着您变得越来越自信，开始您想手动运行它，然后最终您想将其集成到 CI/CD 中。你想让它在你增加爆炸半径后，你可以说，“酷，我们要一直运行它”，并让它成为我们构建过程的一部分。我们再也不会失败了，因为我们一直在这样做。”

这需要一定的成熟度，许多组织不准备打破常规，即使有机会按照他们自己的方式这样做。

这就是为什么 Gremlin 最近发布了一个基于开源领导者[混沌猴](https://netflix.github.io/chaosmonkey/)的[免费版本](https://www.gremlin.com/blog/introducing-gremlin-free/)，它也起源于网飞。

“我们希望看到(组织)立即自动化这些事情，特别是对于拥有微服务、云和分布式应用的大型企业来说，”Gremlin 通信总监[亚当·拉格雷卡](https://www.linkedin.com/in/adamlagreca/)说。

“一旦你变得足够成熟，可以自动完成这些事情，就不再需要大量的手工操作和猜测。但是很多人对它不熟悉，从手工实验开始。他们在自动化之前正在试验并了解如何进行混沌工程，但我们确实认为，一旦你达到一定的成熟度，你就会想要自动化这些实验，”他说。

然而混沌猴子只做一件事:随机关闭服务器。Gremlin 的完整工具包使用户能够对他们的系统进行近 12 种不同的攻击，如资源、状态和网络攻击，以便为这种情况做好准备。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>