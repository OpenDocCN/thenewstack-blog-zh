# 如何开始使用 HTTP/3

> 原文：<https://thenewstack.io/how-to-get-started-with-http3/>

像世界上许多人一样，随着 2022 年的结束，我期待着观看世界杯。有一天，我一边遛狗，一边用手机看世界杯。当美国队即将得分时，我走出了我的 Wi-Fi 覆盖范围，我的手机切换到了蜂窝连接。水流停顿了大约 15 秒钟才回来。我错过了目标！

随着有线连接上 Wi-Fi 的兴起，特别是电话的兴起，我们已经从一个我们与互联网的连接非常稳定的世界变成了一个我们可以进出连接的世界。我们的连接会丢失数据包，我们会定期在网络之间切换，中断我们接收数据的能力，无论是 Slack 上的新消息、与爱人的视频通话还是大型比赛中最重要的进球。如果这经常发生在你的用户身上，他们会去别的地方。HTTP/3 是正确的解决方案。

## 连通性和 HTTP/3 有什么关系？

为了回答这个问题，让我们深入了解一下为什么我没有看到这个目标。 [HTTP/3 是基于 QUIC](https://www.getambassador.io/kubernetes-learning-center/http3) (快速 UDP 互联网连接)，因此是 UDP，而不是传输控制协议(TCP)，TCP 的局限性是导致我的流媒体视频问题的原因。

1.  TCP 上的 HTTP/1.1 和 HTTP/2 都有行首阻塞问题，其中[“流中的一个丢失的包使所有流等待，直到该包被重新传输和接收](https://community.akamai.com/customers/s/article/How-does-HTTP-2-solve-the-Head-of-Line-blocking-HOL-issue?language=en_US#:~:text=HTTP%20Head%20of%20line%20blocking&text=HTTP%2F2%20(h2)%20solves,can%20arrive%20in%20any%20order)
2.  当客户端在使用传输层安全性(TLS)时与已知服务器重新连接时，TCP 连接具有冗余步骤(尽管这可以通过使用 TLS 1.3、[来避免，QUIC 采用了](https://www.linkedin.com/pulse/quic-tls-13-ivan-ristic/))。

所有这些问题都导致我的信息流被中断了很长时间，以至于我错过了这个动作。

HTTP/3 就是为了解决上述问题而设计的。它支持无序的数据包传递。连接可以多路传输数据流，因此传送所有 JavaScript 数据包的延迟不会阻碍 HTML、CSS 或流式视频数据包的传送 。当客户端通过 HTTP/3 与服务器重新连接时，它可以跳过 TLS 握手过程中的几个步骤，从而使该过程更快。HTTP/3 还有其他优点，可以提高用户的生活质量，比如改进的压缩和带宽使用优化。

## 太好了！我如何开始使用 HTTP/3？

今天对 HTTP/3 应用的投资就是对未来的投资。它仍然是尖端技术，支持有限。我以一个连接中断的例子开始的原因是，它是 HTTP/3 的“杀手级应用”如果你的用户有可靠的连接，或者你的网站或应用已经可以处理掉线，你可能现在不需要 HTTP/3。但是，如果需要对不可靠连接的高弹性来支持您的应用程序，那么现在投资是值得的。

### 哪里支持 HTTP/3？

三种主要浏览器中的两种、最受认可的移动应用程序语言、一些服务器端语言以及最大的内容交付网络都支持 HTTP/3。但是有一些警告。

### 客户端

您可以在[跟踪浏览器支持，我可以使用](https://caniuse.com/?search=http%2F3)吗？Chrome 和 Edge 等其他基于 chrome 的浏览器支持 HTTP/3，Firefox 和 Opera 也是如此，在桌面和移动上都是如此。然而，在撰写本文时，桌面和移动设备上的 Safari 只支持 HTTP/3 作为一个实验性特性，可以在开发工具中打开，让我们面对现实吧，您的用户并没有这样做。从 web 应用程序的角度来看，它对于企业应用程序来说是有希望的，因为在企业应用程序中，你可以保证用户会使用兼容的浏览器。当 Safari 提供支持时，现在内置支持也会让你在游戏中领先。

但是！我最初的例子涉及手机应用程序的流媒体视频，在应用程序中，你不需要依赖浏览器的支持。客户端库是为 [Swift](https://developer.apple.com/documentation/technotes/tn3102-http3-in-your-app) 、 [Kotlin](https://developer.android.com/guide/topics/connectivity/cronet) 和 [React Native](https://github.com/akshetpandey/react-native-cronet) 而存在的。现在，您可以在您的应用中为您的移动应用实现端到端的 HTTP/3 堆栈。

### 服务器端

在服务器端，有生产就绪的库，用于:

这个列表遗漏了一些主要的语言/框架，比如 Node.js，这些语言/框架的实现正在进行中。此外，那些生产就绪的库往往是较低级别的库，您的团队需要在其上构建。现在还没有 Spring Bean 自动神奇地添加 HTTP/3 支持。

### 基础设施

当然，客户端设备很少直接连接到您的服务器。它们之间有不同层次的网络技术。好消息是，CDN 和 WAF 领域的大多数供应商都有保持领先的强烈动机。 [Cloudflare](https://www.cloudflare.com/learning/performance/what-is-http3/) 、 [Fastly](https://docs.fastly.com/en/guides/enabling-http3-for-fastly-services) 、 [AWS CloudFront](https://aws.amazon.com/about-aws/whats-new/2022/08/amazon-cloudfront-supports-http-3-quic/) ，当然还有 [Google Cloud CDN](https://cloud.google.com/blog/products/networking/cloud-cdn-and-load-balancing-support-http3) (因为 Google 是 [QUIC](https://thenewstack.io/http-3-replaces-tcp-with-udp-to-boost-network-speed-reliability/) 的发源地)已经在一定程度上支持 HTTP/3。有警告；例如，Fastly 支持客户端使用 HTTP/3 连接到 Fastly，但不支持 Fastly 和您的源服务器之间的连接。

如果您运行的是传统的 web 服务器架构，有两个 web 服务器支持 HTTP/3:

如果您确实决定采用 HTTP/3，并且您碰巧运行在 Kubernetes 上(如果您对前者有足够的前瞻性，明智的选择是您正在做后者)，它确实支持 HTTP/3 连接。但是目前只有一个 Kubernetes-native API 网关支持 [HTTP/3](https://www.getambassador.io/docs/edge-stack/latest/topics/running/http3) : [使者入口](https://www.getambassador.io/products/api-gateway)及其付费版本[大使边缘栈](https://www.getambassador.io/products/edge-stack/api-gateway)。

## **总结一下**

[HTTP/3](https://blog.getambassador.io/benchmarking-http3-performance-envoy-proxy-and-edge-stack-96c37faac832) 是一项令人兴奋的新技术，它将解决我们不断变化的网络世界中出现的许多问题，其中包括更多的移动设备和更不稳定的连接，当我们从家里搬到地铁去工作和娱乐时，我们希望获得无缝、不间断的用户体验。HTTP/3 仍然处于早期阶段，有很大的成熟空间，但是如果您需要这些特性，您现在就可以开始采用它。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>