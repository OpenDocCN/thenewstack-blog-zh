# 本周编程:忽略 C++迅速崛起的谣言

> 原文：<https://thenewstack.io/this-week-in-programming-ignore-the-rumors-of-cs-meteoric-rise/>

好了，这个月的 [TIOBE 指数](https://www.tiobe.com/tiobe-index/)出来了，还有[头条](https://www.thehindu.com/sci-tech/technology/c-is-now-the-fastest-growing-programming-language/article32580426.ece?homepage=true)接着[头条](https://www.techrepublic.com/article/c-is-now-the-fastest-growing-programming-language/)接着[头条](https://www.zdnet.com/article/programming-languages-c-jumps-in-popularity-as-java-falls-away/)吹捧 C++的复兴，敲响了 Java 的丧钟。如果这看起来有点像抓住注意力的结论，那是因为它很可能就是这样。虽然这些故事中的许多只是重复了 TIOBE 的结论——c++是“目前发展最快的编程语言”,但其中一个结论是——这里需要应用一些健康的怀疑态度来看看到底发生了什么。

如果你不熟悉的话，TIOBE 指数是通过计算+" <language>编程"在最流行的搜索引擎上的点击率来计算的，甚至 TIOBE 首席执行官 [Paul Jansen](https://www.tiobe.com/company/management-team/#:~:text=Chief%20Executive%20Officer%20Paul%20Jansen,philosophy%20(both%20cum%20laude).) 也写道，他认为“新的 C++20 标准可能是造成这种情况的主要原因之一。”</language>

ISO C++委员会主席 [Herb Sutter](https://herbsutter.com/) 就在上周写了一篇[博客文章](https://herbsutter.com/2020/09/06/c20-approved-c23-meetings-and-schedule-update/)指出“随着 C++20 的技术工作在 2 月份完成，该标准现在已经获得技术上的批准，这意味着正式发布预计将在 2020 年底左右。”这可能只是推动 C++在搜索排名中上升的那种消息，而不是对其使用的任何特别的新倾向。

当每个人都忙着吹捧 C++卷土重来时，iProgrammer 进一步将这一想法付诸实践，询问[选择 C++是否是一个奇怪的选择](https://www.i-programmer.info/news/184-cc/13986-c-picked-out-by-tiobe-an-odd-choice.html)，并指出“为什么有人会从 2001 年 9 月的 C++流行度图表中得出结论，这是 TIOBE 从那时起开始绘制的数据集，它目前“表现良好”至于“到底发生了什么”这一部分，这张图表显示得最清楚，根据 TIOBE 的排名，C++在稳步下降，最近略有上升。持续减少的数字在短期内的高百分比变化不会成为“增长最快的编程语言”，这是肯定的。现在甚至有一种被设计用来取代 C++的实验性编程语言叫做 [Google Carbon](https://thenewstack.io/google-launches-carbon-an-experimental-replacement-for-c/) 来密切关注。

## 本周的节目中

*   **代码空间合并:**如果你对 Visual Studio 代码空间和 GitHub 代码空间之间的区别感到困惑，那么，不要再犹豫了——两者已经合二为一，Visual Studio 代码空间合并为 GitHub 代码空间。为什么？他们写道:“在预览中，我们了解到从存储库过渡到代码空间是您工作流程中最关键的部分，而且绝大多数人更喜欢全面集成的本机一键式体验。”既然他们恰好拥有大约 5000 万开发者使用的存储库，为什么不呢？有关过渡的更多细节，请查看常见问题。如果你已经是 Visual Studio Codespaces 的用户，你可以转移到 GitHub Codespaces private beta，当前的 Visual Studio Codespaces [门户](https://online.visualstudio.com/login)将于 2021 年 2 月 17 日退役。
*   **GitHub 获得团队整合:**这条新闻最令人惊讶的部分可能是 [GitHub 花了这么长时间才与微软团队整合](https://github.blog/2020-09-10-announcing-the-github-integration-with-microsoft-teams/)，因为微软早在 2018 年 6 月就收购了 GitHub。毕竟，正如他们在公告中指出的，他们“多年来一直有一个 [GitHub + Slack 集成](https://slack.github.com/)”，现在正准备为团队推出一个……实际上仍处于公开测试阶段。要试一试，去微软团队应用商店安装 GitHub(预览版)，或者直接从[这里](https://teams.microsoft.com/l/app/ca9e26b7-dce5-44a0-b2b7-a70a3d65ce25)安装。

*   Rust 想知道你为什么再也不打电话了:Rust 团队正在进行年度灵魂探索调查，他们想知道你是否使用这种语言，如果没有，为什么？玩笑归玩笑，该团队已经[启动了 2020 年 Rust 状态调查](https://blog.rust-lang.org/2020/09/10/survey-launch.html)，这有助于他们弄清楚为什么你可能还没有采用 Rust，为什么你尝试了一次后就放弃了它，或者为什么你继续使用这种语言，等等。这意味着，即使你从来没有真正给过铁锈一天的时间，他们也希望你去参加 [2020 年铁锈状况调查](https://docs.google.com/forms/d/e/1FAIpQLSf__XKjS2xa55jUOi78ONvjG0elG5ZWqOz0MYdX6sgmcjb5pw/viewform?usp=sf_link)并告诉他们原因。像往常一样，他们将在 9 月 24 日停止接受投稿后写下他们的发现。查看去年的结果，一窥他们收集到的真知灼见。
*   **展望 2021 年 Rust 路线图:**正如我们刚刚提到的，Rust 调查的目的之一是让团队找出今后努力的重点，其中一部分是[通过征集博客帖子来规划 2021 年路线图](https://blog.rust-lang.org/2020/09/03/Planning-2021-Roadmap.html)。因此，你不仅应该填写调查，还应该写一篇关于你对 Rust 的体验的博文——语言特性、工具改进、组织变化、生态系统需求——并且[让他们知道这件事](https://forms.gle/Hv41uA5qJEY89XRm7)，这样他们就可以考虑你对来年的想法。为此，他们还就可能的 Rust 2021 版本创建了一个[公开征求意见(RFC)](https://github.com/rust-lang/rfcs/pull/2966) ，他们希望在未来几周内完成。顺便说一下，在你从头开始开发自己的博客之前，团队注意到任何博客(甚至 GitHub gists)都可以。

*   **GitHub 继续照耀用户:**最近，GitHub [推出了突出开源维护者的 README 项目](https://thenewstack.io/githubs-readme-highlights-open-source-maintainers/)，本周该公司继续这一趋势，推出了 [GitHub Stars 计划](https://stars.github.com/)的[介绍](https://github.blog/2020-09-03-introducing-the-github-stars-program/)，它表示将“表彰那些超越自我的人”。或许更重要的是，他们将获得一些[额外津贴](https://stars.github.com/program/)，比如提前获得功能、活动和演讲邀请、GitHub 团队的“洞察召唤”以及“所有赠品”如果你认识一些努力工作的开发人员，你认为他们应该得到这样的认可(和津贴)，你可以继续提名他们。
*   哦，妈的，饭桶！？！要找一本充满幽默、脏话连篇的指南来处理你在使用 Git 时遇到的所有麻烦，直接去[哦，该死，Git！？！如果你不喜欢脏话连篇的说明，你也可以去。？！这两个网站都会带你经历你在使用开源分布式版本控制系统时可能会遇到的最常见的问题，但是你可以直接向下滚动到“糟糕，我不小心进入了错误的分支”，而不是依赖于你知道你所遇到的问题的正确术语比如说。](https://ohshitgit.com/)

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>