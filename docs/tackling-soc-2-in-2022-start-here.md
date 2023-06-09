# 2022 年攻关 SOC 2？从这里开始

> 原文：<https://thenewstack.io/tackling-soc-2-in-2022-start-here/>

[](https://www.linkedin.com/in/crainerunton/)

 [克雷恩·伦顿

克雷恩·伦顿是 strongDM 的安全与合规总监。Craine 在初创公司和服务提供商中建立了并领导了安全、治理、风险和合规项目。当他不建立安全程序时，他可能在温暖的地方和鲨鱼一起潜水。](https://www.linkedin.com/in/crainerunton/) [](https://www.linkedin.com/in/crainerunton/)

当组织迁移到云时，一个主要的风险是存储在组织不能直接控制的系统中的敏感信息可能被泄露。这包括个人身份信息(PII)、财务或业务记录以及受保护的健康信息。各种监管框架，包括通用数据保护条例(GDPR)、加州消费者隐私法案和健康保险便携性和责任法案，管理数字领域的客户数据隐私。

然而，SOC 2 被广泛认为是基于云的服务提供商的数据安全标准。

本文将介绍 SOC 2 框架并探讨合规性的最佳实践，在 [strongDM 的综合 SOC 2 指南](https://www.strongdm.com/soc2/compliance?utm_campaign=Compliance%20Campaign&utm_source=ContentSynd&utm_medium=TNS)中也探讨了信托服务标准、SOC 2、合规性建议和最佳实践。

## 什么是 SOC 2？

系统和组织控制(SOC) 2 报告是由美国注册会计师协会(AICPA)开发的评估和报告框架。审计员使用它来评估服务组织的内部控制，对照同样由 AICPA 制定的信托服务标准。任何组织都可以使用一份完整的 SOC 2 报告来评估将服务外包给云计算模式(如软件即服务(SaaS)、平台即服务(PaaS)和基础架构即服务(IaaS))提供商的风险。鼓励任何提供这些服务并将客户数据存储在云中的组织寻求 SOC 2 报告。

TSC 和 SOC 2 报告是基于理念的框架，而不是合规清单。尽管他们确定了应满足的标准(安全策略、程序和访问控制)，但应由服务组织来设计和编写他们将被评估的控制，允许组织考虑他们的结构、目标和行业。

也就是说，遵守 TSC 和 SOC 2 报告通常是评估基于云的服务提供商的安全控制时使用的最低要求。

## SOC 2 合规性需要什么

SOC 2 报告根据三到五个信任服务标准来评估服务组织，以确保云中客户数据和系统的安全性。这些标准是:

*   安全性
*   有效性
*   处理完整性
*   机密
*   隐私

与其他遵从标准(如 PCI 安全标准委员会指定的标准)不同，TSC 不要求其采用者遵从所有五个服务标准。相反，它提供了设计最适合其服务目标的安全控制的自由。例如，假设云提供商在其数据中心存储但不处理客户信息。在这种情况下，处理完整性要求将是不相关的。

## SOC 2 类型

为了遵守信托服务准则框架，独立审计师必须根据美国注册会计师协会的具体专业标准对组织进行评估。审计员可以准备两种不同的审计报告——类型 I 和类型 II——来衡量组织对信托服务标准的遵守情况。在这两种类型的报告中，服务组织准备系统描述和控制清单，并将其提供给外部审计员。

### SOC 2 型

第一类报告侧重于确定服务组织向审计员提供的系统描述和控制清单是否准确，以及控制措施是否经过适当设计以满足信托服务标准的要求。

### 二型二氧化硫

第二类报告包括与第一类报告相同的系统描述和控制设计适宜性的评估，但还进一步报告了在整个观察期(通常为一年)内所提出的控制是否有效运行。服务组织必须收集证据并提交给审计员，以证明不仅控制存在，而且组织实际上执行了控制中描述的操作。

## SOC 2 信任服务标准

要获得良好的 SOC 2 报告，您的政策、控制和流程必须符合以下信托服务标准:

### 安全/通用标准

安全类别包括所有必需的访问控制、流程和程序，以防止对受保护资源(数据和系统)的未授权访问。防火墙、入侵检测和防御系统、反恶意软件工具和多因素身份认证是保护云中客户数据的重要安全措施。

例如，组织可以安装网络检测和响应解决方案，以持续监控其内部网络和云环境之间的交互。这种方法可确保威胁参与者(如高级持续威胁和勒索软件操作员)无法轻松访问、修改或删除云数据，即使他们成功访问了组织的一个终端设备。

人身安全也是安全标准的一个要素。合规措施可确保云 IT 基础设施和数据中心的安全，免受各种风险，包括盗窃、破坏和自然灾害。典型的物理安全控制包括安全警卫、生物认证和监控摄像头，以保护建筑物免受未经授权的访问。

### 有效性

可用性标准解决了确保客户端不间断访问系统和数据的安全和操作要求。例如，网络性能监控工具、事件响应和数据恢复计划对于支持可用性都至关重要。

不同的组织可能需要多种解决方案来满足可用性标准。这些可能包括:

*   安装网络监控解决方案，如 Nagios Core、OpsGenie 或 Datadog，以持续监控网络性能。
*   实施故障转移解决方案，以便在出现故障或网络攻击时立即替换关键系统、数据和设备。
*   实施备份和恢复策略，加快从网络安全事件(如勒索软件攻击)中恢复的速度。

### 处理完整性

“处理完整性”是指确保数据处理系统按照要求执行其任务，并且没有未经授权方的干涉、延迟或操纵。

例如，云提供商可能会实施几种加密技术来保持存储数据的完整性，并防止未经授权的访问。

### 机密

机密性标准确保所有类型的私人数据，如客户数据、商业秘密和专有信息(如程序源代码)保持机密。根据相关法律、合同和服务水平协议，这些数据只能由授权方访问。

当云提供商存储和处理机密的客户信息时，它应该准备一个保护这些数据的计划。例如，典型的控制可以使用身份和访问管理解决方案来管理员工对受保护资源的访问权限。

### 隐私

隐私标准衡量组织防止未经授权访问私人客户数据的能力，包括姓名、电子邮件和物理地址以及电话号码。组织应具备必要的安全控制措施，以便安全地收集、保留、披露和销毁不再使用的 PII。这些程序应遵守组织规定的隐私政策和美国注册会计师协会隐私原则中的规定。

## 基本审计计划

任何代表客户处理或存储数据的服务提供商或组织都可以努力满足信任服务标准并获得 SOC 2 报告。下面是一个示例方法。

### 准备阶段

在第一阶段，审计公司或内部团队收集信息。审计员可以从创建一份员工问卷开始。调查问卷应试图获得公司结构和功能的整体观点。这可能包括但不限于:

*   业务流程
*   系统基础架构类型和位置(内部或云中)
*   安全、治理和工程策略
*   防止未经授权访问数字资产的安全控制类型
*   出现数据泄露或安全中断时的事件响应计划

### 验证当前流程的有效性

一旦审计员了解了公司的流程和安全协议，他们必须验证这些功能是否符合公司的官方文档。这包括要求提供证据，证明流程是按照规范执行的，政策得到了遵守，控制措施是按照书面规定和预期进行的。

### 评估流程

审计员审查该组织提供的证据，将其与他们最初收到的文件进行比较，并将这两者与信托服务标准进行比较，以评估该组织是否确实符合 AICPA 设定的标准。

### 补救

在此阶段，公司应解决和补救其审核团队发现的任何差距，以便满足未来的信托服务标准。

### 总结报告

最后，审计公司会发布一份总结报告，其中包含对公司安全控制和流程的评估，以及相关的信托服务标准。

## 制定您自己的合规策略

与支付卡行业数据安全标准和 GDPR 标准不同，遵守信托服务标准不是强制性的，获得 SOC 2 报告也不是强制性的。然而，遵守这一附加标准向您的潜在客户表明，您的企业极其重视其数据的安全性、保密性和可用性。

现在，您已经对信任服务标准和 SOC 2 报告框架有了更多的了解，并且已经看到了一个示例实现，您可以制定一个符合您组织需求的法规遵从性策略。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>