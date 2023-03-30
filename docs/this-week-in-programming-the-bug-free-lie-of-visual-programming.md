# 本周编程:可视化编程的无错误谎言

> 原文：<https://thenewstack.io/this-week-in-programming-the-bug-free-lie-of-visual-programming/>

闪回时间:那是 1984 年，你刚刚尽职尽责地花了整整 45 分钟键入《发现》杂志封底的基本源代码，屏息期待着一款游戏，一旦你键入 RUN，它就会出现在你的眼前……而你得到的只是一个语法错误。

这是你的红药丸或蓝药丸时刻。你决定埋头苦干，找出错误，让游戏运行起来，或者你说“见鬼去吧”,然后做点什么，除了给电脑编程以外的任何事情。

正如计算机先驱莫里斯·威尔克斯所说，“当我们开始编程时，我们惊奇地发现，让程序正确运行并不像我们想象的那么容易。调试必须被发现。我清楚地记得，从那时起，我意识到我生命中的很大一部分时间都将花在寻找自己程序中的错误上。”

现在，我们已经领先了几光年，ide 可以帮助我们突出语法错误，并预先警告我们任何编译时的错误，甚至在我们键入时建议代码，但我们仍然接受调试是并将永远是编程职业的一部分是这项工作的一个重要方面。

