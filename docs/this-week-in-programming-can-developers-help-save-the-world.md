# 本周编程:开发者能帮助拯救世界吗？

> 原文：<https://thenewstack.io/this-week-in-programming-can-developers-help-save-the-world/>

这一周(或三周)以来，一些末日般的头条新闻报道了[创纪录的温暖天气](https://www.noaa.gov/news/january-2020-was-earth-s-hottest-january-on-record)、[遭遇疫情](https://www.nytimes.com/2020/02/24/world/asia/china-coronavirus-world-health-organization.html?action=click&pgtype=Article&state=default&module=styln-coronavirus&variant=show&region=MID_MAIN_CONTENT&context=storyline_guide)的可能性，以及随之而来的[股市跳水](https://www.cnbc.com/2020/02/27/stock-market-today-live.html)，这让我向上面的科技之神恳求一些解决方案。不过，实际上，这个问题在一定程度上是一个“可能还是不可能”的问题，还夹杂着一点“有人能解决这个问题吗”和一点“我们能相信技术能帮上忙吗？”当然，我意识到，技术实现通常可以是一个相当复杂的组合，当谈到良好的意图时，有 T7，T8，T9，T10，最终结果 T11。

无论我们是否意识到我们的要求，技术都会按照我们的要求去做。

与此同时，我确实在我日渐淡化的技术解决主义灵魂中保留了一丝希望。我想我们可以，我想我们可以，我想我们可以。(也就是说，我在 2002 年初的毕业论文题为“超文本:文本性的解放”，在论文中，我认为互联网、元数据和维基百科等将开创一个信息自由的新时代，照亮社会的黑暗角落，用上下文和洞察力解放它们。哦，这与现代生活中浏览推特和脸书并试图从巨魔中辨别真相的经历形成了鲜明对比。)

好吧，IBM 已经准备好支持通过代码拯救世界的想法，它的 [2020 呼吁代码全球挑战](https://developer.ibm.com/callforcode/)是一项为期五年、耗资 3000 万美元的全球倡议，旨在召集开发人员“利用他们的技能和对最新技术的掌握，并创造新的技术，用他们的代码在世界各地推动积极而持久的变化。”今年的[代码呼吁](https://callforcode.org/)将目光投向了气候变化，正如杰夫·贝索斯本月早些时候所做的，他创建了 100 亿美元的“[贝索斯地球基金](https://en.wikipedia.org/wiki/Bezos_Earth_Fund)，“这一次”挑战申请者[创造基于开源技术的创新](https://c212.net/c/link/?t=0&l=en&o=2730662-1&h=4089975922&u=https%3A%2F%2Fdeveloper.ibm.com%2Fcallforcode%2Fresources%2F&a=create+innovations)，以帮助阻止和扭转气候变化的影响。”IBM 表示，去年，来自 165 个国家的 180，000 多名参与者创建了 5，000 多个应用程序，重点关注自然灾害防备和救援。

气候变化现在已经被完全解决了(讽刺！)，让我们继续关注疫情——programmable web 有一篇有趣的小文章，关注可用于跟踪冠状病毒新冠肺炎的各种[API，它指出“不能帮助治愈疾病，但它们可以被开发人员用来收集关于爆发的数据，跟踪其传播，甚至产生数据可视化。”](https://www.programmableweb.com/news/apis-to-track-coronavirus-covid-19/review/2020/02/25)

至于股票市场，嗯，你们都是孤独的。你还在等什么？去拯救世界吧。

[https://www.youtube.com/embed/h7dCm2lQLOg?feature=oembed](https://www.youtube.com/embed/h7dCm2lQLOg?feature=oembed)

视频

## 本周的节目中

*   **Firefox 转向 WebAssembly 以增加安全性:**我们已经研究了微软和其他公司由于 C 和 C++中的内存不安全而面临的问题，Firefox 转向了一些相同的解决方案，[将代码分成多个特权减少的沙盒进程](https://wiki.mozilla.org/Security/Sandbox)和[将其重写为 Rust](https://hacks.mozilla.org/2019/02/rewriting-a-browser-component-in-rust/) 之类的内存安全语言。现在，Mozilla 说他们增加了第三个选项，因为进程级沙盒需要大量的系统资源，同时把所有东西都重写到 Rust 里，嗯……你懂的。数百万行代码，诸如此类。因此，他们转而求助于[使用 WebAssembly](https://hacks.mozilla.org/2020/02/securing-firefox-with-webassembly/) (WASM)使用 [RLBox](https://rlbox.dev/) 来保护 Firefox，这是一种新的沙箱技术，使他们能够转换现有的 Firefox 组件，以便在 WASM 沙箱内运行。从本质上说，这让他们可以获取现有的 C/C++代码，将其编译成 WASM 代码，然后编译成本机代码，所有这些都是在 Firefox 本身使用 [Cranelift](https://github.com/bytecodealliance/cranelift) 通过字节码联盟的 [Lucet 编译器和运行时](https://github.com/bytecodealliance/lucet)构建时提前完成的。他们写道，这“能够在多个进程之间共享编译后的本机代码，从而显著节省内存”，并且“提高了沙箱的启动速度，这对细粒度沙箱非常重要。”

https://twitter.com/Mierdin/status/1232820895942467584

*   **Rust 1 . 41 . 1 的快速更新:**说到 Rust 和内存安全以及所有这些问题， [Rust 1.41.1 刚刚发布了](https://blog.rust-lang.org/2020/02/27/Rust-1.41.1.html)，更新了“Rust 1.41.0 中引入的两个关键回归:一个与静态寿命相关的安全漏洞，以及一个导致 segfaults 的错误编译。”如果您使用的是 1.41.0，请尽快更新。
*   **通过 Google 继续学习& GitHub:** 对于你生活中所有那些 13 岁以上、可验证的学生，GitHub 已经为其 [GitHub 学生开发者包](https://education.github.com/pack)增加了 14 个合作伙伴，该公司表示，全球有近 200 万学生在使用该包。新工具使提供给[的总数超过 100 个](https://github.blog/2020-02-25-over-100-partners-to-help-you-succeed-with-the-github-student-developer-pack/)，包括 Blockchair，一个区块链浏览器和超过 15 种加密货币的 API 提供商， [Dashlane](https://dashlane.com/) 基于云的密码管理器， [MongoDB](https://www.mongodb.com/) 和其他工具。你所需要的只是一封学校发的电子邮件、身份证或其他当前注册的证明来申请进入。与此同时，[写道](https://www.blog.google/outreach-initiatives/grow-with-google/digital-learning-day-2020-/)作为[数字学习日](https://digitallearningday.org/)的一部分，[应用数字技能](https://applieddigitalskills.withgoogle.com/s/en/home)(其免费的在线视频课程)已经策划了一系列[最受欢迎的课程](https://applieddigitalskills.withgoogle.com/c/en/digitallearningday2020)，从简历制作到理解你的数字足迹。

*   **GitHub Web Notifications 上线:**虽然它于去年 11 月在 GitHub Universe 上首次推出，但 GitHub 表示[经过数月的测试和迭代，](https://github.blog/2020-02-25-your-new-web-notifications-experience-is-here/)您全新的 Web 通知体验已经到来。基本上，它有点像 GitHub 通知的 Gmail，具有自定义过滤工作流和使用键盘快捷键清除通知的选项。和大多数类似的事情一样，你可以随意告诉他们你有多喜欢或讨厌它。
*   **AWS Lambda 引入 Dart 运行时:**如果您熟悉编写 [Dart](https://dart.dev/) 来创建移动应用程序，现在您可以将这些技能用于创建 AWS 的[引入的用于 AWS Lambda 的 Dart 运行时](https://aws.amazon.com/blogs/opensource/introducing-a-dart-runtime-for-aws-lambda/)的无服务器后端。Dart 是一种静态类型的开源语言，支持 Google 的开源软件开发套件(SDK)Flutter(T7 ),用于创建在桌面和移动平台上使用单一代码库的应用程序。新的运行时是 AWS 的[定制 Lambda 运行时](https://docs.aws.amazon.com/lambda/latest/dg/runtimes-custom.html)之一，允许你在 [AWS Lambda](https://aws.amazon.com/lambda) 中运行 Dart，在你的应用和你的后端之间共享代码。介绍新运行时的博客文章解释说，[自定义 Lambda](https://docs.aws.amazon.com/lambda/latest/dg/runtimes-custom.html) 运行时使用 [AWS Lambda 运行时接口](https://docs.aws.amazon.com/lambda/latest/dg/runtimes-api.html)，定义了“自定义运行时用来服务调用请求的 Lambda 编程模型的基于 HTTP 的[规范](https://docs.aws.amazon.com/lambda/latest/dg/runtimes-api.html)”值得注意的是，运行时仍然处于“早期阶段”,维护者正在寻求反馈——所以也许还不要“直接投入 prod”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>