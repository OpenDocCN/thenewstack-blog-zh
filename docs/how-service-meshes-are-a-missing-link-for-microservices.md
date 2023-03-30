# 服务网格为何是微服务的缺失环节

> 原文：<https://thenewstack.io/how-service-meshes-are-a-missing-link-for-microservices/>

[服务网格如何成为微服务的缺失环节](https://thenewstack.simplecast.com/episodes/how-service-meshes-are-a-missing-link-for-microservices)

现在，人们普遍认为，向微服务和云原生环境的转变只会带来巨大的好处。随着云计算热潮的兴起，许多组织突然意识到了前进道路上的许多困难，例如 Kubernetes 和无服务器平台的出现往往是一项正在进行的工作。

“我们来到所有这些社区，基本上说服他们搬迁，对吗？Solo.io 的创始人兼首席执行官 [Idit Levine](https://www.linkedin.com/in/iditlevine) 说:“我们告诉他们，‘看，monolithic 非常复杂，让我们转向微服务吧’，所以，他们非常非常努力地工作，但后来他们发现工具还没有那么成熟。“实际上，他们以前拥有或使用的工具中存在许多缺口，现在他们正在失去这一功能。例如，记录日志或调试微服务是一个大问题，等等。”

莱文的公司提供服务网格解决方案，他也描述了服务网格是如何被设计成“解决这个问题”的，在由新堆栈的创始人兼主编亚历克斯·威廉姆斯主持的[新堆栈分析师](https://thenewstack.io/podcasts/analysts)的播客中，与 TNS 记者兼 Janakiram & Associates 的负责人 [Janakiram MSV](https://www.janakiram.com/) 一起。

Levine 说，当从单片环境迁移到微服务环境时，组织注意到的第一件事是“突然之间，你失去了对所有应用程序的可观察性”。“这是[服务网格]真正需要解决的一个问题。”

然后是安全。确保应用程序和微服务的安全在许多方面涉及到与整体安全性不同的动态。"微服务之间可以互相对话吗？"莱文说。“如何执行关于允许谁与谁交谈以及这是否安全的政策”是一个主要考虑因素。

路由也会带来问题。“这是为了确保管道对所有连接的所有微服务都可用，”Levine 说。“这是任何组织在尝试迁移到微服务时都会遇到的三个问题之一，这正是为什么需要服务网格的原因，因为它可以解决这些问题。”

Levine 指出，服务网格的早期发展可以追溯到谷歌、IBM 和其他公司创建 Istio T1 的时候。“我相信他们这样做的原因是，他们看了看他们的[联系人](https://linkerd.io/)，他们只是说，‘是的，这个想法非常好，但实施起来并不是最好的。’"

Levine 说，问题是 Java 代码“非常非常重，然后在性能、安装和整体解决方案方面有很多开销。”

“他们做了很多工作，尽可能做出最好的解决方案，”莱文说。“他们已经这样做了，他们创造了 filter 和 C++等等，这就是 Istio。”

谷歌和大多数微服务平台使用[特使](https://www.envoyproxy.io/)作为代理，这是由拼车服务和优步竞争对手 [Lyft](https://www.lyft.com/) 创建的。“特使提供了很好的性能，很好的扩展方式，”莱文说。“所以。我猜这就是他们选择它的原因。一旦他们选择了它，这就变成了一种(事实上的)代理。”

“所以这有点像他们让市场再次有点像碎片整理，对不对？因为现在有很多优惠，顾客很困惑该用哪一个，”莱文说。“除了 Linkerd 之外，所有新版本之间的唯一共同点是，它们都使用 Envoy。因此，在某种程度上，特使将变得有点像商品代理。”

### 在这个版本中:

[1:45:](https://thenewstack.simplecast.com/episodes/how-service-meshes-are-a-missing-link-for-microservices?t=1:45) Levine 对服务网格和该领域当前参与者的看法。
[6:00:](https://thenewstack.simplecast.com/episodes/how-service-meshes-are-a-missing-link-for-microservices?t=6:00) 路径对吗，方向对吗？
[13:44:](https://thenewstack.simplecast.com/episodes/how-service-meshes-are-a-missing-link-for-microservices?t=13:44) 总体而言，这是一个多租户问题吗？
[19:04:](https://thenewstack.simplecast.com/episodes/how-service-meshes-are-a-missing-link-for-microservices?t=19:04) 那么这对 Solo 意味着什么呢？
[24:55:](https://thenewstack.simplecast.com/episodes/how-service-meshes-are-a-missing-link-for-microservices?t=24:55) 对不同的服务网格进行管理和分组，并将它们集合在一起。
[26:54:](https://thenewstack.simplecast.com/episodes/how-service-meshes-are-a-missing-link-for-microservices?t=26:54) 讨论构建在 Kubernetes 之上的无服务器项目。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>