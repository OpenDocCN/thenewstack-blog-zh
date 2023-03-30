# 服务网格如何找到一位前太空尘埃研究者

> 原文：<https://thenewstack.io/how-service-meshes-found-a-former-space-dust-researcher/>

KubeCon + CloudNativeCon 和 [InfluxData](https://www.influxdata.com/) 赞助了这个播客。

[何役目寻一位前太空尘埃研究员](https://thenewstack.simplecast.com/episodes/how-service-meshes-found-a-former-space-dust-researcher)

在学生生涯的早期，安德鲁·詹金斯作为美国宇航局合同的一部分，为美国大气和空间物理实验室研究太空尘埃和其他有效载荷。正是在那里，当他“几乎从物理层”开始研究通信协议时，他开始将注意力转移到软件方面。

监控、可观察性、日志记录和其他对今天的软件生产管道越来越重要的功能，早在 15 年前詹金斯为美国宇航局工作时就已经投入使用了。然而，在那个时候，服务网格还没有开发出来，而 Kubernetes、微服务甚至 DevOps 也还没有出现。

在科罗拉多大学博尔德分校担任为国际空间站开发软件的研究生助理后，詹金斯继续“越来越深入到软件领域”在 2013 年加入 [F5 Networks](https://www.f5.com/) 后，他开始了解平台如何用于云应用的负载平衡、安全和其他任务的应用交付。当 [Aspen Mesh](https://aspenmesh.io/) 于 2017 年作为 F5 的副产品成立时，Jenkins 已经开始开发真正的服务网格平台来管理数据流量，作为向 Kubernetes 集群和微服务中的服务到服务通信转移的一部分。换句话说，可以说服务网格发现了詹金斯。

Jenkins 说:“这真的提升了通信的重要性，因为过去可能只是应用程序内部的一个函数调用，现在是通过网络流量进行的。”

在本期 New Stack Makers 播客中，Kubernetes 部署云网格的必要性和进一步发展是 Jenkins 讨论的中心。

当然，服务网格及其部署是全新的，它们的功能也在不断发展。服务网格平台的许多正在进行的开发工作都是为了响应客户的需求。作为所寻求的能力的一个例子，可观察性已经成为关键的服务网格需求，并且随着网格提供商继续增加改进，它仍然处于积极的发展中。"最重要的部分是将这种可观察性弹性引入服务网格. "詹金斯说:“第一件小事是应用程序开发人员可以在这些层下面的某个地方应用程序，以处理安全性、可观察性和弹性之类的事情。因此，这种工作方式变得有点像你的平台的一个方面，这可能会改变。它甚至可能属于另一个团队。"

Jenkins 用 TCP 栈层开发作为类比。“这几乎就像操作系统中的 TCP 栈，在编写代码时，你不会真正考虑 TCP 栈。詹金斯说:“我敢肯定，如果你在 TCP 栈之外认真思考，会发现有很多非常智能的软件，可以更快、更好、更安全等等，但当你在应用程序领域时，你可能只是把它当作底层来使用。“我认为，这就是服务网格的发展方向:它首先得到这样一个概念，‘嘿，它只是提供这种功能的底层东西，就像，依赖它一样。’随着时间的推移，实现细节可能会在不中断应用程序的情况下有所发展和变化。"

Jenkins 将服务网格的采用比作 TCP，后者消除了“开发人员从不花时间重组数据包”的需要。

“我希望服务网格成为处理分布式跟踪或证书轮换的[默认]方式。因此，如果您有一个应用程序，并且您希望它是安全的，您必须处理所有这些证书、密钥等。，”詹金斯说。“这并不是不可能，但是当您拥有微服务时，您不需要做很多次。这就是为什么您可以通过将它下推到服务网格层来获得更好的性价比，即使这不是不可能的，这只是多了一件事，您不必一直重复它。”

此外，服务网格也应该在微服务部署的金丝雀测试中变得更加流行。詹金斯说:“也许你想加入分布式跟踪，但你不必一下子全部完成。”。“发展道路非常重要，因为大多数用户将逐渐使用服务网格。”

### 在这个版本中:

[1:32:](https://thenewstack.simplecast.com/episodes/how-service-meshes-found-a-former-space-dust-researcher?t=1:32) 服务网格。
[10:55:](https://thenewstack.simplecast.com/episodes/how-service-meshes-found-a-former-space-dust-researcher?t=10:55) 服务网状的整体演进与路径。
[15:17:](https://thenewstack.simplecast.com/episodes/how-service-meshes-found-a-former-space-dust-researcher?t=15:17) 跟踪记录。
[17:28:](https://thenewstack.simplecast.com/episodes/how-service-meshes-found-a-former-space-dust-researcher?t=17:28) 金丝雀。
[22:20:](https://thenewstack.simplecast.com/episodes/how-service-meshes-found-a-former-space-dust-researcher?t=22:20) “去 Kubernetes 需要一个服务网。”
[30:29:](https://thenewstack.simplecast.com/episodes/how-service-meshes-found-a-former-space-dust-researcher?t=30:29) YAML 档案。

AspenMesh 和管理 Jenkins 的 CloudBees 是新堆栈的赞助商。

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>