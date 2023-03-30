# 关于安全云原生开发的 5 件事

> 原文：<https://thenewstack.io/5-things-to-know-about-secure-cloud-native-development/>

[](https://ubuntu.com/blog/author/achalkias)

[Alex chalk IAS](https://ubuntu.com/blog/author/achalkias)

[Alex 是 Canonical 公司 Kubernetes 的产品经理。](https://ubuntu.com/blog/author/achalkias)

[](https://ubuntu.com/blog/author/achalkias)[](https://ubuntu.com/blog/author/achalkias)

云原生开发——从单一应用程序向可以在公共、私有或混合云上运行的灵活容器化应用程序的转变——是许多企业在数字化转型工作中遇到的巨大颠覆性浪潮。

埃森哲 [报告](https://www.accenture.com/_acnmedia/PDF-90/Accenture-Cloud-Native-POV-Final.pdf) 称:“ [云原生](https://ubuntu.com/blog/what-is-cloud-native) 是应用开发的未来，具有巨大的商业影响潜力 — 快速高效地将想法转化为产品的能力”。

[根据](https://www.cncf.io/wp-content/uploads/2020/08/CNCF-The-State-of-Cloud-Native-Development_Q419.pdf)[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)的数据，现在全球有 650 万[云原生](https://cncf.io/?utm_content=inline-mention)开发者，比 2019 年年中增加了 180 万，占后端开发者的 44%。大多数使用开源的 [Kubernetes](https://ubuntu.com/kubernetes/what-is-kubernetes?utm_source=google_ad&utm_medium=search&utm_content=what-is-kubernetes&utm_campaign=7014K000000mT2X&gclid=CjwKCAjwhaaKBhBcEiwA8acsHI_8hSNonQKnC2TNOhHDrh9w0aa4OTdL9DA5vUN8zryHh4lUj8Y1yhoChSUQAvD_BwE) ，这已经成为容器编排 事实上的选择。

然而，虽然云原生架构使组织更容易将新的数字解决方案更快地推向市场，但这些应用程序显然需要安全。

认识到这一现实，Kubernetes 委员会在 8 月发布的 1.22 版本中加强了安全功能。在现有的 [seccomp 支持](http://manpages.ubuntu.com/manpages/bionic/man2/seccomp.2.html)之上添加了一个 sec comp-默认安全层——sec comp(安全计算模式的缩写)是一个 Linux 内核特性，可用于限制容器内的未授权操作。

这个新特性应该是一个强大的工具，有助于减少沙箱逃逸攻击等入侵的出现，这些攻击允许恶意代码在容器环境之外的沙箱中执行。

但是，云原生开发安全性是一个复杂的话题，还有许多其他重要的安全考虑事项，开发人员应该了解并加以考虑。这里有五个:

## **1。** **仔细挑选你的依赖**

云本地开发人员可以使用丰富的资源来编写他们的应用程序。知道使用或不使用哪些资源也是前所未有的安全挑战。最近的 Unit 42 研究表明，部署在云基础设施上的 96%的第三方容器映像包含已知漏洞。

无论是针对 Docker Hub 和其他地方的 OCI (Open Container Images)图片，PyPI 上的 Python 包，NPM 上的 Node.js 包等等。，持续考虑开发人员可以依赖哪些内容以及依赖多长时间至关重要。质量好吗？它是否包含安全漏洞，或者更糟糕的是，恶意软件代码？是否积极维护并及时打补丁？

现在，开发人员比以往任何时候都更加必须小心谨慎，有意识地选择依赖项。企业可以通过提供“合理的默认值”来帮助他们的开发人员选择软件来支撑和支持他们的应用程序。

## **2。** **选择安全稳定的基础镜像**

容器映像中的软件很大程度上来自于基础映像的选择。基础映像为应用程序的运行提供了必要的基础，包括 SSL 和 libc 等共享库，并使开发人员能够专注于他们的应用程序，而不是整个容器。

通常，基础映像包含的软件往往比添加在基础映像上的应用程序多得多。软件越多，安全责任就越大。企业应该非常谨慎地选择一个安全稳定的基础映像。具体来说:

*   基础映像是否定期更新？它包含的软件，是否定期检查安全漏洞，或者它是否由很少使用的库组成？毕竟“眼光够了，每一个 bug 都很浅。” 
*   基础映像是否附带一个大型软件生态系统，以便您可以通过同样安全的软件轻松地在其上构建？还是需要从不太可信的来源添加到基础映像？ 
*   基础映像对开发者友好还是让开发者的日子更难过？难以使用的软件通常会导致开发人员不能正确使用它，或者以完成任务的名义偷工减料，从而造成更严重的安全责任。 

## **3。** **查看云原生构建包。**

[云原生构建包](https://buildpacks.io/) 项目由 Pivotal 和 Heroku 于 2018 年 1 月发起，同年 10 月加入 CNCF。借鉴上一代产品的最佳平台即服务(PaaS) ,云原生构建包使开发人员能够毫不费力地创建强化、优化、安全的代码容器。

Kubernetes 是事实上的云原生容器编排，但将运行复杂应用程序的许多重要方面留给了用户，如处理证书或选择和设置入口。最终用户想要的是一个全面、易用、可靠的 PaaS，能够很好地支持不同大小的组件。构建包提供了这一点。

## **4。** **补丁早，补丁勤**

在没有已知漏洞的情况下投入生产的软件可能会被发现一些漏洞。所有运行的软件必须保持最新，以防止违规。更新需要及时到来，并且推出它们必须尽可能容易和不引人注目。对于操作系统来说，这一点很好理解，对于容器来说也是如此。

因此，企业应该始终确保容器使用最新的安全补丁进行更新。这同样适用于运行时和容器下的基础主机:内核等难以移动的软件部分必须使用实时补丁等技术进行更新，这些技术可以减少计划外停机时间，并在生产关键型安全更新中无缝推出，而不会造成中断。

## **5。拥抱自动化**

软件越难打补丁，这种情况就越少发生。当发现漏洞时，需要快速、可靠、无处不在地进行修复，这需要部署过程完全自动化。在过去的几十年里，作为一个行业，我们在构建软件的自动化方面取得了长足的进步，这是 CI/CD 的持续集成(CI)部分。然而，由于自动化方面的差距，连续交付(CD)并不总是连续的，这影响了为我们的应用程序部署安全补丁所需的时间。

随着越来越多的组织转向云原生开发，最小化安全问题变得越来越重要。遵循这五个步骤可以大大帮助企业迎接挑战。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>