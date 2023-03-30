# 亚马逊希望所有人都在它的云上

> 原文：<https://thenewstack.io/amazon-wants-everybody-on-its-cloud/>

在上周的 Re:Invent 年度用户大会上，亚马逊网络服务(Amazon Web Services)从它的帽子里变出了许多不那么大的兔子，高管们描述了 AWS 对其产品所做的基本上是渐进式的改进，同时寻求作为世界上最大的云提供商推动销量。

虽然有些公告是针对 [DevOps](https://thenewstack.io/category/devops/) 的运营和开发团队的，但其他公告也适用于将 AWS 的云可访问性扩展到公民开发人员或非技术业务用户。有些对于非技术用户来说“哇”的因素特别高，甚至可能是有趣的沙盒项目。

这些公告包括无代码/低代码平台，用于构建快速简单的[机器学习](https://thenewstack.io/category/machine-learning/)模型(ML)和支持开发人员，5G 基础设施，允许用户创建自己的私有 5G 网络，只需要 AWS 云访问；更多支持传统基础架构向云的迁移和扩展的多地理区域云覆盖(更多详细信息见下文)。

亚马逊首席技术官[沃纳·威格尔](https://twitter.com/Werner)在他的会议主题演讲中描述了 AWS 对“无处不在的云”的愿景，很大程度上概括了 AWS 的雄心。简而言之，AWS 寻求允许组织为使用 AWS 的基础设施付费，只要世界上有互联网连接，“在那里你可以看到所有 AWS 服务透明地运行，”他说。

他说，“无处不在的云”应该适应组织向云、内部或沃格尔斯所描述的“坚固边缘”扩展业务，这些云构成了“无处不在的云”。“这是一个大规模分布式系统，但它不是去中心化的——分布式，但不是去中心化的，”沃格尔斯说。

企业管理协会(EMA) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk/) 对《新堆栈》表示，AWS 宣布的交易破坏因素很少，如果有的话，可能会说服一个组织选择 AWS 转向云，否则他们可能会在 AWS、Azure 或谷歌云之间做出选择。沃尔克说，亚马逊主要通过新产品和新品填补了产品组合的空白，这些新产品和新品在主题演讲台上看起来比最终结果更令人兴奋。

然而，没有人敢提及多云或混合云不仅仅包括[亚马逊前哨](https://aws.amazon.com/outposts/)(内部基础设施)，这是房间里的大大象。沃尔克说:“自 2013 年[以来，我们似乎已经兜了一个圈子，VMware](https://tanzu.vmware.com?utm_content=inline-mention) 在一次主题演讲中低估了‘书商’，卡尔·埃申巴赫很可能希望将他从我们的集体记忆中抹去。”。“今天，对于许多企业环境来说，AWS 可能低估了‘Windows OS’销售商和‘搜索引擎公司’的影响力。”

连接数据中心的广域网(wan)早在十多年前就已成为现实，现在，寻求连接其云和内部环境的组织都需要这种网络。在其公告中，AWS 表示，其 AWS Cloud WAN 提供了一个中央界面，企业可以使用该界面通过 AWS 全球网络连接其内部分支机构、数据中心和亚马逊虚拟专用云(Amazon VPCs ),只需点击几下鼠标。

选择区域后，所有远程用户、站点和数据中心将使用 VPN 自动连接到地理上最近的位置。“这实际上是在几分钟内使用大 AWS 主干为您构建的，用于在 AWS 基础架构上运行的高度可靠和高度可用的软件定义的广域网，”沃格尔斯说。

AWS 的无代码/低公告包括其发布的[亚马逊 SageMaker Canvas](https://aws.amazon.com/blogs/aws/announcing-amazon-sagemaker-canvas-a-visual-no-code-machine-learning-capability-for-business-analysts/) 专门作为 ML 模型构建的无代码替代，以及用于 web 应用程序开发的 [Amplify Studio](https://aws.amazon.com/amplify/studio/) 。这两种工具都旨在帮助减少开发人员和/或数据工程师的工作量。例如，Amplify Studio 减少了(尽管没有消除)开发人员必须为 [AWS Amplify](https://aws.amazon.com/amplify/) web 开发栈编写的代码量。

AWS 表示，亚马逊 SageMaker Canvas 允许业务分析师建立预测的 ML 模型，而不必知道如何编写代码或拥有 ML 专业知识。例如，通过图形用户界面，业务用户可以简单地合并来自云中或内部数据源的文件，以便生成货物交付的预测。

“AutoML 是当今机器学习中最令人兴奋的话题，因为它旨在显著扩大 ML 模型的使用，因此培养了人们谈论很多的数据驱动文化，”Volk 说。“Canvas 只是简化访问 AWS AutoML 功能的前端，但它似乎没有为业务用户提供必要的上下文建议和护栏，以便他们从培训中受益，然后使用自己的机器学习模型。”

另一方面，H2O.ai、DataRobot 或 BigML 等竞争对手提供了非常具体的建议，涉及数据源的哪些部分应该转换或排除，以及哪里需要额外的数据，最重要的是，最终学习模型的限制是什么，Volk 说。“虽然 Canvas 显然还没有准备好进入黄金时段，但我相信 AWS 正在努力填补其中的一些空白，因为在整个组织中为机器学习模型创建一个‘自动售货机’显然符合他们的利益，”Volk 说。

当数据集分布在多国和多辖区区域时，AWS 寻求适应那些必须根据地理区域将数据访问和存储本地化的组织。例如，一个组织可能选择提供一个受到严格监管的应用程序，如股票交易或与[亚马逊弹性库本内特服务(亚马逊 EKS)](https://aws.amazon.com/eks/) 的赌博。他们可能会试图锁定或解锁某些应用功能，这取决于法律管辖区，无论用户是在拉斯维加斯还是在阿姆斯特丹。

正如沃格尔斯指出的，AWS 目前为客户提供了 14 个本地区域，组织可以在这些区域中部署单独的 VPC，并通过 EKS 等方式控制每个区域应用的特定应用功能。虽然没有提供具体的时间表，但 Vogel 表示，AWS 正在欧洲、亚洲和澳大利亚增加 30 个新的 AWS 区域。

“我们将在全球范围内扩大本地区域，”沃格尔斯说。

AWS 传达了其内部设计的 AWS Graviton 处理器提供的更多计算能力进步，AWS 使用 64 位 Arm 设计定制构建这些处理器。例如，AWS 表示，与 AWS Graviton2 处理器相比，其在 Re:Invent 期间发布的新 Graviton3 (EC2 C7g 实例)的计算性能提高了 25%(平均)，浮点和加密性能提高了两倍。Graviton3 处理器还包括一个新的指针认证功能，以提高安全性。

亚马逊网络服务(AWS)首席执行官[亚当·塞利普斯基](https://www.linkedin.com/in/adamselipsky/)在活动开始的主题演讲中表示，随着我们提供越来越多的实例，AWS 将“继续为 Graviton3 带来更多的改进”，但没有透露更多细节。

如果没有获得频谱许可证并在移动硬件和电信基础设施方面进行重大投资，组织可能不会计划在不久的将来运营自己的私有 5G。然而，Selipsky 说，AWS 正在使这成为可能。虽然他没有具体说明这样的网络是否可以在世界上适用不同电信法律和法规的任何地方运行，但他描述了 aws 客户如何简单地自动配置和设置移动 5G 网络，“可以跨越从公司办公室到大型园区、工厂车间或仓库的任何地方，”Selipsky 说。“你只需将 SIM 卡插入手机，瞧，一切都连接起来了。

作为 5G 包的一部分，AWS 交付并维护预集成的小蜂窝无线电单元、服务器、5G 核心和 RAN 软件以及 SIM 卡。Selipsky 说，使用 AWS 控制台可以“轻松”订购额外的容量、提供额外的设备或管理访问权限，并指出“目前还没有像 AWS private 5G 这样的产品”。

“您拥有移动技术的所有优势，而没有漫长的规划周期、复杂的集成和高昂的前期成本。非常简单，”塞利普斯基说。

总之，AWS 在 Re:Invent 上没有宣布什么惊天动地的事情。然而，除了上述内容之外，它还发布了几十个公告，涵盖了云计算的几个不同方面，并满足了 DevOps 团队的开发人员、运营和业务需求。

“根据公众的反应，无服务器、机器学习和 5G 是 ReInvent 2021 的核心主题。例如，提供额外的无服务器分析服务可能不是一个迷人的公告，但它是有意义的，因为这是人们每天都在寻找的，”Volk 说。“对于新的机器学习船(Trainium 和 Inferentia)、更细粒度的数据库安全性以及针对 SageMaker Studio 的更深入的 DevOps 集成来说也是如此。这些公告都没有改变世界，但每一项都是 AWS 走向世界统治之旅中必不可少的一步。”

[https://www.youtube.com/embed/8_Xs8Ik0h1w?start=1&feature=oembed](https://www.youtube.com/embed/8_Xs8Ik0h1w?start=1&feature=oembed)

视频

[https://www.youtube.com/embed/WGA2P_oH5Xc?feature=oembed](https://www.youtube.com/embed/WGA2P_oH5Xc?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>