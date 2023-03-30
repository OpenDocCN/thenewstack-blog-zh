# 本周编程:关于敏捷之死的报道被大大夸大了

> 原文：<https://thenewstack.io/this-week-in-programming-reports-of-agiles-death-have-been-greatly-exaggerated/>

宣布编程语言、方法论、哲学等等都死了——我们就是喜欢这么做，不是吗？去吧，在谷歌上快速搜索一下“敏捷已死”。我们会等的。

是的，这些年来只有一些文章宣称敏捷方法——早在 2001 年随着敏捷宣言第一次被提出——已经死亡和消失了，但是本周，该宣言的第一批 17 个签署者之一，[阿利斯泰尔·考克伯恩](https://en.wikipedia.org/wiki/Alistair_Cockburn)在互联网上为备受争议的方法辩护。

考克伯恩写道[敏捷并没有死，恰恰相反](https://heartofagile.com/agile-is-not-dead-quite-the-opposite/)，他查看了一些数字，做了一些他称之为“信封背面的计算”,认为在众多谴责敏捷之死的文章背后有三个特殊的原因，并提供了一个反驳的论点:简单地说，如果你查看“知识工作者”的数字和敏捷周围的数字，敏捷才刚刚开始，而不是要结束。

但首先，回到三个原因:“虚假广告，误解社会中普通的思想运动，以及观察错误的曲线。”第一种基本上是写作，宣称敏捷已死，以销售下一个最好的东西，这有助于解释大量的文章。(然后点击诱饵。)很简单。然而，第二个原因与埃弗雷特·罗杰斯的“创新扩散”和杰弗里·摩尔的“早期采用者和早期大多数人之间的销售差距”有关两者都着眼于采纳和“思想在社会中的运动”，考克伯恩说，这里有两个部分导致了最后一个原因——我们“看到了错误的曲线”

你正在阅读的专家通常是创新者和早期采纳者。他们在 10-15 年前采用了敏捷。很自然地，他们继续前进，并在此后的第二轮或第三轮有趣的事情上工作。[……]例如，他们一直在关注精益创业、假设检验和敏捷产品管理。所有敏捷的结果，只是更高级一点。他们很自然地忘记了第一次发现敏捷方法的喜悦。他们认识的每个人都已经在使用它，或者已经向前迈进了一步。对他们来说，它看起来“过时了”，“死了”

所以也许这只是创新者和早期采用者中的少数人？考克伯恩继续说道，除此之外，我们只是在错误地解读图表。虽然敏捷似乎已经到了采用的后期阶段，但是考克伯恩说“我们从 2001 年以来所走的整个距离甚至没有填满罗杰斯创新扩散曲线的‘创新者’部分！"

本质上，如果我们只看更大的图片——全球劳动力中“知识工作者”的真实数字和增长，敏捷仅仅触及了表面。

## 本周的节目中

*   **将 FaaS 从无服务器中分离出来:** Techcrunch 为我们带来了一个关于[新开源项目的故事，该项目希望将无服务器的愿景扩展到功能之外](https://techcrunch.com/2019/08/27/new-open-source-project-wants-to-expand-serverless-vision-beyond-functions/)。该项目名为 [CloudState](https://cloudstate.io/) ，旨在通过利用现有技术，如 KNative、gRPC、Akka Cluster 和 Kubernetes 上的 GraalVM，来“增强”功能驱动的编程，而不是取代它。本质上，Lightbend 首席技术官 Jonas Bonér 提出了一个[熟悉的论点](https://thenewstack.io/stackery-cloudlocal-brings-lambda-debugging-to-the-laptop/)FaaS 和无服务器经常互换使用，而 FaaS 只是无服务器的一部分，他告诉 TechCrunch“我认为这实际上是缩短了技术。通过尽可能多地尝试自动化，无服务器真正带来的是全新的开发人员体验和运营体验。”Techcrunch 将该项目总结为旨在“实现无服务器意味着什么的更广泛愿景，即开发人员只需编写代码，而不必担心程序运行的底层基础设施。”听起来很棒，不是吗？

*   **容器和虚拟机，和谐相处？**早期，容器和虚拟机总是被认为是非此即彼的，现在它们越来越多地一起工作。本周，在一年一度的 VMWorld 大会上，真正让虚拟机无处不在的 VMware 公司[推出了 Project Pacific](https://blogs.vmware.com/vsphere/2019/08/introducing-project-pacific.html) ，首席技术官 Kit Colbert 称之为“过去十年中 [vSphere](https://www.vmware.com/products/vsphere.html?int_cid=70134000001Caa3&src=WWW_us_VMW_XAa7eBfF5Crp1KEmV6Ly) 的最大演变”那么为什么这是革命性的呢？嗯，VMware 正在“重新设计 vSphere，以深度集成和嵌入 Kubernetes”，这将成为[VMware Tanzu](https://blogs.vmware.com/cloudnative/2019/08/26/vmware-completes-approach-to-modern-applications/)的基础，“这是一个产品和服务组合，改变了企业在 Kubernetes 上构建软件的方式。”如果你打不过他们，就加入他们，好吗？Project Pacific 将提供原生的 Kubernetes 体验，将 Kubernetes 控制面板嵌入到 vSphere 中，使 vSphere 用户能够“从 vSphere Client 查看和管理 Kubernetes 对象(例如，pod)。”该项目不是单独处理虚拟机和容器，而是提供应用程序级管理，“为开发人员应用策略、配额和基于角色的访问”，以及对计算、存储和网络资源的统一访问。欲知详情，请查看我们对新闻的[报道。](https://thenewstack.io/vmwares-project-pacific-integrates-vsphere-with-kubernetes/)

*   **关于 Rust 取代 C 进行系统编程:**在最近的开源技术峰会上，英特尔首席工程师 Josh Triplett 上台讨论[系统编程的未来](https://www.youtube.com/watch?v=l9hM0h6IQDo)——或者如 PaktPub 在其文章[中解释的那样，“Rust 是系统编程的未来，C 是新的汇编语言。”PaktPub 写道:](https://hub.packtpub.com/rust-is-the-future-of-systems-programming-c-is-the-new-assembly-intel-principal-engineer-josh-triplett/)这个演讲概述了“系统编程的历史，C 如何成为‘默认’的系统编程语言，Rust 的哪些特性使它比 C 更有优势，等等。”。至于为什么 Rust 看起来准备取代 C 的位置，他们提供了 Triplett 的推理:“Rust 解决了 C 中的内存管理问题，它提供了自动内存管理，这样开发人员就不必对每个对象手动调用 free。它与其他现代语言的区别在于它没有垃圾收集器或任何类型的运行时系统。相反，Rust 有所有权、借用、引用和生存期的概念。[…]没有运行时也是 Rust 的一个优势。Triplett 认为，拥有运行时的语言很难用作系统编程语言。

[https://www.youtube.com/embed/l9hM0h6IQDo?feature=oembed](https://www.youtube.com/embed/l9hM0h6IQDo?feature=oembed)

视频

*   **亚马逊转录增加普通话&俄语:** Linguiphiles 听起来——[亚马逊转录现在支持普通话和俄语](https://aws.amazon.com/blogs/aws/amazon-transcribe-now-supports-mandarin-and-russian/)，使[支持的语言总数](https://docs.aws.amazon.com/transcribe/latest/dg/what-is-transcribe.html)达到 16 种。该公司在 AWS re:Invent 2017 上首次推出了自动语音识别服务亚马逊转录，并继续向其武库中添加语言，这些语言可以通过一个 API 调用来使用。从本质上说，这项服务可以分析音频文件，并提供转录语音的文本文件，甚至可以实时翻译。
*   **我宣誓效忠 Python 3…** 随着 Python 2.7 的生命周期即将结束，现在是项目转向 Python 3 的时候了，正如 SDTimes 在关于[的故事中所述，许多知名项目都签署了对 Python 3](https://sdtimes.com/data/a-pledge-to-python-3/) 的承诺。这些项目包括 TensorFlow、Apache Spark、Apache MXNet、Tornado、pandas、scikit-learn 和 SciPy 等。Python 2 的支持已经延长了五年，但是时间到了 2020 年 1 月 1 日，所有签署了[誓言](https://python3statement.org/)的人都发誓“不晚于 2020 年放弃对 Python 2.7 的支持，与 Python 开发团队放弃对 Python 2.7 支持的[时间表一致。”该网站提供了](https://www.python.org/dev/peps/pep-0373/#update)[放弃 Python 2 并迁移到 3 的原因和方式](https://python3statement.org/#sections50-why)，甚至检查了[这样做的可行性](https://python3statement.org/practicalities/)。

*   **GitLab 讨论其单一代码库的使用:**GitLab 撰写了一系列博客文章，跟踪其[向单一 Rails 代码库的转移](https://about.gitlab.com/2019/02/21/merging-ce-and-ee-codebases/)，现在该公司提供了关于[为什么他们为 git lab 社区和企业版使用单一代码库的更新](https://about.gitlab.com/2019/08/23/a-single-codebase-for-gitlab-community-and-enterprise-edition/)。他们写道，原因很简单:“多年来，CE 和 EE 为 Rails 应用程序使用了两个不同的存储库。通过使用独立的库，我们可以将私有代码与自由软件代码分开。从表面上看，出于不同的原因(例如，许可)，这似乎是一个好主意，但随着时间的推移，缺点开始超过好处。”他们写道，最大的问题之一是如何在合并成单一代码库的同时保持专有代码和开源代码的分离。“Ruby 为我们提供了这个问题的解决方案。在 Ruby 中，你可以创建一个模块并把它注入到另一个模块或类中。一旦注入，目标模块或类就可以使用该模块的功能。因此，GitLab 创建了 gitlab-foss 库，它本质上是企业版的一个依赖项。GitLab 表示，它预计在 9 月的第一周会有一个单一的代码库，GitLab 12.3 将是第一个使用单一代码库的。
*   TypeScript 3.6 发布:本周，TypeScript 3.6 终于发布了[，PaktPub 再次对其进行了总结，列举了](https://devblogs.microsoft.com/typescript/announcing-typescript-3-6/)[更严格的生成器、TypeScript playground 中的新功能、对标识符更好的 Unicode 支持](https://hub.packtpub.com/typescript-3-6-releases-with-stricter-generators-new-functions-in-typescript-playground-better-unicode-support-for-identifiers-and-more/)等关键新特性。此外，他们写道，3.6“包含了语言和编译器中的许多新特性，如更严格的生成器、更精确的数组分布、改进的 UX 承诺、对标识符更好的 Unicode 支持等等。TypeScript 3.6 还探索了新的 TypeScript 平台、新的编辑器功能和许多突破性的变化。”

GitLab 是新堆栈的赞助商。

Feature image: “The Death of Socrates,” Jacques Louis David French, 1787, public domain, courtesy of [the New York Metropolitan Museum of Art](https://www.metmuseum.org/art/collection/search/436105?&searchField=All&sortBy=Relevance&what=Oil+paint&ft=death&offset=0&rpp=20&amp;pos=1).

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>