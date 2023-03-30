# HPE 承诺在每一个新的服务器上安装 Docker 引擎

> 原文：<https://thenewstack.io/hpe-promises-docker-engine-every-new-server/>

周二下午，HPE 首席执行官[梅格·惠特曼](https://www.linkedin.com/in/megwhitman)在[HPE 2016 年美国探索展](https://www.hpe.com/events/discover/)上告诉与会者，迄今为止最明确的信号是，Docker 容器化的基础设施正在向 Windows 丰富的数据中心转移，在这些数据中心，应用程序通常在部署在亚马逊风格云平台上的经典 VMware 虚拟机中运行。

“所有惠普服务器都将与 Docker 引擎捆绑在一起，”惠特曼说，“使客户能够创建可跨任何基础设施移植的分布式应用程序。”

## 顾客在哪里

Docker 的跨平台可移植性主导了周二会议上对该技术的讨论。HPE 小心翼翼地将 Docker 与将旧堆栈引入云的能力联系起来，而不是求助于 Docker 作为实验性技术的典型企业级特征。

“HPE 致力于满足顾客的需求，”HPE 产品营销副总裁杰伊·贾米森在周二的新闻发布会上说。“随着客户将 Mesosphere 和 Docker 视为对他们非常重要的基础设施，HPE 致力于成为这些技术的强大合作伙伴和支持者，无论是在我们的软件方面，还是在我们的硬件基础设施能力方面。(我们的)战略非常广泛，我们认为这使客户能够拥有一个强大的合作伙伴，专注于满足他们的需求，并为他们提供最常见问题的解决方案。”

HPE 负责产品管理的副总裁 Omri Gazitt 向我们透露，Kubernetes 将成为 [Helion Cloud Suite](http://community.hpe.com/t5/Grounded-in-the-Cloud/Find-our-more-about-the-new-HPE-Helion-Cloud-Suite-at-HPE/ba-p/6867017#.V1gsFpErLIU) 中一些服务的编排平台，并扩展到与制造商 Helion CloudSystem 10 系列硬件捆绑的服务。Gazitt 说，这些服务将在 Cloud Suite 如何为 HPE 客户提供 Cloud Foundry 的过程中表现出来，尽管他说，它的主要兴趣是向迄今为止可能拒绝容器化的客户隐藏工作负载编排的复杂性。

## 虚拟化是针对服务器的

![161607 04 HPE Discover (Meg Whitman + Ben Golub)](img/373a9e558e66bbf5147b0ed69afd1585.png)在周二的第一轮主题演讲中，HPE 首席执行官 Whitman 和 Docker Inc .[一起站在台上。CEO ](https://www.mirantis.com/software/docker/kubernetes/)[Ben Golub](https://twitter.com/golubbe) ，受到在场 IT 专业人士的热烈欢迎，他们对 Docker 的名声非常熟悉。尽管如此，Golub 发现自己向许多可能仍不熟悉 Docker 平台的与会者介绍了 Docker。

有一次，Whitman 问 Golub，Docker 作为 HPE 服务器的标准组件，从长远来看对虚拟化意味着什么。

“虚拟化是一项神奇的技术，”Golub 回应道，“但它实际上是为构建、修改和移动服务器而设计的。如果人们想要构建、修改和组装应用程序，Docker 是一个更好的解决方案。”

在回应惠特曼对安全性的担忧时，Golub 回应说，越来越多的组织采用 Docker 是为了应对他们的安全担忧，而不是无视他们。他向她保证，部署在 Docker 环境中的工作负载是经过数字签名的，“因此，您部署到环境中的东西出现问题的可能性非常低。如果有不好的事情发生——当然，不好的事情总是会发生——把它换出来是小事一桩。您可以换出一个容器，而不会影响其余的应用程序，也不必关闭机器。”
HPE 的首席执行官似乎对 Golub 的说法感到高兴，他认为 Docker 的实施可以将企业的利用率提高多达 20 倍——这个数字我们以前就听说过，至少在新的堆栈中是这样，但直到现在才传播到许多企业。

## Windows 的现实

Helion 已经成为 HPE 云平台的伞式品牌，OpenStack 已经是那里的主要组件。然而，在周二发布其 Helion 云产品组合的新组件和修订组件时，HPE 高管将 Docker 与系统的更深入集成描述为支持工作负载部署和编排的选择，确保在公平的竞争环境中包括 OpenStack 和面向 Windows 服务器的系统。

后一类明确包括 [Nano Server](https://blogs.technet.microsoft.com/windowsserver/2016/02/10/exploring-nano-server-for-windows-server-2016/) ，微软的 Windows Server 的精简实现，设计用于远程部署和管理，包括在容器内。这个等式中也提到了 Azure Stack。

正在出现的是 Docker 成为事实上的基础设施提供商的愿景，不是因为它有能力取代现有的工作负载，而是维护它们。docker Inc .[与微软的现有合作关系](https://azure.microsoft.com/en-us/blog/docker-and-microsoft-announce-more-innovation-to-cross-platforms-and-win-hearts/)在不久的将来可能会在这些方面结出更多的果实。

## 反思的证据

去年 12 月，HPE 在伦敦宣布了与 Docker 合作的第一阶段。在宣布这一消息的同时，当时有消息称，HPE 将建立自己的面向容器的操作系统 ContainerOS，以努力赋予容器安全工具和其他资源，这些工具和资源将被 HPE 的 Synergy 系列硬件开发，也是在去年 12 月宣布的。尽管 Synergy 仍然是 6 月拉斯维加斯展会上的一个主要产品点，但到目前为止我们还没有看到任何关于 ContainerOS 的内容。它可能仍然是目前提供的 HPE 产品，但它不再被称为达尔文进化链的下一阶段。

![161607 06 HPE Discover (Omri Gazitt)](img/d7f992e0d0530fee0d3f367ceba552b0.png)

相反，我们听到了关于生产技术的讨论，这些技术可以将 HPE 平台的范围扩展到云中，而不是将其限制在几个产品线中。Gazitt 告诉 New Stack，HPE 一直在与 [Mesosphere](https://d2iq.com/) 合作，为 OpenStack 和 Cloud Foundry 生产容器化的基础设施，运行在[DC/操作系统](https://thenewstack.io/inevitable-mesosphere-open-sources-mesos-based-data-center-operating-system/)之上，在 HPE——可能还有其他——平台上。

> HPE 希望生产具有全包式云供应的服务器，并提供 OpenStack 和面向 Windows 的系统选项。

这是 HPE 向集装箱化传递信息的明显演变，也是一种新颖的呈现方式:不是新方法对传统工作负载的侵蚀，而是一种新的方式来转移这些工作负载，以延长其有效寿命并提高其效率。

![161607 01 HPE Discover (opening floor show)](img/4208a902fc788857d9a1449ab65648ec.png)

[Cloud Foundry](https://www.cloudfoundry.org/) 、 [Docker](https://www.mirantis.com/software/docker/kubernetes/) 、 [HPE](https://www8.hp.com/us/en/solutions/business-solutions.html) 和 [Mesosphere](https://d2iq.com/) 是新栈的赞助商。

图片:斯科特·富尔顿。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>