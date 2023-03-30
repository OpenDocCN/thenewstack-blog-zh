# 本周编程:我们需要另一个基础吗？

> 原文：<https://thenewstack.io/this-week-in-programming-do-we-need-another-foundation/>

又一周，又一个基金会，阿米利特？

本周，我们已经听到消息称， [Linux Foundation](https://www.linuxfoundation.org/) 已经[将 Node.js Foundation 和 js Foundation 合并为 OpenJS Foundation](https://www.linuxfoundation.org/press-release/2019/03/node-js-foundation-and-js-foundation-merge-to-form-openjs-foundation/) ，目的是帮助“消除这两个组织之间的运营冗余，简化通过会员资格提供重要财务支持的公司的体验，并协调 JavaScript 社区内部以及与附属标准机构的努力，”根据一份声明。

然后是新成立的持续交付基金会 (CDF)的[新闻，它作为](https://thenewstack.io/continuous-delivery-foundation-launches-with-jenkins-jenkins-x-spinnaker-tekton/) [Jenkins](https://jenkins.io/) 、 [Jenkins X](https://jenkins-x.io/) 、 [Spinnaker](https://www.spinnaker.io/) 和 [Tekton](https://github.com/tektoncd) 项目的“供应商中立之家”启动，有 22 个创始成员，包括 Autodesk、CapitalOne、CloudBees、GitLab、Google、微软、网飞和 Red Hat 等。在我们对 Linux 基金会开发人员关系副总裁 Chris Aniszczyk 的采访中，他半开玩笑地将该组织称为“基金会即服务”,一些人对此评价非常赞同，质疑 CDF 是否真的有必要，或者基金会是否应该避免创建另一个基金会。

一个关于新成立的基金会的问题来自云本地计算基金会(CNCF)技术委员会的原始成员 Alexis Richardson，他也是 Weaveworks 的首席执行官。

Richardson 认为，该部门将迫使新项目在 CNCF 和 CDF 之间做出选择，他说这“对社区、最终用户和项目都不利”在进一步的推文中，理查森认为，“谁‘掌握代码’远不如为公司提供清晰的营销和采纳信息重要，”他预测，“我们现在将看到同样的 OCI 与 CNCF 的困惑，但要糟糕 10 倍。”

与此同时，其他人从完全相反的角度看待 CDF，其中的区别很明显——尽管在理想的世界中，持续集成、持续交付(CI/CD)项目的意图是如此，但并不是所有的项目都必然是“云原生的”,因此不属于 CNCF。事实上，他们将 CNCF 视为 Kubernetes 的同义词，显然排除了 Jenkins 等项目，这些项目包括从本地到云原生范围的所有用户。

在对新成立的基金会的报道中， [The Register](https://www.theregister.co.uk/2019/03/12/continuous_delivery_foundation/) 同样认为这种区别足够清晰和明显，写道“就像云原生计算基金会(CNCF)对容器、微服务和编排所做的那样，CDF 完全是关于开源世界中的持续交付，”以及“基金会背后的目标，就像它的兄弟 CNCF 一样，是保持事情一致，并确保项目在 CI/CD 世界中良好合作。”

虽然创建 OpenJS 基金会是为了消除冗余，但争论似乎是，创建连续交付基金会是为了明确以前缺乏的地方，并在需要的地方提供区别。正如新堆栈分析师[劳伦斯·赫克特](https://thenewstack.io/author/lawrence-hecht/)在推特上所言，单单詹金斯的用户群就可能需要创建该基金会。

你怎么看——创建中国发展基金仅仅是另一个分裂，以后需要重新整合，还是一个必要的分裂？在不久的将来，你认为 CNCF 还有必要成立其他分支机构吗？或者，CNCF 应该继续作为所有云原生项目的总体管理机构吗？

当你正忙着考虑结束(或不结束)的时候，这里有一些最新的谷歌开发者新闻(后面还有更多):

[https://www.youtube.com/embed/g5JMKUBMsRg?feature=oembed](https://www.youtube.com/embed/g5JMKUBMsRg?feature=oembed)

视频

## 本周的节目中

*   **Android Q Beta for the Devs:**Google 已经宣布[Android Q Beta](http://android-developers.googleblog.com/2019/03/introducing-android-q-beta.html)的发布，除了为用户提供的新功能之外，作为开发者还有几件事情需要注意。ProgrammableWeb 为开发者提供了一份[新闻摘要](https://www.programmableweb.com/news/google-makes-android-q-preview-available-to-developers-provides-fresh-apis/2019/03/14)，写道“谷歌用一批新的 API 让开发者投入工作，干扰了操作系统的升级”，其中包括“WiFi、蓝牙和蜂窝连接的新的和修订的连接 API”等。在测试版中，谷歌还宣布了新的音频和视频编解码器、原生 MIDI API、神经网络 API 1.2、对 ART 运行时的几项新改进，以及他们“从 Android P 开始的长期努力的延续，以将应用程序转向仅使用公共 API。”SDTimes 还总结了此次发布，写道它“继续关注安全和隐私，包括来自 Google Play Protect 和运行时权限的工作，以及新的隐私和安全功能，新的 API，相机功能，更快的应用启动，以及可折叠手机等创新的增强功能。”对于我们来说，这里真的有太多太多的东西需要完全挖掘，但这三篇文章应该可以让你开始，以及谷歌网站详细介绍的[新功能和 API](https://developer.android.com/preview/features)和 [Android Q Beta 开发者网站](https://developer.android.com/preview/index.html)。哦，虽然我们吸引了你的注意力，亲爱的 Android 开发者，但不要忘记谷歌将在 3 月 18 日星期一的 GDC 2019 上举办其[移动开发者日，并且有一个](https://events.withgoogle.com/google-at-gdc-2019/mobile-developer-day/)[直播。以免我们忘记，由于 Google+即将关闭，官方 Android 测试社区似乎已经转移到 Reddit。](https://www.youtube.com/watch?v=NEHvB21dJMk)

*   **谷歌的“文档季”:**在我们继续之前，该公司有一篇有趣的博客文章[介绍了](http://opensource.googleblog.com/2019/03/introducing-season-of-docs.html)它的[文档季](https://developers.google.com/season-of-docs)，这是一个新的项目，“将技术作家和开源项目聚集在一起，进行几个月的开源文档工作。”引用[开源调查](https://opensourcesurvey.org/2017/)，他们写道，好的文档有很高的价值，但缺乏这种价值，因此有了这个最新的项目。4 月 2 日至 23 日，开放源代码组织将接受对“文档季”的申请，然后从 4 月 30 日至 6 月 28 日，技术作者将选择他们喜欢的项目，并向“文档季”提交他们的建议，然后在一段时间的相互了解后，谷歌将于 12 月 10 日发布成功完成的项目列表。完整的[时间表](https://developers.google.com/season-of-docs/docs/timeline)和[常见问题解答](https://developers.google.com/season-of-docs/docs/faq)可在[Docs 季网站](https://g.co/seasonofdocs)上获得。

*   **召集所有 iOS 开发者:**给所有 iOS 开发者提个醒——好像你们还不知道——苹果已经[开放了 WWDC19](https://developer.apple.com/news/?id=03142019b) 的注册，WWDC19 将于 3 月 20 日星期三下午 5 点(太平洋时间)结束。苹果一年一度的全球开发者大会(WWDC)将于今年 6 月 3 日至 7 日在圣荷西举行，WWDC19 奖学金申请也开始接受，申请必须在 3 月 24 日星期日下午 5 点之前提交。
*   **ML.NET 0.11 增加 TensorFlow 文本输入:**微软发布了[ML.NET 0.11](https://devblogs.microsoft.com/dotnet/announcing-ml-net-0-11-machine-learning-for-net/)，它是面向的开源跨平台机器学习框架。NET 开发人员，关注“框架的整体稳定性，继续完善 API，修复 bug，减少公共 API 表面，改进文档和示例。”此外，这个最新发布的版本增加了对文本输入的支持，所以 TensorFlow 模型现在可以用于文本分析，如情感分析——查看这个[代码中的示例。](https://github.com/dotnet/machinelearning/blob/master/test/Microsoft.ML.Tests/ScenariosWithDirectInstantiation/TensorflowTests.cs#L967)
*   **云中的 Visual Studio 代码:** Infoworld 与我们相关的是，微软流行的开源代码编辑器 Visual Studio Code 已经被在线 IDE 提供商 [Coder](https://coder.com/) 放到了云中[。“一种新的开源工具让开发人员可以在远程服务器上运行微软的开源 Visual Studio 代码编辑器，并通过浏览器访问它，”他们写道。“使用可从 GitHub 获得的 Coder 的](https://www.infoworld.com/article/3356440/coder-puts-visual-studio-code-in-the-cloud.html#tk.rss_applicationdevelopment)[代码服务器工具](https://github.com/codercom/code-server)，开发人员可以在 Chromebook、平板电脑或 PC 上编写代码，并拥有与 Visual Studio 代码同步的环境。该工具还允许开发人员利用 CPU 爆炸式的云实例进行繁重的测试和编译。”目前，Code-Server 支持 Linux 和 MacOS，Windows 也即将推出。

CloudBees、Cloud Native Computing Foundation 和 Linux Foundation 是新堆栈的赞助商。

专题图片由 Hebi B .来自 Pixabay。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>