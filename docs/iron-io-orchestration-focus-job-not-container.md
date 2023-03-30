# Iron.io:编排应该关注工作，而不是容器

> 原文：<https://thenewstack.io/iron-io-orchestration-focus-job-not-container/>

在去年 3 月 31 日于三藩市举行的英特尔云日活动上，在与 New Stack 的 Alex Williams 的一次采访中，[容器工作负载管理提供商 Iron.io](https://www.iron.io/) 的首席执行官兼首席业务开发人员 [Chad Arimura](https://twitter.com/chadarimura) 为软件开发人员最终被允许在构建应用程序时忽略部署和基础设施问题提出了一个强有力的理由。

他提到了所谓的无服务器架构越来越受欢迎，如 [AWS Lambda 和谷歌云功能](https://thenewstack.io/google-cloud-functions-arrives-challenge-aws-lambda/)，其中软件部署的每个细节都对编写代码的开发人员隐藏。

Iron.io 业务开发主管 Ivan Dwyer 也加入了 Arimura 的行列，他指出，在一个最佳系统中，开发人员将只关注工作负载，而不是托管它们的过程。

“如果你看看服务器、虚拟机和现在的容器的演变，从某种意义上说，容器只是服务器的另一个歧义，”Dwyer 说。“现在我们可以将大量容器放入服务器。但我们喜欢将其视为下一次发展:也就是说，围绕工作或工作负载类型。”

点击这里收听播客:

[Iron.io 的 Ivan Dwyer 和 Chad Arimura 谈无服务器架构的复杂性](https://thenewstack.simplecast.com/episodes/iron-ios-ivan-dwyer-and-chad-arimura-on-the-complexity-of-serverless-architectures)

这是一个奇怪的案例，尤其是在英特尔刚刚宣布与一家商业容器制造商(CoreOS)和一家商业 OpenStack 分销商(Mirantis)扩展合作关系的活动上。他们共同努力的一个目标是使英特尔处理器和 CoreOS 容器的编排器能够直接相互通信。通过这种方式，Kubernetes(以及，通过扩展，CoreOS architectural)将能够轮询服务器集群中的单个处理器，并可以根据它们的相对就绪状态将工作负载转移到选定的处理器上。

Iron.io 更倾向于这样一种状态，其中封装应用程序的虚拟信封，无论是 Docker (OCI)容器还是 VMware 风格的虚拟机，在某种程度上对开发人员来说都是不重要的。Dwyer 向 Williams 建议，最佳的平台应该专注于工作负载所代表的工作。

他认为，这种集中将使通常关注 CPU 利用率和延迟等因素的监控功能能够报告与工作本身相关的指标:例如，使用图像处理器，正在扫描和处理多少图像，以及图像的大小。这样，服务提供商和客户之间就可以达成服务水平协议(SLA ),这些协议也与工作绩效有关，而不仅仅是可用性和正常运行时间。

“有了更细粒度的计算单元，可扩展性变得更加高效和有效，”德怀尔在 2015 年 2 月的一篇[iron . io 白皮书](https://www.iron.io/resources/white-papers/microservices-patterns-for-building-modern-applications/)中写道。“作为一种模式，微服务通过将功能元素分解为单独的服务来提升 Y 轴可扩展性，这与传统的复制相反。这种组件分离为构建和维护高度可伸缩的应用程序创造了更有效的环境。”

英特尔和 Iron.io 是新堆栈的赞助商。

专题图片:[旧金山-奥克兰海湾大桥](http://www.loc.gov/pictures/resource/hhh.ca1352.photos.016405p/)的锚缆，美国国会图书馆。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>