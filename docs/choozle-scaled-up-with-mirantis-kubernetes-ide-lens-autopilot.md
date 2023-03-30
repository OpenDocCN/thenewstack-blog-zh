# 米兰蒂斯的镜头自动驾驶仪如何帮助选择缩放 Kubernetes

> 原文：<https://thenewstack.io/choozle-scaled-up-with-mirantis-kubernetes-ide-lens-autopilot/>

***编者按:这篇帖子的主体 Mirantis 是一家由 [Insight Partners](https://www.insightpartners.com/) 控股的公司。Insight 也拥有新的堆栈。帖子中还提到亚马逊网络服务是新堆栈的赞助商。***

“让数字广告变得简单”是 Choozle 公司的座右铭，该公司是一家软件平台提供商，为中小型广告公司和营销部门提供服务。该平台为广告公司提供了一个单一的用户界面，使用消费者数据在多个渠道(包括展示、视频和移动)开展广告活动。

“Choozle 平台连接了广告技术领域的各种技术，如数据提供商、需求方平台和广告服务器，”该公司的产品和工程运营总监 Michael Baldassare[说。“因此，我们需要一些现成的东西，能够处理将所有这些技术结合在一起的负载](https://www.linkedin.com/in/gmbaldassare/)

为了处理所有这些，Choozle 决定从一开始就部署 Kubernetes。该公司的软件工程师负责手动维护基础设施和他们的定制 Kubernetes 平台，以及创建应用程序功能。

Baldassare 说，除了保持所有的连接性，Kubernetes 还使应用程序高度可用，以满足产品上市的需求，并根据当前用户的需求大幅扩展应用程序。2022 年早些时候，该公司决定是时候升级和维护应用程序了，但团队中没有一个经验丰富的 DevOps 工程师。

## Kubernetes:我们应该留下还是应该离开？

唯一真正的选择是完全脱离 Kubernetes，可能使用[谷歌应用引擎](https://cloud.google.com/appengine)或者转换成其他东西。“我们做的事情有很大的风险，但如果离开库伯内特斯，风险会大得多，”Baldassare 说。

Choozle 已经在订阅的基础上使用了 [Mirantis](https://www.mirantis.com/) 的开源版本 [Lens](https://k8slens.dev/) 好几年了。米兰蒂斯将其描述为“世界上最受欢迎的 Kubernetes IDE。”当时，Choozle 的遗留基础设施是在亚马逊网络服务(T21)的一个完全管理的手动实例上。

Baldassare 收到了 Mirantis 为其 DevOpsCare 服务提供的应用程序内广告，这是一个允许您查看 Kubernetes 基础架构和编排的 UI。“这个广告告诉我们，我们目前的设置与该产品不兼容，所以我们无法从它那里获得最大价值，”他说。

因此，Mirantis 帮助 Choozle 团队制定了一个升级和迁移到更现代的 Kubernetes 产品的计划，包括数据库迁移。

在这一点上，Baldassare 说，“我们决定，如果我们要做所有这些，我们还不如转向云产品。”所以首先，米兰蒂斯帮助 Choozle 迁移到[谷歌云平台(GCP)](https://cloud.google.com/) ，其中包括其自动化的 Kubernetes 产品、[谷歌 Kubernetes 引擎(GKE)](https://cloud.google.com/kubernetes-engine) 。将所有东西放在一个平台上提供了访问的便利性和安全性。

## **改进的容量管理、CICD、安全性和正常运行时间**

Baldassare 说，除了技术能力和执行知识之外，迁移还展示了 Mirantis 作为合作伙伴的优势。当他的团队与 Mirantis 的全球专业服务高级总监 Anoop Kumar 一起完成 RFP 流程时，Choozle 对 Kumar 的团队充满了信心。

“我们需要专家在房间里，我们得到了，”巴尔达萨雷说。“当我们准备好执行时，他们对我们的情况了如指掌，所以我们最终能够加快进度。”

现代化包括从 Mirantis 的镜头开源转移到其[镜头自动驾驶](https://www.mirantis.com/software/lens/lensautopilot/)，云原生，DevSecOps as a Service platform。

“Lens Autopilot 在任何地方的任何 Kubernetes 上完全自动化云原生应用的操作，”Kumar 说。它通过在容量管理、持续集成/持续交付(CI/CD)、安全性、正常运行时间和问题解决方面提供基于指标的增量改进来做到这一点。Kumar 说，该产品去年 12 月才推出，所以 Choozle 作为第一个实施者承担了很大的风险。

Choozle 的应用程序现在在 Kubernetes 的最新版本上，与 Mirantis 的 DevOpsCare 和 Lens Autopilot 完全集成。Baldassare 说:“按照我们的操作方式，桌面应用程序实际上是一个我们每天都要登录的仪表板。“如果我们有任何可能出错的杂音，或者有事情被报告，或者客户或内部利益相关者说我们注意到了这种不可靠的行为，这是我们的第一点。”

## **自动化、DevOps 支持释放开发人员的时间**

Baldassare 说，Mirantis 的专业服务 DevOpsCare 是 Mirantis 的 RFP 与其他公司的主要区别。

“这给了我们一年的时间来支持 Autopilot 订阅，以保证迁移工作的初始工作，这是对我们如此有吸引力的地方，”他说。“我们很难招聘到 DevOps 人才。我们现有的团队没有能力让开发人员和软件工程师同时工作。”

Mirantis 的服务为 DevOps 工程师提供了对 Choozle 堆栈的了解，可以对解决方案进行优先排序，并在某些情况下执行它们。

现在，Baldassare 可以安全地与他的所有开发人员共享访问权限。此外，在与 Mirantis 合作之前，他的工程师不得不手动监控负载，并且可能为了安全起见而过度放大。现在，系统负责扩展，Choozle 实现了一些成本节约。

该公司也不必考虑 24/7 全天候保持多个 DevOps 职位的成本，这是它所服务的行业的期望。“例如，他们可能需要在周六工作，”Baldassare 说。“因此，现在我们可以说，届时它将是可用的，不会出现中断。”

Lens 就是这样一个不可或缺的工具，Baldassare 说，“我不必告诉我们团队的每一个工程师，你必须是一个 DevOps 的人。取而代之的是 Lens，它平易近人，想成为什么样的 DevOps 人就成为什么样的人。

## **接下来的步骤**

Baldassare 说，Choozle 的核心遗留应用服务于 75%的客户。他的团队一直在用一种全新的架构基础设施逐步重建它，建立在自己的 Kubernetes 上。一个独立的遗留平台，用于用户和账户管理，在它自己的 Kubernetes 上。

“这两个产品做同样的事情，最终我们将放弃传统的应用程序，”他说。“与 Mirantis 的项目是将两者结合在一起，以便您可以在其中一个平台上运营，这就是我们管理平台过渡的方式。”Choozle 希望用户在新平台上启动他们的核心功能，同时保持对旧平台的访问。

Choozle 还使用 Mirantis 作为教育材料，并将完成 Lens 学习管理系统作为公司目标流程和审查流程的一部分。一些工程师将学习新事物作为他们自己的个人目标之一，他们选择的一件新事物是通过 Mirantis 完成 Kubernetes onboarding。

“这是一个例子，说明使用整个镜头仪表板和用户界面是多么容易，特别是与 Kubernetes 设置它的复杂计算编排方式相比，”Baldassare 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>