本周，“巡回开发者”[迈克·哈德罗](http://mikehadlow.com/)对可视化编程提出异议——主动向[解释为什么这是个坏主意](https://mikehadlow.blogspot.com/2018/10/visual-programming-why-its-bad-idea.html)——集中在几个“关于编程的误解”上在第一次出版时，哈德罗引用了麻省理工学院的 Scratch 作为他的主要例子，并将其作为特征图像，许多读者对这一事实提出异议，认为 Scratch“在编程教学中非常有用，特别是对儿童。”

“任何让更多人了解精彩和激动人心的编程世界的东西都是值得庆祝的，”哈德罗在一次编辑中提出，以缓解读者的愤怒，但我想说的是，Scratch 缺乏你作为程序员必须知道的一件事——你必须处理 bug。见鬼，你甚至应该享受与虫子打交道的乐趣。你应该很快发现自己哪里错了。我觉得，如果一些错误阻止了你坚持到底，那么无论如何这都是错误的。

与此同时，很难不同意 Reddit 的一条评论[认为“你应该让初级程序员考虑算法的结构，而不是分号放在哪里。”](https://www.reddit.com/r/programming/comments/9kgk75/visual_programming_why_its_a_bad_idea/e6yvj21/)

尽管如此，让某人努力学习编程而不知道这是他们将要进入的领域，这似乎是不诚实的——在这个领域，错放的分号和打错的单词可能会导致更大的问题；在这种情况下，即使是你认为不需要在意的细节也可能是最重要的。

或者，也许人工智能会处理所有这些错误，像 Scratch 这样的无 bug 可视化编程工具非常适合新一代的开发人员。语法和编译错误将成为过去，AI 将成为易于编程的未来潮流。

好吧。拥有你的可视化编程教学工具。享受生活的训练轮上和保龄球保险杠保护你免受排水沟球。也许你会学着喜欢编程，然后，当轮子被拉下来，保险杠被拿掉，你就不会害怕地尖叫着跑了。

记住这一点，看一看(如果你还没有看过的话)这个绝对荒谬的“视觉编程”是在《我的世界》创造一个完全可玩的神奇宝贝红色版本。(对于不耐烦的人，我会说[跳到大约 10 分钟的标记](https://youtu.be/H-U96W89Z90?t=600)，在他们潜入游戏中的兔子洞之前看一点可玩的游戏，这是游戏中的游戏编程。)

[https://www.youtube.com/embed/H-U96W89Z90?feature=oembed](https://www.youtube.com/embed/H-U96W89Z90?feature=oembed)

视频

## 本周的节目中

*   **KotlinConf 2018 总结:**首先， [KotlinConf 2018](https://kotlinconf.com/) 本周发布了一系列公告，这些公告在[一篇由 Jet Brains](https://blog.jetbrains.com/kotlin/2018/10/kotlinconf-2018-announcements/) 撰写的博客中进行了简洁的总结。在这些公告中有一个 Kotlin 1.3 候选版本，该公司称其“带来了大量新的特性和功能”，包括协程和多平台项目。此外，JetBrains 和 Google 已经正式宣布了之前宣布的 Kotlin 基金会，该基金会旨在“保护、促进和推动 Kotlin 编程语言的发展”并“确保 Kotlin 作为自由软件的开发和发布。”如果你真的觉得错过了什么，一定要看看 YouTube 上九个半小时的会议视频[——不包括咖啡和午餐。](https://youtu.be/_yaaCtWF8aE)
*   **PyTorch 开发者预览:**正如 SDTimes 所说，随着本周脸书宣布 PyTorch 1.0 的新合作伙伴和生产能力，PyTorch 社区正在[慢慢接近 1.0 版本](https://sdtimes.com/ai/pytorch-community-inches-closer-to-1-0-release/)。“从研究原型到生产部署的一切深度学习平台”不仅得到了脸书的支持，还得到了微软、谷歌和硬件制造商 ARM、IBM、英特尔、英伟达和高通的支持。PyTorch 1.0 的[开发者预览版](https://pytorch.org/get-started)现已可供下载，而 [PacktPub](https://hub.packtpub.com/production-ready-pytorch-1-0-preview-release-is-here-with-torch-jit-c10d-distributed-library-c-api/) 不仅提供了新内容的深度挖掘，还提供了项目的难点所在。

*   **语言排名的混乱:**在一篇我非常关心的文章中，TechCrunch 问[编程语言的流行到底是怎么回事？](https://techcrunch.com/2018/09/30/what-the-heck-is-going-on-with-measures-of-programming-language-popularity/)看一看两个最受欢迎的编程语言排名——[TIOBE 指数](https://www.tiobe.com/tiobe-index/)和 [PYPL 指数](http://pypl.github.io/)——他们发现这些排名似乎奇怪地不协调。“现在的情况是，这两个指数有非常不同的方法，”他们解释说。TIOBE 测量搜索引擎点击量。PYPL 测量了语言教程被谷歌搜索的频率。两者都是糟糕的措施。我们可以预期在线资源的可用性是一个非常滞后的指标；一种曾经占主导地位的死亡语言很可能仍然有数百万专门针对它的残余网页、僵尸网站和多年无人阅读的博客帖子。教程搜索的频率将非常偏向于大量教授给学生的语言。这并不是衡量从业者实际使用哪种语言的有意义的方法。”这似乎是我们在未来研究语言排名时需要记住的事情。
*   **GitHub 升级 Rails 的尾巴:** GitHub 为我们带来了它的故事[GitHub 从 Rails 3.2 升级到 5.2](https://githubengineering.com/upgrading-github-from-rails-3-2-to-5-2/) ，总共花了一年半的时间，给他们提供了一路上学到的许多经验教训，他们很乐意分享。这些经验包括:尽早并经常升级，经常解决技术债务，如果可以的话增量升级，避免使用自己的工具和私有 API。请继续阅读，了解更新 10 年代码库的更多经验和细节。
*   MS-DOS 进入 GitHub: 最后，本周的一点新闻并没有真正改变什么，但看起来很有趣:微软[通过](https://blogs.msdn.microsoft.com/commandline/2018/09/28/re-open-sourcing-ms-dos-1-25-and-2-0/)[将 MS-DOS 1.25 和 2.0](https://github.com/microsoft/ms-dos) 加入 GitHub 重新开源。“为什么？因为如果 MS-DOS 源文件在 GitHub repo 中，比在原始的可下载压缩存档文件中更容易找到、阅读和引用。”根据这篇博文，这两个版本的源代码都是在 1983 年完全用 8086 汇编代码编写的，而 DOS 1.25 只有 7 个文件，DOS 2.0 则激增至 100 个文件。想象一下！

由 Alyssa Stevenson [通过](https://unsplash.com/photos/slpibXIhizI) Unsplash 拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>