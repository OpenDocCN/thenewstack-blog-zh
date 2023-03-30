# 本周编程:建造空中楼阁

> 原文：<https://thenewstack.io/this-week-in-programming-building-castles-in-the-air/>

本周，由受人尊敬的行业观察家 [Adrian Coyler](https://twitter.com/adriancolyer) 撰写的关于[程序、生命周期和软件进化法则](https://blog.acolyer.org/2020/02/14/programs-life-cycles-laws/)的博客文章让我想到了糟糕的应用程序实现和计算机编程本身的本质。科勒的[晨报博客](https://blog.acolyer.org/)定期审查当代关于计算的学术论文，但本周他总结了一篇 1980 年的论文，他说这篇论文“和以前一样新鲜和相关”

“这篇论文的主旨，”Coyler 写道，“是将我们的思维从编程/软件开发/软件工程转变为我们创建一个时间点程序来实现给定过程的过程，而是开始关注一个程序(软件系统)作为一个随着时间推移而发展的实体。”

本质上，本文着眼于整个软件生命周期，将其分解为离散或抽象的表示，要么描述现实，要么描述其中的某些条件。这是一些令人兴奋的东西，正如科伊勒指出的，你真的可以思考一会儿——例如，程序的定义:“任何程序都是世界的某个部分或话语的某个宇宙的抽象模型的理论中的模型的模型。”

[https://www.youtube.com/embed/mNA2PBA6yrQ?feature=oembed](https://www.youtube.com/embed/mNA2PBA6yrQ?feature=oembed)

视频

更具体地说，本文将程序分为三种基本类型，S 程序、P 程序和 E 程序。Croyler 说，s 程序是“教科书喜欢的那种程序”，而 P 程序“是现实世界的问题解决方案，并带我们进入‘理论中的模型的模型’……领域”，而 E 程序“是‘机械化人类或社会活动’的程序”，并有现实世界的反馈回路。该论文断言“总是有可能继续(E-或 P-程序的)系统划分过程，直到所有模块都可以作为 S-程序实现。”

我们为什么要探索这些想法？嗯，它们都归结于我们如何对待一个程序相对于一个整体项目，以及我们如何将我们的焦点应用到更大的应用程序的这些更离散的单元。我们是否将应用程序视为在某个时间点存在的单一事物？有哪一天会完整而静止？或者我们把它看作是沿着变化的轴线不断移动的东西？

该论文接着提供了“程序进化法则”，Coyler 说，该法则可以用来指导软件的长期规划过程。

这甚至关系到程序员到底在做什么的本质，这篇论文和 Coyler 本人都试图给出这个定义:

程序员是做什么的？根据 Lehman 的说法，程序员的任务是“陈述一种算法，该算法正确而明确地定义了一种机械过程，以获得给定问题的解决方案。”虽然如果我必须为“程序员”写一个魔鬼字典条目，那么我会忍不住写一些更像这样的东西:“有人建造空中楼阁，以各种各样和邪恶的格式争论数据，在永无止境的寻求对齐中摆弄 CSS，并在迷宫中导航。”

不管你们开发人员做什么，至少我们知道我们通常能在人群中找到你们。

## 本周的节目中

*   **GitHub 命令行界面出现！**这是一场与 Windows 和 DOS 一样古老的斗争——希望超越 GUI 及其有限的功能，使用命令行，能够做任何你想做的事情……只要你能记住所有的命令。好吧，对于那些喜欢命令行界面(CLI)的 GitHub 用户来说，今天是你们的日子，因为 GitHub[宣布](https://github.blog/2020-02-12-supercharge-your-command-line-experience-github-cli-is-now-in-beta/)GitHub CLI 现在处于测试阶段，可以在 [macOS、Windows 和 Linux](https://github.com/cli/cli#installation-and-upgrading) 上使用。目前，CLI 提供的功能有限，但是它可以处理基本的功能:创建拉请求、检查拉请求、查看问题的详细信息等等。要了解全部细节，请查看[手册](https://cli.github.com/manual/)或浏览[介绍性博客文章](https://github.blog/2020-02-12-supercharge-your-command-line-experience-github-cli-is-now-in-beta/)，其中提供了示例。由于该项目仍处于测试阶段，GitHub 正在寻求您的反馈，要么在[开源库](https://github.com/cli/cli)中创建一个问题，要么通过[谷歌表单](https://forms.gle/umxd3h31c7aMQFKG7)提供反馈。
*   **GitHub 进军印度:**对于那些居住在印度的 GitHub 用户来说(根据博客帖子，GitHub 上活跃的第三大开发者群体)，GitHub 已经[推出了 GitHub 的子公司 GitHub India](https://github.blog/2020-02-12-announcing-github-india/) 。新成立的子公司将有助于迎合那里快速增长的社区，GitHub 表示，社区已经发展到“超过 1 亿个项目的 4000 多万名开发者”作为发布的一部分， [GitHub Education](https://education.github.com/students) 还将把 [GitHub Hackathon Grant](https://mlh.io/event-membership#hackathongrant) 项目扩展到印度的学生，该公司的渠道合作伙伴项目也将扩展到印度。若要更密切地关注，请在 Twitter 上关注 [@GitHubIndia](https://twitter.com/GitHubIndia) 。
*   **GitHub Enterprise 免费版& Enterprise Server 2.2:** 上一篇 GitHub news 本周，该公司宣布 [GitHub Enterprise 现已通过微软免费提供给初创公司](https://github.blog/2020-02-13-github-enterprise-is-now-free-through-microsoft-for-startups/)，这是一个免费程序，帮助初创公司提供服务、软件和其他好处，您可以[在此申请](https://startups.microsoft.com/en-us/)。参与者每月可获得 1000 美元的 GitHub 企业云积分，有效期长达两年。说到企业， [GitHub Enterprise Server 2.2 推出了](https://github.blog/2020-02-11-github-enterprise-server-2-20-is-here/)，它带来了扩展的分支保护规则、个人审计日志页面，以及管理员运行[可选迁移脚本](https://help.github.com/en/enterprise/2.20/admin/installation/migrating-to-internal-repositories)将所有公共存储库转换为内部存储库的能力。

*   那么，你想得到报酬吗？如果你想找一份编程的工作，了解雇主最需要的语言可能会有所帮助，CodingDojo 根据搜索[和](https://www.indeed.com/)的结果列出了 2020 年[七大编程语言](https://www.codingdojo.com/blog/top-7-programming-languages-of-2020)。正如他们所指出的，这份名单“并不反映一种语言的效率或学习的难易程度，而是招聘者在寻找哪种语言”。毫不奇怪，Python 和 JavaScript 的进步最大，Python 超越 Java 成为第一名，JavaScript 也升至第三名。点击至查看全部细节。如果你已经对 JavaScript 了如指掌，这篇关于 ECMAScript 生态系统的指南当然值得一看。
*   **TypeScript 3.8 RC:** 说到 ECMAScript 生态系统，TypeScript 有一个 TypeScript 3.8 的[发布候选版本，而](https://github.com/microsoft/TypeScript/releases) [InfoWorld 有一篇关于新增内容的文章](https://www.infoworld.com/article/3513938/typescript-38-release-candidate-arrives.html)。请放心，它们大多与各种形式和时尚的类型有关。预计将于本月晚些时候或三月初正式发布。

https://Twitter . com/mooncodeflow/status/1227747384765112321

*   不管怎样，Git 是从哪里来的？软件版本控制的世界已经走过了漫长的道路。如今，GitHub 和 GitLab 已经远远超出了最初的设想，称它们为“软件版本控制”是一个非常有限的术语，并不真正适用。为了了解我们的根源，我向你提交了一篇本周在 feeds 上看到的文章，这篇文章回顾了 Git 的历史，跟踪了该项目从 Linus Torvalds 在 2005 年创建到 GitHub 在 2018 年被微软收购的整个过程。
*   **USB 充电器(理论上)可以带我们去太空:**这只是“我们在计算世界已经走了很远”的故事中的另一个小故事，比较了[阿波罗 11 号制导计算机与 USB-C 充电器](https://forrestheller.com/Apollo-11-Computer-vs-USB-C-chargers.html)。你放在那的手机充电线？根据这个快速的小比较，其中只有四个可能有足够的计算能力来复制阿波罗 11 号制导计算机。“我认为比较历史和现代计算是有益的，”作者写道。“让我们看看最近的 USB-C 壁式充电器中包含的 CPU 与阿波罗 11 号制导计算机(AGC)的功率相比如何。阿波罗 11 号宇宙飞船在 1969 年载着 3 个人去月球并返回。剧透一下，Anker PowerPort Atom PD 2 USB-C 壁式充电器 CPU 被发现比阿波罗 11 号制导计算机快 563 倍，内存是它的两倍，所以，在你责怪硬件的局限性之前，请记住这一点。

照片由谢尔盖·贝洛泽罗夫从 Pixabay 拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>