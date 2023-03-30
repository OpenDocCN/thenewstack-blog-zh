# 本周编程:微软用 OpenJDK 构建预览版跳回 Java

> 原文：<https://thenewstack.io/this-week-in-programming-microsoft-jumps-back-into-java-with-openjdk-build-preview/>

谁准备好再次像 1990 年代一样坐下来狂欢了，因为微软本周凭借其一些 Java 相关技术的精彩预览在互联网上掀起了风暴！

不不不，[微软 Java 虚拟机(MJVM)](https://en.wikipedia.org/wiki/Microsoft_Java_Virtual_Machine) 还没有浴火重生，也没有 [Visual J++](https://en.wikipedia.org/wiki/Visual_J%2B%2B) ，更没有 [J#](https://en.wikipedia.org/wiki/Visual_J_Sharp) 。亲爱的开发者，不要担心，因为所有这些微软制造的 Java 风格的实现都被深埋在很久以前的诉讼中。相反，本周 Java 世界令人兴奋的消息(除了最高法院对甲骨文诉谷歌案的裁决——我们将在下面谈到)是微软发布的 OpenJDK 预览版。

正如微软的 Scott Hanselman [指出的那样](https://twitter.com/shanselman/status/1379697686446710786)，这个版本与那些广泛传播和失败的 Java 式实现“甚至不是同一项运动”,而是呈现了一个新的、免费的、长期支持(LTS)的 OpenJDK 发行版，它是开源的，并由微软支持。与过去的那些语言不同，微软的 OpenJDK 基于 [OpenJDK 源代码](https://github.com/openjdk)，并提供通过 Java 技术兼容性工具包(TCK)的 Java 11 二进制文件，使其成为“Java 生态系统中任何其他 OpenJDK 发行版的简单替代物，”该公司在一篇博客文章中写道。

微软先前进军 Java 世界的部分戏剧性事件集中在这样一个事实上，即该公司提供的 Java 实现实际上并不与 Java 规范兼容。MJVM 实际上是在针对微软的[反垄断诉讼](https://en.wikipedia.org/wiki/United_States_v._Microsoft_Corp.)中被引用的，作为该公司当时的“[拥抱、扩展和消灭](https://en.wikipedia.org/wiki/Embrace,_extend_and_extinguish)战略的一部分，其中它试图在添加专有功能以试图使竞争对手处于劣势之前，采用和扩展一种广泛使用的标准。

随着这一版本的发布，在过去的微软和今天站在我们面前的微软之间近四分之一世纪的时间里，该公司正在努力向开发人员保证，它将通过完全开源的 OpenJDK 产品在开源世界中扮演好角色。这一点是 Hanselman [在他的 Twitter 帖子](https://twitter.com/shanselman/status/1379652064414900224)[中对低级 J++的回应](https://twitter.com/shanselman/status/1379470425168572418)中再次和[提到的:与 Oracle 的版本相比，这个版本是免费的、开源的，没有许可费。](https://twitter.com/shanselman/status/1379540207196798976)

除了开源、免费和受支持，微软的 OpenJDK，微软 Java 首席产品经理 Bruno Borges [说](https://twitter.com/brunoborges/status/1379541921362632704)还有另一个好处:“我们还相信，通过向用户提供我们自己的构建，我们更有可能找到更好地匹配我们的基础架构/云和客户需求的修复/增强机会。"

关于版本和所有细节的全部细节，请前往[公告博客](https://devblogs.microsoft.com/java/announcing-preview-of-microsoft-build-of-openjdk/)，但请放心，Java 11 支持将持续“至少到 2024 年”，OpenJDK 的容器将“很快在 Docker Hub 上发布”

## 本周的节目中

*   **Go 变得模糊:**首先，本周有一点更新——Go 编程语言团队已经正式[接受了将 fuzzing 加入 Go 标准库的提议](https://github.com/golang/go/issues/44551#issuecomment-811607377)。第一个[在二月下旬由围棋安全团队成员](https://github.com/golang/go/issues/44551)[凯蒂·霍克曼](https://github.com/katiehockman)提出，预计[围棋模糊功能](https://github.com/dvyukov/go-fuzz)将在[围棋 1.17](https://github.com/golang/go/milestone/163) 中进行实验。在提交 fuzzing 的草案时，Hockman 写道:“这个版本中的功能预计会有错误和缺失的功能，但应该作为 Go 开发人员可以试验和提供反馈的概念证明。”至于 fuzzing 是否是一种值得语言追求的努力，正如在关于新接受的功能的 [Reddit 帖子中所质疑的，一份](https://old.reddit.com/r/golang/comments/mhrg4q/fuzz_test_proposal_just_accepted/)[奖杯](https://github.com/dvyukov/go-fuzz#trophies)列表汇集了 go-fuzz 已经发现并修复的错误。
*   **谷歌在长达十年的使用 Java API 的案件中获胜:**最高法院本周做出了有利于谷歌的判决，裁定谷歌使用甲骨文的 Java API 是[合理使用](https://en.wikipedia.org/wiki/Fair_use)并且 [GitHub 博客详细介绍了该判决](https://github.blog/2021-04-06-supreme-court-sides-with-developers-in-google-v-oracle/)称[裁决](https://www.supremecourt.gov/opinions/20pdf/18-956_d18f.pdf)“重申了开发者在平台间移植其代码和技能的能力是一项需要保护的重大利益。“谷歌在其 Android 操作系统中使用 Java SE API 中的 11，330 行代码是否侵犯了版权受到了审查，一项可能有利于甲骨文的裁决使该公司有权从谷歌价值 88 亿美元的操作系统业务中分得一杯羹。相反，法院发现应用编程接口不同于其他类型的代码，而且“允许甲骨文的版权在这里强制执行会有损害公众的风险。根据 GitHub 对该裁决的解释，这一裁决对所有开发者来说都是一个胜利，该公司写道，“最高法院对开发者利益的强烈认可应该为开发者未来几年的创新自由带来红利。”

*   **GitHub 的全球维护者峰会:**那些维护开源项目的人现在又有一个会议可以期待了，这次是由 GitHub 举办的，[刚刚宣布了首届全球维护者峰会](https://github.blog/2021-04-06-announcing-the-global-maintainer-summit/)。[全球维护者峰会](https://globalmaintainersummit.github.com/)将是一个“讨论元方面的机会”,在 6 月 8 日至 9 日举行的免费虚拟活动中成为一名开源维护者。根据公告，峰会将包括“各种各样的简短流媒体会谈，通过[gathere town](https://gather.town/)的走廊通道，以及在开源社区会见志同道合的同行”，对于那些有兴趣分享观点的人来说，[建议征集](https://sessionize.com/global-maintainer-summit-2021/)是开放的。“谈话可能是严肃的，愚蠢的，或者非常脆弱的，”他们写道。“气氛是诚实的。维护开源并不容易，在幕后，它也并不光彩。”
*   **Python 支持在亚马逊 CodeGuru 中正式发布:** [亚马逊](https://aws.amazon.com/?utm_content=inline-mention)的 CodeGuru 代码审查自动化工具[改变了其定价模式，并将 Python 支持转移到 GA](https://aws.amazon.com/blogs/aws/amazon-codeguru-reviewer-updates-new-pricing-model-and-python-support-in-ga/) 中，该公司称此举将为许多用户节省高达 90%的成本。至于成本节约，这要归功于基于存储库大小的简化定价结构，而不是每月分析的代码行数。在新模式下，前 10 万行代码的定价将是每月 10 美元，包括所有连接的存储库，每增加 10 万行代码每月 30 美元，这意味着开发人员可以随时扫描代码，而不会产生额外费用。至于 Python GA 支持，Python 现在加入了 Java，这一举动带来了四个新特性，包括增加了现有检测器的覆盖范围和精度，改进了资源泄漏检测器，新的代码可维护性检测器，以及新的输入验证检测器。虽然 Python CodeGuru Reviewer 已正式发布，但 Python 对 CodeGuru Profiler 的支持仍处于预览阶段。

*   **AWS CDK 增加了对 Go 的支持:**当我们谈论亚马逊的时候，还值得注意的是[AWS 云开发套件现在在开发者预览版中支持 Go](https://aws.amazon.com/blogs/developer/getting-started-with-the-aws-cloud-development-kit-and-go/) 。查看博客帖子，了解“如何初始化新的 AWS CDK 应用程序，以及使用 Go 编程语言创建和部署 AWS CDK 堆栈的基础知识”的分步指导，如果你感兴趣，请查看[项目委员会跟踪工作，以实现全面可用](https://github.com/aws/jsii/projects/3)。在[开发人员指南](https://docs.aws.amazon.com/cdk/latest/guide/home.html)、[参考文档](https://docs.aws.amazon.com/cdk/api/latest/docs/aws-construct-library.html)和 [AWS CDK Go 模块 API 文档](https://pkg.go.dev/github.com/aws/aws-cdk-go/awscdk)中也提供了进一步的详细信息。
*   **Android 跳上了 Rust 列车:**最近，同样的老故事被一遍又一遍地讲述，本周又一次被重复，Android 开源项目选择支持 Rust“开发操作系统本身”采用 Rust 的原因与微软在 Windows 开发中以及最近在 Linux 内核中加入 Rust 的原因一样:内存安全。谷歌认为，选择像 Rust 这样的内存安全语言，可以让他们降低错误的密度，提高沙盒的有效性，并减少对沙盒的整体需求，他们说这将允许他们引入“更安全、更节省资源的新功能”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>