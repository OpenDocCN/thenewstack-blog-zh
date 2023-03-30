# JFrog 面向开发者的私有分发网络

> 原文：<https://thenewstack.io/jfrogs-private-distribution-network-aims-to-accelerate-software-updates-at-scale/>

DevOps 平台提供商 [JFrog](https://jfrog.com/?utm_content=inline-mention) 将其新的[专用分发网络(PDN)](https://thenewstack.io/jfrog-intros-private-distribution-network-offering/) 吹捧为“行业第一”，因为它允许 DevOps 团队通过结合两种网络加速和优化技术的轻量级解决方案来加速应用程序更新— [点对点(P2P)和内容交付网络(CDNs)](https://jfrog.com/solution-sheet/jfrog-artifactory-cdn-distribution-and-peer-to-peer-download) 。

该公司表示，PDN 可以在跨多个节点和地理位置的任何基础设施或设备上部署，使任何基础设施节点都成为分发节点，具有急切缓存(带 CDN)的能力，并支持大量并发下载(得益于安全的 P2P“分块”技术)。JFrog 声称没有其他供应商以这种方式提供这些功能。

该公司表示，PDN 帮助团队同时更新大量高度分散且通常不同拓扑结构和设备类型的软件。其中包括物联网、边缘、多云以及更传统的内部数据中心环境。

换句话说，JFrog 对其 PDN 的雄心是，它不仅仅是 DevOps 团队的另一个内容分发网络(CDN)和/或 P2P 解决方案。它旨在解决 DevOps 团队面临的一个常见问题:难以在跨大型混合基础架构或设备的不同地理区域部署软件更新，复杂的网络拓扑跨越 LAN(专用网络)和 WAN(公共网络)。

作为“世界上第一个混合私有分发网络，或 PDN”，[JFrog 的首席技术官和联合创始人 Yoav Landman](https://il.linkedin.com/in/yoavlandman) ，在 JFrog 的[swamp 用户大会](https://thenewstack.io/jfrog-platform-crypto-signs-binaries-for-secure-software-lifecycle-management/)上把 PDN 描述为“一个连接到边缘的级联盒子组的设置”

例如，通过将 PDN 用于欧洲和美国的基础设施或设备组，DevOps 团队可以构建自己的拓扑来加速跨分发组的软件更新。Landman 说:“每个 PDN 节点都像一个轻量级远程缓存，我们将节点分组排列，以便突破单机网络容量。”

## PDN 的使用案例

DevOps 团队的最终目标是以更快的速度安全地部署和更新软件，并能够快速修复和回滚对应用程序代码的更改，而不会影响应用程序的性能。在这种背景下，[企业管理协会](https://www.enterprisemanagement.com/)的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉 New Stack，PDN 旨在帮助缩短开发人员完成代码更新的时间，最终使最终用户受益。

“消除边缘的基础设施瓶颈限制了更新的频繁和可靠的代码分发，因此直接有助于开发团队的生产力，”Volk 说。

实际上，PDN 允许开发团队将更新推送到许多不同的设备上，而不考虑节点的位置。

兰德曼说，一个典型的用例是企业依赖 PDN 来更新工厂车间运行的应用程序，如机器人控制的设备或内部传感器或其他设备，这些设备由于安全、专有信息、监管或其他原因不会暴露在公共网络中。

PDN 会自动为您在这些环境中分发软件，并提供自动重试、粒度可见性以及交易失败时的通知。他说。因此，如果您的软件包含需要一起借出的文件，您不希望您的更新中途崩溃，因为您的本地缓存没有全部内容

## 棘手问题

大约两年前，在通过向 JFrog 的平台添加边缘节点来扩展分发功能之后，Landman 描述了客户如何开始要求该公司扩展它，并建立覆盖不同基础设施的拓扑结构，并扩展到低占用空间的设备和物联网，同时保持高可用性、快速和安全。

兰德曼说，客户需要同时发布所有节点和拓扑更新的能力，“以了解所有设备实际部署了什么，并具有完全的可见性，这非常令人兴奋”。这条路导致了 PDN 的建立。

JFrog 的 PDN 建立在该公司与二进制运算符(BinOps)的合作基础上，能够加速阻碍软件分发和软件更新的网络操作。Landman 说，一个可行的 BinOps 还必须提供包意识，以便于开发运维团队发布软件更新等。

JFrog 的 [Artifactory Edge](https://www.jfrog.com/confluence/display/JFROG/JFrog+Artifactory+Edge) 功能支持 BinOps，因此应用程序保持编译、打包和完全可访问。兰德曼说，二进制存储库访问仍然可用，“直到你需要把它推到分布式边缘位置的运行时”。" PDN 为软件更新提供了每一个二进制流的完整血统."

维护和扩展对不同位置和设备的更新访问应该有助于简化开发团队的工作。英国分析师 [Clive Longbottom](https://www.linkedin.com/in/clivelongbottom/?originalSubdomain=uk) 说，开发人员经常不得不为不同的更新和拓扑结构重新架构和打包代码。

DevOps 团队成员可以访问可能由 Docker 容器映像或用 Python 或 JavaScript 编写的应用程序组成的二进制存储库，以便应用程序可以在各种设备类型和地理位置上实时更新。同时，从一开始就对代码进行漏洞扫描，并且在代码更新后继续扫描。

Longbottom 指出，这种扫描能力在内容分发平台中经常缺失，更不用说提供内容分发和 P2P 的平台了。“这方面最大的积极因素是当我们进入物联网时:通过这样的 P2P 网络从中心点快速获得更新和新功能的能力，以及支持边缘功能开发以解决每个设备层面上高度具体的问题的能力，将非常有用，”他说。

## 新的因素

IDC 分析师[Jim Mercer](https://www.idc.com/)说【JFrog 的 PDN 可能在某些方面有助于加强安全性，因为它有内置的安全检查来验证工厂客户。分发的内容在静态下是不可变的，因此在传输过程中受到数字签名的保护，例如使用 [GNU 隐私保护(GPG)](https://gnupg.org/) 。Mercer 表示，下载受到自动生成的下载令牌的保护，分发节点之间使用 MTLS 认证。

“最后，由于 PDN 允许你使用你的网络环境，它更多地由用户控制，而不需要通过第三方，”他说。

Volk 说，如果 JFrog 的 PDN 像它声称的那样工作，并且能够满足 DevOps 团队对软件更新可能存在的安全问题，它可以帮助 DevOps 团队将更多的资源集中在开发和完善新产品和新功能上。

“滚动并持续保护和优化您自己的软件更新分发平台应被视为开销，最好由外部方提供，他们自己也将提供尽可能最好的分发平台视为其核心价值主张。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>