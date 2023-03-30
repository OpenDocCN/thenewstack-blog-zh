# 本周编程:重命名 Perl 会使它免于不受欢迎吗？

> 原文：<https://thenewstack.io/week-programming-renaming-perl-save-terminal-unpopularity/>

2017-11-04 06:00:13

本周编程:重命名 Perl 会使它免于不受欢迎吗？

科学，本周规划，

# 本周编程:重命名 Perl 会使它免于不受欢迎吗？

Nov 4th, 2017 6:00am by [Mike Melanson](https://thenewstack.io/author/mike-melanson/ "Posts by Mike Melanson")![Featued image for: This Week in Programming: Would Renaming Perl Save It from Terminal Unpopularity?](img/527baef36f896db397f4705f92d3020e.png)

又是新发布的一周，比如 Node.js 9 和 Angular 5.0，但我们会及时到达那里。在机器学习和数据科学领域也有一些公告，以及一系列新的 Github 功能。

然而，首先，我们将通过 StackOverflow 的另一篇伟大的、数据驱动的博客文章，回到编程语言流行的有趣的赛马中，并查看一些相关的和后续的文章，这些文章涉及在这方面的失败者之一，即将庆祝其存在 30 周年的语言——Perl。

*   因此，StackOverflow 继续它的系列文章，这一次通过查看他们更喜欢(或不喜欢)使用什么来检查成千上万开发人员的意见。这一次，它着眼于[什么是最不喜欢的编程语言](https://stackoverflow.blog/2017/10/31/disliked-programming-languages/)，恰好是(请击鼓)Perl、Delphi 和 VBA，“遥遥领先”，接下来是 PHP、Objective-C、CoffeeScript 和 Ruby。在此深入探讨之前，我们本周发现了一系列与这些发现相符的其他故事…
*   Jaxenter 也谈到了这个话题，但却关注了另一个极端，指出 [Kotlin，R 和 TypeScript 是最不受欢迎的编程语言](https://jaxenter.com/kotlin-among-least-disliked-languages-138544.html)，并向[提供了来自 RebelLabs](https://jaxenter.com/java-tools-technologies-report-rebellabs-137630.html/) 的最近一项调查,“表明 Kotlin 是最受欢迎的编程语言，他们没有错——事实证明，Stack Overflow 衡量了编程语言的受欢迎程度，并得出了相同的结论。"
*   与此同时，SDTimes 将重点放在了对 Perl 的普遍鄙视上，并补充了一些更通用的技术。最不喜欢的是 Internet Explorer、Visual Basic、Flash、COBOL、Fortran 和 Pascal，最喜欢的是机器学习、Git、Python 3.x、HTML5 和 CSS3。
*   但是为什么 Perl 如此不受欢迎呢？据本周 Perl 博客上的一位作者称，主要是因为这个名字，建议将 [Perl6 重命名为 Perl++](http://blogs.perl.org/users/vstemen/2017/10/perl6-should-be-renamed-perlplusplus.html) 。他写道，看到 Perl 让位于 Python、Ruby 和 PHP 让他很难过，他认为“Perl 形象下降的主要原因之一是用相同的名字命名了一种全新的语言。我相信将它命名为 Perl6 是对 Perl 语言最具破坏性的事情，并将继续如此。”点击阅读更多他的推理，因为本周我们将继续阅读我们自己的文章…
*   沿着这条线索，新堆栈的[大卫·卡塞尔](https://thenewstack.io/author/destiny/)(他写了一些非常有趣的故事)着眼于 Perl 的创造者[拉里·沃尔对百年编程语言](https://thenewstack.io/larry-walls-quest-100-year-programming-language/)的探索。尽管显然不受欢迎，Perl 仍然在两个月后庆祝它的 30 周年纪念。他写道，沃尔“分享了他自己的 Perl 历史，从他在 2000 年打破向后兼容性的重大决定开始，开发了一种全新的语言，称为 Perl 6——众所周知，它花了 15 年时间才最终发布了一个稳定的版本。”沃尔说，他的探索受到了计算机科学家保罗·格拉厄姆 2003 年一篇展望百年语言的文章的启发卡塞尔的帖子继续详细描述了今年早些时候沃尔和 Erlang 的创始人乔·阿姆斯特朗之间的一次谈话，我们在下文中包括:

[https://www.youtube.com/embed/SpH9BTMZKXc?feature=oembed](https://www.youtube.com/embed/SpH9BTMZKXc?feature=oembed)

视频

## 本周的节目新闻中

*   couch base Server 5.0[于](https://blog.couchbase.com/announcing-couchbase-server-5-0/)发布，提供了对“三大支柱”的更新——敏捷性和灵活性、规模化性能和可管理性。Jaxenter 在公告中介绍了[的一些细节](https://jaxenter.com/couchbase-server-5-0-138507.html)，指出了一些亮点，如“[全文搜索参考](https://developer.couchbase.com/documentation/server/5.0/fts/full-text-intro.html)和[查询计划可视化的自适应索引](https://developer.couchbase.com/documentation/server/5.0/n1ql/n1ql-language-reference/adaptive-indexing.html)，以更好地了解查询将如何执行，”以及“支持更好的大规模性能的几个新功能，包括[短暂的内存桶](https://developer.couchbase.com/documentation/server/5.0/architecture/core-data-access-buckets.html)和 [N1QL 查询性能增强](https://developer.couchbase.com/documentation/server/5.0/performance/index_pushdowns.html)，如索引下推优化。”新的 Couchbase 服务器 5.0 可在[官方网站](https://www.couchbase.com/downloads)或通过 [Docker 容器](https://hub.docker.com/_/couchbase/)获得。
*   微软即将推出的 Visual Studio 2017 版本 15.5 IDE 的第二个测试版于本周发布，Infoworld 关注了[的新功能](https://www.infoworld.com/article/3235286/application-development/whats-new-in-microsofts-visual-studio-2017.html)，包括 C++和调试的改进功能，以及对 [Angular 2 JavaScript 框架](https://www.infoworld.com/article/3120314/javascript/googles-angular-2-javascript-framework-finally-arrives.html)的支持。Visual Studio 15.5 预览版[可供下载](https://www.visualstudio.com/vs/preview/)。
*   Programmable Web 警告 iOS 应用程序开发者，苹果希望开发者尽快更新 iPhone X 的应用程序，因为这款手机将于本周发布，包括“将极大影响应用程序性能的硬件重大变化。”
*   SDTimes 写道， [Angular 5.0 现已推出](https://sdtimes.com/angular-5-0-now-available/)，称其为“移动和桌面框架的一个重大发布”，“专注于使 Angular‘更小、更快、更易用’。”“公告的全部细节在[棱角分明的博客](https://blog.angular.io/version-5-0-0-of-angular-now-available-37e414935ced)上。
*   另一篇来自 SDTimes，关于 [IBM 宣布推出一个新平台，将云原生功能引入私有云](https://sdtimes.com/ibm-announces-new-platform-bring-cloud-native-capabilities-private-cloud/)。新平台“使公司能够构建类似于公共云的内部云功能，并加速应用程序开发”，并且“建立在基于 Kubernetes 的容器架构上，支持 Docker 容器和 Cloud Foundry。”
*   本周 Node.js 领域有两条新闻，第一条是 Node.js v8 获得长期支持，新堆栈的 Michelle Gienow 表示“这是一个大新闻，特别是对于那些对 v8 相对于之前的 LTS V6 的显著性能改进感兴趣的大型企业用户来说。“接下来， [Node.js 9 可用于初始测试](https://jaxenter.com/node-js-8-lts-node-js-9-is-here-138535.html)，尽管还没有为生产做好准备。到目前为止，新版本处理了“遗留 API 的贬值或移除”和一个新的错误系统，该系统将给所有错误一个唯一的代码。
*   最后，GitHub 发布了几个公告，包括新的开发者社区论坛[和市场免费试用](https://sdtimes.com/github-community-forum-marketplace-trials/)，它们最初是在上个月的 GitHub Universe 上发布的。第一组项目自动化事件包括[自动更新您的项目板的能力](https://github.com/blog/2458-keep-your-project-boards-up-to-date-automatically)，并且论坛将“提供操作方法、提示和技巧，用户将根据他们对社区的贡献和专业知识的水平进行排名。”至于 [GitHub Marketplace 免费试用](https://github.com/blog/2456-introducing-github-marketplace-free-trials)，用户可以获得“14 天的时间来试用六个精选的特色应用程序，熟悉市场并将应用程序集成到他们的工作流程中。”

## 在本周的机器学习和数据科学中

*   首先，Kaggle 通过对超过 16，000 份回复的调查，展示了数据科学和机器学习的现状。调查结果显示，Python 仍然是最常用的工具，但统计学家更喜欢 r。此外，普通数据科学家的平均年龄约为 30 岁，令人惊讶的是，大多数人都有硕士学位，收入相当可观。该公司“在 Kaggle 上分享了完整的匿名数据集，供你下载和探索”
*   谷歌的移动平台 Firebase 获得了一些[新的机器学习能力](https://sdtimes.com/google-announces-new-machine-learning-capabilities-firebase/)“专注于加强 Firebase 服务的集成，并将更多的机器学习技术纳入工具包。”其中包括 Crashlytics by Fabric 的集成、整体 UI 和控制台大修、新的 A/B 测试框架以及 Firebase 预测，后者使用机器学习来测量分析并根据预测的行为对用户进行分组。
*   最后，Redmonk 研究了 NVidia 在[简化通用深度学习框架](http://redmonk.com/fryan/2017/10/30/packaging-deep-learning-nvidia-simplifies-working-with-common-deep-learning-frameworks/)方面的举措。因此，他们说“对于在 AWS 上从事深度学习的人来说，生活变得更容易了。”NVidia 的深度学习堆栈是“一套精心策划的软件，以容器的形式分发，他们计划向各种云提供商的 GPU 终端用户提供这些软件。这些云产品中的第一款[于本周](https://nvidianews.nvidia.com/news/nvidia-launches-ai-cloud-container-registry-to-accelerate-deep-learning-volta-gpus-debut-on-amazon-web-services)发布，同时[NVIDIA Tesla V100 GPU 在 AWS](https://aws.amazon.com/blogs/aws/new-amazon-ec2-instances-with-up-to-8-nvidia-tesla-v100-gpus-p3/) 上发布。

特色图片:演员尼古拉斯·凯奇在 1997 年的电影《脸/关》[。](https://www.amazon.com/Face-Off-John-Travolta/dp/630512762X)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>

TNS 的所有者 Insight Partners 是新堆栈 Docker 的投资者。

新堆栈更新一份时事通讯摘要，对本周最重要的新闻进行分析&。

新的堆栈不会出售您的信息，也不会与无关的第三方共享。如果继续，您同意我们的

[Terms of Use](/terms-of-use/)

和

[Privacy Policy](/privacy-policy/)

.