# jClarity 将精确的 Java 监控带入了容器世界

> 原文：<https://thenewstack.io/jclarity-apm-java-applications/>

在容器的新世界里， [Java 和 Docker 不一定合得来](https://developers.redhat.com/blog/2017/03/14/java-inside-docker/)。

这是总部位于伦敦的 [jClarity](https://www.jclarity.com/) 正在帮助客户解决的问题之一。它在 Java/JVM 应用的轻量级性能分析和监控工具中采用了[机器学习](/category/machine-learning/)。

联合创始人兼首席执行官 Martijn Verburg 表示，Docker 描述其所拥有的资源——内存、CPU、网络——Java 基本上是从 Docker 那里获取这些数字并曲解它们。

Docker[公司](https://thenewstack.io/docker-updates-legacy-application-migration-program/)，甲骨文，以及[红帽](https://thenewstack.io/red-hat-summit-serves-openstack-io-saas-containerized-java-microservices/)， [IBM](https://thenewstack.io/ibm-takes-cloud-private/) 等都在致力于解决这些问题。

“Docker 的人说是 Java 的错，Java 的人说是 Docker 的错。说到底，Java 是在完全错误的假设下运行的，比如给了它多少内存，给了它多少 CPU。特别是 Java 非常依赖的那两个数字，意味着奇怪的问题开始发生了，”他说。

该公司的初始产品 [Illuminate](https://www.jclarity.com/illuminate/) ，是一个软件即服务的性能诊断引擎，它使用机器学习来帮助用户查明和纠正 Sun/Oracle/open JDK JVM 中的性能问题。它支持所有的 JVM 语言。

它的第二个工具是 [Censum](https://www.jclarity.com/censum/) ，用于检测内存泄漏和应用程序暂停等问题。它从复杂的 Java (JVM)垃圾收集子系统获取日志文件，以帮助用户确定为什么会发生这种情况。jClarity 提供 Censum 作为 SaaS 选项或本地部署。

[https://www.youtube.com/embed/h1ZZDSfRbJI?feature=oembed](https://www.youtube.com/embed/h1ZZDSfRbJI?feature=oembed)

视频

Verberg 说，集装箱对公司产生了巨大的影响。

“Java 一直认为它可以在裸机上、在实际的物理设备上，或者至少在 VMware 的某种虚拟机管理程序上有效地运行，”他说。

JClarity 的软件使用每台主机上的代理从操作系统和 Java 本身收集信息，以执行问题的根本原因分析。他说，对于容器来说，它附着在外部——Java 为此提供了一种机制。

“容器纯粹主义者说每个容器应该只有一个进程，这意味着没有我们的空间。我们不得不改变针对这些客户的部署策略，”他说。“就用户而言，我们的软件只是他们应用程序的一部分。这仍然是一个单一的过程…如果你遵循纯粹的容器方法，我们可以处理。

“我敢说，我们还发现许多人正在采取一种更务实的方法，使用 Kubernetes 之类的东西来允许一个其他进程(通常只有一个其他进程)附加到他们的应用程序上，通常用于监控。这就是我们:我们是一个监控工具。”

用户可以在应用程序的任何方面指定服务级别协议，例如登录页面必须在一秒钟内响应，或者该数据库事务应该在半秒钟内返回。代理包含机器学习引擎的副本，并且它对问题的根本原因做出决定。

“对于用户来说，Java 应用程序可能看起来很慢，但它可能是主机上的一个数据库在向硬盘进行大量写入，从而降低了整个机器的速度并影响了应用程序。我们的算法非常善于发现这些隐藏的关系，”他说。当检测到问题时，它会向用户发送一份简单的英文报告，并推荐后续步骤。

它发出一封电子邮件，敦促用户去一个仪表板。Verberg 说，与 Slack 等其他工具的集成正在进行中。

## 更多自动化即将到来

韦尔伯格在 Java 大会上扮演了另一个自我[恶魔般的开发者](https://www.youtube.com/watch?v=bjp7bhzyhQo&feature=share&list=PLRsbF2sD7JVq8QYW0vlbOS2JuXUWaWMnT&index=30)。—他和联合创始人 [Ben Evans](https://github.com/kittylyst) 写了《扎实的 Java 开发人员 T4》一书，然后在 2012 年左右开始应用他们的性能调优知识。他们与 Kirk Pepperdine 一起创建了位于伦敦的公司，Kirk pepper dine 在高性能计算方面有丰富的经验，他们是在会议世界中认识的。

“我们很快意识到这超出了决策矩阵或简单的统计数据，我们实际上需要使用一些机器学习来获取我们所拥有的人类知识，并将其转化为具有任何合理准确性的算法，”韦尔伯格说。

为此，他们聘请了几位博士数据科学家——[理查德·沃伯顿](https://github.com/RichardWarburton)和[约翰·奥利弗](https://github.com/johnoliver)——来创建这个算法，韦尔伯格称之为它与竞争对手 New Relic 和 AppDynamics 的主要区别。

“New Relic 和 AppDynamics 生成所有指标，并(从中)生成令人惊叹的视觉效果和信息图表。他们真的很聪明。我们真的很钦佩他们在那里所做的一切。

“但是在一天结束时，人类仍然需要查看这些图表，并尝试将三四个不同的图表关联起来，以试图找出潜在的问题。我们更进一步:我们检查所有的数据，告诉他们，‘你的问题就在这里，’”他说，并补充说，然后它会准确地建议需要做什么——比如哪一行代码——来修复它。

到目前为止，用户必须手动去做，但该公司的路线图是自动化这些修复。

“我们知道这是一个教育片，因为用户不一定信任一个自动化系统，”他说。

“我们可能会以‘这是我们的建议’开始。这是一个应用按钮。它会为你应用它。我们认为，随着时间的推移，随着行业对人工智能的信任度越来越高，其中一些修复可以自动应用，当然，只要用户得到通知。"

该公司正在筹集种子资金。它的客户包括旅游网站 Kayak 和英国房地产门户网站 [Rightmove](http://www.rightmove.co.uk/) **，**这两家网站，对它们来说，速度慢会让用户感到沮丧，并导致他们失去客户。

专题图片:[晨拿铁](https://www.flickr.com/photos/wordridden/6055636977/in/photolist-ae7HU6-cZtaCE-8TJjGJ-o9zM2M-rNAPzb-f36Qe8-99eCz7-644eUY-bfbAmk-7RW3kZ-6ZKmW-a1dXW6-4AFHoq-6uzQZX-4ADDAt-4w4LG8-4hMeAn-99dw8Q-cRz6tC-4pHdd5-8KkaWd-Es1aY-Tvcgar-qektu-dNRrQq-887JXd-4Qa)由[杰西卡·斯宾格勒](https://www.flickr.com/photos/wordridden/)创作，获得 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>