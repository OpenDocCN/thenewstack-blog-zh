# 为什么 Kubernetes 使 Lyft 游乐设施成为今天的样子

> 原文：<https://thenewstack.io/why-kubernetes-makes-lyft-rides-what-they-are-today/>

[为什么 Kubernetes 让 Lyft 成为今天的样子](https://thenewstack.simplecast.com/episodes/why-kubernetes-makes-lyft-rides-what-they-are-today)

乘车共享公司 Lyft 将继续在比赛中严重依赖 Kubernetes 和微服务，以提供移动解决方案，最终在不久的将来将包括人工智能驾驶的汽车。这是一个关键点[Lyft](https://www.linkedin.com/in/vickicheung/)的工程经理 Vicki Cheung 在上海举办的[kube con+CloudNativeCon 2018](https://www.cncf.io/kubecon-cloudnativecon-events/)播客中对 New Stack 的创始人兼主编 Alex Williams 说。

在担任 [OpenAI](http://openai.com/) 的工程主管后，特斯拉创始人兼首席执行官埃隆·马斯克(Elon Musk)共同创立了一个非营利性的人工智能研究小组；Cheung 在 Lyft 几年前试图转向基于集装箱的堆栈后加入了 Lyft。这是当“炒作越来越多，每个人都试图做出改变，但在 Kubernetes 出现之前，”张说。

“所以在此之前，Lyft 有一个基于 Salt 的自制供应系统，我们希望让一切都基于容器，所以我们再次在内部构建了一些编排系统，”Cheung 说。“然后 Kubernetes 出现了，然后我们的工程团队就像这样，‘哦，实际上，这看起来好多了，因为我们得到了开源社区的支持，然后我们就不必维护我们自己的东西了。’所以，我们决定等待 Kubernetes 稍微成熟一点，然后我们现在就开始转换。"

对于 Lyft 的基础设施，Go 经常被使用，“特别是因为我们与一系列不同的开源项目深度集成，”Cheung 说。

“我们确实做出了转变，开始将越来越多的 Go 集成到我们的堆栈中..Cheung 说:“我们就像是一家商店。“我们确实有微服务，所以人们可以选择他们想要的任何东西，但这些是首选语言。所以对我来说，我会说，从历史上看，就像我工作过的其他公司一样，我们一直是 Go 或 Python。”

Cheung 说，最终结果是 Lyft 的开发平台和基础设施是“超级微服务、面向微的”。“因此，我们有数百个微服务，对于许多人来说，我认为他们可以自由选择堆栈，容器是一个自然的选择，这样他们就可以从虚拟机层控制整个堆栈。然后，我们现在作为一个基础设施团队，不需要进入如何运行服务的杂草中，”Cheung 说。“我们只需要提供可以运行这些图像的平台。所以我认为我们选择…容器的原因是基础设施和服务所有者之间的对比更加明显。我们只是说，‘好吧，有这个平台将运行这个非常具体的接口，你只需要提供它。’"

Cheung 说，在其他可用平台中，Kubernetes 是一个明确的选择。“我们选择 Kubernetes 是因为我们查找了一系列不同的运行容器的平台，我们决定 Kubernetes 是目前生态系统中最受支持的，我想也是因为它很容易理解，”Cheung 说。“就运营而言，开销更少。”

当然，当客户用智能手机安排 Lyft 的行程时，大多数人显然不知道也不关心支撑他们体验的底层 Kubernetes 平台。

“Kubernetes 使我们能够真正提高开发人员的工作效率，因此我们可以更快地为客户带来新功能，这是因为像现在一样，我们的工程师不需要去和 Salt 打交道。Cheung 说:“他们也不需要去了解那些他们没有接受过培训也不应该了解的基础架构层。现在，他们只需要知道他们可以构建一个需要运行的映像，一旦他们有了这个映像，他们就把它交给基础架构团队，就这样。”

[https://www.youtube.com/embed/PZ3T-UEzdRs?feature=oembed](https://www.youtube.com/embed/PZ3T-UEzdRs?feature=oembed)

视频

### 在这个版本中:

[1:40:](https://thenewstack.simplecast.com/episodes/why-kubernetes-makes-lyft-rides-what-they-are-today?t=1:40)Cheung 如何涉足基础设施软件。
[4:19:](https://thenewstack.simplecast.com/episodes/why-kubernetes-makes-lyft-rides-what-they-are-today?t=4:19) 探索 Cheung 在 Lyft 担任工程经理的工作，以及 it 的特使和服务网格方面
[10:59:](https://thenewstack.simplecast.com/episodes/why-kubernetes-makes-lyft-rides-what-they-are-today?t=10:59) 特使是什么？
[13:49:](https://thenewstack.simplecast.com/episodes/why-kubernetes-makes-lyft-rides-what-they-are-today?t=13:49) 这对开发人员的体验有何影响？
[18:04:](https://thenewstack.simplecast.com/episodes/why-kubernetes-makes-lyft-rides-what-they-are-today?t=18:04) 您开始使用的来自开源社区的其他工具有哪些？
[19:06:](https://thenewstack.simplecast.com/episodes/why-kubernetes-makes-lyft-rides-what-they-are-today?t=19:06) 什么是可观测性栈？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>