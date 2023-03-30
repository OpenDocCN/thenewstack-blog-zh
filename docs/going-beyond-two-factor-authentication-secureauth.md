# SecureAuth 超越了双因素身份验证

> 原文：<https://thenewstack.io/going-beyond-two-factor-authentication-secureauth/>

虽然当今的许多组织已经转向云原生基础架构，但对其他组织来说，这样做仍然具有挑战性。特别是，较老的公司可能会发现，如果不首先采用混合方法，他们可能无法将传统软件和本地系统与安全标准无缝地转换到云。

自适应访问控制管理平台 [SecureAuth](https://www.secureauth.com) 帮助其用户大规模解决的一个问题是导航人们可以对其基础设施进行的安全改进。在今天的[新堆栈制造商](https://thenewstack.io/podcasts/makers)播客中，TNS 副播客制作人 Kiran Oliver 与 SecureAuth 首席安全架构师 [Stephen Cox](https://www.linkedin.com/in/stephencox) 进行了交谈，探讨 SecureAuth 不仅帮助公司保护用户数据安全，还加强其内部安全的方式。

[SecureAuth 超越双因素认证](https://thenewstack.simplecast.com/episodes/secureauth-goes-beyond-two-factor-authentication)

随着移动游戏、真实货币交易和物联网设备的持续增长，双因素身份认证已经成为当今许多移动应用和网站的标准。SecureAuth 对双因素身份认证采取了不同的方法，将其扩展到标准的用户身份检查之外，以建立各种检查和失败系统，帮助更快地标记受损的帐户。其中包括基于地理位置的技术，可以帮助评估风险，以及地理围栏选项，用户可以将其使用锁定在特定的地理位置，并将围栏区域以外的任何请求标记为潜在威胁。

“我们可以查看威胁意图，以确定与身份认证相关联的 IP 地址是否已知是坏的。我们还可以查看目录，并判断与该用户相关的配置文件是否存储在 MySQL 数据库中，并判断这看起来像是一个格式正确的请求，还是看起来像是一个攻击者？”考克斯说。

而 SecureAuth 仍在将其自己的系统迁移到一个容器化的云原生基础设施，远离其旧的。Cox 解释说，SecureAuth 还利用了 Jenkins、Ruby、Amazon Cloud 和广泛的 CI/CD 测试策略，作为其向未来转变的一部分。“我们在 CI 的基础上构建了许多基础设施，因此如果发生了变化，我们可以每天分析我们的代码。这是一种挑战，尤其是对我们的一些传统产品来说，”考克斯说。

考克斯并没有对 SecureAuth 最近投入使用的案例感到惊讶，而是指出:“我总是对我们没有涉及的用例感到惊讶。尤其是在威胁检测方面。我们的日志数据对安全团队来说是无价的。我很惊讶公司没有将身份验证相关数据纳入他们的运营，”Cox 说，并补充说 SecureAuth 已经与许多其他公司合作，组建了它所谓的[互联安全联盟](https://www.secureauth.com/partners/connected-security-alliance)，希望帮助当今的组织为他们自己的堆栈实现完全集成的安全解决方案。

随着对话的结束，Cox 恳求开发人员更深入地研究他们如何实现安全性。“我认为你必须全面考虑安全问题。在我称之为安全的三大支柱:网络、身份和终端方面，您在做什么？你知道你目前的差距在哪里吗？”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>