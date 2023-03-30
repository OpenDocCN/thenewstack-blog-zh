# 利用机器学习和定制管道逻辑扩展 Spinnaker 自动化交付

> 原文：<https://thenewstack.io/extend-spinnaker-automated-delivery-with-machine-learning-and-custom-pipeline-logic/>

开源的 [Spinnaker](https://www.spinnaker.io/) 是一个持续交付工具[，最初由网飞和谷歌](https://cloudplatform.googleblog.com/2017/06/spinnaker-10-continuous-delivery.html)开发，可以用于运行多个云部署的开发管道。该软件已经在 OpenStack 社区找到了归宿。像 OpenStack 一样，Spinnaker 简化并自动化了在异构环境中打包资源的固有复杂过程。

“在理想的世界中，Spinnaker 应该存在于 OpenStack 基金会中，因为 OpenStack 在基础设施领域解决问题的方法与 Spinnaker 在应用交付领域的做法非常相似”[](https://www.linkedin.com/in/borisrenski/)[Mirantis](https://www.mirantis.com/)的联合创始人 Boris Renski 最近向我们解释道。Mirantis 使用 Spinnaker 作为其最近推出的受商业支持的 [Mirantis 应用平台](https://www.mirantis.com/software/application-platform/)的一个组件。

上个月在温哥华举行的 OpenDev 大会上——与 [OpenStack Summit](https://www.openstack.org/summit/vancouver-2018/) 同时举行——Mirantis 的技术和营销内容负责人 [Nick Chase](https://twitter.com/NickChase) 做了一个演示，介绍如何用自己的定制逻辑扩展 Spinnaker 的管道，他称这种方法为“智能交付”

当然，Spinnaker 提供了可定制的管道来创建开箱即用的可部署工件。您可以自动扩展服务器组，或者换出服务器组进行测试。但是 Chase 提供了许多额外的方法来增强 Spinnaker 的智能决策能力。

例如，您可以通过您自己的脚本来扩展 spinnaker，这可以有条件地定义工件如何构建——这类似于 Jenkins 在 CI/CD 等式的持续集成方面的工作方式。Spinnaker 有一个可以编程的 API，维护人员也在命令行界面上工作。

管道可以被外部事件触发，比如 Git 提交。实际上，您可以使用 Spinnaker 作为一个 [GitOps](https://thenewstack.io/gitops-git-push-all-the-things/) 风格的环境的基础，毫无疑问，通过使用该软件创建一些非常复杂的分支条件，以及基于当前和以前的状态设置动作，可以增强这个环境。“你可以有一个脚本，在事情实际发生之前预测它将会发生，并采取行动，”他解释说。

有许多方法可以添加这个额外的逻辑。这可以直接通过预编码逻辑来实现。一个策略引擎，比如[云本地计算基金会](https://www.cncf.io/)的[开放策略代理](https://www.openpolicyagent.org/) (OPA)，或者 OpenStack 的[国会](https://wiki.openstack.org/wiki/Congress)。对于机器学习驱动的系统优化，Chase 推荐了另一个 OpenStack 项目， [Fault Genes](https://wiki.openstack.org/wiki/Fault_Genes_Working_Group) ，它使用 ML 来更好地自动化 OpenStack 基础设施中断的检测和预测。

Chase 提供了三个扩展 Spinnaker 的演示，其中 1:触发器，2:管道变量，3:条件阶段:

[https://www.youtube.com/embed/8zRWcZ20Qg8?feature=oembed](https://www.youtube.com/embed/8zRWcZ20Qg8?feature=oembed)

视频

云本地计算基金会、谷歌和 OpenStack 基金会分别是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>