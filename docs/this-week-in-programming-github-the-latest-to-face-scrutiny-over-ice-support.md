# 本周节目:GitHub 最近面临对 ICE 支持的审查

> 原文：<https://thenewstack.io/this-week-in-programming-github-the-latest-to-face-scrutiny-over-ice-support/>

本周反弹仍在继续，又一家技术公司被发现与美国移民和海关执法局(ICE)签订了合同——这一次 GitHub [成为愤怒的焦点](https://twitter.com/zenalbatross/status/1181935831206027266)。GitHub 的员工和用户对 GitHub 与该机构续签了 20 万美元的合同感到不满，该机构因在寻求进入该国的过程中分离家庭而受到严厉批评。

这一消息来自 GitHub 首席执行官[纳特·弗里德曼](https://twitter.com/natfriedman)泄露的内部电子邮件，现在该公司[发布了一份公开声明](https://github.blog/2019-10-09-github-and-us-government-developers/)解决这一情况，基本上是说他们不同意 ICE 的一些做法，但不同意其他部分，除非该机构明显违反他们的使用条款，否则合同将仍然有效。继微软、HashiCorp、Chef 和其他公司之后，GitHub 是最新一家因与该机构合作而受到批评的公司。

Twitter 上的许多人在回应 GitHub 的声明时没有拐弯抹角，呼吁员工表明立场，并表示用户应该继续抵制这项服务。

GitHub 回应的要点可以归结为继续“参与政策和宣传工作，以改变当前政府糟糕的移民政策”，通过官方渠道开展工作，并捐赠 50 万美元(他们指出这一金额“超过了 ICE 的购买价值”)来抵消合同。当然，这种辩护并没有赢得批评者的支持，他们希望 GitHub 完全放弃合同。

现在，不要使用[滑坡逻辑谬误](https://en.wikipedia.org/wiki/Slippery_slope)，而是问一个诚实的问题，我们发现自己在想——它在哪里结束，我们如何才能为技术领域的几乎任何人工作？在你发现一家公司把他们的软件卖给一些政府机构或其他做坏事的公司之前，你要追踪钱有多远？正如一个人指出的，如果我们抛弃 GitHub，[我们最好也抛弃我们心爱的 Visual Studio 代码](https://twitter.com/bloqhead/status/1181998397173223425)。

对于代码和开发人员来说，这是一个重新评估道德的有趣时机，不是吗？

## 本周的节目中

*   **Rust 的 Async Foundation 专注于完善:**我们上周给你带来了消息，期待已久的 async-await 功能终于[登陆了 Rust beta 分支](https://blog.rust-lang.org/2019/09/30/Async-await-hits-beta.html)，但是，正如[在新推出的](https://blog.rust-lang.org/inside-rust/2019/10/07/AsyncAwait-WG-Focus-Issues.html) [Inside Rust 博客](https://blog.rust-lang.org/inside-rust/)上评论的那样，“还有很多工作要做”，主要涉及“完善、完善以及(咳咳)更多的完善”Rust 团队引用了积压的“奇怪的诊断、次优的性能和偶尔令人费解的类型检查失败”，宣布了[焦点问题](https://rust-lang.github.io/compiler-team/working-groups/async-await/#how-to-get-involved)，他们将……你猜对了，集中精力并尝试一次解决一个。然后是“甲板上的问题”，这可能是下一个受到关注的问题，你可以[给自己加上“甲板上”的标签](https://rust-lang.github.io/compiler-team/working-groups/async-await/#nominating-issues)，并给出一些原因。换句话说，如果你认为有什么事情值得关注，那就去做，让团队知道。当然，作为一个开源项目，你也可以通过参加一个[分类会议](https://rust-lang.github.io/compiler-team/working-groups/async-await/#triage-meeting)或者出现在[# WG-async-foundations on Zulip](https://rust-lang.zulipchat.com/#narrow/stream/187312-wg-async-foundations)来分享修复 bug 的乐趣。最后，你还可以[提名 bug](https://rust-lang.github.io/compiler-team/working-groups/async-await/#nominating-issues)。

*   **GitHub 增加了多行评论:**特使代理创建者 Matt Klein 上周通过他的[欣喜若狂的推文](https://twitter.com/mattklein123/status/1179097586818572292)首次提醒了我们这一点，现在它是官方的，并通过 API 以编程方式提供。GitHub 增加了一个看似简单却非常令人期待的新特性，能够使用 REST API 或 GraphQL 编写[多行注释](https://developer.github.com/changes/2019-10-03-multi-line-comments/)“跨越拉请求中的多行代码”该功能当前处于预览状态。
*   **亚马逊翻译增加了 7 种新语言:**我们一直是创造巴别鱼的忠实粉丝(你读过[这本书](https://en.wikipedia.org/wiki/The_Hitchhiker%27s_Guide_to_the_Galaxy_(novel))，对吧？)而且我们每天都在靠近，各种服务提供翻译。亚马逊本周表示，亚马逊翻译服务将增加七种新语言:希腊语、匈牙利语、罗马尼亚语、泰语、乌克兰语、乌尔都语和越南语。根据这篇博文，这项服务现在支持 32 种语言，包括:阿拉伯语、中文(简体)、中文(繁体)、捷克语、丹麦语、荷兰语、英语、芬兰语、法语、德语、希腊语、希伯来语、印地语、匈牙利语、印度尼西亚语、意大利语、日语、韩语、马来语、挪威语、波斯语、波兰语、葡萄牙语、罗马尼亚语、俄语、西班牙语、瑞典语、泰语、土耳其语、乌克兰语、乌尔都语和越南语。他们还推出了 987 种翻译组合，所有这些组合都可以在亚马逊翻译可用的所有地区立即使用，免费用户在前 12 个月每月获得 200 万个字符。

https://twitter.com/gatsbysghost/status/1181227505824305153

*   谷歌蚱蜢走向桌面:虽然在业余时间学习在移动设备上编程肯定是一项值得的努力，但屏幕、键盘和(可能)鼠标(对于那些不完全生活在终端中的人来说)的好处是显而易见的。因此，当谷歌称数百万人已经使用 [Grasshopper](https://grasshopper.app/) 学习编码时，该公司正在[将 Grasshopper 带到桌面](https://www.blog.google/outreach-initiatives/grow-with-google/grasshopper-desktop-learn-to-code/)。随着桌面可用性，关于使用代码编辑器的课程和网页介绍也被添加进来，所以开始学习吧！
*   **谷歌的 AMP 将捐赠给 OpenJS 基金会:**我们不能说谷歌的 AMP 项目一直是开发者中最受欢迎的项目——一些人认为这是谷歌强加给他们更多的要求，只是为了服务于谷歌自己的目的。嗯，谷歌现在说 [AMP 正在加入 OpenJS 基金会孵化计划](https://blog.amp.dev/2019/10/10/amp-is-joining-the-openjs-foundation-incubation-program/)作为一个孵化项目。为什么？谷歌表示，OpenJS 与 AMP 的[使命](https://amp.dev/about/mission-and-vision/)一致，提供独立性，并与 AMP 最近[改进的治理模式](https://blog.amp.dev/2018/09/18/governance/)相契合。
*   **申请 Google Code-在 2019 年:**今天 Google 新闻的最后一个花絮——[Google Code-在 2019 年组织申请开放](http://opensource.googleblog.com/2019/10/google-code-in-2019-org-applications.html)给有兴趣参加第十届[Google Code-在 2019 年](https://g.co/gci)的开源组织，该组织有 13-17 岁的大学预科学生学习如何为开源软件做出贡献。申请截止时间为 2019 年 10 月 28 日星期一 17:00 UTC。更多信息，请查看[时间表](https://developers.google.com/open-source/gci/timeline)和[常见问题解答](https://developers.google.com/open-source/gci/faq)。

*   **Visual Studio 代码获得原生 Jupyter 笔记本编辑:** Python 数据开发者欢欣鼓舞，微软[宣布在 VS 代码中支持 Jupyter 笔记本原生编辑](https://devblogs.microsoft.com/python/announcing-support-for-native-editing-of-jupyter-notebooks-in-vs-code/)。除了在此版本中解决的 97 个问题，Jupyter 笔记本的原生编辑“为数据科学家和笔记本开发人员带来了一种直接编辑的新方法。ipynb 文件，并获得 Jupyter 笔记本的交互性和 VS 代码的所有功能。”[的新特性](https://devblogs.microsoft.com/python/announcing-support-for-native-editing-of-jupyter-notebooks-in-vs-code/)带来了管理源代码控制、打开多个文件的能力，并带来了智能感知、Git 集成和多文件管理。除此之外，今年 10 月发布的 VS 代码还引入了一个在终端中运行 Python 文件的按钮，以及对 Python 语言服务器的林挺和导入改进。

哈希公司是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>