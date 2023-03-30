# HashiCorp Terraform 和 Terraform 云的最新增强功能

> 原文：<https://thenewstack.io/latest-enhancements-to-hashicorp-terraform-and-terraform-cloud/>

## **什么是 Terraform？**

[Terraform](https://thenewstack.io/how-to-scale-your-terraform-infrastructure/) 是 HashiCorp 的旗舰软件。开源工具提供了一种在人类可读的配置文件中定义 IT 资源的方式，例如监控软件或[云服务](https://thenewstack.io/category/cloud-native/)。这些文件充当蓝图，然后可用于自动配置系统本身。例如，Kubernetes 部署可以通过 Terraform 来简化。

[hashi corp terra form 和 Terraform Cloud 的最新增强功能](https://thenewstack.simplecast.com/episodes/latest-enhancements-to-hashicorp-terraform-and-terraform-cloud)

“Terraform 基本上翻译了您的配置所编码的内容，并将其提供给所需的最终状态，”本月在洛杉矶举行的该公司用户大会 HashiConf 2022 上录制的产品和合作伙伴营销副总裁 [Meghan Liese](https://www.linkedin.com/in/meghanliese/) 、 [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) 在这段播客和视频中解释道。

[https://www.youtube.com/embed/q3yGtwAt3MI](https://www.youtube.com/embed/q3yGtwAt3MI)

视频

在这次采访中，Liese 讨论了 Terraform 和 Terraform Cloud 的最新增强功能，terra form Cloud 是 HashiCorp 云平台的一部分。

## 开发者为什么要对 Terraform 感兴趣？

Liese 解释说，通常，DevOps 团队或系统管理员使用 Terraform 来供应基础架构，但也有越来越多的人希望允许开发人员以自助方式自己完成这项工作。2022 年 HashiCorp 云战略状态调查得出的结论是，多云技术供不应求，因此该公司认为，简化供应过程可以帮助更多的开发者。

Liese 说，今年早些时候推出的 Terraform 自助服务模型可以“减少组织为让开发人员快速使用基础设施即代码软件所需的培训”。

在这种“无代码”设置中，开发人员可以从无代码就绪模块的目录中挑选，这些模块可以直接部署到工作区。不需要[学习](https://learn.hashicorp.com/collections/terraform/configuration-language)的 [HCL 配置语言](https://github.com/hashicorp/hcl)。管理员将不再需要回答同样的“如何在 HCL 中做这件事？”查询。

新的控制台界面旨在大大扩展 Terraform 的使用。该公司已经提供了一段时间的自助服务选项，通过一种架构，允许模块通过 Terraform 云和 Terraform Enterprise 的私有注册表重用。

## 什么是 Make 代码块，为什么它很重要？

最近发布的[Terraform 1.3](https://www.hashicorp.com/blog/terraform-1-3-improves-extensibility-and-maintainability-of-terraform-modules)的承诺通过改进`moved`代码块来大大减少 HCL 骑师必须管理的代码量。

实际上，`moved`从 Terraform 1.1 开始就有了，但是在这个最新版本中做了一些改进。`moved`所做的是提供在 Terraform 配置文件中重构资源的能力，将大的代码块作为单独的模块移走，在那里它们可以通过公共或私有的注册表被发现。

## 什么是持续验证？

在 Terraform 上捕获系统的已知状态后，只需简单地检查一下，就能确保实际运行的系统与在 HCL 中捕获的所需状态一致。很多时候，当管理员甚至应用程序本身对系统进行更改时，会发生“漂移”。尤其是在受监管的环境中，例如医院，系统必须处于正确的状态。

今年早些时候，HashiCorp 在 Terraform Cloud 中添加了[漂移检测](https://www.hashicorp.com/campaign/drift-detection-for-terraform-cloud)，以持续检查基础设施状态，从而检测变化并提供警报，如果选择了该选项，还会提供补救措施。现在，另一个更新，[连续验证](https://www.terraform.io/cloud-docs/workspaces/health)扩展了这些检查，也包括用户断言或后置条件。

一个后置条件可能是确保证书没有过期。如果他们这样做，该软件可以向管理员发出警报，更新证书。另一个条件可能是检查新的容器图像，这些图像可能已经作为对安全补丁的响应而被更新。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>