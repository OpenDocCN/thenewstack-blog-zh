# 资金只是 Log4j 难题的一部分

> 原文：<https://thenewstack.io/funding-is-just-one-piece-of-the-log4j-puzzle/>

上周，我们看了许多对 [Log4j 漏洞](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/)的回应，这些回应似乎都导致了一个结论——[关于开源软件缺乏资金的影响，这是一个很大的“我早就告诉过你了”](https://thenewstack.io/log4j-is-one-big-i-told-you-so-for-open-source-communities/)。

一位作者[称](https://christine.website/blog/open-source-broken-2021-12-11)整个情况“是‘开源’软件所有主要生态系统问题的完美缩影”，而另一位作者[说](https://blog.filippo.io/professional-maintainers/)这种情况是一个明显的例子，是时候让开源维护者的角色“专业化”了。PuTTY 的维护者 Andrew Ducker 简单地说，互联网(和大公司)依赖人们在业余时间免费维护的软件，“可能是不可持续的。”

虽然开源软件缺乏资金确实是一个问题，但是资金能够防止 Log4j 漏洞吗？资金真的能防止未来出现类似的漏洞吗？

在众多组织中，[开源安全基金会(OpenSSF)](https://openssf.org/)[反对用这种过于简单的方式来看待一个复杂得多的问题。如果开源维护者说“我告诉过你”，这实际上不仅仅是开源资金的问题。](https://openssf.org/blog/2021/12/16/open-source-foundations-must-work-together-to-prevent-the-next-log4shell-scramble/)

在 OpenSSF 的一篇博客文章中，[布莱恩·贝伦多夫](https://en.wikipedia.org/wiki/Brian_Behlendorf)认为[开源基金会必须合作防止下一次 Log4Shell 争夺战](https://openssf.org/blog/2021/12/16/open-source-foundations-must-work-together-to-prevent-the-next-log4shell-scramble/)，概述了 OSS 基金会可以做的七点来减轻安全风险。在这七点中——包括安全扫描、外部审计、依赖性跟踪、测试框架、组织范围内的安全团队，以及要求项目删除旧的、易受攻击的代码——没有一次提到资金。相反，Behlendorf 在这些观点之前说，“太多的组织未能应用筹集的资金或设置过程标准来改进他们的安全实践，并且不明智地倾向于代码的数量而不是质量。”

Behlendorf 在他的七个建议行为列表后继续用一个部分完美地总结了一切:

“上述做法都不是为了给开发者更多报酬，或者直接将资金从软件用户那里输送给开发者。不要误解我的意思，开源开发者和支持他们的人应该得到更多的报酬和更多的赞赏。然而，如果你只是把更多的钱塞进他们的口袋，他们就会写出更安全的代码，这将是对大多数维护者的侮辱。与此同时，可以说，当每个下游用户都认为这些做法已经到位，正在由其他人完成并支付费用时，就发生了一场公地悲剧。”

Behlendorf 继续提出了一些关于资金和筹款的观点，但他的观点更多的是关于资金的分配，而不是资金的缺乏，以及他们如何需要专注于付费审计和“提供资源以将关键项目或代码段转移到内存安全语言，或为更多测试提供资金奖励”等事情

Behlendorf 说，在新的一年里，OpenSSF 将致力于“提升”开源的安全性。

“我们有效地做到这一点的唯一方法是开发工具、指南和标准，使开源社区的采用受到鼓励并切实可行，而不是累赘或官僚主义，”他写道。“我们将与其他开源项目和基金会合作，并向他们提供资助，以帮助他们改善安全游戏。”

所以，最后可能不是钱的问题…而是钱的问题。金钱不会神奇地解决开源安全问题，但如果投入正确的方向，它似乎肯定会有所帮助。

## 本周的节目中

*   **在 Visual Studio 仪表板上投票:**对于所有的 Visual Studio 用户来说，这是一个机会，让你们为一个潜在的新特性发表意见。Visual Studio [的高级项目经理 Misty Hays](https://www.linkedin.com/in/mistymadonna/) 在一篇博客文章中写道，她花了三个月时间阅读了四年用户关于 Visual Studio 设置和安装的评论。她说，这些评论是“残酷的诚实”和“难以置信的”在她努力设计您的 Visual Studio dashboard 的过程中，这将是“通过从您的所有工具和资源中聚合个性化内容，帮助您掌握对您的代码最重要的内容的体验”，她希望再次[征求您的想法](https://devblogs.microsoft.com/visualstudio/your-visual-studio-dashboard/#:~:text=of%20customizable%20widgets.-,Vote%20here,-Here%20are%20a)，所以请过来，让您的声音被听到！
*   **GitHub 简化操作入门:** GitHub 发布了新的 GitHub 操作“新工作流程”体验，据称这将使[更容易入门 GitHub 操作](https://github.blog/2021-12-17-getting-started-with-github-actions-just-got-easier/)。这个新特性检查您的存储库，查看诸如编程语言、构建工具、框架和包管理器之类的东西，然后根据所发现的内容提出建议。“例如，如果一个存储库包含一个已经容器化的 Node.js 应用程序，那么存储库分析将优先向您显示容器和节点相关的工作流，”他们解释道。新功能还提供了搜索和过滤建议的能力，他们说这应该“帮助你更快地找到符合你要求的正确工作流程。”

*   **最佳时机:**本周，一篇文章登上了《黑客新闻》(Hacker News)的头条，这确实呼应了最近在我脑海中萦绕的一种情绪——[它声称，这是建立网站的最佳时机](https://www.simeongriggs.dev/there-has-never-been-a-better-time-to-build-websites)，我完全同意。如果你还记得过去的日子，当你不得不运行你自己的服务器，每次你做一个改变就通过 FTP 重新下载所有的东西，完全手工构建几乎所有的东西，我们只能说，事情已经改变了。“虽然入门绝对有一个学习曲线，但一旦你有了动力，现代 web 开发就像有了火箭助推器。他们写道:“想法和执行之间的距离比以往任何时候都要短。如果学习曲线令人望而生畏，我建议以这篇文章为起点，因为它展示了一些工具，可以让你很快上手。正如他所说:火箭助推器。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>