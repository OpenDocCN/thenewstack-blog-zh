# Scytale 推出基于 SPIFFE 的服务身份管理

> 原文：<https://thenewstack.io/scytale-launches-spiffe-based-service-identity-management/>

微服务尤其给 DevOps 团队带来了越来越大的挑战:单个组件如何识别和信任软件系统的其他部分。

这就是“斯皮夫”和“T2”项目的用武之地。

SPIFFE 代表面向所有人的安全生产身份框架，是一个用于跨微服务和服务器认证服务身份的开源框架。它使用 SPIRE (SPIFFE 运行时环境)作为处理身份的中央服务器。

SPIFFE/SPIRE 项目在去年 3 月成为了一个云本地计算基金会沙盒项目。

现在 [Scytale](https://www.scytale.io/) ，SPIFFE/SPIRE 项目的创始赞助商，正在推出 Scytale Enterprise，这是一个基于 SPIFFE/SPIRE 的基于云的订阅，旨在跨云、容器和内部基础设施标准化服务认证。

[Enterprise Management Associates](https://www.enterprisemanagement.com/)(EMA)的研究总监 [Steve Brasen](https://twitter.com/sbrasen?lang=en) 指出:“根据我们的研究，跨云和内部基础架构统一访问控制的需求是当今组织在负责任地交付业务服务方面面临的最大挑战。

他称赞了 Scytale 在复杂的混合 IT 生态系统中统一服务访问控制的方法。

“我们认为这是一个尚未解决的问题，也是一个越来越困难的挑战，”Scytale 的产品负责人 Andrew Jessup 说，他补充说，大多数身份管理系统专注于认证用户而不是相互服务。

“如果我是一家银行，我有一个移动应用程序，我可能会提供基于云的功能，但其他部分仍然使用我数据中心现有的基础架构和服务。我很少完全在云中或者完全在内部构建东西。当我谈到整体解决方案时，我指的是这些解决方案的组合。”

不仅仅是本地和云之间的服务相互对话，还包括多个云上的服务。还有一大堆来自中间件的问题。

“也许我让 Kubernetes 运行我系统的一部分。也许我有类似 Cloud Foundry 的 PaaS 系统。也许一个团队已经开发了自己的系统，”他说。

“我们有越来越多的这种独立服务。当我们谈论面向服务的架构和微服务时，我们不是在内存中传递数据结构，而是通过网络，通常是互联网传递信息。

当他们转移到云，他们发现他们有多个身份提供者，他补充说。对于运行在 Cloud Foundry 和 Azure 上的东西来说，向运行在 Kubernetes 和 AWS 上的东西安全地认证自己真的很难。这些东西根本不能一起工作。这些不同的系统之间没有信任桥梁。对于安全工程师来说，这是一个非常头疼的问题。"

Scytale 首席执行官 Sunil James 之前在《T2:新堆栈制作者》的一集里详细解释了 SPIFFE:

[Scytale 首席执行官 Sunil James 为您解读 SPIFFE](https://thenewstack.simplecast.com/episodes/sunil-james-ceo-of-scytale-explains-spiffe-for-you)

## **在 CNCF 沙盒里**

自从成为 CNCF 的一部分，更多的公司如优步、Pinterest 和 Square 都成为了积极的贡献者。

SPIRE 并不是 SPIFFE 的唯一实现。其他的是 Istio Citadel 和 Hashicorp Consul。SPIFFE 的消费者包括 Envoy proxy、Pinterest Knox 和 Ghosttunnel proxy。

SPIFFE 为服务 id 提供了一个标准。这些 SPIFFE IDs 和被实现为[统一资源标识符(URIs)](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier) 和一种标准，用于在被称为 SPIFFE 可验证身份文档或 SVID 的可加密验证的文档中对它们进行编码。它包括一个用于发布和/或检索 SVIDs 的 API 规范。

SPIRE，现在称为运行时实现而不是参考实现:

*   执行节点和工作负荷证明。
*   实现一个签名框架，用于安全地发布和更新 SVIDs。
*   提供一个 API 来注册节点和工作负载，以及它们指定的 SPIFFE IDs。

“如果您在数据中心的机器上或在 Kubernetes 的 pod 中有工作负载，我们有一种通用语言来以策略驱动的方式表达身份。Jessup 说:“它让我们摆脱了所谓的引导识别，即在部署应用程序时将密码嵌入其中。

它基本上可以识别一个软件系统。

“我们可以创建一个独立于它是否在亚马逊或其他地方运行的标识符。]我们可以在这种非常异构的环境中做到这一点。无论工作负载和身份在哪里运行，我们都可以创建一个通用的目录。

然后它与其他身份提供者集成。

“我们已经开始建立这种身份交换基础设施。手动实现这一点需要您拥有长期令牌……我们现在能够做的是使用 sidecar 服务器来允许工作负载在 OpenDirectory 或亚马逊 S3 之类的东西中交换短期身份。现在，我们能够做的是以一种非常精确和可审计的方式进行治理，确切地说是什么获得了什么身份以及围绕如何治理身份的策略。这种工作量需要一个短暂的凭证来访问亚马逊，将材料写入特定的 S3 桶或类似的东西，”他说。

这是一组非常特殊的特权。然后，它与另一个系统交互以提供该凭证。

“我们给不同身份的混乱带来了理智。他说，现在你可以在一个地方说，“告诉我这个工作负载是什么，它如何能够呈现给所有这些不同的系统。”

“我们还支持开发团队基于 Spiffee 和 Spire 构建自己的身份验证层。他们可以在这些身份的基础上构建更健壮的零信任架构。”

Scytale 还宣布了来自贝恩资本、Bessemer Ventures、TechOperators 和 Work-Bench 的 500 万美元投资。

该公司将在 RSA 2019 展位 103 展示 Scytale Enterprise。

云计算原生计算基金会是新堆栈的赞助商。

专题图片:[情人节设计(从克里斯·加德纳偷来)](https://www.flickr.com/photos/dumbledad/5445699010/in/photolist-9idCAf-nzxNpr-tnkMb-hQUT5t-eco3wo-4NKbGV-cxk7o1-drejcM-apuBhd-UdLJfN-GGMsqt-5ag6Rq-yEYi1-dWAvg1-d9FBDo-DTmfYe-c5UmXw-7Cz33p-b5u94n-dQUYMb-6tQTpA-bwNdRP-dXo477-h7xzTS-fCksV4-b8tAmk-VGnTfS-RzKUhx-7FrrDD-dPh7FC-2cQsRkr-2bEhYF6-cZn9dU-5jkUTM-8JEpmH-23iJWQY-9HZrUq-bjAnT3-bT9G3r-FMimd-SL6EuY-pDT2SE-wzu1by-9KJhEj-mw6r3j-9ig3oc-h7yLDp-8qAAwy-d4TaPm-2C1RyN)[蒂姆·瑞根](https://www.flickr.com/photos/dumbledad/)。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>