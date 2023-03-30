# 视频教程:Weave Scope，展示您用 Docker 构建的缺失部分

> 原文：<https://thenewstack.io/video-tutorial-weave-scope-the-missing-piece-to-show-what-youve-built-with-docker/>

几周前，在新的堆栈上，Weaveworks 软件工程师 [Peter Bourgon](https://github.com/peterbourgon) 和 [David Kaltschmidt](https://github.com/davkal) 发布了一个关于 [Weave Scope](http://weave.works/scope/index.html) 的[教程](https://thenewstack.io/how-to-detect-map-and-monitor-docker-containers-with-weave-scope-from-weaveworks/)，它提供了对基础设施中每个主机、容器和进程的自动检测和监控，并构建了它们的通信地图。

最近，New Stack 创始人 Alex Williams 与 Peter 和 Weaveworks 团队进行了联系，以拍摄 Scope 的视频教程，并讨论这一新产品的开发。

[https://www.youtube.com/embed/7nU4FLqrq18?feature=oembed](https://www.youtube.com/embed/7nU4FLqrq18?feature=oembed)

视频

“当我们开发 Scope 时，激励我们的是目前许多开发人员和技术组织工作的新环境，”Peter 说，“这种环境是建立在许多新概念和技术之上的，如 Docker、容器、微服务等。这是编写软件、部署软件和在生产中运行软件的一种新的思维方式。”

他们认为缺少一些必要的工具。“在这个新世界里，”Peter 说，“你从现成的数据服务，如 Elasticsearch、PostgreSQL 或 Redis 中拼凑出你的应用程序，将它与你自己内部编写的应用程序服务结合起来，在顶层使用标准的负载平衡和流量整形层，最终你会得到一个在构建时有意义的基础架构，但随着时间的推移可能会有点棘手。

> 我们没有看到有一个好的方法来看看你实际上已经建立了什么，并随着时间的推移保持关注。这就是范围的上下文。

“我们想要一种可以像应用程序服务一样部署到基础架构中的东西。至关重要的是，在没有配置、没有声明的情况下，我们希望能够向您展示您已经构建的基础架构，让您探索它，让您看到您已经部署的现有服务，四处点击，并能够监控您已经部署的东西—您的容器—在它们出现问题时对它们进行故障排除，并从根本上了解它们。”

在本教程中，Peter 从主机视图开始，该视图显示了一个简单的单主机设置。然后，他转到 Containers by Image，这显示了他为演示部署的典型的三层堆栈:底层是数据库服务器，中间是应用服务器(业务逻辑所在的位置)，顶层是负载平衡层(如 Nginx 或 HAProxy)。

他强调，Scope 已经从基础设施中收集了这些信息，而无需更改或检测任何这些应用程序。无论是数据库、负载平衡器还是应用程序源，“一切都会好的。”

“Scope 正在查看主机操作系统并进行各种智能关联，”Peter 说，“以找出数据通信路径，而无需插入任何代码。”

容器视图显示了数据库的三个实例，显示了每个实例如何与两个应用服务器进行对话，每个应用服务器与各自的负载平衡器进行联系。

“应用程序”视图显示每台主机上的各个进程。单击代表应用服务器的节点会显示关于该进程的信息，包括 TCP 连接的数量、进程名称以及关于运行它的主机的统计信息。Weaveworks 打算在未来几个月扩大这一资源，以包括带宽和深度包检查。

“Scope 的神奇之处在于，所有这些信息都可以在语义上组合起来，”他说，展示了两个应用服务器的数据是如何通过图像视图合并到容器中的。

“通过这种方式，您可以真正深入了解并发现问题，并查看哪些实例可能行为不当，可能会看到更多流量，”Peter 说，“所有这些都是在没有任何配置和声明的情况下发生的。”

Peter 说，虽然他们认为这个工具在生产环境中很重要，但他强调在典型的开发人员工作流程中拥有它也很重要——构建-运行-测试循环。

“它在那种环境下同样工作得很好，”Peter 说，“它帮助新开发人员和您的基础设施老手弄清楚他们到底在构建什么，以及它是如何交互的——并且是从网络上实际发生的事情的角度，而不是从您认为正在发生的事情或您预期应该发生的事情的角度。当你在构建软件时，这种透明度非常重要，我们认为这是当前生态系统中所缺乏的。”

Weaveworks 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>