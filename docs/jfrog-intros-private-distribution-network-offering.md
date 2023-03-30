# JFrog 推出专用分销网络产品

> 原文：<https://thenewstack.io/jfrog-intros-private-distribution-network-offering/>

DevOps 平台提供商 [JFrog](https://jfrog.com/) 推出了业内首个私有分发网络，使企业能够建立和管理自己的安全、可扩展的混合分发网络来进行软件更新。

[JFrog](https://thenewstack.io/jfrog-its-a-liquid-world-and-developers-are-the-rainmakers/)Private Distribution Network(PDN)提供了两种集成的网络加速技术——基于 HTTP、安全的 [P2P 和 CDN](https://jfrog.com/solution-sheet/jfrog-artifactory-cdn-distribution-and-peer-to-peer-downloads/)——可以在混合基础设施和多层、可定制的网络拓扑中部署。JFrog 的首席技术官和联合创始人 Yoav Landman 在接受 New Stack 采访时表示，它们是以基于使用的价格作为服务进行管理的。

JFrog 将该技术作为 JFrog 发行版的一项新功能引入，这是 JFrog [DevOps 平台](https://jfrog.com/platform/)的一部分。该公司在本周的用户大会上首次推出了 PDN。它目前作为[私有测试版](https://jfrog.com/distribution-network)提供，并将在今年第三季度更广泛地提供。

“我们允许您为软件交付创建自己的内容分发网络。它是完全保密的，而且是安全的，”兰德曼说。“您可以在任何商用硬件上构建分层拓扑。在每个节点之间，我们使用对等网络来实现高可用性。”

兰德曼表示，PDN 将使企业能够在更接近客户的地方运行软件，以提供最佳的数字体验，因为企业范围必须跨越云和多云环境，以及边缘和嵌入式设备。

该公司在一份声明中表示，该公司的新 PDN 还可以帮助企业将软件分发速度提高多个数量级，以加快数万个环境、边缘和嵌入式或物联网设备之间的应用程序更新和二进制文件并发下载的部署。

JFrog 的产品通过使用数十或数百个轻量级分布节点克服了网络限制。它使用基于 HTTPs 的定制 P2P 协议来实现内容的高可用性。

兰德曼在一份声明中说:“那些努力将应用程序交付到更接近消费者边缘的地方，在大规模运行时环境或物联网车队中推出版本的企业，现在可以通过私有分发网络轻松加速和扩展，以满足他们的分发需求，使软件的消费尽可能快，并具有完整的可追溯性和控制力，从任何来源到任何部署目标。”

### 基于现有能力

同时，关于 JFrog 是否是第一个拥有这种能力的，一位专家并不确定。 [Gartner](https://www.gartner.com/) 的分析师 [Dan Wilson](https://www.linkedin.com/in/danmwilson/) 表示:“完全集成的【PDN】功能在技术上可能是行业首创，但在概念上，这种功能已经作为基于 SaaS 的终端管理工具存在，包括或可以与 cdn 集成。

Wilson 引用了 [Adaptiva](https://adaptiva.com/) 、 [VMware](https://www.vmware.com/) 和 Akamai，此外还有 [Ivanti](https://www.ivanti.com/) 和[mobile iron，以及](https://azure.microsoft.com/)[微软](https://azure.microsoft.com/)和 [AWS](https://aws.amazon.com/) 作为提供类似功能的公司的例子。

然而，从二进制库的角度来看，JFrog 的 PDN 是第一个，它建立在该公司的 Artifactory Edge 能力之上，IDC 的分析师 Jim Mercer 说。

“随着组织越来越多地寻求将软件推向边缘，软件工件必须安全一致地分发给所有内部和外部利益相关者，”Mercer 说。“当您将软件分发到边缘时，工件的安全性需要放在最优先的位置——以及某种级别的验证，以确保收到并部署了正确的软件。PDN 提供了一种混合方法，您可以将基础设施添加到分销网络中。因此，这可能是零售场所、工厂车间、电信枢纽等。”

高德纳公司的分析师托马斯·墨菲说，最终，我们的目标是将安全更新推向各种终端和系统。

“我认为这里的一个核心部分是标签和建立在内容分发网络的概念上，”他说。“因此，这是[JFrog]'[liquid software](https://jfrog.com/whitepaper/a-vision-of-liquid-software/)'消息的进一步细化，因为各个部分都在一起。这是他们版的[“价值流交付](https://searchsoftwarequality.techtarget.com/news/252499403/Tasktop-brings-new-visibility-to-value-stream-management)平台”你可以说每个人都在努力做到这一点，但他们的存储库和发行版的力量是 Artifactory 故事中更强大的一部分。"

Mercer 表示，随着越来越多的企业进行数字化转型，世界变得越来越由软件定义，他们将需要开始大规模地向边缘提供软件。

他说:“他们将频繁更新，他们将意识到，他们需要能够自动交付，同时保证来源、安全和可靠的交付。”

美世指出，几乎任何行业的企业都需要这种能力，包括智能电网、自动驾驶汽车和车队、电信和石油天然气等领域的资产远程监控、医疗保健患者监控、设备的预防性维护等。

“随着这些环境越来越多地由软件定义，对 PDN 解决方案的需求将会增长，”美世表示。

他指出，竞争对手如 [Sonatype](https://thenewstack.io/sonatype-expands-focus-to-code-analysis-with-musedev-addition/) 和 [Cloudsmith](https://cloudsmith.com/) 已经建立了二进制库，当然还有其他如 GitHub 包、Google 工件注册和 Azure 工件。

“虽然没有明确专注于分布式资料库，但其他参与者正在加强他们的软件分发能力——例如， [CircleCI 本月早些时候刚刚收购了 Vamp](https://searchsoftwarequality.techtarget.com/news/252500960/CircleCI-nabs-100M-buys-Vamp-release-orchestration) release orchestration 软件，”Mercer 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>