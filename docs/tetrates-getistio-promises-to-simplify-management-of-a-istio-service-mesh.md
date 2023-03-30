# Tetrate 的 GetIstio 承诺简化 Istio 服务网络的管理

> 原文：<https://thenewstack.io/tetrates-getistio-promises-to-simplify-management-of-a-istio-service-mesh/>

虽然开源的 Istio 可能有助于解决管理微服务和提供安全性的许多问题，但服务网格也带来了一些自己的问题，从安装期间的困难到处理第二天的操作，如升级和配置证书管理器。高级服务网格提供商 Tetrate 已经决定通过本月推出的 [GetIstio](https://www.tetrate.io/getistio/) 来解决这些困难，这是一个基于 Istio 和 [Envoy](https://www.envoyproxy.io/) 代理的商业服务网格。

首先，GetIstio 是上游 Istio 的开源发行版，可以帮助用户使用 GetIstio 命令行界面(CLI)轻松安装 Istio。它已经在亚马逊网络服务、Azure 云服务和谷歌 Kubernetes 引擎(GKE)上进行了测试。

该公司声称，当用户使用 GetIstio 安装 Istio 时，他们会得到一个强化的 Istio 映像，并得到持续的支持，更容易安装、管理和升级。“持续支持”的一部分来自于确保 Istio 保持运行，尽管对 Kubernetes 的升级可能会影响兼容性，Tetrate 首席执行官 Varun Talwar 解释道。

“问题是，这些不是静态项目，对吗？既不是 Kubernetes，也不是 Istio，也不是特使，”塔尔瓦说。“每三个月，您通常会从这些项目中获得新的版本，因此您想要给用户的信心是，如果您正在使用 GetIstio，那么我们会在您的环境中负责您的升级。”

随着 Istio 发布新版本，GetIstio 计划在几天内提供一个新版本，针对其三个受支持的云提供商进行测试，确保该版本也能与 Kubernetes 所有受支持的早期版本兼容。

塔尔瓦说:“即使最初的第 0 天没有问题，通常发生的情况是你升级了你的 Kubernetes，但有东西破坏了 Istio。”“那种痛苦是我们想要带走的。”

除了处理安装和升级之外，GetIstio CLI 还允许在多个版本的`istioctl`配置实用程序之间切换，通过使用大量云提供商证书管理系统创建 Istio CA 证书以签署服务网格管理的工作负载，帮助处理证书管理，并为最终用户提供符合[联邦信息处理系统](https://www.nist.gov/itl/publications-0/federal-information-processing-standards-fips) (FIPS)的 Istio 版本。

然而，安装和升级 Istio 并不是 Tetrate 用 GetIstio 瞄准的唯一目标。该公司还提供一个免费的自定进度课程，名为 [Learn Istio Fundamentals](https://certifications.tetrate.io/) ，这是该公司围绕建设社区而推出的更大努力的一部分，该公司表示，它希望将 Istio 和 Envoy 用户和技术合作伙伴聚集在一起，相互分享问题和解决方案。

Tetrate 的总经理 Prasad Radhakrishnan 解释说:“这是为了让与他们相关的其他产品能够与 Istio 建立集成，这样整个社区都可以受益。”“我们只是试图营造一种环境，让他们能够来与我们合作。如果有一个证书管理器或商店——一个产品和供应商——他们想参与 Istio 生态系统，我们如何引导他们？我们如何帮助他们？是的，有一组文档和一个可用的 API，但是我们能在这里做些什么来加速他们的集成工作吗？”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>