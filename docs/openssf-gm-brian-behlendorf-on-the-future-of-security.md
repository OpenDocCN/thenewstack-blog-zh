# OpenSSF 总经理布莱恩·贝伦多夫谈安全的未来

> 原文：<https://thenewstack.io/openssf-gm-brian-behlendorf-on-the-future-of-security/>

西雅图——在 [CloudNativeSecurityCon](https://events.linuxfoundation.org/cloudnativesecuritycon-north-america/) ，开源安全基金会(OpenSSF) 总经理布莱恩·贝伦多夫[、](https://www.linkedin.com/in/brianbehlendorf)、[回忆道，当我们刚开始开发开源软件时，我们真的没有考虑安全性。我们现在都意识到，这是一个错误。](https://openssf.org/)

一个非常非常大的错误。

然后，Behlendorf 在他的主题演讲中回忆道，当我们可以对电子邮件使用 [SMTP(简单邮件传输协议)](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/)时，这在默认情况下是不安全的，“我们理所当然地认为我们可以信任我们下面的软件层，这样我们就可以构建我们想要构建的东西。我们把安全决策留给了子孙后代。”

## 未来就在现在

这是一个不同的时代，未来就是现在。

或者，换句话说，我们的[技术债务](https://thenewstack.io/cloud-native-softwares-technical-debt-is-growing/)的担保利息已经到期。Behlendorf 说，一些团体，如 Trellix，已经采取了自己的方式来偿还部分债务。在发现一个 15 年前的 [CVE-2007-4559](https://nvd.nist.gov/vuln/detail/CVE-2007-4559) Python 漏洞后， [Trellix 在超过 61895 个 GitHub 项目中自行修补了这个路径遍历漏洞](https://www.trellix.com/en-us/about/newsroom/stories/research/trellix-advanced-research-center-patches-vulnerable-open-source-projects.html)。

与此同时，贝伦多夫指出，新的威胁已经出现。多亏了 [ChatGPT、](https://thenewstack.io/ai-moves-to-the-web/) [GitHub CoPilot](https://thenewstack.io/github-copilot-a-powerful-controversial-autocomplete-for-developers/) 和其他人工智能(AI)工具，我们可以期待看到更多针对开源项目的鱼叉式网络钓鱼攻击和人工智能欺骗贡献者，他们将在源代码中放置恶意后门。

这不是科幻小说。贝伦多夫说，“这将在今年发生。”

我同意。不是*如果* AI 驱动的开源代码攻击会不会发生，是*什么时候。*

## 怎么办？

那么，我们能做些什么呢？

嗯，贝伦多夫认为我们真的真的不应该做的一件事是让欧盟的网络弹性法案(EUCSA)以目前的形式通过。事实上，当[开发者的软件被用于非法目的时，他们将承担个人责任。那个愚蠢的想法是开源软件杀手。此外，Behlendorf 补充道，“这些都不是解决网络安全问题的方法。”](https://www.internetsociety.org/blog/2022/10/the-eus-proposed-cyber-resilience-act-will-damage-the-open-source-ecosystem/)

在接受 New Stack 采访时，Behlendorf 谈到了我们必须做些什么来保护我们的代码。我们已经可以看到，他说，很多事情已经发生了。例如，我们“将更多的项目转移到内存安全的语言上，比如 [Go](https://thenewstack.io/what-made-golang-so-popular-the-languages-creators-look-back/) 和 [Rust](https://thenewstack.io/microsoft-rust-is-the-industrys-best-chance-at-safe-systems-programming/) 他还补充道,[我们不仅看到了对 SBOMs(软件材料清单)](https://thenewstack.io/sbom-everywhere-the-openssf-plan-for-sboms/)的更多需求，还看到了对使用 [Sigstore](https://www.sigstore.dev/) 的签名代码的需求。

Behlendorf 警告说，我们还需要采取新的态度来保护我们的代码。比如“没有真正的[零信任架构](https://thenewstack.io/zero-trust-security-and-the-software-development-lifecycle/)。虽然零信任减少了攻击面，但我们无法避免假设、偏见和默认，这些都会使身份和访问管理(IAM)成为一个安全问题。”

此外，Behlendorf 继续说道，“我们认为很难做到的攻击，随着时间的推移只会越来越容易。”而且，随着这些攻击变得越来越容易，其他人将“学习如何为底层食客自动化它们。”

最后，“只要有足够的时间，所有的漏洞都会被利用。软件不是保险箱里的黄金，它们是腐烂的莴苣头。软件需要一个到期日，到期后应该发布一个 CVE。”

与此同时，云原生社区和 OpenSSF 正致力于从许多不同的角度提高安全性。希望它们足以保护我们的软件免受新一波攻击者的攻击。

* * *

在本期《新堆栈制造商在路上》中，了解 OpenSSF 使开源软件更加安全的计划的更多信息，这期节目包括在德克萨斯州奥斯汀举行的 2022 年开源峰会上录制的对 Behlendorf 的采访。

[https://www.youtube.com/embed/kIja2WLSEo8](https://www.youtube.com/embed/kIja2WLSEo8)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>