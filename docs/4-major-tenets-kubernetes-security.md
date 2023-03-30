# Kubernetes 安全性的 4 个主要原则

> 原文：<https://thenewstack.io/4-major-tenets-kubernetes-security/>

[](https://www.paloaltonetworks.com/prisma/cloud)

 [王晨曦博士

王晨曦博士是网络安全战略咨询公司简·邦德项目的创始人。网络安全行业知名战略家、演说家、作家。Wang 博士还担任 OWASP 基金会董事会副主席，ClearSky security 和 630 Cyber 的投资顾问，以及各种安全初创公司和 IT Security Planet 的战略顾问。此前，陈曦是 Twistlock 的首席战略官，负责将 Twistlock 的品牌和业务从零发展到细分市场的领导者。](https://www.paloaltonetworks.com/prisma/cloud) [](https://www.paloaltonetworks.com/prisma/cloud)

在上一篇文章中，我们了解了 Kubernetes 部署面临的[威胁](https://thenewstack.io/4-threat-models-for-kubernetes-deployment-security/)，这些威胁可能会导致大量危害和不良场景。考虑到这些威胁模型，我们现在可以沿着四个主要原则探索 Kubernetes 的安全性:

*   认证和授权
*   资源隔离
*   强化和网络安全
*   日志记录和审计。

我们从容器、Kubernetes 部署本身和网络安全的角度来看待安全性。需要这样一种整体方法来确保安全地部署容器，并最大限度地减少攻击面。从上述原则中产生的最佳实践适用于任何 Kubernetes 部署，无论您是自托管集群还是使用托管服务。

我们应该注意的是，Kubernetes 之外还有相关的安全控制，例如安全软件开发生命周期(S-SDLC)或安全监控，它们可以帮助降低攻击的可能性并增强防御态势。我们强烈建议您考虑整个应用程序生命周期的安全性，而不是狭隘地关注使用 Kubernetes 部署容器。然而，为了简洁起见，在本系列中，我们将只讨论 Kubernetes 环境中的安全控制。

### 认证和授权

Kubernetes APIs 是管理员、用户和应用程序在 Kubernetes 环境中操作和通信的中央界面。用户和服务帐户都可以访问 Kubernetes APIs 来启动操作。因此，控制 API 访问是 Kubernetes 中身份验证和授权的主要任务。

[cyclone slider id = " kubernetes-series-book-2-赞助商"]

Kubernetes 平台具有内置的身份验证和授权控制以及准入控制，这些控制在身份验证和授权之后拦截和管理对 Kubernetes APIs 的请求。准入控制包括内置的构造以及启用 webhook 的方法，可用于调用外部逻辑。

身份验证和授权是 Kubernetes 安全性的核心。因此，保护对 Kubernetes API 服务器的访问是安全的 Kubernetes 环境的首要任务之一。在本章的后面，我们将深入探讨身份验证和授权选项和策略。

### 资源隔离

资源隔离是 Kubernetes 中的另一个主要安全措施。隔离不仅可以防止拒绝服务攻击，还可以提供隐私和数据保护。Kubernetes 平台为许多资源类型提供了隔离机制，包括 pod 和名称空间。您可以对 pod 和命名空间设置的资源限制包括中央处理器(CPU)周期、内存请求和持久存储空间。

### 强化和网络安全

环境强化，包括容器和底层 Kubernetes 基础设施的强化，对于 Kubernetes 环境的安全性至关重要。它有助于抵御由受损容器、误用和错误配置带来的威胁。

强化操作包括对运行特权容器的限制、限制特权升级以及容器是否可以访问主机网络接口和文件系统。

网络安全处理分段，通过传输层安全(TLS)客户端身份验证保护 API 访问，并管理服务网络访问控制列表(ACL)。

[cyclone slider id = " kubernetes-series-book-2-赞助商"]

### 日志记录和审核

除了本地应用程序和系统日志记录之外，拥有特定于 Kubernetes 的日志对于理解 Kubernetes 操作可能是有益的，比如谁访问了哪个 Kubernetes API。

Kubernetes 1.9 提供了一个测试特性——审计日志——来执行单独的日志和审计功能。审计日志记录记录 API 采取的操作。然后可以将记录存档，以供以后分析。管理员可以通过指定审计策略 YAML 文件来指定应该记录哪些事件。

下一次，我们将讨论容器基础设施本身的相关安全问题，包括以安全的方式运行容器，正确配置和加固每个 Linux 节点，主动管理系统中使用的映像以发现和消除已知的漏洞，以及管理您的组织可以使用哪些注册表。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>