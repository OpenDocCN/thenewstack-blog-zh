# SC21: Fugaku 仍然是速度最快的超级计算机

> 原文：<https://thenewstack.io/sc500-fugaku-still-fastest-supercomputer-as-exascale-looms/>

最新发布的世界上最快的超级计算机列表显示，HPC 行业几乎没有什么进展，它正在焦急地等待人们讨论已久的 exascale 系统上线。

日本的巨型超级计算机 fuga ku T1 在一年两次的 T2 世界最快系统 500 强榜单 T3 中保持榜首位置，这是它在 2020 年夏天首次达到这一位置。最新名单于本周在[超级计算大会(SC21)](https://sc21.supercomputing.org/) 开始时发布。总的来说，榜单上的前 10 名系统仍然相当停滞，尽管一个新系统——由巨型云提供商微软 Azure 打造的 Voyager-EUS2，由 AMD 的 Epyc 服务器芯片和[Nvidia A100 GPU](https://thenewstack.io/nvidia-gpus-nudge-hpe-supercomputer-into-the-exascale/)提供支持——挤进了前 10 名，占据了榜单的第 10 位。

Azure 系统也说明了 AMD 在高端计算领域日益增长的实力，前 15 名中的许多最新系统都采用了该公司的硅技术。这份名单反映了 AMD 的 Epyc CPUs 在过去四年中作为顶级芯片制造商回归的作用，该公司在过去十多年中一直输给主要竞争对手英特尔。

这也是美国推动将更多系统列入清单的一部分，侵蚀了中国在过去几年建立的领先优势。

## **等待亿亿次运算**

然而，在这一切的背景下，exascale 计算的出现，这一转变将为系统提供运行复杂工作负载的计算能力，这些工作负载是当前机器无法完成的，或者需要很长时间才可行。据报道，田纳西大学计算机科学教授、橡树岭国家实验室研究员、500 强榜单的合著者 Jack Dongarra 在一次新闻发布会上表示，他曾希望在这份榜单上出现一个亿亿级系统。不幸的是，这并没有发生。

也就是说，亿亿级就在眼前。预计美国将在未来几年内推出三个亿亿亿级系统。由 AMD Epyc CPUs 和镭龙 Instinct MI200 GPUs 支持的惠普企业系统 Frontier 正在橡树岭组装。另一个 HPE 系统 Aurora 预计将于明年在阿贡国家实验室上线，它将运行在英特尔至强芯片及其即将推出的 Ponte Vecchio GPUs 上。

英特尔首席执行官[帕特·基尔辛格](https://www.linkedin.com/in/patgelsinger/)本月早些时候表示，在很大程度上由于 Ponte Vecchio GPUs 的性能，Aurora 将[提供超过 2 exaflops](https://thenewstack.io/intel-eyes-a-future-of-exaflops-and-zettabytes/) 的峰值性能。

与此同时，另一个运行在 AMD CPUs 和 GPU 上的 HPE 系统 El Capitan 计划于 2023 年在 Lawrence Livermore 实验室推出。

据报道，中国已经有两个亿亿亿次系统在运行，尽管该国没有向 500 强组织提交任何信息。此外，英特尔正在与芯片制造商 SiPearl 合作，为欧盟的 exascale 计划提供联合硅解决方案。

【Moor Insights and Strategy 的首席分析师 Patrick Moorhead 告诉 New Stack，超级计算机供应商和组件制造商正在密切关注他们的亿亿级计算的想法是合理的，特别是考虑到对下一级计算的兴趣增加。亿亿级系统尚未推出也不足为奇。

Moorhead 说，“一些组织正等着用 exascale 制造巨大而难忘的轰动”。"此外，达到万亿级是很困难的，需要更多的时间."

## **看看名单**

与此同时，该行业拥有的是 500 强名单上的系统，其中 Fugaku 名列榜首，并带有一点 exascale 的味道。该系统由富士通和理研计算科学中心联合开发，由富士通基于 Arm 的定制 A64FX 处理器的 760 多万个核心提供支持，HPL 基准测试成绩为每秒 442 petaflops，是榜单上第二台超级计算机 IBM Power Summit machine 的三倍多。

Top500 组织指出，在通常用于[人工智能](https://thenewstack.io/nvidia-offers-hosted-large-scale-processing-for-ai/) (AI)和机器学习应用的单一或进一步降低精度的环境中，Fugaku 的峰值性能超过 1 exaflop/s，基本上在这种情况下使其成为一台 exascale 机器。

继 Fugaku 之后的 8 个系统与 6 月份名单发布时的位置相同。如上所述，前 10 名中唯一的变化是 Azure 的 Voyager-EUS2，它是在云提供商美国东部地区成立的。它由 253，440 个 AMD Epyc 芯片(每个芯片有 48 个内核，速度为 2.4GHz)和 80GB 内存的 Nvidia A100 GPUs 提供支持。其性能为 30.05 plops/s。

穆尔黑德说，相对不变的名单是因为“各组织之间按百分比计算的资金逐年保持相对稳定”。“只有当采用不同的方法或架构发生变化时，才会有突破。”

## **大多数互连是以太网或 InfiniBand**

这也包括系统中使用的互连。500 强组织指出，以太网仍然是占主导地位的互连，被用于 240 台机器。InfiniBand 占了 180 台超级计算机，而 Omni-Path，一项由英特尔开发并于去年由芯片制造商剥离出来的技术(现由 Cornelis Networks 所有)，占了 40 个系统。Fugaku 使用富士通开发的豆腐 D 互连。Moorhead 表示，在英特尔开发的 CXL 技术获得牵引力之前，他不希望在互连领域看到以太网和 InfiniBand 以外的更多发展。

在国与国之间的超级计算竞赛中，美国在中国这两个占据 500 强榜单的国家面前取得了一些进展。中国的系统总数从 186 个下降到 173 个，而美国从 123 个上升到 150 个。这两个国家加在一起，几乎占了名单上系统的三分之二。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>