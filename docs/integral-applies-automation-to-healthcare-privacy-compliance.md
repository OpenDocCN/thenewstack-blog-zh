# Integral 将自动化应用于医疗保健隐私合规

> 原文：<https://thenewstack.io/integral-applies-automation-to-healthcare-privacy-compliance/>

当组织想要处理医疗保健数据时，它必须通过隐私认证流程，以遵守 HIPAA 等法规。

通过与 LiveRamp Health 的客户合作， [Shubh Sinha](https://www.linkedin.com/in/shubhsinha/) 发现这是一个繁琐、手动且昂贵的过程。

“想象一下，将你的地理数据、人口统计数据与你的处方、新索赔和手术史结合起来，以便获得特定患者或客户的 360°足迹，并利用它来提供更知情的治疗信息或开发更好的治疗方法——非常了解某人——所以我帮助公司做到了这一点，”他谈到自己在 LiveRamp Health 的工作时说，他将 LiveRamp Health 描述为实验性 Google X 的缩小版。

然而，这些[数据集](https://thenewstack.io/fhir-and-interoperability-in-digital-health-care-part-1/)的隐私认证过程涉及与一名顾问合作，以确保你每次想要为[任何类型的分析](https://thenewstack.io/fhir-and-interoperability-in-digital-health-care-part-2/)合并敏感的医疗数据时，都遵守美国政府制定的政策。这可能意味着来回发送 80 封或更多的电子邮件，耗时数周。

“你不能等上 8 到 10 周才运行查询或做出业务决策，”他说，这让他意识到这个过程迫切需要自动化。这导致了总部位于旧金山的 Integral 公司的诞生，Sinha 和 John Kuhn 一起将自动化和机器学习应用到这个艰巨的过程中。该公司坚称，这一过程可以缩短至两周。

## 协作加隐私监控

集成技术有两个方面:协作平台和隐私引擎。

“今天，你和 HIPAA 顾问签约，你把你所有的数据集发给他们，然后你给他们发一堆电子邮件，就像‘嘿，这就是我想做的。这是数据集。这就是它的全部含义。然后就是一个来回，”他解释道。

“顾问对数据集进行[分析，他们说，‘嘿，这风险太大了。“我需要你去掉这个专栏，消除这个数据集，不管补救措施是什么，”然后他们在修复本身上来来回回，看看从业务用例的角度来看什么是可接受的，然后从法规遵从性的角度来看什么是可接受的。](https://thenewstack.io/the-future-of-healthcare-is-cloud-connected/)

“然后，一旦顾问和客户达成一致，所有的文书工作就完成了，报告也就完成了。然后，数据集以一种非常干净且经过修复的方式被传送回客户端。

“因此，我们软件的一部分是一套协作工具，你可以在一个地方完成所有的项目管理。没有变焦电话和电子邮件线程。这只是一个无缝的平台，你可以在这里添加注释，与你的合作伙伴、利益相关者交流，无论你想去哪里。”

他承认，其中大部分还不能自动化。

隐私引擎持续监控数据集的隐私侵犯，用户可以在 UI 中进行补救。

用户安装 Docker 镜像，然后通过具有读写权限的标准 API 连接 AWS(亚马逊网络服务)或 GCP(谷歌云平台)等数据存储系统，开始分析。

“我们的软件中内置了各种统计模型来进行隐私分析，这样，一旦我们读取了数据，它就会被输入到我们所有的模型中，然后我们输出一个分数。这就是合规得分，”Sinha 解释道。

“通常，这一数字非常高，因为人们根本没有清理他们的数据。…那么我们将给出有问题的列。举个例子，如果你有一个社会保险号，这是最简单的，就像医疗保险中的“不去”…。有时你有某人的地址。有时你可以包括一个城市，有时你不能…

“这就是挑战所在。….那么，如何在隐私和商业用途之间找到平衡点呢？我们帮助走这条线，因为我们根据这些统计模型对每一列进行评分。”

因为来自不同来源的医疗保健数据通常是不干净的，自动化可以辨别不同的列是什么。例如，有时地址被写成“添加”或“起源”它不必去问别人一个列标题“起源”是什么意思。

“该平台的用户可以看到哪些色谱柱问题最大，并修复这些色谱柱。…这里重要的是协作部分，因为我们已经整合了从协作到自动化的一切，我们可以生成所有的文书工作，因为我们拥有端到端的周期，”Sinha 说。

## 一站式商店

HIPAA 顾问是 Integral 的竞争对手之一。辛哈还称赞健康数据巨头 [Datavant](https://datavant.com/) 为 Integral 的建立提供了助力。

“他们的主要产品是这种极端的哈希引擎，他们将其放入不同的医疗保健数据仓库。一旦信息被散列化，人们就会乐于分享，”他说。Datavant 正在发布 [PrivacyHub](https://datavant.com/product/privacy-hub/) ，该产品将在连接不同数据仓库方面与 Integral 展开直接竞争。

“我们的与众不同之处在于，您可以来找我们，我们基本上可以促进整个合规流程。他们纯粹专注于统计隐私引擎方面的事情，而将整个端到端流程留给公司的某个项目经理手动管理。对我们来说，最重要的事情之一就是我们是您的一站式商店。”

该公司最近宣布了一笔未披露金额的种子前资金，来自 Virtue Ventures、Caffeinated Capital、GreatPoint Ventures、Array Ventures、LiveRamp Ventures 和几家天使投资者。

“通过加快医疗保健数据的合规流程，Integral 使创建定制的患者体验、简化药物开发研究等成为可能，同时确保患者隐私。这对于创建一个更好的医疗保健系统至关重要，”辛哈说。

Integral 关注大型健康公司、保险公司和数字医疗保健公司。就像现在这样，如果两家公司想要共享数据，它们都必须聘请 HIPAA 顾问来完成这个过程。

“我们实现合规自动化的最终目标是在整个生态系统中实现标准化。不管有没有我们，这些公司都会分享数据。我们希望成为数据基础设施，推动数据从一个地方到另一个地方的安全交换。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>