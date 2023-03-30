# 本周编程:开源的终结和免费支持的开始

> 原文：<https://thenewstack.io/this-week-in-programming-where-open-source-ends-and-free-support-begins/>

本周，我们向您讲述一个名叫 Patrick Ahlbrecht 的孤独开源开发者的故事，他敢于站出来向世界宣布，[“不，‘开源’并不意味着‘包括免费支持’”](https://raccoon.onyxbits.de/blog/bugreport-free-support/)，然后，当许多人以各种预期的方式做出回应时，[再次重申了他的(有些站不住脚的)立场](https://raccoon.onyxbits.de/blog/reactions-bugreport-free-support/)。

Ahlbrecht 关于这个话题的第一个帖子的要点是:他的开源软件的用户想要报告“错误修复”，他指示他们提交一个支持票，他们不想这样做，因为这涉及到付款。

“从那以后，它通常会变成一篇牢骚满腹的长篇大论，说我是一个蹩脚的二位开发人员，对自己的代码不屑一顾(这很荒谬，因为，抛开职业尊严不谈，我有各种动机去修复错误，以防止我的收件箱被淹没)，只想敲诈他的用户，”他写道。

他继续解释说，他编写开源软件来解决他的问题，如果你想解决这个问题，我们会提供源代码。除此之外，许多所谓的“错误报告”被证明是不需要付费的支持请求。“这就是通常所说的工作，”阿尔布雷特写道。"令人惊讶的是，工作是人们期望得到报酬的东西."

当然，阿尔布雷特在这个问题上严肃的态度和相当直白的语言激起了一点狂热，他有资格的读者感到被拒绝回应，对此他提供了更直白和坚定的反驳。我认为所有这一切的主要错误是他错过了插入来自“[好家伙](https://www.imdb.com/title/tt0099685/)”的视频的最佳机会，但也许这不是荷兰的文化现象，因为它在这里。

[https://www.youtube.com/embed/3XGAmPRxV48?feature=oembed](https://www.youtube.com/embed/3XGAmPRxV48?feature=oembed)

视频

在这篇文章中，Ahlbrecht 提供了一种挑衅的语气，这种语气肯定是你们中的一些人在错误报告回复中梦寐以求的。“天哪，人们对我非常恼火(据说)说我不会在没有预先付款的情况下接受他们的手工编织、金边、玫瑰香味的错误报告。我怎么敢？！嗯，我就是这么想的，”他开始说道。他在结尾总结了他整个论点的大部分内容:

我不是在经营慈善机构，也不需要你的“支持”。和你一样，我想为我所做的工作得到报酬。我发现把我的作品放在开源许可下，然后花大量的额外工作在我的用户身上来收集施舍是完全不诚实的。如果许可证上说，软件可以免费使用，那就成交了。你完全明白。不多不少。其他一切都是额外收费的。

无论如何，对于那些维护开源项目的人来说，这提供了一个宣泄的阅读，其中你的一个兄弟决定站起来，就像“好家伙”剪辑一样，向所有寻求免费搭车的人宣布“去你的，付钱给我”。不管你同意与否，这本书都值得一读……而且值得一笑。

## 本周的节目中

*   **Docker 用数字支持其限速声明:**本月早些时候，Docker 对来自 Docker Hub 的图片下载进行了限速，称只有 1%到 2%的用户群负责“大约 30%的下载量”现在，该公司发布了一篇博客文章，通过数字审视其[限速，他们说这“显示了极小比例的匿名免费用户对 Docker Hub 的巨大影响。”基本上，这是相同的论点，但是这次用了一个图表，并且为那些觉得每六个小时拉 100 到 200 次还不够的人做了计算。“在开发人员的日常工作流程中，6 小时内 100 次拉动相当于连续 6 小时平均每 3.6 分钟一次码头工人拉动，”他们写道，并指出如果你需要更多，嗯，你可以考虑订阅](https://www.docker.com/blog/rate-limiting-by-the-numbers/)[付费计划](https://www.docker.com/pricing)。一个月加起来有 12，000 次匿名拉货，或者 24，000 次如果你被认证的话。他们说，受影响的应该是 200 多万个 IP 地址中的 4 万个左右。如果你正在寻找一种方法来解决这个问题，因为 Kubernetes 用户在配置方面可能会有一些困难，请查看我们在[上的解释，Docker Hub 限制是什么以及如何绕过它们](https://thenewstack.io/docker-hub-limits-what-they-are-and-how-to-route-around-them/)。对于 GitLab 用户来说，本周它的博客上有一篇关于[如何让 Docker Hub 速率限制监控变得轻而易举](https://about.gitlab.com/blog/2020/11/18/docker-hub-rate-limit-monitoring/)的新文章。

*   **GitLab 集中集成配置:**说到 GitLab，该公司已经[引入了集成管理](https://about.gitlab.com/blog/2020/11/19/integration-management/)，这是一个管理各种应用集成的中心位置——Slack、吉拉、普罗米修斯等等——这样你就不再需要在项目级别管理每一个，而是在整个 GitLab 实例中管理所有项目。从 GitLab 13.3 开始，您可以在整个 GitLab 实例中为所有项目添加集成，而在 GitLab 13.6 中，您也可以在组级别上这样做。该特性还允许您在不共享项目级凭证的情况下推出集成。更多信息，请查看下面的视频，但在我们完全离开 GitLab 之前，还要注意 [GitLab 的第一个 GitLab 社区日即将在 12 月 1 日](https://about.gitlab.com/blog/2020/11/19/gitlab-community-day/)到来，看起来它是为那些刚刚进入持续集成的人量身定制的，所以请注意。

[https://www.youtube.com/embed/6mz1y15JEHE?feature=oembed](https://www.youtube.com/embed/6mz1y15JEHE?feature=oembed)

视频

*   **GitHub 解决通知疲劳问题:**GitHub 继续处理通知疲劳问题，这是它今年早些时候关注的问题，GitHub 已经[引入了自定义通知控件](https://github.blog/2020-11-20-whatcha-watchin-custom-notification-controls/)，上周进行了更新，以帮助用户[解除对他们不再与之交互的](https://github.blog/changelog/2020-11-10-unwatch-recommendations/)存储库的监视，本周还推出了一个对通知内容类型的更多控制。现在，您可以获得精确的更新，并选择您想要通知的内容类型—代码审查、拉式请求、讨论等等。查看完整的细节和如何开始的帖子。
*   **GitHub 恢复 Youtube-dl 回购:**如果你没有跟上，不用担心，GitHub 向[提供了一个故事的回顾](https://github.blog/2020-11-16-standing-up-for-developers-youtube-dl-is-back/)，从 GitHub 上一个受欢迎的项目开始，该项目最近在数字千年版权法案(DMCA)的要求下被删除，随后在[收到额外信息](https://github.com/github/dmca/blob/master/2020/11/2020-11-16-RIAA-reversal-effletter.pdf)后恢复。请继续阅读一个国际阴谋的故事(不是真的)，它可以追溯到 20 世纪 90 年代末围绕“规避技术保护措施(TPM)”的法律，该法律未能毫不奇怪地解释今天的互联网。在这个特殊的案例中，争论部分归结为“仅仅因为代码可以被用来访问受版权保护的作品，并不意味着它不能被用来以非侵权的方式访问作品”，回购协议在做了一些微小的修改后得以恢复。这篇文章值得一读，因为它剖析了这一切是如何发生的，也因为 GitHub 计划做些什么来解决这个问题，包括努力[修改法律](https://docs.github.com/en/free-pro-team@latest/github/site-policy/dmca-takedown-policy#learn-more-and-speak-up)和“特别倡导 DMCA 的反规避条款，以促进开发者自由开发[对社会有益的](https://freedom.press/news/riaa-github-youtube-dl-journalist-tool/)工具，如 youtube-dl。"
*   **GitHub Desktop 获得 Split Diffs:**GitHub 本周的另一个快速更新:GitHub Desktop 中的 Split Diffs[介绍](https://github.blog/2020-11-17-introducing-split-diffs-in-github-desktop/)，这是一个非常受欢迎的功能，它可以让您随意地在并列视图或 Split 视图中可视化代码更改，并突出显示语法。[下载](https://desktop.github.com/)最新版本的 GitHub 桌面以获得新功能。

基诺·克雷斯科利通过 Pixabay 制作的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>