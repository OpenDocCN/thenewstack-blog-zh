# Cloud Foundry 的 Eirini 和对互操作性的承诺

> 原文：<https://thenewstack.io/cloud-foundrys-eirini-and-the-commitment-to-interoperability/>

[Cloud Foundry](https://www.cloudfoundry.org/) 赞助了这个播客。

[云代工峰会的主题是互通和 Eirini](https://thenewstack.simplecast.com/episodes/cloud-foundry-summits-theme-of-interoperability-and-eirini)

上周在费城举行的 Cloud Foundry Summit 北美峰会的一个主题是互操作性及其对 Cloud Foundry 的重要性——随着验证项目 Eirini 的 Cloud Foundry 应用运行时版本的核心功能测试开始。

在 New Stack 的创始人兼主编亚历克斯·威廉姆斯主持的播客中，他说:

作为 Cloud Foundry 不断提高互操作性的努力的一部分，Eirini 就是为了这个目标而创建的，用于为 Cloud Foundry 应用程序运行时进行调度。正如 Cloud Foundry 指出的，组织可以选择采用 Diego/Garden 或 Kubernetes 来编排应用程序容器实例。

以前，Cloud Foundry 中的容器调度仅限于 Diego。弗里德曼说，这是因为 Cloud Foundry 比其他容器调度程序更早建立了 Diego。“所以，我们必须自己建造，对吗？如果你想建立一个云铸造推送体验，你将需要一个容器调度器，”弗里德曼说。“一个都不存在，所以我们造了一个。”

弗里德曼说，今天，Cloud Foundry 可以为组织提供“每当他们想要云 Foundry 推送用户体验时的云 Foundry 推送用户体验”。“我认为这是很大的价值——它扩大了你可以进行 CF 推送的地方的数量，并扩大了生态系统，因为 Kubernetes 生态系统非常强大，”弗里德曼说。“现在，能够利用这一点是一件大事。”

Krannich 说，Eirini 的创建始于“市场现实”，Kubernetes 成为这些天来集装箱管理的事实标准。“因此，很明显，云代工厂要保持相关性——你需要能够应对这些市场现实和整体演变，”Krannich 说。“另一件事是，市场上推出了更多新技术，可能 Kubernetes 甚至是技术堆栈中更成熟的一部分。”

通过 Kubernetes，Istio 响应了分布式系统中的另一个需求，允许“一个大的微服务网互相交谈，”Krannich 说。“我想，正如我们在计算机科学研究中所了解的那样，网络并不总是可靠的，你想与之交谈的服务并不总是可用的，等等。，”克兰尼克说。“因此，Istio 是一种(对开发这些服务的人来说是透明的)处理几个方面的技术，比如如果服务第一次不可用，如何实际上重试对另一个服务的调用，”Krannich 说。“如何正确地做到这一点，就像它不会真的有助于用请求淹没服务，但你需要一点时间，一秒钟后尝试，两秒钟后尝试，然后可能等待更长时间。诸如此类的事情。”

Krannich 说，Istio 也是一种保证服务间通信安全的方法。“传统上，我们要求服务开发商自己处理类似 TLS 加密和所有这些技术的事情，”Krannich 说。“现在，我们基本上看到了一种趋势，Istio 是有所帮助的技术之一，它说，不，实际上，使用这些服务的人应该从做那些艰苦工作的负担中解脱出来，应该有共同的底层技术来处理这些方面。”

今天，Kubernetes 显然也主导着容器运行时。“当我们在这个社区中谈论时，你实际上只指 Kubernetes。还有其他容器运行时，但 Kubernetes 更受欢迎，”高说。“所以，我们试着看看你的团队或公司需要什么，然后试着看看什么更适合你的要求，因为我看到这个社区真的很丰富多样。”

[https://www.youtube.com/embed/MZoKCs6r5I0?feature=oembed](https://www.youtube.com/embed/MZoKCs6r5I0?feature=oembed)

视频

### 在这个版本中:

[1:52:](https://thenewstack.simplecast.com/episodes/cloud-foundry-summits-theme-of-interoperability-and-eirini?t=1:52)ei rini 是如何向前迈进的。
[4:22:](https://thenewstack.simplecast.com/episodes/cloud-foundry-summits-theme-of-interoperability-and-eirini?t=4:22) 开源环境的好处。
[7:24:](https://thenewstack.simplecast.com/episodes/cloud-foundry-summits-theme-of-interoperability-and-eirini?t=7:24) 运行时比较。
[11:10:](https://thenewstack.simplecast.com/episodes/cloud-foundry-summits-theme-of-interoperability-and-eirini?t=11:10) 云铸造与其他云原生技术。
[15:34:](https://thenewstack.simplecast.com/episodes/cloud-foundry-summits-theme-of-interoperability-and-eirini?t=15:34) 探索抽象的分级和“漏抽象”
[20:26:](https://thenewstack.simplecast.com/episodes/cloud-foundry-summits-theme-of-interoperability-and-eirini?t=20:26) 那些抽象的进化。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>