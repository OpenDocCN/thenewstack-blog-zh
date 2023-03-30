# 红帽 OpenShift 第 2 部分:从墨盒到 Kubernetes

> 原文：<https://thenewstack.io/shift-red-hat-openshift-part-2-cartridges-kubernetes/>

在…里

[part one](https://thenewstack.io/red-hat-openshift-part-1-from-gears-to-docker/)

在我们关于 OpenShift 的简介中，我们看到了该平台是如何采用 Docker 的。在第二部分中，我们将探讨 Kubernetes 扮演的角色以及这对 OpenShift 平台意味着什么。

OpenShift 的新版本 3 是红帽对 Docker 的实现。它不是码头工人的替代品，也不是码头工人的“风味”是码头工人。无论新的 OpenShift 对系统的贡献是什么——即使是在 Red Hat 对开发者的解释和演示中——都是最重要的。

正如我们在这个故事的第一部分中看到的，在 OpenShift 的新系统下，Docker 图像(后来可能是 OCI 图像，因为 Red Hat 是创始成员)取代了墨盒作为 OpenShift 的集群机制。Kubernetes master 取代了 OpenShift broker，Docker 容器取代了 OpenShift gears。需要共享同一个文件系统的容器被分组在一起，就像 Kubernetes 所说的那样，在 pods 中。

CoreOS 的 etcd 取代了 MongoDB，成为服务发现的键/值存储的提供者。红帽企业版 Linux 6 被 RHEL 7 取代，伴随而来的是[原子，红帽的最小化版 RHEL](https://thenewstack.io/red-hat-releases-container-focused-operating-system-rhel-7-atomic-host-competition-matures/) 在容器内运行。

当然，所有这些意味着 Docker 的容器网络概念完全取代了 OpenShift 为路由节点开发的系统。

## 更换变速器

正如红帽中间件专家 Veer Muchandi 在去年四月制作的[视频中解释的那样，你过去在 OpenShift 插件中发现的一些功能现在将作为“容器化服务”发布——例如，](https://www.youtube.com/watch?v=b5THfQzVUqk) [JBoss xPaaS](https://www.openshift.com/xpaas) ，代表红帽的品牌中间件。

“你还会有一个 Docker 中心，你的 Docker 图片会在这里存放并注册，”Muchandi 说，“还有一个市场，其他供应商可以通过它向你提供 Docker 图片供你使用。墨盒将被那些 Docker 图像所取代。”

他继续说，在新堆栈的顶部(套用一句话)，“用户体验层”将通过一个反应灵敏的命令行界面和替代的网络控制台向开发者展示 OpenShift 的健壮性。这些工具将通过 RESTful API 与 Kubernetes master 连接。OpenShift v3 应该提供 Muchandi 所说的“更好的服务和更好的开发者体验”

Red Hat 的产品管理总监 Joe Fernandes 强调，OpenShift v3 将运行与 v2 相同的代码。虽然部署和分发机制已经被取代，但真正改变的只是开发人员和管理员部署代码的步骤。甚至这些步骤也是彼此相似的。

版本 3 包括一个叫做“源到图像”的功能，Fernandes 说这个功能和 v2 中的墨盒或者 Heroku 中的[build pack 具有相同的基本功能。“开发人员只是通过 Git 推送代码，然后平台获取这些代码，并确定运行这些代码需要什么——如果是 Java 代码，可能需要 JBoss 或 Tomcat。然后它把那些东西结合起来，建立一个新的镜像，然后在平台上运行。OpenShift 的上一个版本是通过我们的开放容器模型实现的，Heroku 是通过他们的‘Droplets’和‘Dynos’等产品实现的，而我们现在有了 Docker 的这个模型。”](https://devcenter.heroku.com/articles/buildpacks)

在某种程度上，这种模型取代了 Docker 为其自己的容器内置的部署模型，使其实际上更像 open shift v2——但前提是开发人员选择以这种方式使用它。“我们的想法是让开发者做他们想做的事情，”费尔南德斯说。

> “如果他们推出源代码库，然后进行构建，我们只需观察该库，当我们看到代码时，我们将获取它，构建它，然后部署一些东西。”

“我认为这对开发者来说是一件大事，因为它让他们从我认为的玩具，也就是在笔记本电脑上玩 Docker，转变为你可以大规模运行的东西。”

## 放大比例

旧的 OpenShift 与 Cloud Foundry 的区别在于其独特的、简单定义的机械方法来表示分布式应用程序的组件。根据 Red Hat 的说法，OpenShift 版本 3 与其类似更新的竞争对手的区别在于它区分标准化的、不那么独特的、当然不那么简单的分布式功能的方法。

在向 OpenShift 转变的整个过程中，有一个信息是 Red Hat 需要传达的，但可能不希望传达得如此清楚:在新的 PaaS 上分发的程序可能需要设计得与旧的 PaaS 不同。Red Hat 不愿意直接声明 OpenShift 的应用程序应该改变，可能是担心放弃向下兼容性。兼容性不是这里的争论点，但方法论肯定是。

“我们发现，通过将应用程序分解成更多的组件(例如容器、服务、路由、构建、秘密、存储等)。)我们能够为用户提供更多的灵活性和创建更好应用的能力，”[Red Hat 产品经理 Mike Barrett](https://blog.openshift.com/openshift-enterprise-3-evolving-paas-future/) 去年 6 月在 OpenShift 博客的一篇文章中写道。

你可以从中读出什么:为 OpenShift v3 设计的应用程序将遵循与为 v2 设计的不同的架构隐喻。一种完全不同的机制现在负责管理容器映像、这些容器在系统中的复制、单个容器的部署以及容器启动后的生命周期管理。

你看，Kubernetes 是一个网络管理员，特别是关于容器如何相互联网。如果存储在 gears 或 containers 中的应用程序从不相互通信，它们就永远不会改变。但是首先利用 Kubernetes 的全部目的是实现一个完全分布式的架构，这在旧系统中是不可能的。有一个新的完全透明的工作流，Kubernetes 通过环境变量将它提供给应用程序。OpenShift v3 应用可以看到幕后发生的事情，并在必要时进行调整和适应——这些适应在 v2 中可能不可行。

正如我在关于 OpenShift 的简介的第一部分中所写的:

> 用一种更隐喻的方式来说，乘坐福特雷鸟的整个想法从 57 年的车型到 61 年的车型发生了根本性的变化，增加了一个后座。把你的双座汽车换成四座不用再回驾校，从 OpenShift v2 转到 v3 也不用重新学习怎么开发。但是一旦你搭载了额外的乘客，你可能会发现你正在开车去一些你以前不会去的地方，并且会停下来。

但是 Red Hat 大胆转向 PaaS 架构的风险在于:旧平台永远不会消亡。(只要看看有多少主要零售商还在使用 Windows 2000 就知道了。)OpenShift 的 v2 和 v3 之间的架构思维转变如此之大，以至于不太可能每个人都能做到。根据一些分析师的估计，OpenShift 的市场份额略微领先于 Cloud Foundry(Cloud Foundry 已经[向 Docker 和 Kubernetes](https://thenewstack.io/docker-on-diego-cloud-foundrys-new-elastic-runtime/) 做出了类似的转变)。如果真的是这样的话，Red Hat 正在偏离一个已经获得巨大动力的架构方向。

当供应商告诉他们“左转”时，组织不会只是左转我们可以预期一些现有的 OpenShift 客户群会坚持使用版本 2。这种分布式计算的新隐喻到底有多聪明，也许要在两年后才能衡量出来，那时我们已经衡量出有多少开发人员还在忙着将他们的设备包装在盒子里，并把它们推销给经纪人。

CoreOS、Docker 和 Red Hat 是新堆栈的赞助商。

专题图片:[朱塞佩·米洛](https://www.flickr.com/photos/giuseppemilo/)的[英国苏格兰福尔柯克](https://www.flickr.com/photos/giuseppemilo/16840211908/in/photolist-bg7Dzr-hoDTnj-hoDSAu-hoDMDs-hoEWZr-rE7uib-cvGDy5-dRKPKr-ouFvAw-f85pkz-ekif1u-dvU7gA-cvGCdY-oLUi5t-f85tak-58i2WA-4BWM6W-dq69ev-4E1Hby-4E1P2C-f85yaK-4DWo1g-4DWo14-4E1Hbu-f8jGmj-4rMvha-4E1P2s-4E1MAy-4E1MAC-4E1P2Q-4E1P2N-4DWo1e-4DWqEa-4E1MAq-4DWqDR-4E1Hbs-4DWo1v-4E1MAJ-4DWqDV-f8jN99-f8jFgU-4TR2J3-idJiKn-idJPvT-mdULeQ-mdUKp3-rGBCua-mdT4DK-8qiW5e-avVuHc)福尔柯克轮【2.0 在 [CC 下授权。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>