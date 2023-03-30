# 本周编程:GitHub 讨论上线

> 原文：<https://thenewstack.io/this-week-in-programming-github-discussions-goes-live/>

GitHub 本周表示，它终于将 GitHub 讨论从测试版中移除，并使其普遍可用。该功能于 2020 年 12 月首次引入公共测试版，并于去年 3 月向私人存储库[提供，使讨论变得更容易(正如你可能从名称中想象的那样)。](https://github.blog/2021-03-09-github-discussions-now-available-for-private-repositories/?utm_source=thenewstack&utm_medium=website&utm_campaign=platform)

我必须说，作为一个在互联网上讨论事情长大的人，甚至在互联网成为现实之前的[，我对这种事情情有独钟，老实说，我有点惊讶 GitHub 花了这么长时间才到达那里。毕竟，开发工具使自己的生活变得更容易的开发人员通常是技术的第一个用例，对吗？](http://www.bbsdocumentary.com/)

也许这只是守旧派的功能，但是考虑到 GitHub 托管开源项目的普遍性，为这些社区增加与我们期望的许多现代便利进行讨论的能力似乎只是常识。

正如 GitHub 在其公告中所写的那样，“今天创建开源软件不仅仅是源代码。它是关于管理伟大思想的涌入，开发下一代维护者，帮助新开发人员学习和成长，以及建立你的社区的文化和个性。”

经过近一年的测试，GitHub 讨论现在已经推出，似乎那些在这段时间内已经开始使用它的人完全支持新功能。

GitHub Discussions 的 GA 带来了一些新功能——能够标记您的讨论，使用 [Discussions GraphQL API](https://docs.github.com/en/graphql/guides/using-the-graphql-api-for-discussions) 和 [Webhooks](https://docs.github.com/en/developers/webhooks-and-events/webhooks/webhook-events-and-payloads#discussion) 进行集成，并在移动设备上使用讨论——更多功能正在开发中，如进行投票和使用“充满可操作数据的仪表板”监控您的社区。

## 本周的节目中

*   **Go 1.17 带来编译器改进&更多:** [Go 1.17 于本周](https://blog.golang.org/go1.17)发布，带来了“对编译器的额外改进，即一种传递函数参数和结果的[新方式](https://golang.org/doc/go1.17#compiler)，”据说这表明“Go 程序的性能提高了约 5%，amd64 平台的二进制文件大小减少了约 2%。”虽然 [now-beta fuzz 测试功能](https://go.dev/blog/fuzz-beta)并没有像最初建议的那样在 1.17 中登陆，但谷歌开源语言的最新版本也增加了对 Windows 上 [64 位 ARM 架构的支持，并引入了](https://golang.org/doc/go1.17#ports)[修剪模块图](https://golang.org/doc/go1.17#go-command)，该团队表示这“应该有助于避免下载或读取 go.mod 文件以获得不相关的依赖关系。”该版本还“对语言做了三个小的[改变”，和往常一样，还做了许多其他改进和错误修复，这些可以在](https://golang.org/doc/go1.17#language)[完整版本说明](https://golang.org/doc/go1.17)中找到。
*   **Go 开始它的网络整合:**当我们在谈论 Go 的时候，该项目已经表示他们将在未来几个月开始[整理 Go 网络体验](https://go.dev/blog/tidy-web)。目前，go 占据了许多网址，从 2019 年推出的作为新 Go 开发者中心的 [go.dev](https://go.dev/) 网站[到配套的](https://go.dev/blog/go.dev) [pkg.go.dev](https://pkg.go.dev/) 网站，该网站旨在托管关于 Go 包和模块的信息，以及 golang.org 域的各种网站。即将到来的整理将包括把这些不同的网站整合到一个位置，在 go.dev，而不是它们目前所在的不同网址。正如他们指出的那样，现在的方式“都有点支离破碎和混乱”，因此他们将“将 golang.org 的网站合并成一个统一的网站”，同时采取措施确保“所有现有的网址都将重定向到他们的新家:没有链接会被破坏。”

*   **CNCF 实习，有人吗？**如果一个为期三个月的[云计算本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)项目的带薪实习听起来很合你的胃口，那么你最好抓紧时间，因为你只剩下一点时间了。 [CNCF LFX 项目于 2021 年秋季](https://www.cncf.io/blog/2021/08/16/cncf-lfx-projects-are-open-for-fall-2021-apply-by-august-22nd/)开放，申请截止日期为[8 月 22 日](https://github.com/cncf/mentoring/blob/main/lfx-mentorship/2021/03-Fall/README.md)。参与 CNCF 项目的[阵容](https://github.com/cncf/mentoring/blob/main/lfx-mentorship/2021/03-Fall/project_ideas.md)包罗万象，从 Kubernetes 本身到 Vitess 再到 OpenEBS 或 Meshery，有 30 个项目创意可供学员研究。如果你感兴趣，请在 8 月 22 日[之前直接在](https://github.com/cncf/mentoring/blob/main/lfx-mentorship/2021/03-Fall/README.md) [LFX 平台](https://mentorship.lfx.linuxfoundation.org/#projects)上申请，月底你会收到申请的回复。
*   **GitHub 取消 Git 操作的密码:**这个改变期待已久，本周终于到来了——在你的 GitHub 上执行 Git 操作时，你将需要[通过双因素认证保护你的 GitHub 账户](https://github.blog/2021-08-16-securing-your-github-account-two-factor-authentication/)。事实上，如果你还没有注意到，我们已经进行了一周的改变，日落日期已经在 8 月 13 日。从那以后，GitHub 要求“对 GitHub.com 上所有经过认证的 Git 操作使用强认证因素，如个人访问令牌、SSH 密钥(针对开发人员)，或 OAuth 或 GitHub 应用程序安装令牌(针对集成商)。”有关如何[为您的 GitHub 帐户启用双因素认证(2FA)](https://docs.github.com/en/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication) 的详细信息，请访问[博客文章](https://github.blog/2021-08-16-securing-your-github-account-two-factor-authentication/)。哦，当我们谈论 Git 时，GitHub 也有一篇关于 Git 2.33 的[亮点的博客文章，这是最近刚刚发布的](https://github.blog/2021-08-16-highlights-from-git-2-33/)，包括几何重新打包、合并的新策略和许多其他功能。

*   **GitLab 推出了一个“数据驱动的反滥用引擎”: [GitLab](https://about.gitlab.com/?utm_content=inline-mention)** 本周[推出了 Spamcheck](https://about.gitlab.com/blog/2021/08/19/introducing-spamcheck-data-driven-anti-abuse/) ，这是一个反垃圾邮件引擎，据说已经在 GitLab.com 的所有项目中启用，并将在 8 月 22 日 GitLab 14.2 发布时提供给自托管版本。Spamcheck 将在 GitLab 平台上与 Akismet 一起运行，帮助阻止垃圾邮件和滥用，介绍新服务的博客帖子进入了 GitLab 的开发方法，另一篇承诺的博客帖子将检查所涉及的具体技术栈。敬请关注。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>