# PagerDuty 如何发展其事后最佳实践

> 原文：<https://thenewstack.io/how-pagerduty-developed-its-postmortem-best-practices/>

[page duty](https://www.pagerduty.com/)赞助本帖，关于[传播事件响应知识的系列文章之二](https://thenewstack.io/pagerduty-open-sources-its-incident-response-best-practices/)。

 [雷切尔·伯恩

Rachael 是一位敏捷人士，帮助跨职能部门的产品开发、移动、QA、客户支持和业务运营团队反复交付价值并有效协作。她是 PagerDuty 的第一个非技术事故指挥官。](https://www.pagerduty.com/) 

作为我成为 [事件指挥官](https://www.pagerduty.com/blog/top-skills-incident-commander/) 培训的一部分，我学习了 PagerDuty 的 [事件响应文档](https://response.pagerduty.com) 。我是一名前 scrum 大师，我对我们的事后分析过程特别感兴趣，因为它似乎是事件响应中持续学习和迭代改进的机制。

但是当我看到事故响应文档中的事后处理部分时，我惊讶地发现这个说明是如此的简单。

以下是尸体所有者最初几个步骤的简化版本:

1.  安排尸检会议；
2.  创建时间线；
3.  分析事件。

那就是我被卡住的地方。文档接着说，分析包括捕获影响和潜在原因，然后进行到第四步:“编写外部消息。”我在想，“等等，但是怎么做呢？”应该采取哪些行动和思路来确定潜在(或根本)原因？

因此，我们决定写一份关于如何进行尸检的综合指南。没有其他资源(我们发现的)涵盖文化变化的细微差别，如何进行深入分析的细节，以及促进关于失败的冷静和迷人的对话所需的独特技能。我们对这个新文档的目标不仅仅是概述过程的步骤和分享一些技巧和诀窍。相反，我们解释为什么这些概念是重要的，描述与实现它们相关的挑战，并提供可操作的指导来进行无可指责的事后分析。

软件故障固有的复杂性意味着识别根本原因说起来容易做起来难。在他的论文中， [“复杂系统是如何失败的”](http://web.mit.edu/2.75/resources/random/How%20Complex%20Systems%20Fail.pdf)Richard Cook 博士说，因为像软件这样的复杂系统对失败有很强的防御能力，所以这是一种明显无害的失败的独特组合，它们结合起来就产生了灾难性的失败。

此外，因为明显的失败需要多重错误，归因于“根本原因”从根本上说是错误的。复杂系统中的主要故障没有单一的根本原因；相反，它是导致失败的各种因素的组合。很少会有一个简单明了的答案来解释是什么导致了一个事件，如果这是您的事件分析的结果，那么您可能还没有进行足够的调查。

当我开始研究*如何*进行深入的事件分析时，我问了一些工程师他们通常采取的步骤。我了解到，他们也发现很难准确指出分析涉及的内容。他们只是调查。通过一系列采访和一些跨学科阅读，我能够确定重大事故事后分析的具体步骤——查看完整的 [事后文件](https://postmortems.pagerduty.com/how_to_write/writing/) 来阅读它们。

我明白了进行深度分析的关键是问正确的问题。你可能熟悉[“5 个为什么](https://www.isixsigma.com/tools-templates/cause-effect/determine-root-cause-5-whys/) ”方法论，但是我发现这个策略是任意限制的。我建议问一系列问题，从多个角度探究事件的起因。

另一种开始分析的方法是查看您对受影响服务的监控。搜索从事故开始到事故发生的异常情况，如突然的峰值或平缓。包括您用来从 [监控工具](https://www.pagerduty.com/blog/devops-monitoring-tools/) 中查找数据、图形图像或链接的任何命令或查询，以便其他人可以看到数据是如何收集的。如果您没有针对此服务或行为的监控，请将建筑物监控作为此事后分析的行动项目。

确定事故原因的另一个有用策略是在非生产环境中重现事故。通过修改变量来隔离这种现象。如果您修改或删除一些输入，事件还会发生吗？

此外，受 Gary Klein 在 Sidney Dekker 的“理解人为错误的现场指南”*，*中的报告问题的启发，我们编制了一个非详尽的问题列表，以帮助鼓励深入分析。

在事后会议上合作讨论事件会带来更深刻的见解。对于一个成功的事后总结会议，有一个熟练的主持人是很有帮助的，他不会试图在讨论中贡献自己的想法。他们仍然致力于创造一个让所有与会者都能舒服发言的环境。通过鼓励与会者提出任何和所有问题，主持人帮助小组达成共识并考虑新的观点。

要了解更多有关进行有效验尸的所有步骤和 [促进](https://postmortems.pagerduty.com/meeting) [验尸](https://postmortems.pagerduty.com/meeting) [会议](https://postmortems.pagerduty.com/meeting) 的提示，请查看 [PagerDuty 的验尸指南](https://postmortems.pagerduty.com/) 。

好奇想了解更多？ [为自己检查培训](https://sudo.pagerduty.com) 。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>