# Sysdig 检测跨容器和云的横向移动攻击

> 原文：<https://thenewstack.io/sysdig-detects-lateral-movement-attacks-across-containers-and-clouds/>

随着[持续云安全态势管理(CSPM)](https://sysdig.com/products/secure/cspm-cloud-security-posture-management/) 的推出，安全系统提供商 Sysdig 增加了统一云和容器安全功能。这个跨越云、工作负载和容器的单一安全平台加快了您检测和响应[横向移动攻击](https://attack.mitre.org/tactics/TA0008/)的能力。

你问什么是横向移动攻击？ [Omer Azaria](https://www.linkedin.com/in/omer-azaria/) ， [Sysdig](https://sysdig.com/) 的工程副总裁解释说:“横向移动是一种攻击模式，当一个坏演员通过多个系统和帐户获得对客观目标的访问时，就会出现这种攻击模式。在获得初始访问权限后，攻击者会尝试更深入地搜索敏感数据和其他高价值资产。”

Azaria 补充说，这通常是通过“一个公开的易受攻击的应用程序可以作为一个入口来实现的。从那里，攻击者可以尝试进入云环境，试图泄露敏感数据或执行恶意活动，如加密挖掘。”

您可能认为这些攻击发生得更频繁。Azaria 引用了 [2019 Capital One 违规事件](https://krebsonsecurity.com/2019/08/what-we-can-learn-from-the-capital-one-hack/)和臭名昭著的 [2017 Equifax 违规事件](https://www.csoonline.com/article/3444488/equifax-data-breach-faq-what-happened-who-was-affected-what-was-the-impact.html)作为例子。

这就是它的工作原理。Sysdig 威胁研究小组发现，通过利用容器中的 Apache 漏洞，攻击者可以秘密地转移到云环境中。从那里他们可以扩大攻击面。在这种情况下，攻击者可以在机器中执行任意代码，并在系统中打开反向外壳。这样的话，你就真的有麻烦了。在提升权限后，攻击者可以使用 pod 访问来查找暴露的云凭据，并最终获得对更广泛的云环境的访问权。在这一点上，他们可以窃取敏感数据，让你的生活完全痛苦。问问 Capital One 或 Equifax 的安全人员就知道了。

为了做到这一点，Sysdig 在开源软件 Falco 和 T2 云托管软件 T3 的基础上构建了自己的程序。正如大多数人所知，Falco 是由 Sysdig 创建的，是[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)的开源云本地运行时安全项目。它经常被用作一个威胁检测引擎。

云托管工作在[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)。在那里，它与 CloudTrail 协同工作，cloud trail 将所有 AWS API 调用记录到一个日志文件中。今天，有超过 200 个现成的 CloudTrail 规则。Sysdig 和其他贡献者正在以每月 20-50 条新规则的速度添加更多的规则。虽然不如 Falco 知名，但 Cloud Custodian 在采用、自动修复功能和多云支持方面势头强劲。

在 Sysdig CSPM，该公司表示，您的安全团队可以识别整个攻击链，并更快地响应威胁。具体来说，Sysdig 的新连续 CSPM 包括:

*   [基于云托管的 AWS 云安全态势管理](https://sysdig.com/opensource/cloud-custodian/) : Sysdig 增加了云资产发现、云服务态势评估、合规性验证。云安全团队可以通过自动发现所有云服务，以及标记错误配置和违反合规性和法规要求的行为来管理他们的安全状况。这些新功能基于云托管，这是一个开源的云基础设施安全工具。
*   [基于 Falco 的 AWS 和 GCP 多云威胁检测](https://sysdig.com/press-releases/sysdig-adds-unified-threat-detection-across-containers-and-cloud-to-combat-new-lateral-movement/) : Sysdig 通过[谷歌云平台(GCP)](https://cloud.google.com/) 审计日志增加了对云威胁检测的支持。有了这种安全性，团队可以持续监控可疑的活动或配置更改，而不依赖于定期的配置检查。这一点很重要，因为聪明的攻击者可以跳进去，改变暴露的配置以访问云，然后一旦他们进入了云，就立即把它改回来。静态检查可能会错过这些快速变化的攻击。

此外，所有 Sysdig 事件，包括 CSPM、合规性、容器运行时和 AWS CloudTrail 事件，都可以发送到 [AWS 安全中心](https://aws.amazon.com/security-hub/)。这使得安全团队更容易在威胁造成破坏之前做出响应。

*   云风险洞察:Sysdig 针对互联的云和容器安全事件提供新的可视化洞察，并按风险级别划分优先级。目标是让您即时了解整个云攻击链。根据严重程度对事件进行分类，使团队能够确定首先调查和响应的优先顺序。然后，您的安全团队可以调查所有可疑活动，以了解情况有多糟糕，并迅速开始对事件做出响应。

想试试吗？你可以免费。Sysdig 为单个帐户提供永久免费的持续云安全。该公司声称，“通过简单的入门，开发人员可以在几分钟内开始管理云状态。免费层包括针对 CIS 基准的日常检查和持续威胁检测，以确保云环境始终处于安全、合规和强化的状态。”最后，它还包括对 [AWS Fargate](https://aws.amazon.com/fargate/) 和[Elastic Container Registry(ECR)](https://aws.amazon.com/ecr/)每月多达 250 张图像的[在线扫描](https://sysdig.com/products/secure/image-scanning/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>