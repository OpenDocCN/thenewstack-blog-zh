# Red Hat OpenShift Online 现在支持 Docker、Kubernetes

> 原文：<https://thenewstack.io/red-hats-openshift-online-3-supports-docker-kubernetes/>

自从几年前 Red Hat 确定了其应用程序的“gears”编排模型以来，该企业在某种程度上已经被 Google 倡导并由 Docker 推动的 Kubernetes 模型所吸引，

去年发布的 Red Hat 的平台即服务软件 OpenShift 3 解决了这些偏好，增加了对 Docker 的支持。从那时起，红帽又向前迈进了重要的一步，与[进行了整合。NET Core 和 JBoss 融合企业服务总线](https://thenewstack.io/openshift-3-1-opens-door-net-jboss-middleware/)，进入公司的 OpenShift Enterprise 3.1 和 OpenShift 专用 3.1 平台。

因此[open shift Online](https://www.openshift.com/)——与 Heroku 和 Salesforce 等竞争的全公共选项——需要做相当多的追赶工作。

周四，Red Hat 在这个方向上迈出了重要且必要的一步，推出了 OpenShift Online 3 的开发者预览版，使公共 PaaS 与 open shift 3.0 版本更加一致，适用于托管数据中心和私有部署。

“我们在这里所做的是，你有能力在一个虚拟机内让多个客户孤立地运行他们的容器，”Sathish Balakrishnan 说，他是 Red Hat 的 OpenShift Online 的负责人，在接受新堆栈的采访时说。他告诉我们，这种隔离是基于每个项目进行的，也就是说，每个客户项目都在 Kubernetes pod 中进行，使用独特的网络覆盖，与多租户 SDN 上的其他项目相隔离。

这样，客户可以同时运行多个项目，尽管 Red Hat 将保持它们之间的区别，就好像它们在独立的数据中心运行一样。

## 现在你看见了，现在你看不见了

虽然版本 3 将在后端采用 Docker 容器化，但事实是，Red Hat 的客户不会直接与 Docker 引擎打交道，或者在大多数情况下，不会与 Kubernetes orchestrator 打交道。这是因为该平台将在后台处理 docker 文件的源到映像(S2I)创建，以及使用 docker 文件构建的容器。与客户现有 IDE(大概是 Eclipse)的集成将使 OpenShift Online 看起来是一个无缝连接的组件。

Balakrishnan 说，这使得 OpenShift Online 3 与使用谷歌容器引擎有些不同，他认为，谷歌容器引擎在 PaaS 中为客户提供了完整的 Docker 和 Kubernetes 体验。他认为，相比之下，OpenShift 可以通过声明式部署模型等功能，对能够从完整的公共 PaaS 中受益的特定客户类别隐藏 Docker 的实现细节。

这就是说，在部署到生产之前，开发阶段的每个应用程序都在一个具有 2 GB 内存的隔离环境中运行，产品总监告诉我们。他承认，在有限的空间内，客户将无法——或者不需要能够——运行集群或将项目分配给托管 OpenShift 的特定虚拟机。(OpenShift Online 的每个实例都是一个虚拟机。)但是客户可以指定同时运行的容器实例的数量。

## 当然，除非你现在还这么想

由于 OpenShift 的实现现在作为开发人员预览版提供，但该实现的细节——如管理 Docker——在设计上对开发人员是隐藏的，我们问 Balakrishnan，Red Hat 希望开发人员客户向公司提供什么，以便公司可以使用该平台的最终版本进行全面发布？

“我们希望看到开发人员将要抛出的用例，”他回应道。“我们把它作为 GA 发布出来是否足够安全？对于 Docker 和 Kubernetes 来说，人们已经将许多东西带入安全领域，所以我们想看看它们是如何工作的。另一件事是，[OpenShift]如何在负载下工作？当我们有 50 名开发人员在同一个虚拟机中敲打容器时，这是如何工作的？”

事实上，由于一些实现细节应该在开发者的视线之外，Red Hat 想知道在平台的当前状态下，开发者是否会被这些细节困扰。“这不仅对 OpenShift Online GA 有用，”他补充道，“还因为我们正在尝试引入一种新的模式，我们将有安全知识可以应用到 OpenShift Enterprise 和 OpenShift Dedicated。这就是我们的价值主张:这是一种多云、多消费模式。”

## 趋同是刚刚发生的吗？

自从 Red Hat 的 Gordon Haff 对 IaaS 和 PaaS 服务类有效合并的可能性进行了著名的推测以来，已经过去了将近两年半的时间——例如，关于 OpenShift 和 OpenStack 之间的界限变得模糊甚至完全消失。Red Hat 将 Kubernetes 实现为 OpenShift 的指挥者，这是否让我们更接近 Haff 没有准确预测但在合理范围内估计的收敛点？

“我认为进化总是在发生，”Balakrishnan 说。“PaaS 现在正在转变为容器即服务。这可能是基础设施行业的最佳时期，因为事情是如此的动态，过去四年比过去四十年发生了更多的变化。

Balakrishnan 继续说道:“OpenStack 仍然在一些方面提供了价值，例如，如果有人希望拥有他们无法容器化的巨大虚拟机工作负载，或者他们正在运行 Siebel 等打包软件，并且他们希望使用云来管理它，或者他们只是希望向人们提供虚拟机。“如果他们想要一个数据块存储解决方案，该怎么办？或者，如果他们希望在其场所内运行 it，并且希望管理容器工作负载和非容器工作负载，该怎么办？不同的事情解决不同的问题；我们试图做的是让 OpenShift Online 让开发人员的生活更轻松，并消除他们在使用和部署基于 Docker 的容器平台时可能遇到的任何障碍。"

码头工人和[红帽](https://www.openshift.com/)是新堆栈的赞助商。

专题图片:斯科特·富尔顿在[加尔维斯顿铁路博物馆](http://www.galvestonrrmuseum.com/)修复的圣达菲“沃博尼”客运列车引擎。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>