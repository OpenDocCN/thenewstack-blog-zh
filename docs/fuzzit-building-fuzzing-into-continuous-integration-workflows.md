# Fuzzit:将模糊化构建到持续集成工作流中

> 原文：<https://thenewstack.io/fuzzit-building-fuzzing-into-continuous-integration-workflows/>

在更快交付软件的复杂性中——尤其是在云中——模糊化已经不是什么新鲜事了。

最新进入该市场的公司之一是总部位于特拉维夫的 Fuzzit，这是另一家来自 T2 的安全初创公司，其创始人拥有与以色列国防军打交道的经验。

模糊化包括将伪随机输入输入到程序中，以观察它的行为，并根除 bug。这是一个[黑客利用](https://ciso.economictimes.indiatimes.com/news/why-ai-fuzzing-could-be-next-cybersecurity-threat/68609808)寻找漏洞并加以利用的过程。

“我们专注于帮助公司将模糊化引入其当前的 CI 工作流程。我们可以与任何 CI 整合:GitHub、GitLab、内部 CI、Jenkins，”创始人兼首席执行官 [Yevgeny Pats](https://github.com/yevgenypats) 说。

他在一家咨询公司的经历表明，对许多客户来说，自己做模糊处理被证明过于繁重。

“你需要第三方的原因是因为 fuzzing 的工作量。…起毛通常是一项长期工作。如果不阻止您的整个 CI 团队，您无法在 CI 中轻松运行它们。因此，你需要运行 fuzzing 另一个地方，”他说。

## 专注于开源

Pats 在 2019 年初创立了这家五人公司。他还创立了反钓鱼自动化平台 Phish.AI。

它最初是一家咨询公司，在网络和移动应用程序上做笔测试。在为客户编写模糊测试并发现一些错误后，他们要么根本不运行测试，要么一年后才运行测试。

“最终他们要求我们管理它，这样他们就可以在每次推出新代码时运行测试，”他说。

开源项目包括 Systemd、CoreDNS、Prometheus、Envoy proxy 都是它的用户。

他说，开源项目面临着特殊的挑战。

“有很多不同的人参与其中。[他们可能]对拉请求使用 fuzzing，但当他们进行合并时，他们没有这个版本，现在他们找不到开发人员。当找不到开发人员时，我们帮助他们找到拉请求中的崩溃，并修复所有这些崩溃，”他说。

## 按比例

SaaS 产品使用户能够运行他们当前的 LibFuzzer， [AFL(美国模糊 Lop)](https://github.com/google/AFL/blob/master/README.md) target，并进行深度分析。它可以在 C，C+，Java，Golang，Rust 和 Swift 上运行。

它可以与任何持续集成(CI)工具一起工作。您可以对每个 pull 请求和在后台生成新测试用例的长时间作业运行快速回归测试。

你首先上传一个**tar.gz**文件，包含为 [LibFuzzer](https://llvm.org/docs/LibFuzzer.html) 编译的目标，覆盖引导的进化模糊引擎。使用 Fuzzit CLI，您可以进行身份验证并将二进制文件推送到 Fuzzit。一旦将代码推送到 master，Fuzzit 将异步运行代码，而不会阻塞 CI。如果发现了 bug，它会通过您配置的通道提醒您。

该平台每分钟更新一次日志，每小时自动合并所有工人之间的语料库。它的重点是确保 bug 被修复，如果它们在 pull 请求中再次被引入，它会再次提醒您。

“如果你写了 5 到 10 个模糊测试，我们一次只运行一个版本。如果你推一个新版本，我们停止旧版本，开始新版本。它在运行之间创建了一个语料库。每次你推送代码时，fuzzer 不会从头开始，而是从旧版本停止的地方开始。

要测试多个版本，您可以使用特定的版本分支/标签来模糊特定的版本。

## 也在内部

模糊测试有一些有趣的历史，可以追溯到 20 世纪 50 年代。

最近的项目包括谷歌的 [ClusterFuzz](https://google.github.io/clusterfuzz/) 扩展为 [OSS-Fuzz](https://github.com/google/oss-fuzz/) ，由 [Linux 基金会的](https://www.linuxfoundation.org/) [核心基础设施倡议](https://www.coreinfrastructure.org/)联合发起，以提高关键开源应用的安全性；以及微软的[微软安全风险检测](https://www.microsoft.com/en-us/security-risk-detection/)(原春田项目。)

然后还有像 [ForAllSecure](https://forallsecure.com/) 、 [FuzzBuzz](https://fuzzbuzz.io/) 和 [Synopsys](https://www.synopsys.com/software-integrity/security-testing/fuzz-testing.html) 这样的公司。

对于 ClusterFuzz，Pats 说，“你必须管理它，设置它，拥有服务器。即使不运行任何测试，计算能力的最低成本也是每月 600 美元。

“你必须拥有 GCP。有了 AWS 或者 on-prem，就真的用不上了。我们的解决方案也适用于内部。我们有一个托管版本。”

在低端，两个容器的价格是每月 25 美元，开源有一个免费层。

展望未来，虽然该公司去年专注于开源项目，但明年将专注于更多的企业功能，如简化内部安装、集成到内部票证系统以及大型组织的自动化。

一场名为 [FuzzCon](https://www.eventbrite.com/e/fuzzcon-tickets-79551591953) 的活动定于 2 月 25 日在旧金山举行，演讲者来自谷歌、微软、新思科技、ForAllSecure 等公司。在这里找到 fuzzing [的 GitHub 资源。](https://github.com/cpuu/awesome-fuzzing)

[https://www.youtube.com/embed/koUmZFK7LP0?feature=oembed](https://www.youtube.com/embed/koUmZFK7LP0?feature=oembed)

视频

Linux 基金会是新堆栈的赞助商。

专题图片:[迪伦·鲁德](https://www.flickr.com/photos/luder5/)的《Fuzz 》。根据 CC BY-SA 2.0 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>