# Linus Torvalds 预测，到 2023 年，Linux 内核将会生锈

> 原文：<https://thenewstack.io/rust-in-the-linux-kernel-by-2023-linus-torvalds-predicts/>

德克萨斯州奥斯汀。— [Rust](https://thenewstack.io/rust-whats-next-for-the-fast-growing-programming-language/) ，快速发展的系统编程语言，可能会在明年，或者“也许是下一个版本”被合并到 Linux 内核中，据 Linux 的创造者 [Linus Torvalds](https://twitter.com/linus__torvalds) 称。

周二， [Linux](https://training.linuxfoundation.org/full-catalog/?_sft_product_type=training&utm_content=inline-mention&utm_source=thenewstack&utm_medium=website&utm_campaign=platform) 的创造者在 [Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)北美[开源峰会](https://events.linuxfoundation.org/open-source-summit-north-america/)的舞台采访中发表了声明。

在奥斯汀市中心的 J.W .万豪酒店(J.W. Marriott hotel)举行的峰会上，他的声明赢得了观众的热烈掌声，之后他警告说，“不要太激动。我们知道你是谁。”

他告诉采访者 [Dirk Hohndel](https://www.linkedin.com/in/dirkhohndel) ，卡尔达诺基金会[的首席开源官](https://cardanofoundation.org/)，鉴于全球有多少用户依赖 Linux，Linux 内核项目在如何做出改变方面变得更加谨慎。

“30 年前，我们更加随心所欲，”他告诉早期 Linux 贡献者 Hohndel。“这更像是狂野西部:有人会送来一个补丁，它就会被合并，为什么不呢？但现在我们负担不起这样做。”

托瓦尔兹指出，一些将新语言融入 Linux 内核的尝试并没有成功:“25 年前我们就尝试过 C++。我们试了两个星期。然后我们就不再尝试了。”

他说，这种谨慎是 Linux 项目的基石。“我一直告诉我的子维护人员和开发人员，‘你可以做任何事情，但我们不能破坏人们的工作量。’我们不能破坏别人做的事。"

他补充说，“如果你升级内核，它应该做它应该做的事情。如果不行，你应该冲我们大喊大叫。最终，真正重要的是用户。”

## “稳定的”开发过程

托瓦尔兹告诉霍恩德尔和观众，Linux 项目在开源世界中是一个异类。

“如果你看看一般的开源项目，它们通常都很小，”他说，几乎没有维护人员。“有很多项目只有五个人，偶尔还会出现临时拼凑的情况。然后你看内核。每次发布我都要和大约 50 个人互动。每次发布都有 1000 名开发人员参与。”

托沃兹说，放牧所有这些猫需要一个“平静的，可以说是‘稳重的’”发展过程。

> “30 年前，我们更加随心所欲。这更像是狂野的西部:有人会发一个补丁，它就会被合并，为什么不呢？但现在我们负担不起这样做。”

—Linus Torvalds，Linux 创建者

然而，他补充道，“我们有一个无聊而古板的开发并不意味着我们有一个无聊而古板的项目。我积极鼓励人们尝试新事物，”正如 Rust initiative 一样。

他承认，他说，一旦编程语言成为 Linux 内核的一部分，许多用户将需要接受教育:“我看到人们不理解 Rust。我们会有维修生锈零件的人。就像我们有其他部分的维护者一样。”

## 安全和硬件难题

当话题转移到软件最热门的话题[安全性](https://thenewstack.io/category/security/)时，托沃兹告诉观众，“任何认为你可以 100%安全的人都生活在一个梦想的世界里。这不是现实。”

他敦促人们接受错误是不可避免的，并使用多层安全措施来保证整个堆栈的安全。

他说，软件开发商无法控制的一个安全因素是不安全的硬件。他指出，从 2018 年 1 月起，英特尔 x86 微芯片上的 [Spectre 和 Meltdown 漏洞是一个转折点。](https://thenewstack.io/linus-torvalds-meltdown-spectre-perhaps-move-arm/)

托沃兹说:“在过去的五年里，人们越来越意识到，有时即使你编写了非常安全的软件——这很罕见，也很难——硬件最终还是会把你搞得一团糟。

“好消息是，现在比以前好多了。硬件问题变得越来越深奥，越来越罕见。”

他说，处理影响 Linux 内核的硬件错误仍然是“我最不喜欢的主题”。"但是五年后，你会逐渐习惯这种痛苦."

供应商对内核的需求有更好的响应了吗？霍恩德尔问道。

> “在过去的五年里，人们越来越意识到，有时即使你编写了非常安全的软件——这很罕见，也很难——硬件最终还是会把你搞砸。”

—Linus Torvalds，Linux 创建者

托沃兹建议说，是也不是。问题的关键是软件和硬件生产商之间的文化差异。

“硬件公司不习惯于你发布一些东西，然后每个月都有增量补丁，”他说。“你发布了你的硬件，而你的客户在三四年内都不知道他们有问题。”

托沃兹说，当 Linux 内核项目发现一个漏洞时，维护人员会在一周内修复它，并公布补丁。

他说，相比之下，有时当硬件供应商被告知他们的产品有缺陷，必须拿出一个修复方案时，“他们会说，‘这个产品的发布日期是 12 个月后。你就走吧，现在就杀了我。

## Git 信用太多？

当 Hohndel 问到他有什么爱好时，Torvalds 承认他自己摆弄了一些硬件，一个他在疫情早期设计的小电子板。他还提到他喜欢水肺潜水——并致力于一个旨在记录他潜水的开源项目。

他借此机会更正了他参与的另一个开源项目的记录: [Git](https://git-scm.com/) ，这是 2005 年创建的广泛使用的版本控制系统。

“我女儿上大学学的是计算机科学。我没有推她，”托瓦尔兹说，举起双手表示抗议。她告诉他，在她的 CS 部门，Git 的创建完全归功于他。

“我只在 Git 上工作了六个月，”他抗议道。

相反，他说，更多的功劳应该归于[朱尼奥·哈马诺](https://www.linkedin.com/in/gitster)，这位谷歌首席技术官自 2005 年以来一直是项目的关键维护者。"如果你见到他，请他喝杯啤酒或什么的。"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>