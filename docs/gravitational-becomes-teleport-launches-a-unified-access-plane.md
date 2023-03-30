# 引力变成了瞬间移动，发射了一个统一的访问平面

> 原文：<https://thenewstack.io/gravitational-becomes-teleport-launches-a-unified-access-plane/>

[蜂巢](https://www.honeycomb.io/)赞助了新栈对 Kubecon+CloudNativeCon 北美 2020 的报道。

万有引力不复存在。这家总部位于奥克兰的公司专注于“无环境”计算，正更名为[传送](https://gravitational.com/)，这是其最初的安全服务器访问产品的名称。

据首席执行官兼联合创始人 [Ev Kontsevoy](https://github.com/kontsevoy) 称，人们就是这样记住这家公司的。

在本周举行的 KubeCon+CloudNativeCon 大会上，该公司还推出了 Teleport 统一接入平台，该平台承诺在网络地址转换(NAT)的支持下，为所有环境中的所有计算资源(如服务器、Kubernetes 集群或内部应用程序)提供单点接入，无论其位于何处。

“我们相信，现在我们正在进入云成熟阶段，在这个阶段，大多数新项目……都建立在云之上，这是一等公民。对于大多数组织来说，这不再是一个次要项目，”Kontsevoy 说。“所以云是默认了。其他主机外形只是对其的补充。

“大多数组织都在使用多种云。因此，我们认为开发者应该把我们居住的整个地球看作一台巨大的计算机。因为现在，每个开发者都需要记住，‘哦，我们在亚马逊上运行这个，我们在 Azure 上运行这个。’信不信由你，组织有数百个 AWS 帐户，他们在不同的项目之间周旋。…

“因此，我们认为计算环境的这种碎片化绝对会扼杀生产力。我们的客户和 Teleport 的用户都同意这一点，但安全人员也很担心，因为在过去，您必须保护一个数据中心。但是现在，一般的组织都使用多个云，在每个地方都有数百个帐户。您如何保护所有这些信息？”

他说，Teleport 通过创造该公司所谓的无环境计算解决了这一问题，在无环境计算中，一切都是一台巨大的计算机，以一种统一的方式访问一切。

Teleport Unified Access Plane 是开源的，依赖于 SSH、HTTPS、SAML、OpenID Connect 等开放标准。它被部署为 OpenSSH 的单二进制插件替代品。

通过单点登录和短期证书，它消除了管理共享机密或 SSH 密钥的需要。它集成了所有企业和社区 SSO 提供商，包括 GitHub、Okta、Active Directory、Google 等。

据该公司称，它使用户能够看到世界任何地方所有环境中任何基础设施上的所有服务器、Kubernetes 集群、内部应用程序、数据库，甚至实时会话。此外，它还提供了对所有环境中谁在访问每项资源以及他们在做什么的可见性。此外，用户可以邀请同事进行协作，提供会话记录和审计日志。

该公司以前提供服务器访问和 Kubernetes 访问，但作为 Teleport 5.0 的一部分，增加了应用程序访问。

“如果您想要访问内部应用程序，例如 Grafana 仪表板、Kubernetes 仪表板，可能是您正在构建的一些内部仪表板，可能是 Jenkins 实例、CI/CD 管道、每个生产环境、每个云，人们会在其上运行许多内部工具。但是如果你想访问它们，那么你需要暴露它们。你需要有一个公共 IP 地址，你需要有一个域名，你需要有一个 SSL 证书，你需要有认证和用户名和密码，”Kontsevoy 说。

“所以事实上，要揭露所有这些事情需要做大量的工作。Teleport 应用程序访问会自动完成所有这些工作。”

他说，除了生产率的提高，第二个好处是对安全团队而言。它还使用户能够改造现有应用并集成定制应用，以符合 SOC2、PCI 和 FEDRamp 等安全标准，而无需修改。

“这意味着他们现在可以为其传统应用程序实现 FedRAMP 合规性等功能。因为如果您希望您的生产环境符合 FedRAMP，保护您自己的代码是不够的。你还需要确保像詹金斯和其他东西有相关的访问控制。而传送会自动给你这些，”他说。

Teleport 提供了一个加密的审计日志，即使现有的应用程序不提供它。

传送应用程序访问是传送 5.0 的两个新功能之一。另一个是托管云服务，可从其网站上获得。

作为为公司创造一台巨型计算机的愿景的一部分，它正在研究其他形式的访问，如数据库和桌面。它有一个名为 [Teleconsole](https://github.com/gravitational/teleconsole) 的预览版，允许用户通过命令行使用 SSH 或使用 HTTPS 浏览器与可信的人共享终端会话。

KubeCon+CloudNativeCon 是新堆栈的赞助商。

图片由来自 Pixabay 的 Gerd Altmann 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>