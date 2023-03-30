# Bitnami 的 Stacksmith 致力于让传统应用毫不费力地迁移到云端

> 原文：<https://thenewstack.io/bitnamis-stacksmith-aims-make-moving-legacy-apps-cloud-effortless/>

Bitnami 提供可以部署到各种云供应商的预打包应用程序，它已经发布了其 [Stacksmith](https://bitnami.com/stacksmith) 企业应用程序迁移解决方案。

它旨在帮助公司(尤其是那些几乎没有云经验的公司)将他们的定制和应用程序迁移到公共云或私有云。

“Bitnami 在打包和维护云应用程序以实现点击部署体验方面拥有深厚的专业知识，这使我们能够实现自动化，而不仅仅是重新打包应用程序。首席执行官[丹尼尔·洛佩斯](https://www.linkedin.com/in/daniel-lopez-ridruejo-993120/)表示:“它还让我们能够应用平台特定的逻辑、模板和组件，来交付经过优化、随时可以部署的重新打包的应用。”。

Stacksmith 基于其内部使用的技术来打包和维护其发布到所有主要云市场的大约 120 个开源应用程序的目录。

它旨在将传统应用程序自动打包到云就绪映像中，将它们迁移到云中，并在升级和修补后持续监控它们。

https://www.youtube.com/watch?v=6KtlPjknAWw

“这并不神奇，但这是我们已经从应用程序目录业务中获得的大量自动化和知识。营销副总裁汤姆·麦卡弗蒂说:“我们的目的是将这种方法简单化。

如果你看看今天的世界，你把你的应用程序放在云中的选择是一个虚拟的提升和转移:你只需要把你的虚拟机放在云中的一个容器中，他说。

“你必须具备构建一个[ARM](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-authoring-templates)(Azure Resource Manager)模板或 [CloudFormation](https://aws.amazon.com/cloudformation/aws-cloudformation-templates/) 模板的知识，但你必须围绕它进行所有的设计，以使它实际运行。在我们的情况下，您不必这样做。我们也为你建造这些东西。这是我们每天为数百个应用程序所做的事情。

“我们的目标是为世界提供比提升和转移选项更好的东西，并让他们知道，如果应用程序确实需要重新架构或重写，我们会为他们提供实现这一目标的途径。”

不需要任何代码修改，Stacksmith 模板带来了目标平台所需的所有组件以及最佳实践。之后，它会自动执行日常维护任务，包括监控更新和安全漏洞补丁。

如果它在 Kubernetes 环境中的容器中运行，Stacksmith 还会构建一个[舵图](https://docs.helm.sh/developing_charts/)来配合它，这样它就有了关于基础设施以及如何部署它的指令。

REST APIs 可用于希望将 Stacksmith 添加到其交付管道中的公司。

[Adnan Abdulhussein](https://twitter.com/prydonius),[Bitnami](https://bitnami.com/)的软件开发人员，最近在 Docker 伦敦会议上讲述了他在公司三年集装箱化工作中所学到的经验。

Chef 是提供软件打包工具的供应商之一。它的 [Habitat Builder](https://www.habitat.sh/) 允许开发人员打包应用程序，但在部署之前不要决定导出格式或运行时间。它将更多的安全性集成到其合规自动化解决方案 [InSpec](https://www.chef.io/products/chef-inspec/) 中。

与此同时，包装软件和包装啤酒的相似性是一月份分析公司 RedMonk 在伦敦举办的活动的主题之一。

主厨是新烟囱的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>