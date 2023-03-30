# “DevSecOps Insights 2020”:谁真正拥有 DevOps 的安全性

> 原文：<https://thenewstack.io/devsecops-insights-2020-who-really-owns-security-in-devops/>

[](https://www.linkedin.com/in/talliran/)

 [李然塔尔

李然是 Snyk 的开发者倡导者，也是 Node.js 安全工作组的成员。Liran 还是 Essential Node.js Security 的作者，是 OWASP NodeGoat 项目的核心贡献者，喜欢涉猎代码、测试和软件哲学。在 Snyk.io 免费注册，查找并修复开源库和容器中的漏洞。](https://www.linkedin.com/in/talliran/) [](https://www.linkedin.com/in/talliran/)

DevOps 是一个快速发展的领域，但有时在通往终点的比赛中，有些步骤可能会被忽略，安全性很可能就是这样一个步骤。

在 Snyk 的 DevSecOps Insights 2020 报告中，我们确定了一些可能存在安全失误的领域。“安全是每个人的事”这句话几乎成了老生常谈，但实际情况往往更加微妙。

我们关注的一个重要话题是责任问题。通常，您可能认为安全专业人员负责安全；但我们发现的不是这样。事实上，根据我们纳入 Puppet 报告的数据，在报告中，48%的受访者仍然认为安全性是快速交付软件能力的主要制约因素。

当这么多的回答者同意在尝试快速交付软件时安全性是一个主要关注点时，这意味着我们需要提升安全性以支持安全修复的快速交付。这样做的关键在于开发人员，因为他们最终会修复应用程序源代码中的安全问题。这也与我们的调查一致，我们的调查发现 81%的受访者指出，他们认为开发人员应该对自己代码的安全性负责。

应用程序代码安全性并不是我们的调查解决的唯一问题，因为应用程序通常仍然需要某种服务或基础设施来运行。当被问及他们认为谁应该负责基础设施的安全时，61%的人回答说这是安全团队的责任。

除了谁应该负责之外，我们还研究了组织在开发运维管道中采用的应用安全方法。

## 测试的是什么

今天的开发人员使用不同方法的组合来审计代码。我们发现开发人员既进行手工审查(79%)，也利用自动化安全测试工具(65%)。

在测试时，57%的人指出他们测试了开源代码依赖中的已知漏洞。虽然这是大多数受访者，但仍然不是一个很大的数字，这意味着 43%的人没有扫描这些问题，这可能会使他们的组织面临严重的风险。

雪上加霜的是，只有 14%的受访者报告说他们测试了容器图像中的已知漏洞。集装箱图像缺乏扫描是一个真正的问题。
[《2019 年 Snyk 开源安全状况报告》](https://res.cloudinary.com/snyk/image/upload/v1551172581/The-State-Of-Open-Source-Security-Report-2019-Snyk.pdf?utm_medium=Paid-Content&utm_campaign=Contributed-Article&utm_content=DevSecOps-Insights-2020-The-New-Stack-Q1-2020)显示，调查受访组织扫描的 44%的 Docker 映像存在已知的安全漏洞，有更新、更安全的基础映像可供使用。

Snyk 2019 年的报告[“未知领域:赫尔姆海图安全的未知故事”](https://snyk.io/wp-content/uploads/helm-report.pdf)也进一步澄清了不扫描集装箱图像的风险。在该报告中，我们发现 68%的稳定舵图表包含具有高严重性漏洞的容器映像。

## 为什么 DevSecOps 如此重要

借助 DevOps，自动化是整个持续集成(CI)/持续部署(CD)流程的主要组成部分。

DevSecOps 的概念是将安全性集成到 DevOps 中，但我们的研究发现这并没有像应该的那样经常发生。不幸的是，38%的受访者表示他们没有将自动化安全扫描集成到他们的 DevOps 管道中。

缺乏集成安全方法的组织发现他们交付软件的能力很快受到限制。“ [2019 傀儡开发状态](https://puppet.com/resources/report/state-of-devops-report/)”报告发现，48%的受访开发者表示，安全性是减缓他们发布软件能力的主要制约因素。

根据 Puppet 的研究，当安全和部署团队需要协作时，这种限制可能会在所有级别的开发运维成熟度之间产生摩擦。

那么应该怎么做呢？我们有一些想法:

1.  **拥抱安全集成。**当团队各自为政，活动和总体目标不一致时，他们会制造紧张和摩擦，表现为安全失误。
2.  安全是共同的责任。在整个组织中树立共同责任感有助于树立安全第一的思想。
3.  **在 DevOps 上执行良好是 DevSecOps 的关键。**当组织展现出强大的 DevOps 工具和文化采用水平时，他们就处于有利地位，可以进一步实现安全实践和开发合作。

归根结底，重要的是，安全性不是事后才想到的，也不是在流程结束时附加上去的。为了使安全和 DevSecOps 发挥作用，它需要成为流程的自动化和集成部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>