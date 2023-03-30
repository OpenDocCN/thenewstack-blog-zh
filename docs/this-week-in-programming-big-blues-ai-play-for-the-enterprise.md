# 本周编程:蓝色巨人的企业人工智能游戏

> 原文：<https://thenewstack.io/this-week-in-programming-big-blues-ai-play-for-the-enterprise/>

如果你问一个初露头角的开发人员他们最想去的公司是什么，世界上最古老的计算机公司之一可能不在名单上。尽管如此，这家以古老的“计算-制表-记录公司”起家的公司，在更名为更现代(充满讽刺)的“国际商业机器公司”——你知道它是 IBM——之前，仍然因其机器学习和量子计算的努力而成为头条新闻。

当你想到最前沿的编程语言时，Big Blue 可能不在你的舌尖上，但它最近的声明确实专注于为最新的编程工作提供动力。据 [SDTimes](https://sdtimes.com/ai/ibm-focuses-enterprise-ai-adoption-think-2018/) 报道，该公司本周推出了“许多旨在帮助企业利用人工智能力量的新解决方案”，包括 [IBM Watson 数据集](https://www.prnewswire.com/news-releases/ibm-launches-watson-data-kits-to-help-accelerate-enterprise-ai-adoption-300616363.html)和[IBM Watson Services for Core ML](https://developer.apple.com/ibm/)，据称这将使“构建直接从 iPhone 和 iPad 访问强大 Watson 功能的应用程序变得容易”

根据 ZDNet 的说法，IBM 在这里的真正重点是[让现有企业再次变得伟大](https://www.zdnet.com/article/ibm-think-2018-postmortem-making-incumbent-enterprises-great-again/)(呻吟)，也被称为“搭乘大企业的人工智能资金列车”。不过，严肃地说，这项工作的核心是 IBM 的 [Watson Studio](https://www.ibm.com/cloud/watson-studio) ，ZDNet 称之为“对 [Watson 数据平台](https://www.ibm.com/analytics/us/en/watson-data-platform/)和数据科学体验的 2.0 反思”，它“提供了一种更加可视化的集成用户体验”，同时仍然“非常针对核心数据科学家”。对于那些核心数据科学家来说，“Watson Studio 可以自动生成复杂的多层神经网络，并自动运行超参数优化来调整模型，否则需要大量的手动操作。”哦，还有对 [Anaconda 包](https://docs.anaconda.com/anaconda/packages/pkg-docs)的支持，引导。

对于其他可能在未来几年都不会真正接触到 IBM 产品的人来说，本周有很多其他的东西可以讨论，所以让我们继续吧。

## 本周的节目中

*   Java 10 来了:没错，欢呼吧(如果你对新的 Java 版本这么做的话)，因为 [Java 10 来了！](https://jaxenter.com/java-10-is-here-142550.html)尽管如此，从 HackerNews 上的评论来看，很明显[你们中的许多人仍在使用 Java 8](https://jaxenter.com/java-8-still-strong-java-10-142642.html) ，所以按照这个时间表，也许你们会在 2021 年之前使用 Java 10！无论如何，这是 Oracle 新设计的六个月发布周期之后的第一个版本，(Java 9 才六个月)，亮点包括局部变量类型推断、G1 的并行完整 GC、应用程序类数据共享和基于 Java 的试验性 JIT 编译器。要了解完整的细节，请务必查看 Oracle 对 Java SE 10 的介绍。对于那些关注未来的人来说，InfoWorld 有一篇关于 Java 11 路线图的文章。
*   **使用谷歌的转换 API 为 Android 应用程序添加情景意识:**活动识别转换 API 背后的想法很简单。它让你知道用户的活动——走路、跑步、骑自行车、开车等——何时发生了变化。虽然这看起来像是一个简单的问题，但它有一堆微妙的变量(正如谷歌所指出的，你应该相信非驾驶活动中的峰值还是暂时的分类错误？).嗯，谷歌有大量的数据作为其分析的基础，现在它作为 API 提供给你。未来几个月将会增加更多功能，如“区分公路和铁路车辆”，但 API 现在已经可用。详情见[过渡 API 指南](https://developer.android.com/guide/topics/location/transitions.html)。
*   **AWS 文档转到 GitHub:**Application Development Trends Magazine 报道称，亚马逊网络服务已经将其[文档放在 GitHub](https://adtmag.com/articles/2018/03/19/open-source-aws-docs.aspx) 上，现在正在征求“拉取请求”，作为开源开发者指南和其他文档的持续努力的一部分。作为这一整体努力的一部分，亚马逊已经在 [awsdocs](https://github.com/awsdocs) 库中开源了 [AWS SDK](https://aws.amazon.com/tools/) 开发者指南，现在已经增加了超过 138 个新的开发者和用户指南。亚马逊的博客[帖子](https://aws.amazon.com/blogs/aws/aws-documentation-is-now-open-source-and-on-github/)上周有完整的细节。
*   **GitLab 将 CI/CD 引入 GitHub:** 在 [Techcrunch](https://techcrunch.com/2018/03/22/gitlab-adds-support-for-github/) 称之为“有趣的转折”中，GitLab 10.6 已经[发布，为 GitHub 和更深层次的 Kubernetes 集成提供 CI/CD。“GitLab](https://about.gitlab.com/releases/2018/03/22/gitlab-10-6-released/) 在许多方面与 GitHub 竞争，作为团队的共享代码库服务，”Lardinois 写道，“正在将其持续集成和交付(CI/CD)特性[引入 GitHub](https://about.gitlab.com/features/github/) 。”根据公告，持续集成、交付和部署“构成了现代 DevOps 的支柱”，但“缺少的一点是，你不能将 GitLab CI/CD 与 GitHub 一起使用。”如果你有兴趣试用，它将免费向开发者开放，直到 2019 年 3 月 22 日。
*   LG 开源 webOS:还记得 2009 年首次推出的 PalmOS 操作系统吗？嗯，从那以后，它一直在为智能冰箱和电视等产品供电，LG 已经决定[推出开源版本](https://sdtimes.com/os/lg-launches-open-source-version-webos/)。根据 LG 的说法，webOS“现在是一个成熟稳定的平台，准备超越电视。”webOS 开源版现已上市。
*   C# 8.0 即将到来:看起来 C# 8.0 即将到来，开发者 Kenneth Truyers 已经了解了[C # 8.0 的新特性](https://www.kenneth-truyers.net/2018/03/20/whats-new-c-8-0/)。总之，他说“计划中的增加将是使 C#更加健壮和简洁的重大改进”，包括默认情况下不可空的引用类型，在迭代器中使用 async/await 的能力，在接口方法上提供实现的能力，以及创建扩展属性、字段和操作符的能力。关于潜在功能的完整讨论在 [GitHub](https://github.com/dotnet/csharplang/tree/master/proposals) 上。

https://Twitter . com/internet kelvin/status/976092573935714304

*   **那些天杀的隐私规则:**(参考，先[看这条推文](https://twitter.com/NSQE/status/974005089512783872)。)当然，你现在已经听说过《GDPR 》,因为它将于 5 月 25 日全面生效。本周，Adrian Coyler 在他的学术论文每日评论中关注了 GDPR 的遵守情况，尽管他似乎并不完全同意 most 关于如何为 GDPR 做准备的观点。“本文的中心思想是，业务流程建模可以成为管理目的和法规遵从性的强大工具。Coyler 写道:“当你的架构看起来像死星，并且你正在朝着每天 10，000 次部署的目标前进时，我不确定这有多实际，但你肯定需要某种方式来跟踪和管理数据、同意和目的。”“在这里，我有一个不同的观点:对于许多组织来说，我认为需要对所有流程和数据流有完整、准确、最新的全局了解的方法很可能注定要失败，因为这是一项不可能完成的任务！然而，我们无法逃避作者(和法规)摆在我们面前的挑战。我个人认为，我们需要在数据流经组织时跟踪数据的来源，包括同意证明和同意的目的，然后根据同意记录匹配流程的目的。”
*   API 是 GDPR 的解决方案吗？从一个稍微不同的角度来看同一个话题，API 布道者 Kin Lane 提出，GDPR 正迫使我们对我们的数据提出疑问。他写道:“大多数公司收集大量数据，认为这些数据对他们带来的价值至关重要，但并不真正了解正在收集的所有数据，也不知道为什么要收集、存储和保留这些数据背后的任何逻辑原因。”。然而，“做 API 和符合 GDPR 标准是密不可分的。要做 API，你需要绘制出整个组织的数据图景，这将有助于 GDPR。为了响应 GDPR 事件，您将需要 API 来提供对最终用户数据的访问，并利用 OAuth 等 API 身份验证协议来确保合作关系，以及对最终用户数据的第三方访问是负责任的。”

*   **宜家算法指南:**最后，让我们以一些有趣的小故事结束本周。首先，[创意指令](https://idea-instructions.com/)，“一系列正在进行的非语言算法组装指令”，这些指令打破了宜家的设计风格。没错，如果你曾经想知道合并排序算法是如何工作的——没有那些麻烦的单词和数字，这就是你要去的地方。
*   **编程风格的练习:**如果你把编程和文学结合起来，你会得到这个来自 20 世纪 60 年代的文学运动，叫做 Oulipo。本质上，它有时就像是用算法创作的作品。这是通过限制和公式创造出来的作品。这种形式的一个产品是由欧利珀的创始人之一雷蒙·格诺创造的。在这部电影中，同样的故事被一遍又一遍地讲述，但在观点或所使用的语言类型上略有不同，展示了所使用的语言是如何形成核心真理的——如果存在核心真理的话。好了，现在有一个编程风格的[练习，它由一个用 33 种不同编程风格实现的简单程序组成。我不知道你怎么想，但那只是吸引我的大脑。](https://dzone.com/articles/exercises-in-programming-style)

特征图像来自[创意](https://idea-instructions.com/)，关于[合并排序](https://idea-instructions.com/merge-sort/)算法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>