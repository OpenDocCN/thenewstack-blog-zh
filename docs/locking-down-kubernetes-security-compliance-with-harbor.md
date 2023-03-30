# 锁定 Kubernetes 安全性，遵从 Harbor

> 原文：<https://thenewstack.io/locking-down-kubernetes-security-compliance-with-harbor/>

[https://www.youtube.com/embed/VOQG8w5bJxc?feature=oembed](https://www.youtube.com/embed/VOQG8w5bJxc?feature=oembed)

视频

利用微服务和 Kubernetes 提供的巨大资源节约和扩展机会的热潮并非没有挑战。首先，云原生计算和 Kubernetes 并不适合所有人，因为许多组织，尤其是较小的组织，通常[缺乏投资能力和需求来将](/a-google-engineer-on-when-an-sre-and-kubernetes-are-and-not-worth-it/)部署和运营扩展到 Kubernetes 设计的特定规模。

此外，一些企业可能会发现，如果没有一系列新的安全挑战，这种转变就不会到来，最新的 [Docker 漏洞](https://thenewstack.io/the-docker-hub-hack-the-quick-fix-and-the-long-term-questions/)就是一个例子。

[VMware](https://www.vmware.com/) 的产品管理总监 [Michael Michael](https://www.linkedin.com/in/mimichael) 在新堆栈演示期间表示，对于组织来说，在将映像部署到 Kubernetes 等平台上进行生产之前，可能开始保护映像的一种方法是将 Harbor 添加到他们的 DevOps 工具列表中。

一个在代码部署前作为安全注册表的安全工具也被认为是 Kubernetes 开发人员的优势，他们可能会犯“快速和经常失败”的错误，这是他们工作风格的一部分。“在这个云原生世界里，开发者的权力更大，对吗？无论是通过 Kubernetes 还是其他管弦乐队，他们都获得了更多的能力，他们可以以一种更加自由流动的方式将事情推向生产，”迈克尔说。“这就是安全性和合规性需求的来源，也是 Harbor 在这里如此重要的原因。”

迈克尔说，作为一个企业级注册中心，它是一个开源项目，已捐赠给云原生计算基金会(Cloud Native Computing Foundation)，该基金会也处于孵化阶段，Harbor 是“保护云原生资产的一个非常重要的难题”。“因此，随着越来越多的企业和用户转向云原生技术，如 Docker 和 Kubernetes，他们已经看到他们正在构建所有这些云原生应用程序，并将它们推向某种形式的存储库，”迈克尔说。“但是没有很多流程和政策来确保企业获得生产类型工作负载所需的安全性和合规性。”

Michael 在他的演示中描述并展示了 Harbor 作为一个开源云原生注册表是如何“存储、签名和扫描容器图像以发现漏洞的”“我们的使命，作为一个社区和 VMware 作为 Harbor 的最大贡献者，是为用户提供补充管理和分类容器映像的能力，”Michael 说。“如果您从一家企业创建了一组包含您的应用程序或微服务的工件，我希望您能够说，‘我是合规的，我相信部署的任何东西都是正确的，或者是我推送的相同映像。’"

Michael 在演示期间展示的功能包括如何启用内容信任、漏洞静态分析以及开发一个策略来指导用户如何根据环境管理容器。被利用。政策指标包括“谁被允许下载容器，或者这些容器中是否有任何使它们易受攻击的 CVE，”Michael 说。Michael 还展示了 Harbor 如何用于内容签名和验证。

迈克尔还展示了 Harbor 与公证人集成的可信内容服务如何帮助确保签名和围绕图像的证书管理，以及漏洞扫描如何使用 Red Hat 的 [Clair](https://coreos.com/clair/) 扫描 Docker 图像的不同层，“以确保没有简历出现，并为您提供他们发现的所有内容的良好目录，”迈克尔说。

“因此，在一切的基础上，我们将有本地或远程存储。因此，您可以在运行 Harbor 的节点上使用本地存储，或者您可以使用 S3 兼容存储或任何其他您想要的块文件对象存储，以便您有一个非常可靠和有弹性的存储库来托管您的映像，”Michael 说。

云计算原生计算基金会、Red Hat 和 VMware 是新体系的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>