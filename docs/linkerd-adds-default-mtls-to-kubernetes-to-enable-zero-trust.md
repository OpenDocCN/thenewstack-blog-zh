# Linkerd 将默认 MTL 添加到 Kubernetes 以实现零信任

> 原文：<https://thenewstack.io/linkerd-adds-default-mtls-to-kubernetes-to-enable-zero-trust/>

开源服务网格 Linkerd 已经更新了许多新功能，包括支持 ARM 架构、新的多核代理运行时，以及自动启用所有 TCP 连接的相互 TLS (mTLS)安全性。

[Linkerd](https://linkerd.io/) 背后的公司[浮力](https://buoyant.io/)的首席执行官威廉·摩根说，零配置 mTLS 是 Linkerd 关注 Kubernetes 的[零信任安全](https://thenewstack.io/how-to-start-applying-googles-zero-trust-model/)的一大进步，它处理了许多复杂性，否则可能是不安全行为的原因。

“安全是这样一种东西，当你把它变得复杂和难以实施时，人们就不会去做了。摩根说:“你制造的东西越复杂，它就越不安全，这是人的本性。”

虽然 Linkerd 现在已经有了几个版本的 MTL，但它只适用于 HTTP 和 gRPC。有了 Linkerd 2.9，这将扩展到所有的 TCP 连接，Morgan 指出，有许多软件超越了这两种协议，尤其是当你在构建一个内部应用程序时。

“Linkerd 的独特之处在于，我们不需要用户进行任何配置，默认情况下是开启的。从您启用 Linkerd 的那一刻起，我们就负责所有的证书管理、轮换、身份供应等工作，”Morgan 说。“这真的很复杂，因为理想情况下，您希望定期轮换这些证书。做这种类型的证书管理是困难的部分。您希望以映射到您的 Kubernetes 基础设施等的方式将这些证书与服务身份联系起来。”

这种零配置、自动启用的 mTLS 只是 Linkerd 对 Kubernetes 的零信任安全方法的开始，Morgan 说，FIPS 合规性和 Kubernetes 政策是下一个需要解决的领域。

Linkerd 2.9 带来的另一个关键变化是多核代理运行时，这将允许 Linkerd 处理更高的流量情况。与其他服务网格不同，Linkerd 使用自己的代理 Linkerd2-proxy 运行，这是一个专门用于此目的的“微代理”内置 Rust。

“我们称之为微代理的原因是，它实际上只是为这一种使用情形而设计的；我们可以摆脱各种各样的复杂性，处理许多其他方式的代理可以做的，只关注这一点。结果是，运行这些代理的运营开销实际上非常非常小，所以用户很少接触到代理，它们只是工作，不需要调整、配置和调整，并且有大约 10，000 行 YAML 文件，”摩根说。“这款 Linkerd2-proxy 微代理速度如此之快，重量如此之轻，以至于我们实际上只需一个单核架构就可以升级到 Linkerd 2.8。”

在此版本中，Linkerd 将获得更大的吞吐量和单个单元的并发性，并能够扩展到多个内核。该项目将在不久的将来为此发布新的基准。

最后，Linkerd 2.9 增加了 ARM64 支持，使其可以在 Raspberry Pi 等设备上运行，也可以在基于 ARM 的计算上运行，如 [AWS Graviton](https://aws.amazon.com/ec2/graviton/) ，对 Kubernetes 新服务拓扑功能的支持将再次提高运营效率，并能够决定路由偏好。

在[完整发布说明](https://github.com/linkerd/linkerd2/releases/tag/stable-2.9.0)中可以找到 Linkerd 改进、性能增强和错误修复的完整摘要。

由 [Ralf Skirr](https://unsplash.com/@ralfskirr?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/s/photos/trust?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>