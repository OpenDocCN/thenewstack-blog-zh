# 红帽的 Keycloak 身份访问管理投标加入 CNCF

> 原文：<https://thenewstack.io/red-hats-keycloak-identity-access-management-bids-to-join-cncf/>

开源的 [Keycloak](https://www.keycloak.org/) 是一个主要由 Red Hat 开发的身份访问管理(IAM)项目，该项目已经获得了[的广泛采用](https://github.com/cncf/toc/pull/405#issuecomment-624043670)，但该项目仍在朝着一个目标努力，因为它自 2018 年秋季以来一直在努力——被[云原生计算基金会(CNCF)](https://www.cncf.io/) 采用。

[https://www.youtube.com/embed/Qr2PZkpBpwo](https://www.youtube.com/embed/Qr2PZkpBpwo)

视频

在加入 CNCF 的第一次投标中，该项目着眼于成为潜在的孵化级项目，而不是沙盒级项目，但投标不符合要求。现在，该项目再次[申请](https://github.com/cncf/toc/pull/405)加入沙盒级别的 CNCF，并一直稳步获得博世、思科、日立等用户的支持。当该项目于 2014 年首次发布稳定版本时，它首先瞄准了一个主要问题——许多开发人员难以轻松地为他们的应用程序添加安全性。

“只是有一种普遍的感觉，身份和访问管理太难了，太贵了，而且对开发者不友好。如果您正在构建一个云原生应用程序，来连接安全位以完成诸如单点登录之类的复杂事情，这实际上是相当困难的。所以，几个 Red Hat 开发人员集思广益，基本上构想出了这个名为 Keycloak 的项目，”Red Hat 产品管理高级主管 Rich Sharples 在一次采访中解释道。“如果您正在构建一个现代应用程序，构建社交登录和联合安全等功能，并与 active directory 或 LDAP 等后端集成，实际上仍然非常困难。这是你真正需要做好的事情。”

[https://www.youtube.com/embed/GZTN_VXjoQw?feature=oembed](https://www.youtube.com/embed/GZTN_VXjoQw?feature=oembed)

视频

从本质上讲，这确实是 Keycloak 项目的核心——无论您的应用程序在哪里运行，都可以轻松地对其进行安全认证，并提供单点登录、用户联盟、身份代理和社交登录等功能，以及一个管理控制台来配置一切。Keycloak 可以在传统和容器化的环境中运行，并以一种不管应用程序的架构或运行的基础设施如何都可以工作的方式抽象出身份验证。用户(或微服务)不是通过应用程序本身登录或退出，而是通过 Keycloak 进行身份验证，根据该项目网站的说法，这意味着“您的应用程序不必处理登录表单、验证用户和存储用户。”虽然容器化的应用程序可能难以处理状态，但 Sharples 指出,“这是 Keycloak 要解决的问题，而不是你的应用程序。你不需要担心州政府，我们会处理好的。”

根据 Sharples 的说法，该项目从早期开始就把在容器化环境中运行作为重点，Red Hat OpenShift 是一个明显的目标。

Sharples 表示:“围绕云原生开发和微服务有一系列使用案例，在这些案例中，您实际保护的是单个微服务以及微服务之间的交互。“在其他解决方案过于沉重的情况下，Keycloak 的设计总是考虑到云，并考虑到运行 OpenShift。它很容易就能装进集装箱里。”

这种对云原生开发的关注是 Kubernetes 的创建者和 CNCF 技术监督委员会(TOC)的贡献者 [Joe Beda](https://www.linkedin.com/in/jbeda) 在该项目第一次尝试加入 CNCF 期间对[问题](https://github.com/cncf/toc/pull/176#issuecomment-507738695)的关注。根据 Beda 的说法，该项目“不像 CNCF 的许多其他项目那样感觉像‘云本地’”，因为安装说明“明显倾向于更传统的环境”并且“与 Red Hat 商业产品集绑定”当时，红帽高级经理 [Boleslaw Dawidowicz](https://www.linkedin.com/in/boleslawdawidowicz/) ，一直在处理 Keycloak 的 CNCF 申请过程，认为这个问题更多的是一个文件而不是现实，指向一个超过 1000 万次点击的 [Docker 图像](https://hub.docker.com/r/jboss/keycloak/)。关于治理和外部贡献者，Dawidowicz 当时指出，大多数代码不是由 Red Hat 员工贡献的，并且“治理模型将会改变，更多的非 Red Hat 维护者将会跟进，尽管我希望从我们的社区渠道来看，这一领域的道路是可见和清晰的。”

最近，该项目见证了 Keycloak 10.0.1 的[发布，此前](https://www.keycloak.org/2020/05/keycloak-1001-released)[宣布](https://www.keycloak.org/2019/10/keycloak-x)将专注于构建一个“更精简、更简单、更经得起未来考验”的版本，名为 Keycloak.X。通过这个新的、尚未发布的 Keycloak 版本，该项目希望通过增加对零停机升级和连续交付的支持，使其更容易配置、扩展和扩展。除了“新的和改进的存储层”，Keycloak。x 还希望提供一个“由 [Quarkus](https://quarkus.io/) 支持的新发行版”，这是一个开源的 Kubernetes-Native Java 框架，为 Java 虚拟机量身定制，也由 Red Hat 提供支持。

虽然钥匙卡住了。x 是去年秋天宣布的，Sharples 说，疫情在这个过程中遇到了一点困难，并指出“我们的重点肯定是不同的，将产品推向市场可能不是目前的最高优先级，帮助现有客户解决他们正在处理的问题才是我们真正关注的。”

至于该项目加入 CNCF 的申请，这一过程正在进行中，个人用户和供应商提供支持性的遗嘱。最近的投标是在三月底由[发起的](https://github.com/cncf/toc/pull/405)，这一次的重点是在沙盒级别的加入，Dawidowicz [写道](https://github.com/cncf/toc/pull/405#issuecomment-607096865)“我相信这是一个足够成熟的项目，足以匹配孵化。尽管从过去的经验来看，我倾向于避免这一方面使讨论脱轨，并对适用的标准产生疑问。”

云计算原生计算基金会和 Red Hat 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>