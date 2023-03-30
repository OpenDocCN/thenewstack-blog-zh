# 用静态分析工具检查 Linux 内核

> 原文：<https://thenewstack.io/checking-linuxs-code-with-static-analysis-tools/>

今年早些时候， [Greg Kroah-Hartman](https://thenewstack.io/greg-kroah-hartman-commander-chief-linux-stable-branch/) ，稳定分支的 Linux 内核维护者，愤怒地发现[明尼苏达大学(UMN)的安全“研究人员”试图用故意损坏的补丁毒害 Linux 内核](https://thenewstack.io/university-of-minnesota-researchers-tried-to-poison-the-linux-kernel-for-a-research-project/)。后来，UMN 的研究生声称他们的补丁是好的，基于他们新的静态分析器。克罗阿-哈特曼并不买账。

作为回应，他禁止整个大学提交内核补丁。

*[【补丁】显然不是由任何智能的静态分析工具](https://lore.kernel.org/linux-nfs/YH%2FfM%2FTsbmcZzwnX@kroah.com/)创建的，因为它们都是完全不同的模式的结果，并且所有这些显然甚至根本没有修复任何东西。那么，除了你和你的团队通过发送这种无意义的补丁继续在内核社区开发者身上做实验之外，我在这里应该怎么想呢？*

*当提交由工具创建的补丁时，每个这样做的人都会提交类似“由工具 XXX 发现，我们不确定这是否正确，请告知”的措辞你在这里根本不是这么做的。你没有寻求帮助，你声称这些是合法的修复，你知道这是不正确的。*

UMN 最终为自己的行为道歉。此后，[学校跟进了 Linux 内核社区](https://www.zdnet.com/article/university-of-minnesota-response-to-linux-security-patch-requests/)。经过适当的考虑，内核开发人员和 [Linux 基金会的技术顾问委员会(TAB)已经检查了所有潜在的破坏性补丁](https://www.zdnet.com/article/linuxs-technical-advisory-board-reports-on-the-umn-hypocrite-commits-patches/)，并决定探索再次与 UMN 合作的可能性，如果学校提高“建议纳入内核的更改的质量”

具体来说，TAB 要求 UMN 和许多其他组织一样:

指定一组经验丰富的内部开发人员在公开提交内核变更之前对提议的内核变更进行审核并提供反馈。这一审查发现了明显的错误，并减轻了社区反复提醒开发人员基本实践的需要，如坚持编码标准和彻底测试补丁。它产生了更高质量的补丁流，在内核社区中遇到的问题会更少。

TAB 的报告称，在此之前，“来自 UMN 的补丁将继续受到冷遇。”为什么，是的，他们肯定会的。

## 什么是静态分析工具？

让我们后退一步，看看是什么引发了这场爆炸。什么是静态分析工具，它们在 Linux 中是如何使用的？

正如[开放 Web 应用安全项目(OWASP)](https://owasp.org/) 所述，静态分析工具是源代码分析工具，又名[静态应用安全测试工具(SAST)](https://owasp.org/www-community/Source_Code_Analysis_Tools) 。它们旨在分析源代码或编译后的代码版本，以帮助找到安全漏洞。他们通过对照一组规则分析代码来做到这一点。

例如，几乎所有人都使用过或者很少听说过 [lint](https://www.embedded.com/introduction-to-lint/) ，这个原始的 C 和 C++静态分析程序。它寻找诸如未初始化的变量、超出数组边界的索引以及日益流行的空指针滥用等“明显”的问题。

虽然这对于在代码中找到真正的漏洞来说很好，但是您需要的不仅仅是 lint。其他静态分析程序使用编码指南，如 Perforce 的 [MISRA](https://www.perforce.com/resources/qac/misra-c-cpp) 或编程标准。细节有所不同，但游戏的名字总是一样的:对照一个已知的标准检查错误。

通常，静态分析用于在程序运行前找出源代码中的缺陷。例如，你可以在编码和[单元测试](https://www.guru99.com/unit-testing-guide.html#:~:text=UNIT%20TESTING%20is%20a%20type,an%20application%20by%20the%20developers.)或[动态代码测试](https://www.checkpoint.com/cyber-hub/cloud-security/what-is-dynamic-code-analysis/)之间进行。

但是，Linux 是一个不同的故事，它可以追溯到近 30 年前。到 2020 年， [Linux 内核就达到了 2780 万行代码](https://www.linux.com/news/linux-in-2020-27-8-million-lines-of-code-in-the-kernel-1-3-million-in-systemd/)。这有很多历史，很多代码，而且这些年来还出现了很多错误。因此，Linux 开发人员除了编写新代码之外，还不断地——尽管有时很不情愿——检查内核的旧代码中的错误。

有一个人不介意在古老的代码行中筛选错误，他就是[舒哈汗](https://www.linkedin.com/in/shuah-khan-9527a414/)、[内核维护者和 Linux 基金会的第三位 Linux 研究员](https://www.linuxfoundation.org/en/blog/interview-with-shuah-khan-kernel-maintainer-linux-fellow/)。Khan 有许多工作，但其中一项是带领开发人员从事 Linux 安全方面的工作。

“在开发过程中更容易发现和修复问题，”Khan 在接受新堆栈的采访时说。“静态分析是开发可靠软件的必要组成部分。我更喜欢在我的开发和补丁工作流程中尽可能地融入静态分析。”

因此，Khan 说，她在静态分析工具中寻找以下品质:

*   易于安装和使用
*   易于集成到开发和修补工作流程中
*   开发和测试系统易于升级和管理
*   易于添加到内核集成环中

Khan 说，在许多 Linux 静态分析工具中，特定于 Linux 内核的" [checkpatch.pl](https://github.com/torvalds/linux/blob/master/scripts/checkpatch.pl) 进行基于模式匹配的静态分析。对于新代码来说，这是一个很好的选择。它很容易整合到开发和补丁验收工作流中。”

## 稀疏，匹配，和瓢虫

另外两个必须使用的 Linux 内核静态分析工具是 [Sparse](https://lwn.net/Articles/689907/) 和 [Smatch](https://lwn.net/Articles/691882/) 。稀疏是由 Linus Torvalds 写的。这是一个简单的 C 解析器，可以查看程序的结构，并创建一个符号表，准确显示每个全局符号的定义位置。

然而，稀疏只查看程序的本地代码。Smatch 让您看到代码序列中的值是如何变化的。它还能让你发现那些永远或永远不会为真的情况；空指针；并根据代码路径锁定不同的状态。不用说，这对于验证错误路径和很少测试的代码非常有帮助。

“稀疏和 Smatch 的设计考虑到了内核，并且有从内核 Makefile 运行的钩子，”Khan 说。“它们很容易整合到开发工作流和补丁接受工作流中。Sparse 和 Smatch 具有外部依赖性，但在开发和测试系统上更容易管理和维护这些工具。”

另一个重要的工具是 [Coccinelle](https://coccinelle.gitlabpages.inria.fr/website/) ，它不再是特定于 Linux 内核的。这是一个模式匹配和文本转换工具，可以分析复杂的树型补丁并检测有问题的编程模式。它通过顶层 Makefile 应用语义补丁来工作。通常它会向开发人员提交一份报告，但是您可以运行它来为遇到的问题生成建议的补丁。

可汗认为这是“一个强大而复杂的工具。然而，有效使用它有一个陡峭的学习曲线，并且[它]有点难以整合到开发和补丁接受工作流中。”因此，她偏爱稀疏和匹配。

尽管如此，开发者认为 Cocinelle 值得花时间和精力去掌握。关于如何使用它的例子，请查看 Julia Lawall 的“Coccinelle:Linux 内核的 10 年自动进化”演示。

Khan 指出 [gcc](https://gcc.gnu.org/) 和 [clang](https://clang.llvm.org/) 是内核之外的工具，作为内核开发工作流程的一部分更容易使用。具体来说，Khan 推荐 gcc 10 是因为新的 [-fanalyzer](https://developers.redhat.com/blog/2020/03/26/static-analysis-in-gcc-10) 选项。这是一个内置的 C 静态分析工具。它还不适用于 C++。

她喜欢它，因为它“有助于发现内核代码中的问题”。这个特性很有用，因为它增加了对检测[软件开发类别](https://cwe.mitre.org/data/definitions/699.html)常见弱点枚举的支持。这类错误包括空解引用和释放后使用等。

Khan 继续说道，“我很高兴看到 gcc 增加了对 fanalyzer 的支持，并希望看到增加静态分析的覆盖范围，以检测与软件开发相关的[常见弱点枚举(CWEs)](https://cwe.mitre.org/) 。”这反过来“将使 Linux 及其生态系统更容易支持需要/强制静态分析的[安全关键](https://www.sciencedirect.com/topics/computer-science/safety-critical-systems)域的需求。”

## 假阳性的挑战

可汗对这些进展特别感兴趣，因为她也是 T4 ELISA 项目 T5 的技术指导委员会主席。ELISA 是一项开源计划，旨在创建一套共享的工具和流程，帮助公司构建和认证基于 Linux 的安全关键型应用和系统。

但是，尽管静态分析工具很好，但它们并不完美。“大多数静态分析工具都存在误报，”Khan 说。这使得“很难筛选出真正的错误。我也希望看到这方面的工具有所改进。误报是许多开发人员发现难以有效使用它们的主要原因之一。”

尽管如此，这些努力还是值得的。要了解更多关于 Linux 上的静态分析测试和其他代码安全测试方法，Khan 推荐关于静态分析概念和安全工具的 [LF Live: Mentorship 系列网络研讨会](https://events.linuxfoundation.org/lf-live-mentorship-series/)。这些都是免费的在线研讨会，对于任何想了解 Linux 开发和安全性的人来说都很有价值。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>