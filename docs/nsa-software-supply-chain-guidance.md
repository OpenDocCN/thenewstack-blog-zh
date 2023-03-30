# NSA 软件供应链指南

> 原文：<https://thenewstack.io/nsa-software-supply-chain-guidance/>

重要的事情先来。美国国家安全局(NSA)不仅仅是侵入他人的通信。美国国家安全局也致力于保护通信免受窃听。所以，就是 NSA 做出了最初的[安全 Linux(SELinux)](https://www.redhat.com/en/topics/linux/what-is-selinux)；撰写了关于如何[保护视频会议、文本聊天和协作工具](https://www.zdnet.com/article/heres-the-nsas-guide-for-choosing-a-safe-text-chat-and-video-conferencing-service/)的指南；现在解释如何[强化 Kubernetes 对抗攻击者](https://www.nsa.gov/Press-Room/News-Highlights/Article/Article/2716980/nsa-cisa-release-kubernetes-hardening-guidance/)。现在，他们与[网络安全和基础设施安全局(CISA)](https://www.cisa.gov/) 和[国家情报总监办公室(DNI)](https://www.dni.gov/) 一起，致力于保护软件供应链。

为什么？因为我们一直被一个可悲的简单事实所困扰，那就是我们的软件供应链安全就像瑞士奶酪一样强大。无数高调的攻击、漏洞和利用，如[网络安全管理软件产品](https://www.zdnet.com/article/solarwinds-the-more-we-learn-the-worse-it-looks/)惨败和 [Log4J 漏洞](https://www.zdnet.com/article/log4j-zero-day-flaw-what-you-need-to-know-and-how-to-protect-yourself/)，都清楚地表明我们必须提高其安全性。当情况变得如此糟糕时，约瑟夫·拜登总统发布了一项行政命令，呼吁我们所有人保护软件供应链的安全，你知道事情已经变得很严重了。

## 不仅仅是未修补的洞

历史上，软件供应链攻击是针对已发布程序中未打补丁的安全漏洞进行的。这种情况每天都在发生。但是，在过去几年中，源代码软件供应和修补系统本身正在受到损害。这些下一代软件供应链妥协攻击开源和商业软件产品。

因此，国家安全局和它的朋友们发布了[为开发者保护软件供应链](https://media.defense.gov/2022/Sep/01/2003068942/-1/-1/0/ESF_SECURING_THE_SOFTWARE_SUPPLY_CHAIN_DEVELOPERS.PDF)。[持久安全框架(ESF)](https://www.nsa.gov/About/Cybersecurity-Collaboration-Center/Cybersecurity-Partnerships/) 撰写了这份报告。这个公私合营的工作组提供安全指导，解决国家关键基础设施面临的高优先级威胁。

具体来说，它汇集了开发人员保护其软件所需的资源和最佳实践。展望未来，ESF 将为软件供应商和客户发布类似的文档。单靠开发人员无法保护我们的软件链。每个人都需要帮助。

这些新的攻击通常包括利用软件设计缺陷、整合易受攻击的第三方组件、在软件交付之前用恶意代码渗透供应商的网络，以及注入恶意代码，然后由客户部署。解决这个问题并不容易。保护软件开发生命周期是一个过程，而不是一个产品。

这也是一个巨大的工作量。引用报告中的话，“开发团队的安全培训最好由一个集中的专家安全团队来进行，他们可以帮助产品团队增长他们在安全开发方面的专业知识。”你的公司有这样的安全专家吗？他们也精通编程。我来回答你这个问题:你很可能不知道。很少有企业这样做。

## 推荐

该报告还支持自上而下的安全管理。在我 40 多年的计算经验之后，我可以有把握地说它很少能很好地工作。

另一方面，他们也建议使用自动化工具来帮助开发者更容易地保护他们的软件开发链。我强烈推荐这个。使用[左移安全软件过程](https://thenewstack.io/shift-left-where-cloud-native-computing-security-is-going/)要容易得多，例如[软件工件的供应链层次](https://security.googleblog.com/2021/06/introducing-slsa-end-to-end-framework.html) (SLSA，发音为“salsa”)；[软件包数据交换(SPDX)](https://spdx.dev/) / [软件物料清单(SBOM)](https://thenewstack.io/sboms-are-great-for-supply-chain-security-but-buyers-beware/)；和[静态应用程序安全测试(SAST)和交互式应用程序安全测试(IAST)](https://thenewstack.io/verification-scans-or-automated-security-requirements-which-comes-first/) 来保护程序，而不是培训开发人员成为安全专家。

不管怎样，我们必须保护我们的软件供应链。我们承受不起更多的安全灾难。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>