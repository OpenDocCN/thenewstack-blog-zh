# Linux 发行版:Red Hat 与 Docker 的新的紧密联系，SUSE 也是如此

> 原文：<https://thenewstack.io/linux-distros-red-hats-new-deep-ties-to-docker-suse-similarily-so/>

Docker 容器化、分发和编排正在成为世界主要企业 Linux 发行版的两个版本中的标准设备:Red Hat Atomic Enterprise Platform 和 SUSE Enterprise Linux 12。但这是否意味着企业将很快进入一个 Docker 生态系统？或许这些主要厂商都有自己的打算。

当 OpenStack 首次在企业中占据一席之地时，从 Linux 提供商的角度来看，存在(现在仍然存在)一种危险，即从静态部署到私有和混合云平台的过渡可能会扰乱现有的 Linux 部署，迫使企业更换供应商。本周，操作系统供应商 SUSE 和 Red Hat 宣布了将 Docker 容器化作为一个组件的捆绑包，这显然是为了阻止 Docker 运动再次出现这种混乱的可能性。

## 私有注册表

在 Red Hat 和 SUSE 的案例中，关键的区别在于它们的注册中心，它们都被描述为 Docker 的“附加值”。标准的 Docker 生态系统基于一个名为 Docker Hub 的集中式容器存储库。SUSE 和 Red Hat 现在都在捆绑 Linux 发行版，让客户建立“私人注册处” *s* ,“在自己的平台上部署自己的容器……使用带有供应商品牌的存储库”。

周三，红帽公司在波士顿举行的[红帽峰会上宣布了捆绑销售的消息。在那里，红帽透露其原子企业平台将捆绑 RHEL 7 与 Docker 容器运行时和 Kubernetes 编排。Docker 和 Kubernetes 现在也是 OpenShift Enterprise PaaS 平台的一部分。每个还将有一个红帽私人集装箱登记服务，利用红帽集装箱认证，在 3 月首次推出。](http://www.redhat.com/summit/)

SUSE 的声明是在周一发布的，称其 Linux Enterprise Server 12 发行版将包括 Portus，这是一个私人注册表，其中包括一个开源前端，SUSE 将其描述为增强企业私人容器的安全性。

本周在旧金山的 DockerCon，Docker Inc .并没有忽视突然出现的对私人注册的需求。作为 Docker 1.7 的一轮实验性开发的一部分，它推出的创新之一是[公证，这是一种认证服务](http://www.cmswire.com/information-management/docker-engineer-our-containers-are-secure/)，它使用户能够在容器被注册到任何地方的任何存储库之前，对容器(或任何内容)进行签名和认证。

公证的不太明显的目的是给容器化模型的新订户一种安全毯，这样他们可以放心，他们发布到公共注册中心的容器通过基于角色的访问控制(RBAC)受到保护，不会被任何人使用。这有助于将 Docker 作为容器生态系统的中心。

与此同时，试图通过客户服务来区分其产品的 Linux 发行商需要一种利用 Docker 的方式。正如 SUSE 和 Red Hat 所证明的，私有注册是他们的增值。他们的信息是:公共存储库可能天生就不安全。即使它们相对来说比将容器的二进制文件发布到 GitHub 或 Dropbox 更安全，也没有什么比自己托管存储库更安全的了。

“Portus 是一个简单易用的与注册表交互的前端，”SUSE 全球联盟副总裁迈克尔·米勒在接受 DockerCon 新堆栈的采访时解释道。“现在，很难搜索注册表。一旦你建立了一个注册表，你如何搜索它？

“我们正在将管理您的注册表的能力集成到 Portus 中，”他继续说道，“不仅仅是建立一个注册表并在它前面放置一个 API，而是实际上在一个真实的企业环境中放置一个可供真实的人使用的企业、DevOps、SecOps 管理前端。”

## 堆栈与平台

SUSE 的 Linux 管理环境叫做 YaST。Miller 说，在第 12 版中，它将开始包括 Docker 和使用 Docker 构建的私有容器注册的管理功能，但打算使用 Portus 作为它们的前端。

“随着我们的发展，我们将把它扩展到我们的 SUSE Manager 管理基础设施中，”他继续说道，“也扩展到我们的 OpenStack 发行版和工具集中。从我们的角度来看，只是把 Docker 位扔进发行版，并说，'嘿，我们做 Docker！'不是我们想要的。我们的最终愿景是一套集成的工具和技术，真正解决现实世界中管理员在操作系统工具、注册表工具、安全工具、管理基础架构、作为私有云的 OpenStack 等方面面临的挑战，以统一的方式将所有这些整合在一起，真正在现实环境中发挥作用。然后，像 SUSE 这样的企业公司可以提供培训、服务和支持。"

软件开发人员从提供与他们交互的功能的服务的角度来考虑堆栈。为企业采购平台的人认为“平台”是工具和服务的集合，作为他们应用程序的基础设施。SUSE 和 Red Hat 在这里的举动迎合了负责项目预算和资金支出的人的需求，这些人认为“一体化”意味着由同一品牌提供的能力。

但是这种品牌选择可能会影响容器化应用程序的架构，因为开发人员可能很快就会发现他们对存储库的选择是为他们量身定制的。

SUSE 的迈克尔·米勒对 Docker 生态系统有更多的话要说，我们将在稍后的新堆栈中呈现我们对米勒的采访的更多摘录。

Docker 和 Red Hat 是新堆栈的赞助商。

专题图片: [Emmanuel Huybrechts](https://www.flickr.com/photos/ensh/) 的《[波士顿港之夜](https://www.flickr.com/photos/ensh/4743036023/in/photolist-8e8ina-dDAEd2-8UfEJK-8FgGBi-71UfUa-bPkHhK-7bgh9Q-d9pJn-8EaTgZ-HtqpE-ae6Ri-ej5AAZ-53LCUv-8cnXV7-3JASqq-87P2XP-72aVHZ-833fRo-crbd7S-dvdbPz-cQnyUm-9BpVRh-aLFTSB-bUzgce-4kLCiT-fYUrx-cw22P5-dfS77e-6dy1Kt-4Zu4fA-hbL42k-4Jf9R6-cQnMCq-8Db8nN-cfMWpA-bKZjC2-buP27v-escoF1-8hB67r-bUzgYB-dVUyXF-bBva2h-jsLMdx-6ZsFyS-bBva2m-c4qvej-51yysp-ad4Vee-Aj2Xo-suRY27)》由[CC 2.0](https://creativecommons.org/licenses/by/2.0/)授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>