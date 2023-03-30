# Codefresh 发布了一个用于 CI/CD 管道的实时调试器

> 原文：<https://thenewstack.io/codefresh-releases-a-live-debugger-for-ci-cd-pipelines/>

[Portworx](https://portworx.com/) 赞助了 New Stack 对 KubeCon + CloudNativeCon 北美 2019 的报道。

Codefresh 提供了一个基于 Kubernetes 的持续部署和持续集成(CI/CD)平台，它发布了第一个用于 CI/CD 系统的实时管道调试器。它可以将复杂 CI/CD 管道中发现和修复问题的时间减少六分之一。

该公司在本周于圣地亚哥举行的 [KubeCon+CloudNativeCon 北美](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/)会议上展示了这项技术。

[Codefresh 首席技术宣传员 Dan Garfield](https://codefresh.io/) 在接受 New Stack 采访时表示，Codefresh 正试图避免陷入大型提交、推送、测试和重新运行似乎永无止境的循环中的常见 CI/CD 瓶颈。

加菲尔德说:“当你整天在 CI/CD 管道上工作时，你正在做出改变，测试这些改变的唯一方法就是重新运行管道。”。

他继续说，然后找出哪里出了问题是非常复杂的。Codefresh 构建了这一新功能，因为当您的 CI/CD 管道以调试模式运行时，您可以在该管道中设置断点，在出现错误的地方进行干预，并处理错误，所有这些都是实时的。实质上，您可以直接在管道中进行修改。

Garfield 说，在一个典型的企业 CI/CD 管道中，可能需要三个小时来完成这个迭代循环。新的 Codefresh 调试器将它缩短到 20 到 30 分钟。

另一个耗时的用例是当组织的生产 CI/CD 管道崩溃时。这种调试可能需要几个小时，因为“这些变化中的每一个都可能需要你通过几十个变化来重新运行你的管道，”加菲尔德解释说。

对于 Codefresh 的新功能，他说这个过程是同步的，所以只需要几分钟。“从来没有人有过这样的经历。在其他工具中做到这一点的唯一方法是用老方法进行更改并重新运行管道，”Garfield 说。

Garfield 继续说，为了让这个新的 CI/CD 调试工作流工作，你不仅仅需要发现生产中的问题。他说你需要在你的流程中建立适当的安全原则，包括基于角色的访问控制和基于账户的访问控制。

CI/CD 管道已经运行了很多年，但是从整体架构向微服务和高度分布式系统的转移逐渐增加了对这种工具的需求。

加菲尔德说:“当人们在构建单片应用程序时，他们的 CI/CD 管道可能是一个大麻烦，但这没关系，因为你只需要维护一个管道。”

他继续说道，“有了微服务，语言和管道会爆炸式增长。在 Codefresh，我们的使命是让所有这些转向微服务的人拥有一个可扩展、易于使用的 CI/CD 平台，使他们能够向前发展。”

现在，有数百甚至数千名开发人员将代码提交给一个 CI/CD 管道的企业。他们需要能够获得对他们代码的反馈，知道是否有任何问题，并恢复到以前的代码，所有这些几乎都是瞬间完成的，这样一个提交就不会成为阻塞。

“构建”选项卡中的另一个新功能也扩展到了整个组织，提供了一个显示所有项目的构建项目的全局视图，以及一个基于项目的视图，其中包含单个项目内部的设置。

新的 Codefresh CI/CD Live 调试器于 11 月初在一些帐户中上线，并将在接下来的几周内继续推出。你可以报名参加 12 月份的现场演示。

Codefresh 还在 KubeCon 上宣布，它现在提供与 DigitalOcean 的双击本地集成。加菲尔德认为这是一个更大趋势的一部分，即中小型公司正在采用 Kubernetes 架构，而 DigitalOcean 正是为这一趋势而构建的。

最后，在其“KuBEERnetes”社区活动中，Codefresh 宣布赞助 1 亿美元的开源基金，为开源项目提供资助，以便它可以用 Codefresh 构建其他项目。Codefresh 将于 2020 年推出，它将为所有这些开源项目的工具使用提供资金支持，无论供应商是谁。

云原生计算基金会和 KubeCon+CloudNativeCon 是新堆栈的赞助商。

由 Pixabay 的一个故事的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>