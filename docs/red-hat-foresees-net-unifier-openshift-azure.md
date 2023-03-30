# 微软，红帽协议承诺真正的跨平台微服务

> 原文：<https://thenewstack.io/red-hat-foresees-net-unifier-openshift-azure/>

“Windows 容器”如果只是在微软平台上运行，就不会很有趣。容器化的更广泛的理想是，Linux 和 Windows 工作负载可以在相同的云平台上共存，并且使用相同的底层硬件。

上周，微软和 Red Hat 达成了备受吹捧的和平协议，使得跨平台微服务的理想比以往任何时候都更加可行。虽然 [Azure 推出基于 Linux 的虚拟机已经有几年了](http://www.linuxjournal.com/content/linux-azure%E2%80%94-strange-place-find-penguin)，但这种虚拟化水平并不完全等同于互操作性。

这就更深入了:使用混合的。NET 语言、Java 和 Node.js，部署在完全许可的基于 Red Hat Enterprise Linux 的容器平台上，托管在 Microsoft Azure 上。或者，如果您愿意，可以使用 OpenShift 上的 Red Hat 原子主机。

“我们会包括在内。NET 技术，包括 RHEL 原子主机，以及我们的 OpenShift 平台，”红帽公司负责产品和技术的执行副总裁保罗·科尔米耶在周三与分析师的电话会议上说。

“我们认为这让开发人员能够构建包含以下内容的应用程序。NET 服务，如果这是他们需要并选择做的事情。我认为这将给我们带来跨技术的更好的互操作性，并真正开始给我们的客户提供他们真正想要的异构世界。我们希望一如既往地给予开发者在这方面的选择权。”

## 条件均等的机会

去年，[微软开源了。NET](https://thenewstack.io/why-you-should-care-about-the-new-open-source-net-core/) ，成为一个可互操作的框架。这使得红帽包括。NET 技术在 RHEL，而不改变其许可。

Azure 现在肯定不再是“Windows Azure”的简称。虽然 Azure 托管 Red Hat Linux 在技术上可行已经有一段时间了，但是到目前为止，它还是一个受支持的选项。这意味着 Azure 承认 RHEL 的许可，因此，RHEL 支持的一切都可以在 Azure 上运行，包括 RHEL 原子、JBoss 和 OpenShift。

Azure 上的红帽 Linux 上的 OpenShift。段落结束。

当红帽在 2011 年春天首次发布 OpenShift 时，紧随其早期收购面向 Java 的 PaaS 平台 Makara 之后，这个新平台被视为红帽对 Azure 的回应。在此期间，DevOps 专业人员找到了在 Azure 上部署 OpenShift 的方法，尽管不是通过使用 Red Hat Enterprise Linux。

去年，开源贡献者 [Isaac Christoffersen 分享了一个在 Azure 上部署 CentOS Linux 6.5 版本的过程](http://blog.vizuri.com/open-hybrid-cloud-with-openshift-origin-and-windows-azure)，然后占用该操作系统，以便 OpenShift 仍然可以从用于 Red Hat 产品的同一个 RHEL 6 仓库安装在那里。克里斯多佛森拒绝列举这个过程的步骤，这也许是明智的，以免他最终要详细阐述的步骤比一般卡片组的卡片还要多。

自从[甲骨文在 2010 年秋天](http://www.computerworld.com/article/2469218/network-software/oracle-rips-red-hat-and--sort-of--launches-a-new-linux.html)发布了它的 Linux 版本，它的名声就在于它与红帽 Linux 看似“牢不可破”的兼容性(很大程度上是因为甲骨文 Linux[在很大程度上基于](http://www.oracle.com/us/technologies/linux/product/comparisons/index.html)RHEL)。2013 年，微软 MSDN 开发者网络的一名成员发现了一种将 Oracle Linux 6.4 虚拟硬盘部署到 Azure 的方法。在对源代码的检查表明是后来添加的页面注释中，可能是为了回应问题，开发人员指出，将 RHEL 部署到 Azure 应该也是同样的过程，尽管他警告说这不是官方支持的。

当一个过程没有自动化时，它就不是非常理想的。任何人都想在 Azure 上安装 OpenShift，而不是为开源 PaaS 提供一个更友好的平台，唯一的原因可能是已经订阅了 Azure 的人不想在亚马逊上开第二个账户。这很可能是一个非常小的样本量。

## 墙壁倒塌了

去年 2 月，微软和 Red Hat 之间的障碍——包括技术上的障碍——看起来是如此难以逾越，以至于无法通过理性的手段来克服。GigaOM 的撰稿人巴布·律界英豪认为，解决这个混乱局面的唯一方法是微软直接收购红帽。

“鉴于微软已经竭尽全力让 Azure 适应第三方操作系统和工具集(Ubuntu Linux 和 SUSE Linux 在其上运行)，RHEL 的缺席尤其引人注目，因为当你谈论甲骨文和其他供应商的企业应用程序时，RHEL *是* Linux(对不起，甲骨文 Linux，你还没有)，”律界英豪写道。

就在 Red Hat 宣布它将启用开源应用程序之后。NET 在 OpenShift 上运行，红帽向全世界明确表示(通过*华尔街日报)*根据其公司条款，RHEL 的认证实例不得在未经认证的供应商的公共云平台上运行。

当然，RHEL 确实可以安装在 Azure 平台上运行的虚拟机上。但是把它弄到那里是 DevOps 的人做的一种技巧，这样他们就可以用视频记录这个过程，然后[在 YouTube](https://www.youtube.com/watch?v=7bvzhP4D4Nw) 上展示这个视频来打动朋友和潜在客户。

在潜在用户(更不用说投资者)的眼中，将 Red Hat 与微软隔开的那堵墙越来越像是一个不必要的、武断的障碍，更不用说两家公司都在宣扬多平台混合云计算的优点，这可能会让他们感到尴尬。所以墙倒了。正如红帽公司的保罗·科尔米耶告诉分析师的那样，开发商很快就会看到好处。

“我们现在的计划是集装箱化。“NET 在 RHEL 的一个容器中，”科尔米耶说，“供应用程序开发人员调用。所以现在，随着事情转向微服务之类的东西，你现在可以想象这些服务——无论它们是 JBoss 服务还是。NET 服务—用于连接跨越这四个领域的应用程序[ *裸机、虚拟机、私有云、公共云* ]。我认为 OpenShift PaaS 平台实际上开放了很多，让这些服务相互融合。”

在上周的分析师会议上，科尔米耶补充说，他认为 Windows 虚拟机和 Windows 容器有可能在 Red Hat OpenStack 上运行，从而使 Windows 和 Linux 混合工作负载具有一致的可扩展性。但微软执行副总裁斯科特·格思里(Scott Guthrie)立即补充说，微软目前没有让 Azure 运行在 OpenStack 上的计划——这是一种很好的方式，表明它们是两种不能混合的结构。

Guthrie 说:“从应用程序开发的角度以及基础架构工作负载的角度来看，我们认为这在公共云领域提供了最大的灵活性和选择，同时提供了这种混合功能，因此客户可以将这些在 Azure 中运行的 Red Hat 工作负载连接到本地的 OpenStack 环境，或者本地的 Hyper-V 或 Azure Stack 私有云。”

本周，两家公司都将展示出为了客户的利益而克服分歧的意愿。[微软与 Red Hat](https://azure.microsoft.com/en-us/campaigns/redhat/webinar/) 定于 11 月 11 日星期三美国东部时间下午 1:00/太平洋时间上午 10:00 举行联合网络研讨会。

但是，当两家公司交换工程联络员，在对方的工作场所工作时，他们的合作伙伴关系的真正力量还没有到来。在那里，他们不只是测试彼此的软件，而是为两条产品线和服务的客户提供技术支持。

红帽是新堆栈的赞助商。

专题图片:“[东西方在铺设最后一条铁路联合太平洋铁路](https://commons.wikimedia.org/wiki/File:East_and_West_Shaking_hands_at_the_laying_of_last_rail_Union_Pacific_Railroad_-_Restoration.jpg)”(由 [Andrew Russell](https://en.wikipedia.org/wiki/Andrew_J._Russell) 修复)，通过维基共享公共领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>