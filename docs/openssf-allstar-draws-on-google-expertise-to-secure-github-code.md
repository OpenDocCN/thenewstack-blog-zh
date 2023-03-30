# OpenSSF Allstar 利用 Google 的专业知识来保护 GitHub 代码

> 原文：<https://thenewstack.io/openssf-allstar-draws-on-google-expertise-to-secure-github-code/>

说一个好的安全游戏很容易。实际实现良好的安全性完全是另一回事。现在，[谷歌开源](https://opensource.google/)和 [Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)的[开源安全基金会(OSSF)](https://openssf.org/) 联手让你更容易保护你的 [GitHub](https://github.com/) 库。

这是通过 [Allstar](https://github.com/ossf/allstar) 实现的，这是一款 [GitHub 应用](https://docs.github.com/en/developers/apps/getting-started-with-apps/about-apps#about-github-apps)，为 GitHub 项目提供自动化的持续执行安全最佳实践和策略。这适用于谷歌和 OSSF 新发布的安全记分卡。记分卡使用一组自动化的通过/失败检查，目前有 18 个，以提供对开源软件项目安全性的快速审查。具体来说，记分卡检查安全性启发，例如它是否使用分支保护、加密签名发布工件以及要求代码审查。

这为开源代码产生了一个“风险分数”。这是一种快速、肮脏且实用的方式来查看给定代码库的可信度。

Allstar 利用这一数据向前推进了一步。有了它，维护人员可以自动强制执行特定的检查。然后，如果您的存储库未能通过检查，Allstar 会介入解决问题。这避免了手动修复的额外工作和烦恼。换句话说，安全记分卡可以帮助您衡量当前的安全状况，以达到您的目标，而 Allstar 可以帮助您实现目标。

具体来说，“Allstar 的工作方式是根据定义的安全策略不断检查预期的 GitHub API 状态和存储库文件内容(存储库设置、分支设置、工作流设置)，并在预期状态与策略不匹配时应用强制措施(归档问题、更改设置)。”

这种方法有几个优点。首先，因为它不断地执行您的安全策略，它可以捕捉您可能永远不会注意到的秘密攻击。例如，如果有人临时禁用分支机构保护以进行恶意更改，然后重新启用保护，Allstar 将检测到违反策略的情况并阻止它。其次，坦率地说，人们不善于发现安全问题。通过自动化流程，您可以消除安全等式中的人为错误因素。

现在，Allstar 只能运行一些安全策略检查。以下是迄今为止的运行情况:

[分支保护](https://docs.github.com/en/github/administering-a-repository/defining-the-mergeability-of-pull-requests/about-protected-branches):

*   要求对拉请求的批准，这有助于满足软件工件供应链级别的代码评审需求( [SLSA](https://security.googleblog.com/2021/06/introducing-slsa-end-to-end-framework.html) )。
*   设置一些必需的拉式请求审批。
*   解除过时的提取请求批准。
*   阻挡力推动。

其他保护措施包括:

*   要求安全策略文件 [SECURITY.md](https://docs.github.com/en/code-security/getting-started/adding-a-security-policy-to-your-repository) 出现在项目中。
*   锁定外部协作者管理员并阻止外部协作者的推送访问。这样，您可以要求所有管理员和协作者在参与您的项目之前成为您组织的成员。
*   当在存储库中发现二进制 blob 时，发现并提醒管理员和维护人员。

展望未来，随着开源安全补丁的制作，Allstar 将自动更新依赖关系。它将通过确保启用通过[dependent bot](https://github.blog/2020-06-01-keep-all-your-packages-up-to-date-with-dependabot/)或[renew](https://github.com/renovatebot/renovate)的自动依赖性更新来实现这一点。

与此同时，如果你担心来自外部的坏代码，Allstar 可以冻结依赖关系更新，直到你有机会审查它们。这将通过锁文件或类似的特定于语言的锁定机制来完成。这将保护您免受折衷的依赖发布的影响。

不想检查记分卡可以发现的特定安全策略吗？没问题。Allstar 允许您选择对您、您的存储库和您启用的策略有意义的强制执行操作。目前可采取以下执法行动:

*   记录安全策略遵守失败，无需其他操作
*   打开一个 GitHub 问题
*   恢复修改后的 GitHub 策略设置，以匹配原始的 Allstar 配置

更多的强制措施将在未来的更新中提供。

这个开源工具在很大程度上是一项正在进行的工作。如果你想帮忙，你也应该帮忙，因为全明星和记分卡的结合有望改变安全游戏规则，他们会很乐意帮忙的。只要开始使用 Allstar，并通过提交[问题](https://github.com/ossf/allstar/issues)和/或拉动[请求](https://github.com/ossf/allstar/pulls)来帮助改进它。您和开源编程社区的其他人将会很高兴您这样做了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>