# 应用程序自动化和管理的现状

> 原文：<https://thenewstack.io/the-state-of-application-automation-and-management/>

[应用自动化和管理的状态](https://thenewstack.simplecast.com/episodes/the-state-of-application-automation-and-management)

上周在 ChefConf 的讨论围绕着 T7 栖息地展开。这个开源项目为开发人员带来了一个部署层，允许他们为任何基础设施打包应用程序。考虑到 [Chef](https://www.chef.io/) 仍然是配置管理和环境配置的流行途径，添加这一新的统一部署准备层为开发人员带来了更令人兴奋的方式来自动化他们的持续集成和部署流程。

“我个人把它描述为两件事。首先是包装系统。Chef 的高级开发工程师 Nell Shamrell-Harrington 解释道:“你要做的是，为你的应用程序创建一个计划文件，首先编写应用程序，然后该计划文件在 Bash for Linux 和 Powershell for Windows 中定义该应用程序应该如何构建、安装和运行。“那个包几乎可以出口到任何东西。它可以导出到 Docker 容器中。这是迄今为止人们使用的最流行的出口商。”

Shamrell-Harrington 说，Habitat 非常擅长为云部署准备遗留应用程序。“假设您想尝试[云代工厂](https://www.cloudfoundry.org/)，我们有一家云代工厂出口商。在 Cloud Foundry 中运行应用程序时，您不必重写应用程序。你需要做的就是把它导出到 Cloud Foundry 格式。我们有库伯内特斯的舵图。我们真的认为，没有一种真正的方法可以部署应用程序。”

Habitat 还包括一个运行时元素，Shamrell-Harrington 详细描述了使用 Habitat 硬币这一面的好处。“我们有所谓的栖息地监督员。这就是实际解包、运行和管理打包的应用程序。奇妙的是，您可以运行几个 Habitat 包实例。我们称之为服务。这些组成了我们所说的管理环，它们相互了解，并可以自组织成不同的拓扑结构。Shamrell-Harrington 说:“对于数据库来说，最受欢迎的是领导者/追随者。

这允许更快地响应问题，因为团队可以一起部署系统网络，并根据需要自动进行配置。“五年或十年前，我们认为我们可以预见应用程序可能出现故障的每一种方式，然后我们添加了应急措施。嗯，我们的观点是，它会以某种方式失败。它可能会以一种完全不可预测的方式失败，因为这就是墨菲定律和生活的本质。因此，无论失败的原因是什么，我们都希望您的应用程序能够在没有任何其他干预的情况下快速恢复。

[https://www.youtube.com/embed/9yQRixcCmXc?feature=oembed](https://www.youtube.com/embed/9yQRixcCmXc?feature=oembed)

视频

### 在这个版本中:

*   [1:32:](https://thenewstack.simplecast.com/episodes/the-state-of-application-automation-and-management?t=1:32) 有了 Habitat，控制平面的概念是否变得更容易让人理解了？
*   [5:37:](https://thenewstack.simplecast.com/episodes/the-state-of-application-automation-and-management?t=5:37) 栖息地如何提供弹性？
*   [6:57:](https://thenewstack.simplecast.com/episodes/the-state-of-application-automation-and-management?t=6:57)Docker 集装箱使用量的增长对 Habitat 有何影响？
*   [13:01:](https://thenewstack.simplecast.com/episodes/the-state-of-application-automation-and-management?t=13:01) 您如何管理复杂性？
*   [17:42:](https://thenewstack.simplecast.com/episodes/the-state-of-application-automation-and-management?t=17:42)Habitat 如何适应 [Chef Automate](https://www.chef.io/products/automate/) ？
*   [23:48:](https://thenewstack.simplecast.com/episodes/the-state-of-application-automation-and-management?t=23:48) 从这里开始，你认为人居的方向是什么？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>