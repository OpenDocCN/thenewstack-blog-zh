# Docker CEO: Docker 已经是一个安全平台了(也就是说有了 Swarm)

> 原文：<https://thenewstack.io/ceo-ben-golub-docker-already-security-platform-swarm/>

Docker Inc .的首席执行官 Ben Golub(上图右，与 HPE 执行副总裁 Antonio Neri 在一起)在上周二上午举行的[HPE 2016 年伦敦探索大会](https://www.hpe.com/events/discover/)上告诉与会者，Docker 平台通过其独特的架构解决并改善了用户的安全问题，这强化了其公司的营销信息，即集装箱化作为一种架构在设计上更安全。

Golub 告诉与会者:“我们从这个星球上使用 Docker 的最有安全意识的组织那里听到的是，他们使用 Docker 并不是出于安全考虑，而是为了解决安全问题。”

这位首席执行官然后引用了【2016 年 7 月 Gartner 分析师 Joerg Fritsch 的一篇博客文章，建议该分析师小组的客户，容器化的应用程序通常比运行在裸机或基于虚拟机的基础设施上的应用程序更安全。

Fritsch 写道:“尽管容器无法防止应用程序受到危害，但它们极大地限制了成功危害的损害，因为应用程序和用户是基于每个容器隔离的，因此它们无法危害其他容器或主机操作系统——只要主机操作系统上不存在内核权限提升漏洞。”

自从两年前码头工人安全问题首次在[被提出以来，最后一条就一直是人们关注的焦点。迄今为止，还没有人成功地恶意利用这个理论上的安全漏洞。但是软件工程师直到今天还在不断发出警告，容器的主机操作系统内核可能受到危害，导致容器完全暴露。](https://thenewstack.io/the-new-stack-analysts-show-9-dockers-inherent-lack-of-security-the-black-hat-view/)

去年 10 月，安全开发人员 [Gabriel Lawrence 在 YouTube](https://thenewstack.io/the-new-stack-analysts-show-9-dockers-inherent-lack-of-security-the-black-hat-view/) 上发布了一段视频，旨在演示在 Amazon AWS 实例上运行的安全测试环境中，[Linux 内核漏洞如何被利用](https://blog.paranoidsoftware.com/dirty-cow-cve-2016-5195-docker-container-escape/)来修改容器的内容，以根级别权限打开容器的外壳。

这里使用的 Linux 函数是写时复制(COW)特性，它的一部分代码显然是作为库的一部分跨多个 Linux 进程共享的。虽然我们不会解释这个漏洞，只是为了给任何人一些坏主意，但足以说劳伦斯的演示似乎显示了任意恶意代码被复制到同一个库中，从而充当提供漏洞的代理。

《米特 CVE 词典》将这种虫子归类为 CVE-2016-5195，人们开始称它为“肮脏的母牛”公平而明确地说，这是一个 Linux 错误，而不是 Docker 错误。

但在某种程度上，这就是问题所在:Docker 容器对 Linux 内核的依赖，从理论上来说(而且，正如 Lawrence 可能指出的那样，主动地)可能会将托管容器暴露给内核本身面临的任何漏洞。随着我们越来越清楚地认识到，Linux 中可能有许多未被利用的 bug，它们在 Docker 问世之前很久就已经潜伏起来了。

在[去年 8 月 Docker 安全总监 Nathan McCauley](https://thenewstack.io/foundation-of-secure-containers/) 为新的 Stack Analysts 播客所做的采访中，他评论说任何新技术的安全性问题都可能出现。但是在过去的两年里，他说，他的公司和它的贡献者已经在 Docker 平台中引入了“基础”安全措施。其中一项措施是加密节点身份，他将其描述为 PKI 注册表，为 Docker 群环境中的各个服务器节点提供可验证的身份。Swarm 是 [Docker 的编排引擎](https://thenewstack.io/docker-engine-1-12-will-come-built-orchestration-capabilities/)，现在嵌入在核心 Docker 引擎中。

“我们已经实现了一个实际上非常容易使用的 PKI，”McCauley 说，“在我们做的最初演示中，甚至在 Docker[*Inc .*]这里，我们也没有说任何关于它的事情。我们刚刚打开它，它是默认打开的，所有的命令看起来完全一样。的原因。。。是因为它们都是默认内置的。作为 Swarm 一部分的每个 Docker 引擎都有一个 TLS 身份，这使我们能够在此基础上构建一堆东西。”

Docker Inc .的 Golub 在给 HPE 发现伦敦的评论中表示，Docker 平台的自动化元素(他没有命名，但他指的是 Swarm)完善了其安全模型。推而广之，他认为，只要数据中心能够信任其容器映像的真实性，以及在服务器集群中托管这些映像的节点，那么被肮脏的牛、猪、羊或任何可能出现在 Linux 漏洞堆中的东西利用的可能性就可以忽略不计了。

“如果你想一想，这意味着什么:如果你正在部署的一切都是从源构建的，放入一个容器中，经过数字签名，可以扫描已知的漏洞，可以自动化和测试，并且[你可以]在几秒钟内完成这些，”Golub 说，“那么你正在部署到基础设施中的东西出现问题的可能性非常低。如果有问题，当然，总会有[问题]，您可以跟踪它，并像[*snap*]那样修复它。您可以推送更新，而不必关闭服务器，也不必做类似的事情。所以你实际上更安全，更有弹性。”

Docker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>