# GitHub 现在提供免费的秘密扫描

> 原文：<https://thenewstack.io/github-now-enables-you-to-find-and-fix-code-for-free/>

当我开始编程时，没有人会在他们的代码中放入秘密，比如密码、凭证、密钥和访问令牌。这简直是自找麻烦。但是随后出现了带有秘密的代码驱动自动化。突然间，我们经常在代码中加入秘密。然后，使用[软件即服务(SaaS)](https://thenewstack.io/intel-to-continue-buying-spree-of-saas-vendors/) 和[基础设施即服务(IaaS)](https://thenewstack.io/investigating-the-next-generation-of-infrastructure-as-a-service/) ，我们通常会在代码中插入令牌来调用其他服务。当然，这个安全问题的答案是在它们进入生产环境之前找到并删除它们。说起来容易做起来难。现在， [GitHub](https://github.com/) 及其[秘密扫描合作伙伴程序](https://docs.github.com/en/developers/overview/secret-scanning-partner-program)将让你免费扫描你代码中的秘密。

我喜欢这个主意！很多。

## 逐步地

要使用它，您必须完成以下步骤:

1.  要开始注册流程，请发送电子邮件至[secret-scanning@github.com](https://mail.google.com/mail/?view=cm&fs=1&tf=1&to=secret-scanning@github.com)。
2.  然后通知 GitHub 你要扫描的秘密，并创建正则表达式来捕捉它们。
3.  对于在公共存储库中找到的秘密匹配，创建一个秘密警报服务，接受来自 GitHub 的包含秘密扫描消息有效负载的 webhooks。
4.  在您的秘密警报服务中实现签名验证。
5.  在您的秘密警报服务中实现秘密撤销和用户通知。
6.  为误报提供反馈(可选)。

这项服务已经证明了它的价值。GitHub 可以扫描 200 多种令牌格式的存储库。2022 年至今，GitHub 向其合作伙伴通报了超过 170 万个在公共存储库中暴露的潜在秘密。

## 使用服务

扫描可以揭露你可能泄露的秘密。你说了算。因此，举例来说，如果不可能通知合作伙伴，比如说你自己主持的 [HashiCorp 保险库](https://www.vaultproject.io/)的钥匙暴露了，你会得到你可能有麻烦的消息。机密警报也使得跨所有警报跟踪它们变得容易。这样，您可以更深入地研究泄漏的来源和采取的审计措施。

具体来说，一次性秘密扫描警报在您的存储库中可用，您可以通过“代码安全和分析”设置下的存储库设置来查看它们。您可以通过导航到存储库的“安全”选项卡并选择“漏洞警报”下的侧面板中的“秘密扫描”来查看任何检测到的秘密在那里，您将看到任何检测到的机密的列表，并深入到任何警报以揭示泄露的机密、其位置和建议的补救措施。

这很好，但是通过推送而不是手动查看你的设置来获得秘密提醒不是更好吗？或者，更好的办法是，在代码接近交付时发现秘密时得到提醒？为什么是的，它会是。但是，那样的话，你需要额外付费。

为此，您必须订阅 [GitHub Advanced Security](https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security) 。该服务仅面向 [GitHub Enterprise](https://github.com/enterprise) 客户。

## 帮助开发者

根据英特尔软件工程总监[大卫·弗洛里](https://www.linkedin.com/in/david-florey/)的说法，它运行良好。“如果我试图推动一个秘密，我立刻知道它。GitHub 的秘密扫描推送保护在秘密被推送到代码库之前阻止了我，节省了我大量的时间。相反，如果在秘密已经暴露之后，我仅仅依靠外部扫描工具来扫描存储库，我将需要撤销秘密并快速重构我的代码。GitHub 的秘密扫描和推送保护直接集成到开发人员的流程中，节省了时间，并有助于向开发人员传授最佳实践。”

他说得很有道理。要在您的组织中试用 GitHub Advanced Security 或观看演示，请联系您的 [GitHub 销售合作伙伴](https://github.com/enterprise/contact?utm_source=github&utm_medium=site&utm_campaign=adv-security&ref_page=/features/security&ref_cta=Contact%20Sales&ref_loc=hero)。

同时，我强烈推荐你尝试免费服务。如果你认为它和我相信的一样有用，在 2023 年，你会想和你的首席信息官谈谈增加你的开发者预算。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>