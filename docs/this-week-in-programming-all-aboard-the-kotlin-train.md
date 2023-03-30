# 本周节目:所有人登上科特林火车

> 原文：<https://thenewstack.io/this-week-in-programming-all-aboard-the-kotlin-train/>

在享受了几年草根流行之后，看起来由 [JetBrains](https://www.jetbrains.com/) 开发的开源 Java 替代品 Kotlin 已经成功了。

如果你错过了新闻，快速回顾一下，谷歌[上周在其谷歌 I/O 开发者大会上正式宣布](https://android-developers.googleblog.com/2019/05/google-io-2019-empowering-developers-to-build-experiences-on-Android-Play.html) Kotlin 为 Android 开发的首选语言，该公司正在通过几项举措支持这一点，使大多数 Android 开发者现在使用的语言更容易(和免费)学习。为此，[谷歌与 Udacity](http://android-developers.googleblog.com/2019/05/new-learn-how-to-build-android-apps.html) 合作，提供[使用 Kotlin](https://www.udacity.com/course/developing-android-apps-with-kotlin--ud9012) 开发 Android 应用，这是一门免费的、自定进度的在线课程，介绍如何使用 Jetpack 和 Kotlin 构建 Android 应用，面向有编程经验并且熟悉 Kotlin 基础知识的人。谷歌还宣布了“ [Kotlin/Everywhere](http://everywhere.kotlinlang.org/) ，这是一系列社区驱动的活动，重点关注 Kotlin 在所有平台上的潜力，”它将与 JetBrains 联合举办。

当然，这就留下了之前被问了很多次的问题——为什么是科特林？——IT 顾问克里斯汀·卡特(Kristen Carter)就 Android 应用程序开发如何成为 Kotlin-first 发表了看法。

卡特提供了一些商业角度，例如 2010 年甲骨文对谷歌的诉讼，这比科特林早了一年，她推测这可能是该语言发展背后的推动力，因为“谷歌一直想摆脱(Java)生态系统。”与此同时，Carter 也提供了一些特定于语言的推理，比如 Kotlin 相对简洁的本质，没有 Java 的 NullPointerExceptions，以及 Java 开发人员可以轻松过渡到 Kotlin。卡特在文章的结尾提出了一种可能性，即甲骨文“知道 Java 在 android 应用程序开发中的重要性”，并可能“在下一版本中对 Java 进行一些升级，以应对科特林。”

与此同时，Android 开发者 [Lemuel Ogbunude](https://dev.to/lemuelogbunude) 写道“[有趣的 Java 与 Kotlin 之争](https://dev.to/lemuelogbunude/the-funny-java-vs-kotlin-battle-492m)”，评论道“在我看来，Java 和 Kotlin 之间不断的争斗是非常不必要的。”

记住卡特最后的思考，Ogbunude 提出，许多 Java 和 Kotlin 的比较都是在检查错误的 Java 版本，而且“看到 Java 12 代码，可能会误认为它是 Kotlin，这就是 Java 改进的程度。”

当我们都忙着跳上科特林的火车时，我们也可以提醒自己，评论家永远不会远离，看看这篇关于[为什么科特林很烂](https://proandroiddev.com/why-kotlin-sucks-ab27a6b15cb6)的文章，它显然是基于一个维基百科的[为什么你喜欢的语言都很烂](https://wiki.theory.org/index.php/YourLanguageSucks)。为此，Ogbunude 的那句话应该是许多开发人员的口头禅:“作为一种语言的爱好者不应该让你成为另一种语言的敌人。”

所以跳上车，跳下车，也许带上一些袋装的爪哇咖啡——做任何能让你到达那里的事情；这才是真正重要的，对吧？与此同时，如果你对 Kubernetes 的这些新玩意感到困惑，让凯尔西·海托华为你解释一下。

[https://www.youtube.com/embed/9OHNejqXOoo?feature=oembed](https://www.youtube.com/embed/9OHNejqXOoo?feature=oembed)

视频

## 本周的节目中

*   **GitLab 对 GitHub 的包注册表的精辟反驳:**这很有趣，因为你经常可以在该公司最近的许多公告之后谈论 GitLab 对 GitHub 的精辟反驳。GitLab 似乎经常说“哦，是的，我们已经做了很多年了…这个怎么样？”这也是该公司对 GitHub 上周在[发布的](https://github.blog/2019-05-10-introducing-github-package-registry/) [GitHub 包注册处](https://github.com/features/package-registry)的声明所说的话，“这是一种包管理服务，可以很容易地在你的源代码旁边发布公共或私有包。”GitHub 的包注册表，如果你没有听说过，可以与 npm，Maven，RubyGems，NuGet 和 Docker 镜像一起工作，更多的配对即将到来，目前可以在 beta 版中使用。“自 2012 年将 CI 与 SCM 结合以来，GitLab 一直在为整个 DevOps 生命周期构建单一应用，”GitLab 在博客文章中写道，“并在 2016 年发布了集成打包——从 Docker 注册表开始——并在 2018 年添加了 Maven 和 NPM。”不甘示弱的是，该公司还指出，它“也在着手通过依赖代理[使软件包管理对软件包用户来说更加安全和可审计。”除了两家公司之间的来回，一位开发者博客作者提供了他们对移动的看法，写道他们认为开发不仅仅是易用性或“买入”“正如我们在 NPM 看到的，信任一个包(以及谁实际上发布了它)最近已经咬了 NPM 的用户，”他们写道。“通过将源代码与包的公开绑定，这可能有助于我们(作为一个社区)更容易地找到坏的包所有者(因为我们可以看到代码差异中的所有权)。不过，我可能是错的。”](https://about.gitlab.com/direction/package/dependency_proxy/)

[https://www.youtube.com/embed/0JUgBBynPdU?feature=oembed](https://www.youtube.com/embed/0JUgBBynPdU?feature=oembed)

视频

*   **GitLab、GitHub、BitBucket 联手对抗勒索软件:**你现在肯定已经听说了，但是本月早些时候，有消息称黑客[清除了 Git 仓库并持有它们以勒索赎金](https://www.zdnet.com/article/a-hacker-is-wiping-git-repositories-and-asking-for-a-ransom/)。那么，GitHub、GitLab 和 BitBucket 已经在[发表了一篇关于整个磨难的联合博文](https://about.gitlab.com/2019/05/14/git-ransom-campaign-incident-report-atlassian-bitbucket-github-gitlab/)，试图“帮助教育和告知这三个平台的用户关于安全的最佳实践”，并指出“没有证据表明 Atlassian Bitbucket、GitHub 或 GitLab 产品受到了任何损害。”最终，这似乎都归结于用户端的不安全做法，这使得他们的登录凭证受到损害，因此这三家公司都建议一个简单的解决方案——对真正重要的事情使用双因素身份认证——例如 Git 存储库中的所有代码。如果你想知道这一切是如何发生的全部细节，请继续阅读。

*   **锈转 4！**Rust 编程语言本周庆祝[Rust 四年](https://blog.rust-lang.org/2019/05/15/4-Years-Of-Rust.html)和五年的“开放开发”(以及之前几年的草图)，于 2015 年 5 月 15 日首次发布。虽然该团队将其对语言向后兼容性的承诺归功于现在看起来与过去没有太大不同，但它也表示，它正在以前所未有的速度前进和增长，并指出它已经连续四年成为 StackOverflow 的[“最受欢迎的编程语言】](https://insights.stackoverflow.com/survey/2019#most-loved-dreaded-and-wanted)，拥有“稳定 Rust 的全新开发领域:[嵌入式开发](https://www.rust-lang.org/what/embedded)”，更不用说最近发布的 [Rust 2018](https://blog.rust-lang.org/2018/12/06/Rust-1.31-and-rust-2018.html) 。对于 Rust 用户，请注意[版本 1.34.0 和 1.34.1 受到一个可能导致内存不安全的漏洞](https://hub.packtpub.com/rusts-recent-releases-1-34-0-and-1-34-1-affected-from-a-vulnerability-that-can-cause-memory-unsafety/)的影响，这个问题已由最新版本 [Rust 1.34.2](https://blog.rust-lang.org/2019/05/14/Rust-1.34.2.html) 解决，所以现在就去获取它吧！
*   **AWS Lambda 获得 Node 10:** 亚马逊[将在其](https://devclass.com/2019/05/14/aws-lambda-supports-node-js-v10/) [AWS Lambda](https://aws.amazon.com/lambda/) 无服务器产品中添加对 Node.js v10 的支持，以及最新一代的亚马逊 Linux，亚马逊 Linux 2。正如 [DevClass](https://devclass.com/) 在其新闻报道中指出的，Lambda 现在支持两个 Node.js 运行时，Node.js 8.10“处于 Node.js 支持生命周期的维护阶段，并将于 2019 年底结束生命周期，而 v10 目前处于长期支持(LTS)阶段。”Node.js v10 使用来自开源 Chromium 项目的 [V8 JavaScript 引擎](https://v8.dev/)，并且“在代码编译和缓存方式上引入了许多旨在提升性能的变化。”

https://Twitter . com/fournachotruths/status/1127036223665557504

*   **谷歌推出语音到语音的“translate tron”:**谷歌人工智能博客本周发布了一篇有趣的文章，[介绍 translate tron:一种端到端的语音到语音翻译模型](http://ai.googleblog.com/2019/05/introducing-translatotron-end-to-end.html)，虽然它似乎还没有可供公众使用，但它看起来很有可能在未来实现。“这个系统被称为 Translatotron，它避免了将任务分成单独的阶段，比级联系统具有一些优势，包括更快的推理速度，自然地避免了识别和翻译之间的复合错误，使翻译后保留原说话者的声音变得简单，更好地处理不需要翻译的单词(例如，名字和专有名词)，”他们写道，并指出这是“第一个可以直接将一种语言的语音翻译成另一种语言的端到端模型。”请务必点击进入博客文章以听取不同风格的翻译。

通过艾比·富勒[展示形象模因。](https://twitter.com/abbyfuller/status/1129485119805304832)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>