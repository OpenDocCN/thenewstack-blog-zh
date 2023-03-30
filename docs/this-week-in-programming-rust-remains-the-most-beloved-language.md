# 本周编程:Rust 仍然是最受欢迎的语言

> 原文：<https://thenewstack.io/this-week-in-programming-rust-remains-the-most-beloved-language/>

根据 2020 年栈溢出开发者调查，看起来 Rust 又一次登上了“最受喜爱”语言的榜首。在总结调查结果的博客文章中，该公司写道，尽管大多数受访者甚至不熟悉 Rust 语言，但 Rust 仍保持在榜首。

[调查](https://insights.stackoverflow.com/survey/2020)，第 10 年(“取决于你如何计算，”他们写得有点神秘)提供了来自 65，000 名开发者的答案，尽管有一个很大的警告——他们都是在疫情开始之前进入的。因此，“谦虚和现实很重要:如果今天进行同样的调查，开发人员给出的许多答案可能会看起来非常不同，”他们写道——尽管我们假设最大的差异可能来自就业和习惯的答案，而不是某人是否喜欢用特定的语言编码。

对于 Rust 来说，这是一个有趣的位置，因为语言[一直在与陡峭的学习曲线](https://thenewstack.io/this-week-in-programming-whats-holding-back-rust-and-go/)斗争，同时缺乏学习资源，需要更好的 ide 集成，以及文档的滞后。诚然，这些是 Rust 团队最近一直在努力解决的痛点。在谈到 Rust 的魅力时，StackOverflow 总结道:“Rust 承诺了性能、控制、内存安全和无所畏惧的并发性——这是一个诱人的组合，尤其是对于系统编程来说。”

每当你听到 Rust，[你可能也会想到 Go](https://thenewstack.io/this-week-in-programming-rust-versus-go-why-not-both/) ，StackOverflow 指出，谷歌支持的 Rust 竞争对手今年也有了很大的飞跃，从最受欢迎语言排行榜的第十位上升到第五位。至于你在哪里能赚到最多的钱，Go 在美国远远超过 Rust，但两者都支持 Scala。

与此同时，令人恐惧的语言列表由一些常见的嫌疑人领导，如 VBA、Objective-C 和 Perl，而 Rust，尽管它有任何挣扎，仍位于最底部，其最接近的竞争对手享有两倍的恐惧百分比。的确如此，至爱的人类。

StackOverflow 将这些“语言”从其他“编程、脚本和标记语言”中分离出来，在过去的八年中，JavaScript 一直稳坐第一的位置。与此相关的是，TypeScript，JavaScript 的编译超集，仅次于 Rust 排名第二，以 0.1%的微弱优势击败 Python。

根据一项指标，这就是我们在编程语言流行的永无止境的赛马中所处的位置。这是本周编程界发生的一些其他事情。

## 本周的节目中

*   Quarkus 得到 Red Hat 的全力支持:如果你担心的话，对在 Kubernetes 上运行 Java 的框架 [Quarkus](https://quarkus.io/) 感兴趣的 Java 开发人员可以放心了——Red Hat 已经表示 [Quarkus 现在是一个完全支持的运行时](https://www.redhat.com/en/blog/bringing-java-kubernetes-native-future-quarkus)，作为其 [Red Hat 运行时](https://www.redhat.com/en/products/runtimes)组合的一部分。这意味着它可以部署在 Red Hat OpenShift 上运行的生产工作负载中，将得到 Red Hat 的支持，并且现在是 IBM Cloud Pak for Applications 的一部分。
*   **Android 11 有自己的发布会:**对于你的 Android 开发者来说，由于疫情，Android 11 的发布会被推迟了一点，但好消息是[Android 11:Beta 发布会](http://android-developers.googleblog.com/2020/05/android11-beta-launch-show-heres-how-to.html)将于下周美国东部时间 6 月 3 日上午 11 点开始。该活动将在 YouTube 和 Twitter 上进行直播，此外，谷歌表示，它将分享十几场“从 Jetpack 到 Android Studio 和 Google Play 等一系列主题的演讲——这些演讲是我们最初为谷歌 I/O 计划的——以帮助你利用 Android 开发的最新成果。”在[活动页面](https://g.co/android11)获取所有详细信息。当我们谈论 Android 的时候， [Android Studio 4 刚刚放弃了](https://android-developers.googleblog.com/2020/05/android-studio-4.html)，下面让我们快速浏览一下新功能。

[https://www.youtube.com/embed/f1fHPqAYj5I?feature=oembed](https://www.youtube.com/embed/f1fHPqAYj5I?feature=oembed)

视频

*   **Rust 回顾 2018 年的重新设计:**Rust 社区继续展示其开放性和自省性，这一次是与[一起回顾 2018 年 rust-lang.org 的重新设计](https://blog.rust-lang.org/inside-rust/2020/05/26/website-retrospective.html)，团队提供了“记录从项目中吸取的经验教训的尝试，并为那些感兴趣但没有直接参与的人提供项目背景。”这篇博文着眼于 2018 年对 [Rust 网站](https://www.rust-lang.org/)的改造以及围绕这项工作的争议，提供了一个回顾，称其“旨在成为[无可指责的](https://blog.newrelic.com/technology/blameless-retrospectives/)和前瞻性的”，并对“规划、项目管理和社区方面，而不是批评设计或实施”感兴趣在我看来，这些博客文章对于任何参与开源项目、希望更好地理解开源工作的动态并希望让事情进展顺利的人来说都是一本好书。一些“经验教训”包括关注人而不是时间表，保持沟通畅通，确保项目所有权得到明确定义，不要将所有事情安排在同一时间交付。请继续阅读，如果你碰巧是 Rust 贡献者，或者甚至希望在未来成为贡献者，请去参加 [2020 Rust 贡献者调查](https://blog.rust-lang.org/inside-rust/2020/05/27/contributor-survey.html)，该调查将[开放提交](https://forms.gle/G1jKM1ppGunft6j29)到 6 月 10 日。

*   **GitHub 开始开源支持:**也就是说， [GitHub 支持社区已经经历了](https://github.blog/2020-05-27-the-github-support-community-has-a-new-look-and-feel/)“对外观和感觉的重大更新”，并过渡到 Discourse 的开源社区平台，包括对 [CommonMark Markdown](https://commonmark.org/help/) 的支持，“使用相同的 GitHub 风格的 Markdown- extensions，使您在支持社区和 GitHub 之间的编辑体验无缝。”除此之外，该网站将提供一个响应式的设计，简单的代码片段共享，以及可定制的个人阅读体验。
*   **GitLab 13 带来了 ECS 部署和更多:** DevClass 看了一下 [GitLab 13.0 版本](https://about.gitlab.com/releases/2020/05/22/gitlab-13-0-released/)，向[提供了该网站的新黑暗面](https://devclass.com/2020/05/26/gitlab-13/)(黑暗模式)，作为一个亮点，以及“ECS 的自动部署，更好的 Terraform 支持，改进的大文件处理，以及没有 NFS 的高可用性 Git 存储。”展望 GitLab 的路线图，诸如识别瓶颈的可视化助手、A/B 测试功能、策略管理和 API 模糊支持等特性也将在不久的将来发布。
*   **Google Cloud Functions 获得 Java 11:** SDTimes 向我们讲述了 [Google 如何在其无服务器计算平台 Google Cloud Functions 中添加对 Java 11](https://sdtimes.com/java/google-cloud-functions-adds-support-for-java-11/) 的支持，这将允许开发人员“通过 Functions Framework for Java(用于编写 Java 函数的函数即服务框架)用 Java、Kotlin、Groovy 和 Scala 等 JVM 语言编写代码。”除此之外，他们注意到 Google 还将支持 Micronaut 框架和 Spring Cloud Function 项目，暂时在 beta 中支持 Java 11。
*   **微软通过 Project Tye 提供微服务支持:**最后，微软希望通过其新工具 [Project Tye](https://github.com/dotnet/tye) 来“更容易地开发、测试和部署微服务和分布式应用程序”，该工具是上周在虚拟微软构建开发者大会上[推出的](https://devblogs.microsoft.com/aspnet/introducing-project-tye/)。他们写道，该项目有两个目标——通过用一个命令运行许多服务并使用容器化的依赖关系，使微服务开发更容易，以及自动化部署。NET 应用程序到 Kubernetes。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>