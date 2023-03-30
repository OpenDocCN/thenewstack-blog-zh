# 开发运维工作流如何减少工作量和成本

> 原文：<https://thenewstack.io/how-a-devops-workflow-reduces-efforts-and-costs/>

[](https://www.linkedin.com/in/brein-matturro-081a801/)

[Brein Matturro](https://www.linkedin.com/in/brein-matturro-081a801/)

[Brein，高级内容营销经理，客户，为 GitLab，是一位经验丰富的软件技术作家和编辑。她与丈夫和两个儿子住在新罕布什尔州，教授 Vinyasa 瑜伽，并拥有一家 Ben & Jerry's。](https://www.linkedin.com/in/brein-matturro-081a801/)

[](https://www.linkedin.com/in/brein-matturro-081a801/)[](https://www.linkedin.com/in/brein-matturro-081a801/)

[Glispa](https://www.glispa.com/) 是一家总部位于柏林的数字营销和移动广告公司，为应用程序开发人员和移动广告客户提供高效、吸引人的解决方案，以接触目标受众。但是为了在这方面取得成功，Glispa 需要修改自己的软件开发管道。

Glispa 遵循一个简单的理念:为了让品牌在当今 24/7 的信息洪流中推出新服务或创造令人兴奋的客户体验，他们必须提供出色的用户体验，无论涉及何种技术平台。然而，由于消费者的决定会立即受到内容或新技术的影响，即使是规避风险的 B2B 品牌也不得不选择 B2C 市场中更具创造性和活力的方法:新的应用程序、高级选项和实时评估工具。速度也是一个关键因素。

## 牛仔装置刺激管道打嗝

随着 Glispa 不断发展以支持新的服务，如在多个国家的全服务电子商务，对其软件开发和现代 IT 编排的需求也在增长。

该公司的开发人员越来越多地使用容器化来缩短软件生命周期，这导致 IT 团队寻找更简单、更灵活的管道和自动化报告的方法。

Glispa 的解决方案？采用 DevOps 实践和敏捷策略，以简化流程。

然而，这种向 DevOps 工作流的期望切换需要对其原始编排平台进行修订。Glispa 最初使用 D2IQ 的[DC/操作系统](https://dcos.io/)进行编排，但其工程团队难以管理这个拼凑起来的平台。该团队需要一种方法来减少令人头痛的问题，改善管道，并节省持续进行修复的正常运行时间。

> 有了 GitLab 和 Kubernetes，我可以一天部署三次——不像传统的每三个月发布一次。

“我们的 DC/OS orchestrator 几乎每周都会引发问题，”Glispa 的高级系统工程师 Paride Martino 说。" Docker 注册表不可靠，调试中使用的方法没有明显的原因就失败了."

Martino 以前有过使用 Kubernetes 的经验，并且知道迁移的唯一方法是使用一个具有适当版本控制的工具，该工具将很容易集成。唯一符合这一标准并针对 Kubernetes 迁移进行了全面优化的工具是 T2 git lab T3。

幸运的是，GitLab 已经被 Glispa 有机地采用了，但是团队一直在没有任何真正指令的情况下使用这个工具。马蒂诺和工程团队认为 [GitLab Premium](https://about.gitlab.com/pricing/premium/) 满足了他们的所需功能清单。

“你不能用其他产品或服务进行适当的安装，”Martino 说。“因此，如果您想要在自己的数据中心内部部署某种产品，那么 GitLab 是不二之选。有了 GitLab 和 Kubernetes，我可以一天进行三次部署——不像传统的每三个月发布一次。我从我的步骤中知道测试已经通过，我可以直接在 GitLab 中从 staging 自动提升到 production。”

## 转换成本和生产率

Glispa 的开发者很欣赏 GitLab 基于规则但更易访问的网络资源。其系统工程师现在可以定义组和分配角色，以提供对应用程序、打印机和扫描仪等资源的访问，并可以轻松管理在不同存储库中工作的人员的权限。

“管理安装中的用户要容易得多，我们也不需要创建任何用户，”Martino 说。“我们只需点击‘同步’，用户就就位了。”

Martino 现在看到了安全性和生产力的重大改进，而不需要复杂的用户授权。

“对于其他工具，要么是读授权，要么是只读授权，”他说。“使用 GitLab 很容易。如果我们有一个顾问在这里一个星期，我们只给他访客权限。我们可以定义三个或四个访问级别，或者分配一个三周后到期的限时令牌。”

通过使用 GitLab Premium，Glispa 将管道集中在一个地方，具有强大的自动化报告和持续的透明度。

“我们几乎所有的项目都有一个管道，但有了 GitLab，我们不必先管理一个权限，然后将其他权限交给其他东西，然后再次进行 Docker 注册权限——这就简单多了，”Martino 解释道。“所有授权都在一个地方进行管理。我们不需要给开发者任何指示，比如“现在就为 Kubernetes 提供”,因为这已经在准备中了。你输入你的代码，五分钟后它就会出现在 Kubernetes 上，就这样。”

此外，GitLab 的 CI 模板可以不间断地完成复杂的任务。

Martino 说，模板“使我能够在开发人员没有注意到的情况下完成复杂的任务”。“我不必调试管道，我只需确保我的模板工作。”

从创建 Java 项目到使用 Docker 图像，团队使用 GitLab 提供的东西。“我们使用 GitLab 来存储代码，开发我们的解决方案，构建 Docker 容器，然后将其分发到 Kubernetes，”Martino 说。

## 发展与创新

随着 GitLab 和 Kubernetes 的引入，Glispa 的运营成本也有所降低。

“它们只是亚马逊会产生的费用的 30%左右，”马蒂诺说。迁移还降低了集团一般基础设施的成本。

“因此，一家公司将其所有集群都放在亚马逊网络服务(AWS)上，但迁移后，成本降低到了原来的四分之一，”Martino 说。新平台还有助于优化 Glispa 集团其他公司的发展。

“我们与集团中其他面向 Windows 的公司合作，”Martino 说。“通过 GitLab，我们从池中创建了一些 Windows runners，并对它们进行了标记。现在成功了。”

Glispa 现在拥有强大的 DevOps 引擎，可以实施其服务创新和增长计划。开发人员最欣赏 GitLab 的是无缝协作。

“我是一名系统工程师；这意味着你不应该注意到我在工作，”马蒂诺说。"由于 GitLab 运行流畅，你甚至不会注意到它的存在."

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>