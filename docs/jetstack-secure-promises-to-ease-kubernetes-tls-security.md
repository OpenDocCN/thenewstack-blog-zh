# Jetstack Secure 承诺减轻 Kubernetes TLS 的安全性

> 原文：<https://thenewstack.io/jetstack-secure-promises-to-ease-kubernetes-tls-security/>

要保护几乎所有东西，最简单的方法之一就是让网络连接更容易使用 TLS(传输层安全性)。对于 [Kubernetes](https://kubernetes.io/) ，这意味着使用[证书管理器](https://cert-manager.io/)。现在，该项目的母公司， [Jetstack](https://www.jetstack.io/) ，一家 Kubernetes 产品和服务提供商，与 [Venafi](https://www.venafi.com/) 合作，推出了 [Jetstack Secure](https://www.jetstack.io/jetstack-secure/) ，这是一款基于 cert-manager 的全自动机器身份管理软件，适用于 Kubernetes 和 [Red Hat OpenShift](https://www.openshift.com/) 。

Cert-manager 是一个开源的本机 [TLS x.509](https://www.venafi.com/blog/what-ssltls-x509-certificate) 机器身份/证书管理程序。它和 Jetstack Secure 支持[自动证书管理环境(ACME)](https://www.thesslstore.com/blog/acme-protocol-what-it-is-and-how-it-works/) 兼容的证书颁发机构(CAs)，例如 [Let's Encrypt](https://letsencrypt.org/) 、 [HashiCorp Vault](https://www.vaultproject.io/) 、[维纳菲](https://www.venafi.com/)，以及跨[服务网格](https://thenewstack.io/category/service-mesh/)使用 [mTLS](https://wott.io/blog/tutorials/2019/09/09/what-is-mtls) 的自签名私有内部证书。它还支持[谷歌证书授权服务(CAS)](https://cloud.google.com/certificate-authority-service) 。该程序通过使用 Kubernetes 的内置自定义资源定义来扩展 Kubernetes API 来实现这一点。

虽然 cert-manager 仍然是一个[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)沙盒程序，有着三年的历史，但它非常有用。

Jetstack Secure 提供基于 web 的管理界面和直接来自项目团队的企业级支持。除了为服务器实例提供 TLS 安全性之外，它还跨多个集群和云构建了容器和服务器的详细视图。

眨两次眼睛，Kubernetes 集群中的情况就会发生变化，但其制造商向用户保证，Jetstack Secure 是为了在快节奏、快速发展的 Kubernetes 和 OpenShift 环境中运行而构建的，它可以使用 Kubernetes 资源轻松部署，包括一个开源代理，该代理由 Jetstack 管理的可靠且可扩展的 SaaS 提供支持。您可以将其界面设置为在单个集群上免费运行，并且客户可以升级高级多集群和警报功能。

这个项目很有必要。正如 Jetstack 首席技术官兼联合创始人 Matt Bates 在一份声明中所说，“我们从与客户的合作中直接看到，采用云原生技术和现代微服务架构非常迅速地导致 TLS 证书的显著增长——从入口 TLS 到内部服务 mTLS、Kubernetes webhooks 等等。”因此，“随着基础架构的扩展和集群的积累，需要非常高的自动化水平来确保证书一致并保持最新。”

“借助 Jetstack Secure，”Bates 总结道，“我们的客户可以看到每个集群的详细视图以及所有工作负载证书的即时可视化状态，包括它们与 Kubernetes 资源的关联。至关重要的是，它将识别并帮助缓解可能导致运营或安全风险的问题。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>