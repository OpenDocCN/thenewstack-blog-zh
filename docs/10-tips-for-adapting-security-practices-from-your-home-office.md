# 从家庭办公室调整安全实践的 10 个技巧

> 原文：<https://thenewstack.io/10-tips-for-adapting-security-practices-from-your-home-office/>

Snyk 赞助了这篇文章。

 [盖伊·波德贾尼

Guy Podjarny 是 Snyk 的联合创始人兼总裁。](https://www.linkedin.com/in/guypo/) 

远程工作人员的新常态发生得如此之快，以至于很少有公司真正为这种变化做好了准备。虽然许多人都在努力适应，但在公司的每个层面扩展新的远程流程时，都有一个学习曲线。然而，当涉及到您公司的安全实践时，尤其如此。

你现在可能在想，我错过了什么吗？别慌。相反，让我们深入了解一些行业最佳实践，这不仅有助于您和您的团队在家中适应，而且有助于扩展实践，即使当您再次回到办公室时也是如此。

1.  **建立成文的指导方针，授权给远程开发者。**

在家工作意味着在一个“典型”的工作日里会有非典型的干扰。考虑到这一点，重要的是让开发人员能够自己做决定，而不是等待无关的批准。制定清晰的指导方针有助于团队达成一致的期望，并且是成功的关键因素。投资于记录这些指导方针是关键的下一步，这将给予开发人员每次自主做出正确决策所需的权威和信心。

2.  **少关注破坏构建，多关注失败的拉取请求。**

虽然“破坏构建”是面对安全违规时一种流行的 CI/CD 安全措施，但不幸的是，它也是一种破坏性措施——使开发人员在开发新软件时陷入困境。当团队通信必须克服远程工作的分离时，这就成了一个更大的问题。我建议将破损限制在最极端的情况下。

对于其他问题，请尝试失败的拉取请求。这种方法的优点包括只测试代码被修改的分支本地的新代码更改，以及选择给定的失败是阻止合并还是仅仅提供信息的能力。这些优势有一些共同点:它们使开发人员能够做出决定，给予他们更多的自主权，即使在不可预见的问题下也能推进他们的项目。

3.  **优先投资安全可见性。**

安全性可见性可以采取多种形式，但是我有一些适用于大多数组织的具体建议。首先，利用软件材料清单(SBOM)来捕获打包到应用程序中的依赖项。另一种方法是通过特定的 Slack 渠道或通知电子邮件，甚至是显示每个团队处理安全问题情况的排行榜来众包可见性。这些策略让每个人都参与到这个过程中，并帮助团队积极地看到自己变得更好，或者如果他们没有达到目标，给他们一个纠正的机会。

4.  花额外的时间提升个人技能。

在家工作的好处是，以前花在通勤上的时间现在可以用于职业发展。对于开发者来说，可以通过在线资源，如 [MyDevSecOps](https://www.mydevsecops.io/) 、OWASP 或 [DevSecCon](https://www.devseccon.com/media/) 会议视频，或通过商业工具如 [SecureCodeWarrior](https://securecodewarrior.com/) 投资安全教育。

为了安全，投入时间和资源来提高团队的编码技能。我推荐像[Cybrary:Python for Security Professionals](https://www.cybrary.it/course/python-security-professionals-archive/)、 [Lynda/LinkedIn: JavaScript 培训与教程](https://www.lynda.com/javascript-training-tutorials/244-0.html)和 [Codecademy: Learn Go 编程](https://www.codecademy.com/learn/learn-go)这样的资源。

5.  不要忘了赞美是可以虚拟发送的。

记住，开发者也是人！尤其是在这种孤立的时候，重要的是要注意一句好话或团队的认可可能意味着很多。从一张摆放得当的 GIF 到特殊的公司礼品，不要忘记庆祝你团队的成就。

6.  **不要让距离混淆安全和开发人员的关系。**

远程开发人员需要知道，当不可避免的安全问题出现时，他们可以向某人求助。幸运的是，团队之间的联合不需要组织的改变，只需要团队之间在日常工作实践中的定期联系。我建议在同事之间预定重复的同步，并让安全和开发合作伙伴参加一些其他的团队会议以保持可见性。

7.  请记住，卫生也可以应用于安全实践。

卫生正在成为 2020 年的关键词，但在这种情况下，它不仅仅适用于洗手。在安全方面，这意味着在更隐蔽的攻击之前优先考虑基本问题。对于大多数公司来说，易受攻击的组件、配置错误和含铅令牌应该优先于复杂的攻击。一旦安全卫生成功地扩展到您的远程开发团队，您就可以继续扩展您的视野。

8.  **采用双因素认证。**

当大多数员工在 VPN 中工作或在云环境中操作时，投资双因素身份认证基础架构不仅仅是一个好主意。事实上，它可以在未来带来回报，允许您将该功能扩展到网络或云环境中的其他系统。

9.  **增加 SSH 连接的安全性。**

这可以通过启用相互身份验证和缩短会话时间来轻松实现。随着越来越多的生产机器远程化，攻击的风险也随之增加，加强这些接口上的身份验证变得至关重要。我建议使用像网飞的 [BLESS](https://github.com/Netflix/bless) 或 [SmallStep](https://smallstep.com/) 这样的开放课程系统，或者像 [Okta](https://www.okta.com/products/advanced-server-access/) 或其他这样的商业选项，以实现更强的基于身份的认证。

10.  利用臭虫奖励计划。

公司裁员的悲惨现实带来的一个积极结果是，许多专业人士将在零工市场寻找机会。这是一个通过像 Hacker One 或 BugCrowd 这样的 bug bounty 程序来加强您的安全评估策略的机会。您不仅可以为有需要的人创造工作机会，还可以增加另一层安全评估能力。

我希望这些提示不仅能帮助你在我们在家工作期间保持安全实践的正轨，而且它们能真正加强你的整体方法，并与你和你的团队一起走向未来。

## 专业人员如何实现安全开发

为了更深入地了解这些实践并在您的组织中付诸实施，[请参加与我本人(](https://info.snyk.io/tips-for-working-from-home-security-webinar) [Guy Podjarny](https://www.linkedin.com/in/guypo/?originalSubdomain=uk) ，Snyk 联合创始人兼总裁)、Atlassian 首席信息安全官 [Adrian Ludwig](https://www.linkedin.com/in/adrianludwig/) 和 InVision 高级安全工程师 [Sara Dunnack](https://www.linkedin.com/in/saradunnack/) 的小组讨论，讨论如何在 WFH 环境中维护安全开发。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>