# 开源 Mizu 解除了对 Kubernetes API 流量的封锁

> 原文：<https://thenewstack.io/open-source-mizu-unblocks-view-into-kubernetes-api-traffic/>

来自微服务测试平台 UP9 的最新开源项目名为 Mizu，这是一个使开发者能够在本地 web 应用程序中看到他们所有 Kubernetes API 流量的实用程序。

你可以在 [Kubernetes](https://thenewstack.io/category/kubernetes/) 中查看所有微服务之间的 API 通信，就像你会使用 Google ChromeDevTools 查看 web 应用的流量一样。

“过去，通过流量检测进行故障排除是一件非常简单的事情。有了 Kubernetes，就不再容易了，”Up9 创始人兼首席执行官[阿龙·吉蒙斯基](http://linkedin.com/in/alongirmonsky/)说。

“今天，当开发人员遇到问题，他们想要排除故障时，由于多种原因，没有流量—流量是分布式的，流量需要权限，流量处于加密层和新协议之下，需要先解密才能了解发生了什么。

“所以流量是很难获得的。如果你看看行业中的其他工具，它们都需要代码插装。对吗？你必须安装一个 SDK、一个代理，或者修改你的代码，以便能够在时机成熟时，真正看到通信的内部，弄清楚发生了什么。”

相比之下，开发者可以下载 40 兆字节的实用工具 Mizu 并查看流量。

Mizu 是一个[可观察性](https://thenewstack.io/category/monitoring/)工具，它注入了一个[容器](https://thenewstack.io/category/containers/)，该容器在 Kubernetes 集群的节点级别执行类似 tcpdump 的操作。此操作可通过 CLI 按需执行，无需准备即可使用。使用后，容器被移除。

在运行时，Mizu 被动地观察网络级别的流量，而不是代理。Mizu 不需要代码检测。

CLI 内置于 [Golang](https://thenewstack.io/go-the-programming-language-of-the-cloud/) 中，无需安装即可下载运行。Mizu 使用 kubectl，所以可以在任何配置了 kubectl 的节点上运行。

Mizu 可以作为[可执行二进制文件](https://github.com/up9inc/mizu/releases/latest)下载，或者作为源代码直接从其 [GitHub 库](https://github.com/up9inc/mizu)下载。

使用正则表达式，您可以观察所有流量或特定的 pod。当 Mizu 运行时，名称与正则表达式匹配的 pod 将被观察到，它们的流量将被记录。

可观察性工具支持 HTTP/1.x、HTTP/2、AMQP、Apache Kafka 和 [Redis](https://redis.com/?utm_content=inline-mention) 协议。需要 1.16.0 或更高版本的 Kubernetes 服务器。

## 挖掘交通

对于一个使用 API 的现代云开发人员来说，仅仅看到 TCP 包被传递是不够的。"

开发人员将打开浏览器，看到 Kubernetes 集群内部的实际流量。他们想深入了解:他们知道 Kafa、gRPC、REST 等协议，这些协议承载于整个网络堆栈之上。"

“如果我是一名 web 开发人员，我会使用 Chrome DevTools 来检查和查看流量。但是在 Kubernetes，你没有 Chrome DevTools 你甚至没有过去的 tcpdump，你必须有运行它的权限。然后，它只会给你 TCP 包，这…一切都有点混乱，在某种程度上在开发人员的眼中。

“使用 Mizu。我获得许可，我点击，我翻译，我在一个漂亮的用户界面上看到我面前的一切。我可以开始挖掘并尝试找到问题的遗迹，这将引导我找到问题的根本原因，并有可能解决问题。”

也就是开发者在公司内部有没有查看流量的授权。该工具允许公司根据用户角色设置不同的授权级别。

Mizu 包括一个建立在名为 [Basenine](https://github.com/up9inc/basenine) 的数据库软件之上的过滤系统。它不受模式限制，可实现最快的写入速度和线性扩展的读取速度。它接受 JSON 作为记录格式，只允许创建和读取访问。

过滤系统在 Basenine 数据库服务器内部采用 [Basenine 过滤语言(BFL)](https://github.com/up9inc/basenine/wiki/BFL-Syntax-Reference) ，实现高效、精确的流量日志查询。

有了新的过滤语法，许多 UI 元素都是可查询的，并且结果可以打上时间戳。

## 测试自动化

2011 年，Girmonsky 创建了 Blazemeter，这是一个基于开源的负载测试云。它被 CA Technologies 收购，后来被 Broadcom 收购，最近于去年 9 月被 Perforce 收购。

在 Broadcom 工作期间，Girmonsky 和他目前的联合创始人 [Alex Haiut](https://www.linkedin.com/in/alexhaiut/) 、 [Andrey Pokhilko](https://www.linkedin.com/in/andreypohilko/) 和 [Refael Botbol Weiss](https://www.linkedin.com/in/refaelbotbol/) 遇到了一个[反复出现的问题](https://up9.com/why-i-started-up9):新发布的产品会破坏以前无缝运行的功能，客户的愤怒电话随之而来。

持续的问题使他们得出结论，软件测试在[微服务](https://thenewstack.io/category/microservices/)时代被打破。他们不是唯一这么说的。

他们创建了 UP9，这是一家位于加州帕洛阿尔托的初创公司，为微服务、Kubernetes 和[云原生](https://thenewstack.io/category/cloud-native/)技术提供开箱即用的测试自动化。结合了机器学习和人工智能，这是一种内部技术，而不是 SaaS。

这些工具使开发人员能够解包 Kafka、REST、gRPC、Redis 和 RabbitMQ 等 API 协议，并持续监控 API 有效负载，以检测进入生产环境的漏洞。

该公司在 12 月宣布收购总部位于英国的 [MockLab Ltd.](https://get.mocklab.io/) ，开源 API 模仿工具 [WireMock](https://wiremock.org/) 的创造者。

一个基于 HTTP 的 API 的模拟器，它使开发人员能够原型化一个尚不存在或不完整的 API。您可以使用它来测试真正的 API 不会可靠地产生的边缘情况和故障模式。

收购完成后，WireMock 创始人汤姆·阿克赫斯特被任命为 UP9 的首席技术官。

[https://www.youtube.com/embed/zeN2xo-ttz4?feature=oembed](https://www.youtube.com/embed/zeN2xo-ttz4?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>