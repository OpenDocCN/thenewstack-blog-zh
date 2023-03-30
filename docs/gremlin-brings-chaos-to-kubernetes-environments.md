# Gremlin 给 Kubernetes 的环境带来混乱

> 原文：<https://thenewstack.io/gremlin-brings-chaos-to-kubernetes-environments/>

Portworx 赞助了 New Stack 对 KubeCon+CloudNativeCon 北美 2019 的报道。

进一步扩展其故障即服务平台， [Gremlin](https://www.gremlin.com/) 在 Kubernetes 环境中推出了对混沌工程的本地支持。[混沌工程](https://thenewstack.io/how-chaos-engineering-can-drive-kubernetes-reliability/)的团队通过模拟分布式系统的压力和攻击为最坏的情况做准备。

该公司去年增加了对 [Docker 环境](/gremlin-now-treats-containers-as-first-class-failures/)的支持，并在 10 月通过其[应用级故障注入](https://www.gremlin.com/the-next-step-application-level-fault-injection/) (ALFI)技术增加了对[无服务器](/gremlin-applies-chaos-testing-to-serverless/)的支持，该技术提供了一种通过将断点插入开发者代码本身来进行应用级故障测试的方法。

Expedia 项目管理总监西蒙·戈维尔说:“Gremlin 为我们在 Kubernetes 的特定服务上运行混沌实验提供了一种简单可靠的方法。“这大大减少了进行故障注入所需的时间，并提高了我们系统的故障恢复能力。"

Gremlin 声称它是唯一一个直接与 Kubernetes 集成的企业产品。

Gremlin 的联合创始人兼首席技术官 Matthew Fornaciari 说:“你在那里嵌入一个控制器，它会贯穿你的部署，并使它变得非常容易，然后根据你如何进行部署来运行一点混乱。

“你不需要围绕如何定位目标来转换思维。你可以说，‘好吧，这个部署，这个守护进程集或者这个 pod，这就是我要攻击的。然后你只需进入我们的用户界面，找到它，按名称空间过滤，就可以了。"

在一篇博客文章中，产品总监 Lorne Kligerman 是这样说的

*“过去，如果您在 Kubernetes 集群中的一个容器上安装了 Gremlin，那么您需要处理由 Kubernetes orchestrator 上下旋转的容器。将您想要试验的服务的底层容器作为目标有点像打地鼠游戏。”*

Gremlin 允许锁定 Kubernetes 集群中的对象。选择一个集群后，您可以通过选择一个名称空间来过滤可见的对象集。选择您的任何部署、副本集、状态集、守护集或单元。当选择一个对象时，所有子对象也将成为目标。

他补充说，现在你不必再在一长串特定的容器中寻找，也不必怀疑你是否找到了所有的容器。相反，此攻击的目标容器将显示在攻击详细信息屏幕中，按它们所属的 Kubernetes 对象分组。

根据您选择的对象数量，UI 提供了攻击的可视化效果。

根据 Fornaciari 的说法，在仪表板的右上角是一个红色的停止按钮，这意味着你可以立即停止攻击并回滚一切，安全是最重要的。

该公司在 9 月份的[混沌会议](https://www.chaosconf.io/)用户大会上宣布了其[场景](/gremlins-scenarios-simulate-common-outages-for-chaos-engineering/)功能。它由六个推荐场景组成，对系统承受常见云中断场景的能力进行了开箱测试。该公司计划很快在一个场景中实现针对 Kubernetes 的功能，尽管这还不可用。

该公司还就其推荐的 Kubernetes 攻击类型提供指导。

“Kubernetes 是一个非常强大的工具，你可以用它做任何事情。但这也意味着对新用户来说会有点复杂。“所以给他们一点指导，让他们尽可能简单地走出去，引起一点混乱，这就是释放本地社区支持的目标。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>