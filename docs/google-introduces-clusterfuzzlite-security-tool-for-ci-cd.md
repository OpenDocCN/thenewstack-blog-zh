# Google 推出用于 CI/CD 的 ClusterFuzzLite 安全工具

> 原文：<https://thenewstack.io/google-introduces-clusterfuzzlite-security-tool-for-ci-cd/>

你有没有注意到这些天我们越来越重视编码安全了？我有。我们有理由。软件供应链攻击，比如对 Kaseya 的 VSA、T2、网络安全管理软件产品和 T4 PHP 的攻击已经变得司空见惯。当[国家标准与技术研究所(NIST)](https://www.nist.gov/) 和白宫发布关于改善国家网络安全的[行政命令](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/)要求更多的代码测试时，你知道网络安全终于被认真对待了。实现这一点的一种新方法是使用[连续模糊化](https://github.com/google/fuzzing/blob/master/docs/intro-to-fuzzing.md)。为了让这变得更容易，谷歌发布了 [ClusterFuzzLite](https://github.com/google/clusterfuzzlite) 。

Fuzzing，对于那些不知道它的人来说，是一种简单的调试技术。几周前，我遇到了一位大学计算机科学编程专业的大四学生，他没有被教授任何安全措施，你们中的很多人可能都不知道。你真的给你的程序输入垃圾，看看会发生什么。这可以追溯到 50 年代，那时他们从垃圾桶里拿出一副穿孔卡片，看看会出什么问题。

听起来很简单，不是吗？确实是。但这很有效。

ClusterFuzzLite 使您能够在您的[持续集成和交付(CI/CD)](https://www.hpe.com/us/en/insights/articles/continuous-integration-and-delivery-tool-basics-1807.html) 管道上运行持续模糊化。结果呢？您将比以往更容易、更快地发现漏洞。

这是至关重要的。2020 年 GitLab DevSecOps 的一项调查发现，虽然 81%的开发人员认为模糊测试很重要，但只有 36%的人实际上在使用 fuzzing。为什么？因为设置 fuzzing 并将其与他们的 CI/CD 系统集成太麻烦了。然而，与此同时，正如[舒哈·汗](https://www.linkedin.com/in/shuah-khan-9527a414/)、[内核维护者和 Linux 基金会的第三位 Linux 研究员](https://www.linuxfoundation.org/en/blog/interview-with-shuah-khan-kernel-maintainer-linux-fellow/)所指出的，“在开发过程中检测和修复问题[要比在游戏后期等待人工测试或质量保证更容易。](https://thenewstack.io/checking-linuxs-code-with-static-analysis-tools/)

fuzzing 通过向程序中输入意想不到的或随机的数据，来捕捉那些原本会逃过最细心的眼睛的错误。 [NIST 软件验证指南](https://www.nist.gov/itl/executive-order-improving-nations-cybersecurity/recommended-minimum-standards-vendor-or)规定模糊化是代码验证的最低标准要求。毕竟， [Chainguard](https://thenewstack.io/chainguard-a-zero-trust-supply-chain-security-company/) 的创始人兼首席执行官、前谷歌开源安全团队软件工程师 Dan Lorenc 最近告诉[新的堆栈](https://thenewstack.io/)，“像构建系统、源代码管理工具和工件库这样的组件都需要被视为关键的生产环境，因为它们确实如此。”

ClusterFuzzLite 与谷歌的[OSS-模糊](https://security.googleblog.com/2016/12/announcing-oss-fuzz-continuous-fuzzing.html)项目紧密合作。自 2016 年以来，OSS-模糊已经在 500 个关键开源项目中发现了[6500 个](https://bugs.chromium.org/p/oss-fuzz/issues/list?q=Type%3DBug-Security%20status%3AVerified&can=1)漏洞和[21000 个](https://bugs.chromium.org/p/oss-fuzz/issues/list?q=Type%3DBug%20status%3AVerified%20-Type%3DBug-Security&can=1)功能 bug。这些问题后来都被解决了。现在电力可以用在你的项目上了。

尽管 ClusterFuzzLite 要新得多，但它已经被成功地用于重要的项目，如 [systemd](https://github.com/systemd/systemd/actions/workflows/cifuzz.yml) 和 [curl](https://github.com/curl/curl/actions/workflows/fuzz.yml) 。根据 curl 的作者 [Daniel Stenberg](https://www.linkedin.com/in/danielstenberg/) 的说法，“当人类评审员点头认可代码，而你的静态代码分析器和 linters 不能检测到更多问题时，模糊化就是把你带到代码成熟度和健壮性的下一个层次。OSS-Fuzz 和 ClusterFuzzLite 帮助我们保持 curl 作为一个高质量的项目，日以继夜，每天每时每刻。”

ClusterFuzzLite 有许多与它的老大哥 [ClusterFuzz](https://github.com/google/clusterfuzz) 相同的特性。这包括持续模糊化、杀毒支持、语料库管理和覆盖报告生成。您还可以将 ClusterFuzzLite 用于专有的源项目。

在这个初始发布版本中，程序支持以下模糊引擎和杀毒程序: [libFuzzer](https://llvm.org/docs/LibFuzzer.html) 用于覆盖引导测试； [AddressSanitizer](https://clang.llvm.org/docs/AddressSanitizer.html) 用于查找内存安全问题；[内存初始化器](https://clang.llvm.org/docs/MemorySanitizer.html)用于查找未初始化的内存问题；以及[未定义行为初始化器](https://clang.llvm.org/docs/UndefinedBehaviorSanitizer.html)，用于查找未定义的行为(例如整数溢出)。又是简单的问题，但它们在我们的代码中反复出现。

程序支持 C、C++、Java(以及其他基于 JVM 的语言)、Go、Python、Rust 和 Swift。今天，你可以将它与 [GitHub Actions](https://docs.github.com/en/actions) 、 [Google Cloud Build](https://cloud.google.com/build) 和 [Prow](https://github.com/kubernetes/test-infra/tree/master/prow#readme) 一起使用。Google 承诺将很快支持更多的 CI 系统。谷歌声称增加对其他 CI 系统的支持非常简单。

想了解更多？查看 [ClusterFuzzLite 文档](https://google.github.io/clusterfuzzlite/)。我吗？如果我正在为我的团队组装 CI/CD 管道，我已经在我的测试管道上修补 ClusterFuzzLite 了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>