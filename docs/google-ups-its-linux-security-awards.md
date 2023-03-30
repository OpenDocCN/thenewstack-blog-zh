# 谷歌提高其 Linux 安全奖

> 原文：<https://thenewstack.io/google-ups-its-linux-security-awards/>

他们是如何从 Kubernetes 过渡到 Linux 的？这是下一个合乎逻辑的举动。通过 kCTF，研究人员可以使用 [Google Kubernetes 引擎(GKE)](https://cloud.google.com/kubernetes-engine) 实例。如果他们能成功破解，他们就能得到一面旗帜，还可能得到一些现金。但是，早在 1995 年， [Mozilla 基金会是第一个提供 bug 奖金的组织。现在，每个人都是任何人提供给他们的。几乎在所有事情上都使用 Linux 的谷歌，正在扩展其基于 T4 Kubernetes 的捕获标志(kCTF)项目和 kCTF 漏洞奖励项目(VRP)(T7)，以更加关注追捕 Linux 内核漏洞(T9)。](https://www.cobalt.io/blog/the-history-of-bug-bounty-programs)

哎呦！

## Linux 内核黑客社区

特别是，发现的错误往往是堆内存损坏漏洞，谷歌的计划是建立一个 Linux 内核黑客社区。任务完成！

展望未来，[谷歌将 kCTF VRP 延长至 2022 年 12 月 31 日](https://security.googleblog.com/2022/02/roses-are-red-violets-are-blue-giving.html)。这些奖励现在为谷歌实验室 kCTF 部署的漏洞支付 20，000 美元至 91，337 美元。这是对谷歌现有的 [Bug Hunter 补丁奖励](https://bughunters.google.com/about/patch-rewards)的补充。

## 缓解措施

为了帮助打击 Linux 内核安全漏洞，谷歌还推出了带有额外奖励的新实例。在这些情况下，研究黑客将检查最新的 Linux 内核稳定映像，以及自定义 Google 内核中新的实验性缓解措施。换句话说，黑客们不仅会调查稳定的 Linux 内核，还会检查谷歌自己最新的、更具实验性的 Linux 安全缓解措施。

具体来说，谷歌正在检查应该——应该——更难利用最近发现的漏洞的缓解措施。如果你成功突破了这些新的 Linux 内核补丁，谷歌将会付给你额外的 21000 美元。

这些 [Linux 内核强化缓解](https://github.com/thejh/linux/blob/slub-virtual/MITIGATION_README)旨在阻止对以下漏洞原语的攻击:

## 去拿钱

对于利用其实验性缓解措施损害谷歌定制 Linux 内核的攻击，奖励将是另外 21，000 美元。为此，您必须明确绕过测试缓解措施。你总共可以赚到 133，337 美元。

当前的目标是创建一个管道来分析、实验、测量和构建 Linux 内核安全缓解。最终，我们希望尽可能地降低利用 Linux 内核漏洞的难度。

至于我？对于这种钱，是时候拿出我的 [Linux 静态分析工具](https://thenewstack.io/checking-linuxs-code-with-static-analysis-tools/)了，看看我是否能找到任何线索来获得那些甜蜜的，甜蜜的 bug 赏金。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>