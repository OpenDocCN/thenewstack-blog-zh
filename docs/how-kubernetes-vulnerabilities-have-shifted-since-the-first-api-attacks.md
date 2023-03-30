# 自从第一次 API 攻击以来，Kubernetes 漏洞是如何转移的

> 原文：<https://thenewstack.io/how-kubernetes-vulnerabilities-have-shifted-since-the-first-api-attacks/>

Kubernetes 有许多内置的安全特性，但这并不意味着它开箱即用就是安全的。依赖性管理的安全性仍然缺乏，新的攻击媒介(如恶意容器)正在出现。尽管在安全性方面有所进步，API 仍然是 Kubernetes 的主要入口。

好消息是，在过去几年中，安全团队已经学到了很多关于如何保护 Kubernetes 部署和运行在容器上的应用程序的知识。这种威胁可以通过跨越开发人员、安全团队和 IT 运营部门的工作流和工具的组合来更容易地解决。例如，恶意容器和其他攻击媒介很容易通过异常检测和扫描工具发现。

在本期[New Stack Makers](/podcasts/makers)播客中， [Palo Alto Networks](https://www.paloaltonetworks.com/prisma/cloud) 的云安全宣传员 [Robert Haynes](https://www.linkedin.com/in/robert-haynes-7aa95a/) 讨论了 Kubernetes 超越原生功能的安全性，以及自几年前第一次 API 攻击发生以来 Kubernetes 漏洞格局的演变。《新书库》的创始人兼发行人亚历克斯·威廉姆斯主持了这一集。

[Kubernetes 已经进化，所以你的安全](https://thenewstack.simplecast.com/episodes/kubernetes-has-evolved-so-should-your-security)

Kubernetes 安全性及其局限性也是新堆栈的[“Kubernetes 生态系统的状态”](/ebooks/kubernetes/state-of-kubernetes-ecosystem-second-edition-2020/)电子书中涵盖的主题，Palo Alto Networks 是该电子书的赞助商。书中提到的一个主要安全问题是 Kubernetes 并没有提供一个组织可能需要的所有安全特性。然而，好消息是，在过去几年中，安全团队已经能够收集到很多关于如何保护运行在容器和 Kubernetes 上的部署和应用程序的信息。

“如果你评估 Kubernetes，它是如何工作的，它的设计目的是什么，人们试图滥用它的两三种主要方式是相当明显的，”Haynes 说。“我认为这一点在我们看到早期的关键简历时得到了反映。”

自从第一次 API 攻击以来，安全社区在评估攻击是如何策划的方面做得相当不错。Haynes 说，几年前针对 API 服务的第一次严重攻击“教会了我们一些我们已经知道的东西 Kubernetes 是软件，所有软件都有漏洞”。

“我认为我们可以从早期的事情中吸取的东西实际上非常令人鼓舞。所以，是的，确实存在问题，而且这是一个很多人都在使用的开源项目，存在严重的安全漏洞——人们会有什么样的反应？”海因斯解释道。“实际上，反响非常好。我认为 Kubernetes 的维护者应该对他们在发现、修复和沟通问题方面做得相当不错感到满意。”

尽管在安全性方面有所进步，API 仍然是 Kubernetes 的主要入口。“API 服务器是基础设施中一个关键且明显的部分，可能会受到攻击。Kubernetes 的建立是为了让开发者可以快速运行。在一个平台上，他们不必担心底层架构。因此，这意味着人们必须更好地访问…告诉它做事情，”海恩斯说。“因此，没有一个相当全面的控制平面是不可避免的，因此，这将始终是您需要严格保护的一点。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>