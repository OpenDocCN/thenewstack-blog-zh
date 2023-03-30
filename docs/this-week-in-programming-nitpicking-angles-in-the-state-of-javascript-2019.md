# 本周编程:在 JavaScript 2019 年的状态中吹毛求疵

> 原文：<https://thenewstack.io/this-week-in-programming-nitpicking-angles-in-the-state-of-javascript-2019/>

另一项调查，另一个指出一切都是错的机会。本周进入互联网上每个人都在挑毛病的调查类别的是 JavaScript 2019 的[状态，这是由](https://2019.stateofjs.com/)[Sacha Greif](https://twitter.com/sachagreif)和[raphal benitet](https://twitter.com/benitteraphael)进行的年度调查。在调查的技术区别方面，似乎有一个特别的问题对许多观察者来说是成立的——角度和角度之间的区别(或缺乏区别)。

最初的 AngularJS 和随后的 Angular 2 和 Angular 4 JavaScript 框架之间有一个很大的差异。AngularJS 最初是由 Google 在 2009 年作为一个开源的、基于 JavaScript 的框架发布的，用于动态前端 web 应用程序开发，而 Angular 2 和向后兼容的后续产品 Angular 4 都是开源的、基于 TypeScript 的前端 web 应用程序平台。虽然 Angular 2 和 Angular 4 现在通常仅被称为“Angular”，但许多人指出，调查中缺乏区分导致了数字的不公平倾斜。

在关于该主题的一个 [GitHub pull 请求](https://github.com/StateOfJS/StateOfJS-Vulcan/issues/26)中，开发者 [Suguru Inatomi](https://github.com/lacolaco) 写道“这是不公平的，因为 1)关于 Angular/AngularJS 的命名约定还不为人所知。2)许多开发人员在几年前就有 AngularJS-only 的经验 3)因此,“使用它>会避免”加薪是很自然的。4)即使他们有过棱角分明的经历，也不清楚调查询问的是哪种棱角分明。”

查看围绕 Angular 的调查数字，New Stack 分析师 [Lawrence Hecht](/author/lawrence-hecht/) 指出，在 2017 年和 2018 年 JavaScript 调查状态之间，“以前使用 Angular 但不会再次使用它的人”数量大幅下降，数字从 10%跃升至 40%——这一跃升与引入术语“Angular”的时间有关，因为它指的是 Angular 2，而不是 AngularJS。

与此同时，Hecht 指出，2019 年 [StackOverflow 调查](https://insights.stackoverflow.com/survey/2019)和 [JetBrains 调查](https://www.jetbrains.com/lp/devecosystem-2019/)展示了措辞对最终结果的影响。在 JetBrains 的调查中，23%的 JavaScript 开发人员经常使用 Angular，这与 JavaScript State 报告中发现的 22%的人使用“Angular 并会再次使用”类似。但 JetBrains 也询问了 AngularJS，47%的 AngularJS 用户也表示他们使用较新的 Angular。总的来说，总的“角度和/或角度”与 StackOverflow 研究中报告的相似。

Hecht 认为，给定正确的上下文，JavaScript 报告的状态实际上似乎是有棱角的开发者的代表，并没有受到独特的样本偏差的过度影响。因此，抛开措辞不谈，Hecht 指出，所有这些都掩盖了一个事实，即 Angular 已经准备好搭上 TypeScript 崛起的顺风车，这是一个正式类型的 JavaScript 超集，在[非常火](https://2019.stateofjs.com/images/captures/typescript_experience.png)，86%计划继续使用 TypeScript 的人也计划继续使用 Angular。

与此同时，软件工程师和博客作者 Laurie Blarth 指出，数据存在一个主要问题，这可能比其他任何事情都更容易扭曲数据——男性占压倒性优势！

Blarth 随后指出，她故意使用“令人不安”这个词，而不是“令人惊讶”——因为，事实上，科技领域对女性的排斥仍然是一件令人不安但并不令人惊讶的事情。

## 本周的节目中

*   **一个关于鸡蛋和篮子的说法……**本周早些时候， [The Information 报道](https://www.theinformation.com/articles/google-brass-set-2023-as-deadline-to-beat-amazon-microsoft-in-cloud)谷歌高管将 2023 年定为在云领域击败亚马逊和微软的最后期限，根据 2018 年初关于此事的一次对话的报道。报告称，从本质上讲，如果该公司的云产品达不到第二名，谷歌将考虑取消其云产品。当然，谷歌[以扼杀产品](https://killedbygoogle.com/)而闻名，所以这个“新闻”对许多人来说并不意外，尽管许多[其他人](https://news.ycombinator.com/item?id=21819078)已经站出来争论这样一份报告的优点。所以，你知道了——这是“多重云”存在的另一个原因，它是唯一一个描述必然状态而非理想状态的流行词。

*   **GitLab 展望合并请求的未来:**对于 GitLab 的用户来说，现在是时候开始为合并请求的未来[带来实时协作了。该公司正在寻求对其所说的“可能是](https://about.gitlab.com/blog/2019/12/19/future-merge-requests-realtime-collab/)[合并请求](https://docs.gitlab.com/ee/user/project/merge_requests/)和[代码审查](https://about.gitlab.com/direction/create/code_review/)的未来”的反馈，这可能包括许多功能，从在线指示器到在你离开时了解发生了什么的功能。但是不要相信我们的话——查看完整的博客帖子或视频，了解一些潜在新功能的完整概述。

[https://www.youtube.com/embed/KpdvIU6hv94?feature=oembed](https://www.youtube.com/embed/KpdvIU6hv94?feature=oembed)

视频

*   **GitLab 将可观察性转移到核心:**正如你可能知道的，GitLab 基于开放核心模式运行，本周该公司宣布[将他们的可观察性套件转移到核心](https://about.gitlab.com/blog/2019/12/16/observability/)，这意味着[的可观察性功能](https://about.gitlab.com/blog/2019/08/29/monitoring-team-update/)如自定义指标、日志记录、跟踪和警报都将在 2020 年从其专有代码库转移到开源代码库，你可以跟随[的进度](https://gitlab.com/groups/gitlab-org/-/epics/2310)。
*   **JetBrains 为 Android Studio 带来 iOS 支持:** InfoWorld 报道称 [JetBrains 通过一个插件为 Android Studio 带来 iOS 设备支持](https://www.infoworld.com/article/3509457/jetbrains-bringing-ios-device-support-to-android-studio.html)，该插件将允许开发人员在 iOS 设备和模拟器上运行、测试和调试 Kotlin 应用程序。该插件将于 2020 年在 preview 中推出，尽管它不会为 Swift 或 Objective-C 提供语言支持，但它将让您的 Android 优先开发人员在您首选的 ide 中测试 iOS 兼容性。

*   **Julia 对于数据科学来说速度更快吗？** Julia 是一种据说可以做所有事情的语言，本周在《走向数据科学》上的一篇博客文章询问它是否可以做所有事情，并且比数据宠儿 Python 更快。好吧，如果 Julia 是否比 Python 更快的问题困扰着你，那就直接过去吧，因为他们做了一些基准测试，甚至将 Julia 与“某种优化/矢量化的 Python 代码(如 Numpy 函数使用的代码)”进行比较正如他们所写的，“Numpy 非常快”，但“当复杂的逻辑被引入计算问题时，Julia 得分更高。”去了解所有的细节。
*   **2020 年的 IntelliJ:**不，这不是一个竞选口号——JetBrains 已经提供了一个[2020 年的 IntelliJ 平台路线图](https://blog.jetbrains.com/idea/2019/12/intellij-platform-roadmap-for-2020/)，它强调了该公司在未来一年对其 IDE(以及基于 IntelliJ 平台的其他产品)的设想。他们写道，这些变化“围绕两个主题:性能和对现代开发工作流的支持。”早在 2020 年第一次发布时，他们就表示，他们希望针对索引性能、UI 冻结、无需重启即可加载和卸载插件以及支持云执行和协作编辑等问题。如果这还不够，他们说“这篇文章中描述的努力只是我们团队工作的一小部分，我们计划在假期后发布更多关于我们计划的信息”，所以我们将密切关注接下来的事情。

*New Stack 分析师 Lawrence Hecht 对此文有贡献。*

特征图片[通过](https://freerangestock.com/photos/120550/businessman-on-top-of-ladder-overlooking-manhattan.html)散养。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>