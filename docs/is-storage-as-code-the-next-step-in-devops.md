# 开发运维的下一步是代码存储吗？

> 原文：<https://thenewstack.io/is-storage-as-code-the-next-step-in-devops/>

[DevOps](https://thenewstack.io/category/devops/) 的下一次进化已经到来。有时被称为 [AppOps](https://thenewstack.io/why-an-appops-model-empowers-developers/) ，这一举措通过将[基础设施作为代码(IaC)](https://thenewstack.io/developers-are-putting-pressure-on-infrastructure-teams-to-modernize/) 进行自动化管理和供应，使开发人员至少能够掌控部分底层基础设施，而不会产生成为所谓的全栈开发人员的认知超载。或者基础架构团队疲于应对随着部署速度增加而增加的订单。

如果适当的[防护栏和策略](https://medium.com/container-talks/demystifying-appops-devops-done-right-ac20db45e205)作为代码存在，团队被授权做决定，同时减少错误和成本。然后，应用程序开发人员和基础设施工程师都可以解决创造性问题，这些问题的解决方案可以提高业务价值，进一步兑现 DevOps 的承诺。

纯存储公司的人认为，这种技术合乎逻辑的下一个扩展是他们所谓的存储即代码。然后，存储从另一个瓶颈变成了基本的另一部分 [DevOps 单一事实来源](https://blog.scaleway.com/infrastructure-as-code/)。

如果做得正确，存储即代码应该包含云计算模型的敏捷性和可扩展性，而不管环境或谁需要访问它。

## 混合世界中的存储即代码

很少有企业是纯公有云。大多数组织[更喜欢混合方法](https://www.idc.com/getdoc.jsp?containerId=US48191321#:~:text=%22IDC%20research%20shows%20that%20the,Cloud%20Infrastructure%20Services%20at%20IDC.)，大多数[应用程序现代化计划](https://thenewstack.io/how-to-build-a-roadmap-to-app-modernization/)追求公共云和私有云、内部部署和[边缘计算](https://thenewstack.io/category/edge-iot/)的某种混合。

纯存储产品管理和营销副总裁丹·科岗告诉新堆栈，当开发人员需要云资源，如存储、联网、T21 和计算时，他们可以通过 Terraform 按需访问。

但是在传统的内部架构中，这些开发人员开出了一张 IT 罚单，随之而来的是围绕资源调配和如何采购内部基础架构的长时间讨论。后一个过程可能需要几周或几个月。

纯存储的核心是一个名为 [Purity](https://www.purestorage.com/products/storage-software/purity.html) 的操作系统，它在 FlashArray 系列的设备上运行，并通过云块存储在云中运行——但是，科岗说，尽管它们有不同的名称，但它们实际上是相同的代码和产品，只是在不同的环境中工作。

顾名思义， [Pure Fusion](https://www.purestorage.com/enable/pure-fusion.html) 希望跨位置进行虚拟化，让云成为一种运营模式，而非目的地。“无论你是在本地、边缘还是公共云上运行，你都可以在相同的运营模式下运营，”他说。

Pure Fusion 提供了一个带有区域和可用性分区的拓扑模型，并结合了基于策略的各类存储供应方法，而不是云与本地决策。基础架构团队可以决定整个组织的数据保护策略和主机对存储的访问。

Pure Fusion 带来云计算的可见性、可扩展性、即时可用性、智能工作负载和服务级别协议(SLA)方法，并将其扩展到 FlashArray 系列产品。

大约有 12 家纯存储客户测试了 Pure Fusion，其中包括几家全球最大的金融机构，他们在自己的数据中心内构建了自己版本的超大规模云。

根据科岗的说法，这种体验很像大型云提供商的体验，即使是面向客户的门户，但这些大型、监管良好的行业只希望他们的基础架构和开发运维模式模仿超大规模云，以获得好处，而没有公共云可能带来的额外成本、安全性和扩展挑战。

## 代码存储和 DevOps 的未来

毫无疑问，存储将成为无所不包的 DevOps 世界的一部分。

通过能够通过基础架构即代码实施策略即代码，基础架构团队可以提供一个服务菜单，包括通过 API 调用按需提供的存储，作为不断响应相同票证的替代方案。毕竟，DevOps 的核心是绝不重复做同一件事的承诺，这样所有的工程师都可以成为具有协作精神和创造力的员工。

Pure Storage 负责 API 和开发人员体验的产品管理负责人安东尼·费拉里奥认为，这是传统存储专家提升技能进入 DevOps 领域的[趋势的一部分，他们“不再是一个痛苦的票务服务人员”](https://www.harrisonclarke.com/devops-sre-candidate-blog/how-devops-engineer-became-the-most-in-demand-job-title)

他说，通过 Pure Fusion 学习如何从拓扑和布局角度设计应用程序，这些工程师更有能力按需定义、构建和提供基础设施。这是 IT 能够继续提供更多可衡量的商业价值的另一种方式。

“大型存储团队和 IT 组织正在寻求进入这种模式，”他说。"人们很高兴能摆脱这种单调乏味的工作，以代码的形式构建一些东西."

费拉里奥说，虽然开发人员不是存储市场的决策者或预算持有者，但他们也是有重要影响的受众。

“IT 开发人员知道他们有责任构建和自动化他们自己的基础设施服务，”他说。"虽然他们不掌管财政大权，但他们是执行者."

费拉里奥说，这是遵循流行的库伯内特抽象的逻辑趋势；人们普遍要求基础设施足够通用，每个人都可以访问他们需要构建的东西，而不必一直打扰基础设施工程师。在护栏和政策到位的情况下，加快行动速度。

“如果你看看几年前云运营模式的起源，你作为开发人员或应用程序所有者需要的基础设施是按需的——你不必担心幕后发生的事情，”费拉里奥说。但是，当它在本地时，流程仍然是手动的。"你需要基础设施即服务到位，有政策定义等等."

另一方面，他认为，如果你不构建你的基础设施即代码，如果你不交付你的基础设施即服务，那么你就不是真正以云思维来构建——无论你在哪里存储。

这是因为 IaC 和 IaaS 是云购买者和云消费者的期望。费拉里奥认为，尤其是在一个混合的世界里，编码一切的云实践应该跨环境和角色传播。

## 纯开发:更快地交付应用

传统上，开发人员并不是存储供应商在开发产品时考虑的用户。“大多数存储是为了满足基础设施人员的需求，”科岗说。“开发者只有在需要的时候才体验到。”

考虑到这一点，5 月 11 日，Pure Storage(以前被视为基础架构第一的组织)将通过虚拟活动 [Pure Dev](https://purestorage.com/company/events/pure-dev-2022.html?utm_medium=email&utm_source=newsstack&utm_campaign=bma&utm_region=ams&utm_content=default&utm_creative=default&utm_term=default&utm_keyword=default) 正式开始与应用程序基础架构开发人员的对话。

60 分钟的活动将包括:

*   行业小组:关于存储即代码如何融入基础设施即代码的对话，以帮助开发人员构建他们需要的东西，主讲:[凯尔·拉迪](https://www.linkedin.com/in/kmruddy/)，Terraform 在[哈希公司](https://www.hashicorp.com/?utm_content=inline-mention)的高级技术产品营销经理； [Keith Townsend](https://www.linkedin.com/in/kltownsend/) ，CTO Advisor 创始人；[英特尔云解决方案架构师 Kiran agra hara](https://www.linkedin.com/in/kagrahar/)；以及主持人 Robert Lee，Pure Storage 的首席技术官。
*   纯融合:“开发人员生活演示中的一天。”从开发人员的角度看存储即代码的工作方式，从吉拉票证到部署。
*   Spire Animation Studios，Inc .的技术和基础设施副总裁 Ali Zaidi 的采访，讨论与异构数据库相关的挑战。
*   Portworx 数据服务:案例研究。对该产品早期采用者之一的采访，包括面向开发人员的数据库即服务演示。

*[注册](https://purestorage.com/company/events/pure-dev-2022.html?utm_medium=email&utm_source=newsstack&utm_campaign=bma&utm_region=ams&utm_content=default&utm_creative=default&utm_term=default&utm_keyword=default)参加 5 月 11 日的活动直播，或在活动结束后接收录音。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>