# 网络安全管理软件产品，世界上最大的安全失败和开源的更好的答案

> 原文：<https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/>

网络安全管理软件产品专有软件猎户网络监控产品供应链安全故障越来越大。自身也是受害者的微软报告称[40%的用户安装了猎户座](https://www.fireeye.com/blog/products-and-services/2020/12/global-intrusion-campaign-leverages-software-supply-chain-compromise.html)的木马版本。受害者包括美国能源部和国家核安全局，至少一些州政府，以及许多其他人。

有多糟糕？网络安全基础设施和安全局表示，黑客攻击[对美国各级政府构成了“严重风险”](https://arstechnica.com/information-technology/2020/12/feds-warn-that-solarwinds-hackers-likely-used-other-ways-to-breach-networks/)。就是这么糟糕。

然而真正引起我注意的是网络安全管理软件产品多年来一直反对开源。云原生计算，从 [Docker](https://www.zdnet.com/article/what-is-docker-and-why-is-it-so-darn-popular/) 和 [Kubernetes](https://kubernetes.io/) 到[云原生计算基金会(CNCF)](https://www.cncf.io/) [云原生交互格局](https://landscape.cncf.io/)上的最后一个小程序都是开源的。

具有讽刺意味的是，网络安全管理软件产品声称开源软件是不可信的，因为任何人都可以用恶意代码感染它。一位网络安全管理软件产品作家声称:[安全“当涉及到专有软件时，风险要小得多。由于开源软件允许任何人更新代码的特性，下载恶意代码的风险要高得多。网络安全管理软件产品社区的一名成员称使用开源软件为“用脏叉子吃饭”。他写道，“当你在抽屉里拿一把干净的叉子时，你可能会拿出一个脏的器皿。这个类比是正确的。"](https://thwack.solarwinds.com/t5/Geek-Speak-Blogs/The-Pros-and-Cons-of-Open-source-Tools/ba-p/478665)

没错。当然可以。

网络安全管理软件产品接着在另一篇博客中评论道，云原生计算的整个基础——容器和容器编排也不可信。[网络安全管理软件产品联邦销售工程高级经理 Omar Rafik](https://www.linkedin.com/in/omar-rafik-27b50a88/) 写道，“容器的设计妨碍了可视性”“[当使用 Docker Swarm 或 Kubernetes 等编排工具](https://thwack.solarwinds.com/t5/Geek-Speak-Blogs/Will-Security-Concerns-Break-Open-Source-Containers/ba-p/506038)来管理不同容器之间的连接时，可视性变得特别成问题，因为很难判断发生了什么。”

相信我们，我们已经知道安全性是云计算中的一个挑战。我们[每天都致力于锁定云计算。](https://thenewstack.io/kubernetes-security-best-practices-to-keep-you-out-of-the-news/)

但是，开源并不是本质上不安全的。专有软件——一个你永远不知道到底发生了什么的黑匣子——现在是，过去是，将来也永远是一个更大的安全问题。

我不会相信任何对专有软件至关重要的东西，就像我不会在晚上开一辆没有灯或没有系好安全带的车一样。这就是为什么我在 Linux Mint 上用 LibreOffice 写这篇文章，而不是用 Windows 和微软的 Word。这就是为什么互联网、云计算和云——是的，甚至是微软 Azure——使用 Linux 和开源。

现在，开源软件没有什么神奇的。那些认为当你使用开源软件时奇迹会发生并且你在某种程度上绝对安全的人——当他们没有更新他们的软件时，他们活该。在这种情况下，是 [Apache Struts](https://struts.apache.org/) 。

在另一个臭名昭著的案例中，在验证包含长度的变量时，在 [OpenSSL](https://www.openssl.org/) 中遗漏了一个简单的错误，导致了 [Heartbleed 安全漏洞](https://www.zdnet.com/article/heartbleed-open-sources-worst-hour/)。我称之为开源迄今为止最大的失败。我没有错。

那么，为什么有了这些历史，我还要说开源软件本质上更安全呢？因为确实如此。

一个基本的开源原则是，通过给程序带来更多的关注，更多的错误将被发现。这并不意味着所有的错误都被发现了，只是比一个独立公司的错误要多得多。

由此得出的推论是 Eric S. Raymond，开源的创始人之一，他有一句名言，“[给了足够的眼球，所有的错误都是肤浅的](http://www.catb.org/~esr/writings/cathedral-bazaar/cathedral-bazaar/index.html)”他称之为“莱纳斯定律”效果很好。想想严重的 Windows bugs 的数量——一个月没有一个 bug 了吗？—与 Linux 相比。

有很多方法可以找到那些开源错误。你当然可以自己做。毕竟，代码是公开的。不确定您的软件供应链计划中有什么新内容？你可以使用[红帽](https://www.redhat.com/en)的[发布监控](https://release-monitoring.org/)或者[回复](https://repology.org/)。nvchecker 程序也很有用。或者，你可以看看第三方代码分析工具 [Synopsys 的黑鸭子](https://www.synopsys.com/software-integrity/security-testing/software-composition-analysis.html)或 [Sonatype Nexus Lifecycle](https://www.sonatype.com/nexus/lifecycle) 。

[Linux 基金会](https://www.linuxfoundation.org/)也一直致力于用[开源安全基金会(OpenSSF)](https://openssf.org/) 武装开源软件链。这个跨行业的组织通过构建一个更广泛的安全社区，将开源领导者聚集在一起。它结合了来自[核心基础设施倡议(CII)](https://www.coreinfrastructure.org/) 、 [GitHub 的开源安全联盟](https://github.com/Open-Source-Security-Coalition/Open-Source-Security-Coalition)以及其他开源安全公司的努力，如 GitHub、GitLab、Google、IBM、Microsoft、NCC Group、OWASP Foundation、Red Hat 和 VMware。

微软 Azure 首席技术官 Mark Russinovich 表示，OpenSSF 的目标是帮助开发者更好地理解开源软件生态系统中存在的安全威胁以及这些威胁如何影响特定的开源项目。

为了帮助强化开源软件，该基金会有四个目标。1)帮助开发者发现安全问题，2)为开源开发者提供最好的安全工具，3)为他们提供最佳实践建议；以及 4)创建一个开源软件生态系统，在该系统中，修复漏洞并在整个生态系统中部署补丁的时间是以分钟而不是以月来衡量的。

简而言之，像网络安全管理软件产品这样的专有软件公司仍然在犯巨大的安全错误，这些错误对用户是隐藏的，直到损害已经造成。当时，开源程序员和他们的盟友正在继续使他们的程序更加安全和开放，以便每个人都受益。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>