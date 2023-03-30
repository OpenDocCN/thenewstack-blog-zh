# Pivotal Cloud Foundry 现在可以通过 Concourse 提供自动修补

> 原文：<https://thenewstack.io/pivotal-cloud-foundry-now-can-offer-automated-patching-concourse/>

Pivotal 将其 [Concourse](https://concourse.ci/) 软件作为 [Pivotal Cloud Foundry](https://pivotal.io/platform) 服务平台的默认持续集成/持续部署(CI/CD)工具。

该公司将[工具](https://content.pivotal.io/announcements/security-innovation-through-platform-automation-pivotal-launches-concourse-for-pivotal-cloud-foundry)吹捧为在补丁发布后几小时内自动修复操作系统和应用程序堆栈的特别有用的工具。它使用户能够完全自动化地加载、测试和应用安全补丁到他们的整个云平台。

“我们一次又一次地看到，组织可能很难仅仅推出补丁。这是一种工具，可以消除猜测，”Pivotal 的首席产品安全官[贾斯汀·史密斯](https://twitter.com/justinjsmith?lang=en)说。

他指出 [Wanna Cry](https://www.forbes.com/sites/jasonbloomberg/2017/05/14/deeper-lessons-from-this-weeks-massive-ransomware-attack/#430d81731a10) 勒索软件攻击是组织未能应用可用补丁的最新例子。

他说，早在 2015 年，该公司就开发了自己的 CI/CD 和其他任务自动化工具 Concourse，作为开源工具。

他说:“我们已经把所有自己的基础设施都转换过来使用它，我们发现它非常强大。”。

**"** 我们坚信我们必须消除部署服务器端补丁的所有摩擦。Pivotal 是一家全栈公司。我们提供操作系统、中间件和应用层，因此我们对它有一个整体的了解。我们知道软件需要频繁更新，因为我们引入了如此多的开源依赖项。所以我们很快就发布了补丁，”他说。

有了 Concourse，组织只需将它指向更新管道，就可以无缝地(据说不需要点击)将其部署到 Pivotal 平台。他将其比作 Chrome 浏览器中的自动更新功能，但用于服务器端平台。

[https://www.youtube.com/embed/7AIpTodHXSo?feature=oembed](https://www.youtube.com/embed/7AIpTodHXSo?feature=oembed)

视频

该公司正在将其整合到平台中，作为一个可以自我更新的[瓦片](https://docs.pivotal.io/tiledev/index.html)——史密斯称之为“一个循环的、令人费解的想法”这是一个将与平台一起运行的服务，它将使平台保持最新。

开发人员还可以使用 Concourse 不断部署他们自己的应用程序。

“价值是你如何在你的组织中以一种同质的方式推广它，”Smith 说。

他解释说，如果你有 100 个或更多的团队，他们都会有自己的基础设施来完成 CI/CD 任务。这些 CI/CD 系统的设置和配置完全是这些团队的职责。有了 Concourse，用户可以获得开箱即用的配置，因此团队不再需要考虑这种设置，而且它是标准化的。

使用 Concourse，用户可以基于[的三个核心概念](https://concourse.ci/concepts.html)创建管道:任务、资源和组成它们的作业。定时触发和外部环境的同步使用等功能是使用这些概念建模的，而不是作为顶层。

[https://www.youtube.com/embed/hBNcLQxIXNU?feature=oembed](https://www.youtube.com/embed/hBNcLQxIXNU?feature=oembed)

视频

Pivotal 在内部使用 Concourse 来维护其在 Google 云平台和 Amazon Web Services 上托管的 Cloud Foundry 环境。它还运行在 VMware 的 vSphere 和 OpenStack 云上。

该公司概述了其使用其他 CI/CD 工具的经验，即 Jenkins、 [Travis CI](https://travis-ci.org/) 和 [GoCD](https://www.gocd.org/) over [here](https://concourse.ci/concourse-vs.html) 。Smith 说，当然，Pivotal Cloud Foundry 用户可以选择使用另一个 CI/CD 工具。

Smith 说，让 Concourse 为客户提供开箱即用的状态，“坦率地说，我们花了几年时间。"要使它在操作上不受干扰，需要大量的工程设计。"

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>