# 用容器网络接口标准化容器网络

> 原文：<https://thenewstack.io/standardizing-container-networking-cni/>

随着标准化的讨论继续席卷容器社区，它也扩展到了容器的网络空间。这一领域的一项努力是最初由 T2 的 core OS T3 发起的容器网络接口 T1(CNI)。

在这一集的[中，新堆栈分析师](https://thenewstack.io/podcasts/analysts/)播客、中间层产品管理和营销主管 [Somik Behera](https://www.linkedin.com/in/somik) 和[思科](http://www.cisco.com/)首席技术官 [Ken Owens](https://www.linkedin.com/in/kenowens12) 讨论 CNI 和集装箱网络的所有事情。

[#118:与 CNI 标准化集装箱联网](https://thenewstack.simplecast.com/episodes/118-standardizing-container-networking-with-cni)

贝赫拉指出，与 Docker 自己的网络接口 libnetwork 相比，CNI 的灵活性是一个优势。“Libnetwork 是一种生命周期模型，或者更像是一种将技术连接在一起的覆盖模型。在我看来，网络管理员或开发人员对它并不熟悉，”Owens 说。“如果我看看 CNI，它与我所期望的网络工作方式非常相似。它非常简单，并且符合网络管理员的逻辑。”

“容器网络接口和容器网络模型之间的最大区别是，CNI 对实现技术非常不可知。它托管 API 的本地规范，并且在每台主机上都有。贝赫拉说:“CNI 非常固执己见，并得到了许多厂商的支持。

将这种复杂性从等式中抽象出来是欧文斯希望 CNI 继续关注的事情，他强调说，“我的观点一直是，开发者只是想让网络做网络需要做的事情，允许端口与其他可用的服务进行通信。我不认为你希望你的开发人员在应该开发应用程序的时候还想着联网。”

“进行多种类型的编排、多种类型的网络以及快速安装和运行插件的能力:所有这些组件共同构成了一个非常强大的案例，可以将 CNI 视为基础网络的起点，”Owens 说。

[![barcelona](img/19403431e61caee7d8e0ebecb3ae0718.png)](https://www.eventbrite.com/e/openstack-summit-pancake-breakfast-tickets-27692501016)

[思科](https://blogs.cisco.com/tag/mantl)、 [CoreOS](https://coreos.com/) 、 [Docker](https://www.mirantis.com/software/docker/kubernetes/) 和 [Mesosphere](https://d2iq.com/) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>