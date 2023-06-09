# 开发者如何挫败坏人

> 原文：<https://thenewstack.io/how-developers-can-thwart-bad-actors/>

云为开发人员带来了大量新的机会，但也为攻击者带来了引入新威胁的机会。

为了保护企业免受这些威胁，开发人员必须了解攻击者在寻找什么，以及为什么他们比以往任何时候都更容易访问您的敏感数据。

Lacework 的最新一期季度[云威胁报告](https://info.lacework.com/cloud-threat-report.html?utm_source=website&utm_medium=blog&utm_campaign=cloud-threat-report-vol3)强调了公共云中的威胁，揭示了网络罪犯利用业务的新的和最受欢迎的途径。

我们将分析这些趋势是什么，为什么它们越来越受欢迎，以及如何防范它们。

## **用于窃取数据的加密货币挖掘工具**

 [索姆亚·卡尔马里

Sowmya 是 Lacework 的产品管理总监。她在大规模构建软件平台、应用数据驱动设计和视觉叙事以及在全球范围内发展一流团队方面拥有超过 20 年的经验。Sowmya 曾在 Crowdstrike、Harman International、Cloudera 和微软等公司担任产品领导职务。](https://www.linkedin.com/in/sowmya) 

加密货币挖掘工具 XMRig 是最常安装的工具。攻击者有许多应用程序可供选择，但通常会选择收益最大的应用程序。攻击者使用工具来帮助他们泄漏数据或提升权限来帮助他们获取这些信息。攻击者很容易利用云中的信息，因为他们可以利用如此多的不同配置和设置。如果云用户在他们的配置中犯了一个小错误，就很容易受到攻击。

虽然安全分析师通常是检测安全事件的人，但他们需要将其传递给开发团队来解决问题。开发人员希望快速行动，检查代码，然后快速导航到开发一长串待办事项中的下一个功能。他们最不希望的是在应用程序投入生产后收到安全事件的警报，然后不得不回溯以找出事件发生的位置以及如何修复它。

这就是为什么 DevOps 必须在 CI/CD 管道中实现安全控制，以从一开始就防止部署漏洞。我们建议在版本控制软件中启用双因素身份验证并实现[签名提交](https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work)，以防止凭证黑客攻击。使用软件材料清单来清点和跟踪软件在您的环境中的使用情况也很有帮助。

## **图像是攻击的新入口**

攻击者通过部署恶意容器映像并在公共存储库中托管恶意映像来危害暴露的 Docker 套接字。攻击者还擅长隐藏恶意软件，所以开发人员通常不会意识到他们的容器映像中有恶意的东西。

为了防止这种情况，开发人员在他们的代码中只使用批准的图像是很重要的。团队可以执行内联扫描，预先批准他们的映像，并在部署之前将它们放在注册表中，以评估其容器映像的漏洞。这为开发人员提供了一组安全的图像来使用，并防止他们意外地从互联网上下载恶意图像。

## **检测开采后活动同样重要**

[在 Log4j 的关键远程代码执行漏洞披露后不久，Lacework 观察到](https://www.lacework.com/blog/new-lacework-report-reveals-increase-in-sophisticated-cloud-attacks/)许多漏洞利用有效载荷。在缺陷被发现后不久，大多数成功的攻击尝试都是良性的；然而，随着时间的推移，来自恶意来源的数量不断增加。这是因为攻击者改进了他们的有效负载，并继续调整他们的利用方法，以领先于大多数安全产品使用的基于签名的检测。

在这种情况下，开发人员保护自己和系统的有效方法是实现金丝雀令牌。金丝雀令牌是资源，如目录、文件或帐户，当有人访问它们时会提醒管理员。开发者可以[将金丝雀令牌](https://www.lacework.com/blog/diy-canary-tokens-in-aws/)与云原生工具配对，并定制它们在某些资源被访问时发送警报。这是一种最佳做法，可以快速通知相关人员环境中的危害后活动。

## 云服务也为黑客提供了机会

随着平台、软件和存储解决方案的新产品不断涌现，云提供商的数量也在不断增长，这使得公司无论规模大小或位置如何，都可以轻松创新。

这使得开发人员可以轻松地创建新的应用程序和重新设计旧的应用程序。过去，开发人员需要先获得数据库或 web 服务器许可，然后才能开始创建应用程序，这既费时又费钱。

Docker 和 Kubernetes 简化了开发过程，因此开发人员现在可以编写新的应用程序，并在多个地方大规模部署它们。因此，越来越多的公司开始使用云或迁移到云，这为新来者提供了公平的竞争环境。这就是为什么我们看到这么多新的云原生企业——例如，金融科技公司，它们使用技术来改善或自动化金融服务。

云有一个独特的安全责任分担方法。公司必须保护他们的服务和平台；但是，每个用户都有责任保护他们的内容和数据。由于这种[共担责任](https://www.lacework.com/blog/the-shared-responsibility-model/)的方法以及云创新的新的便利性和速度，安全性通常被置于次要位置，这为不良行为者提供了新的机会。

## **了解攻击者想要什么是关键**

攻击者不断寻找新的方法来利用您的系统，但开发人员可以通过实施最佳实践、建立对 CI/CD 管道的控制、扫描图像和执行预先批准的检查和平衡来保护代码，从而战胜他们。要更全面地了解如何保护您的系统，请参见 [Lacework 的云威胁报告](https://info.lacework.com/cloud-threat-report.html?utm_source=website&utm_medium=blog&utm_campaign=cloud-threat-report-vol3)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>