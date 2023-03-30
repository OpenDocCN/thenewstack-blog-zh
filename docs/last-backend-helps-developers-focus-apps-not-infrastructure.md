# 最后。后端帮助开发者专注于应用，而不是基础设施

> 原文：<https://thenewstack.io/last-backend-helps-developers-focus-apps-not-infrastructure/>

最后一名的队伍。后端正在为一个游戏开发项目研究虚拟化技术，这时他们发现了 containers 和 Docker。

相信容器将“占领世界”，他们欣然接受新技术，开始为开发人员构建自动化容器管理系统。他们的目标是让开发人员专注于编写基于云的应用程序，而不必担心管理底层基础设施。

“第一个也是最基本的想法是用基础设施自动化工作，”Last 说。后端首席执行官亚历山大·卡洛辛。“对我们来说，主要活动是设计和开发，我们直接知道它是什么:测试和部署软件的过程。对于我们以前的项目，我们已经不止一次地编写了我们自己的自动化系统。当容器化技术出现时，我们可以为整个开发者社区提供一个相当通用的解决方案。”

他说，截至 2015 年他的公司成立时，只有去年。后端和 [Tutum](https://thenewstack.io/tutum-offers-docker-container-management/) 都专注于这个目标。当然，Tutum 已经被 Docker 收购，Docker 利用这项技术推出了自己的云托管服务。

去年 12 月。Backend 开发了基于 Kubernetes 的平台即服务，[开源](https://github.com/lastbackend/lastbackend)。

## **混合技术**

该产品混合了多种技术，包括容器编排、应用容器化、来自容器的度量和分析、容器的虚拟覆盖网络以及日志存储。

该团队开发了一个系统，用于在有大量机器的集群上部署和扩展 Docker 容器，以及一个钩子系统和一个命令行界面，目的是使管理变得容易。系统从诸如 GitHub 或 BitBucket 等存储库中的源代码构建容器映像，然后使用这些映像进行编排。它部署在三台服务器上:一台用于 REST API，另一台用于代理服务器和 DNS 服务器，还有一台用于三个组件:构建管理器、编排器和调度器。

Kaloshin 这样解释他的团队的任务:

配置管理器跟踪所连接机器的配置，如果配置不匹配，就将作业发送给调度器进行更新。

调度程序为主系统生成机器规范和各种任务，比如构建源代码任务、钩子管理和节点管理。它接收来自控制器的信号，并生成特定机器的规格。代理接受这些规范，并将受管节点的状态引导到正确的状态。这种方法在大型集群中提供了更简单的系统扩展，并提供了可靠性。

构建管理器——最简单的组件之一——启动构建映像的过程，然后监控它们的执行。托管 Docker 的独立机器集群可以作为构建映像的服务器池来调用。该公司计划将其建成一个完整的持续集成系统。

Kaloshin 说，任何人都可以开始使用该系统，即使只有一台服务器，你也可以轻松地从一个集群和数千台服务器开始。

原始架构中的所有组件都应该能够独立运行，以实现高容错性。对于本地测试，您还可以在一个包中运行除代理之外的所有内容。

“我们还有很多工作要做。我们需要加强我们的网络交互模型，我们在持久性卷设计上花费了大量时间。我们期待从开源社区获得一些帮助。在很多任务中，更有经验的专家的能力对我们所有人都是有用的，”他说。

“我不能直截了当地说我们在发明新的东西，因为所有这些都在许多第三方服务中得到了部分实现，但我们还没有见过一个带有 CI /CD、web-UI 的单一开源系统，您可以轻松地将它放在一台服务器或一组服务器上。”

## 只需点击几下

总部设在俄罗斯圣彼得堡，去年。后端已经获得了俄罗斯政府支持的加速器[互联网倡议发展基金](https://www.bloomberg.com/research/stocks/private/snapshot.asp?privcapId=247776879) (IIDF)的资助。它于去年进入中国市场，至于美国市场，Kaloshin 表示，只要他们继续专注于创造一种优秀的产品，政治就不会成为障碍。

最后。Backend 也得到了来自[微软](https://channel9.msdn.com/Blogs/PartnerApps/LastBackend-Picks-Azure-to-Help-Deliver-Geo-Distributed-Apps)的支持，成为其 Azure 合作伙伴计划的一员。它的视觉也可以与 AWS 和 DigitalOcean 一起工作，并与聊天室 Slack 和 HipChat 集成在一起。

“我们希望节省 IT 专业人员的时间，避免与基础设施打交道，”Kaloshin 说。“让他们专注于开发优秀的应用。如果他们需要一个数据库，只需点击几下就能得到。是的，你可以在 DigitalOcean 上打开一些指南，自己做所有的事情，但为什么要浪费时间呢？你的代码更新了？—让 Last.backend 构建、测试并在服务器上运行它。”

他说，虽然 Docker 和 Kubernetes 的生态系统更侧重于企业，但他希望他的公司也能帮助较小的团队和独立开发者。他补充说，虽然 Kubernetes 很棒，但不是每个初创公司都可以在生产状态下部署它——这就是为什么 orchestrator 更经常用于测试。他的公司也专注于为舞台和制作提供解决方案。

最后。这位首席执行官说，后端与 Heroku、Deis 和 OpenShift 等 PaaS 平台竞争，在某种程度上，也与 Docker 和 Kubernetes 等容器化组件竞争。Kaloshin 告诉我们，与竞争对手相比，该平台对正在使用的物理资源提供了更高层次的控制——在操作系统层面、在流程层面的控制。

他说，像 Heroku 这样的服务对于小型项目来说是理想的，但对于拥有大型基础设施的公司来说，以及在微服务架构上使用十几个存储库的应用程序来说，就变得更加困难了。

作为对开发者的激励，该公司制定了一个奖励计划:免费提供有限的资源，以换取对开源项目的贡献。所有奖励将单独确定。

DigitalOcean 是新堆栈的赞助商。

专题图片:[蓝色机器人](https://www.flickr.com/photos/peyri/48825808/in/photolist-5jfdh-81MXJq-fykiqY-6wLw3u-7D1RPo-e47Jj-EHyap-rG9Fqw-dxckg-dxckp-66EEpg-p9uUnM-kf1MYx-kf1NYZ-4gwdZx-5jfek-56zNeu-8q6foW-bxrnpQ-aztFKe-Zj2Yr-4C7jkH-s9Wi-8he8WU-6X9XsW-EHvxr-4Vf4td-d2EUi-7kTnAQ-B1Vr2-6MTRz-dBZ9VH-aeJXd-bWFd4x-iBoPYa-ncZxNm-7t5BDs-eNaHc-c2mmos-78XPTL-5VpEr-bbwkYD-5EBSLh-3VGGk-6qeq8D-7dAZE8-eeDhBC-7B1Kkj-6hHzvc-oMHnd)，作者[佩里·埃雷拉](https://www.flickr.com/photos/peyri/)，获得 CC BY-SA 2.0 许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>