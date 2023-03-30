# 与 Kasten 的 Georgi Matev 讨论微服务、DevOps 和数据

> 原文：<https://thenewstack.io/discussing-microservices-devops-and-data-with-kastens-georgi-matev/>

[用卡斯滕的 Georgi Matev](https://thenewstack.simplecast.com/episodes/managing-data-at-scale-with-kastens-georgi-matev) 管理大规模数据

对于微服务环境，数据可能很棘手。在一个一切都被设计为高度短暂、可扩展和临时的系统中，数据存储不属于任何一个类别。有状态应用程序需要稳定的数据平台，这些平台不会在流量下降时消失，也不会在站点过载时不堪重负。

由于这种方钉圆孔的问题，许多 DevOps 从业者会发现自己被沉重的数据所拖累。它会拖累敏捷流程，在团队等待 DBA 手动调整存储或更新模式以适应应用程序更改时，会在发布周期中产生很大的间隙。

[Kasten](https://www.linkedin.com/in/georgimatev)的产品主管 Georgi Matev 花了很多时间专门思考这个问题在 Kubernetes 下会如何发展。Kasten 提供了一个运行在 Kubernetes 上的开源数据管理平台 [Kanister](https://github.com/kanisterio/kanister) 。他说，在基于容器的环境中，数据管理和 DevOps 通常面临的问题之一是团队内部的责任问题。

“当组织计划过渡到 DevOps，或者他们已经在这样做时，真正了解不同团队之间的关系需要如何改变是非常重要的。我的意思是，负责基础设施方面的人需要做什么不同的事情，负责开发方面的人需要做什么不同的事情。这两者之间有相当多的相似之处，但我们肯定会看到一些活动有些专门化。当涉及到处理微服务正在使用的数据时，尤其如此，”Matev 说。

他补充说，当涉及到数据库时，这种职责划分可能变得难以界定。“传统上，有许多操作员专注于一些数据管理任务，但在 DevOps 世界中，许多这些功能正在转移给开发人员，这两者合作以提供仍然满足业务连续性要求的应用程序，并确保数据安全存储，这一点非常重要。”

将 Kubernetes 加入其中会使事情变得更加复杂，但 Matev 仍然相信这是未来管理数据库的方式。“Kubernetes 是开始为您的组织构建数据库即服务类型产品的绝佳平台。我们经常与开始考虑这一点的集中式 IT 团队合作，他们发现这是一个很好的平台，可以应对自动扩展和处理额外负载方面的许多挑战。但是，当他们规划其中一些过渡时，他们会考虑，“在这样的环境中，我将如何执行一些有关业务连续性、数据保护和灾难恢复的传统业务要求。”做这些事情的工具还不太到位。"

### 在这个版本中:

[0:45:](https://thenewstack.simplecast.com/episodes/managing-data-at-scale-with-kastens-georgi-matev?t=0:45) 为负责自动化微服务相关操作任务的人员提供全面的建议

[5:00:](https://thenewstack.simplecast.com/episodes/managing-data-at-scale-with-kastens-georgi-matev?t=5:00) 您是否注意到数据敏捷性已经成为公司特别寻求的东西？

[6:45:](https://thenewstack.simplecast.com/episodes/managing-data-at-scale-with-kastens-georgi-matev?t=6:45) 你能告诉我你在 Kubernetes 做的工作吗？

在 Kubernetes 上托管一个数据库是什么样子的？

[12:02:](https://thenewstack.simplecast.com/episodes/managing-data-at-scale-with-kastens-georgi-matev?t=12:02) 处理新数据点的控制

[14:05:](https://thenewstack.simplecast.com/episodes/managing-data-at-scale-with-kastens-georgi-matev?t=14:05) 人们应该在容器中运行数据库吗？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>