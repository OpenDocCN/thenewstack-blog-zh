# Terraform Cloud 现在提供了更少的代码(甚至没有代码)选项

> 原文：<https://thenewstack.io/terraform-cloud-now-offers-less-code-and-no-code-options/>

云计算基础设施软件提供商 HashiCorp 为其广受欢迎的 Terraform 自动供应工具提供了一个图形用户界面(GUI)，希望它足够简单，甚至开发者都可以使用。

产品和合作伙伴营销副总裁[梅根·列塞](https://www.linkedin.com/in/meghanliese/)、[哈希公司](https://www.hashicorp.com/?utm_content=inline-mention)表示，Terraform 自助服务模式可以“减少组织为让开发人员快速使用基础设施即代码软件所需的培训”。它在 Terraform Cloud 上提供，terra form Cloud 是 HashiCorp 云平台的一部分。

Terraform 的无代码选项是本周在洛杉矶举行的 HashiConf 2022 周四主题演讲中推出的新功能之一。

Terraform 是 HashiCorp 的旗舰软件，也是该公司多云管理架构的基石。开源工具提供了一种在[人类可读的配置文件](https://thenewstack.io/install-terraform-and-the-gaia-web-ui-on-ubuntu-server-22-04/)中定义 IT 资源的方式，比如监控软件或云服务。这些文件充当蓝图，然后可用于自动配置系统本身。Kubernetes 部署，例如，可以通过 Terraform 简化。

Liese 解释说，通常，DevOps 团队或系统管理员使用 Terraform 来供应基础架构，但也有越来越多的人希望允许开发人员以自助方式自己完成这项工作。2022 年 HashiCorp 云战略状态调查得出的结论是，多云技术供不应求，因此该公司认为，简化供应过程可以帮助更多的开发者。

新的控制台界面旨在大大扩展 Terraform 的使用。该公司已经提供了一段时间的自助服务选项，通过一种架构，允许模块通过 Terraform 云和 Terraform Enterprise 的私有注册表重用。

然而，模块的使用仍然需要一些专业知识，因为“开发人员仍然需要根据其内容选择一个模块，将其添加到版本控制报告中，在 Terraform Cloud 中创建一个工作区，并从该工作区提供模块，”根据 HashiCorp 的宣传资料。

在这种“无代码”设置中，开发人员可以从无代码就绪模块的目录中挑选，这些模块可以直接部署到工作区。不需要[学习](https://learn.hashicorp.com/collections/terraform/configuration-language)的 [HCL 配置语言](https://github.com/hashicorp/hcl)。管理员将不再需要回答同样的“如何在 HCL 中做这件事？”查询。

## 较少代码

最近发布的[Terraform 1.3](https://www.hashicorp.com/blog/terraform-1-3-improves-extensibility-and-maintainability-of-terraform-modules)的承诺通过对`make`代码块的改进，大大减少 HCL 骑师必须管理的代码量。

实际上，`make`从 Terraform 1.1 开始就有了，但是在这个最新版本中做了一些改进。`make`所做的是提供在 Terraform 配置文件中重构资源的能力，将大的代码块作为单独的模块移走，在那里它们可以通过公共或私有的注册表被发现。

Leise 提供了一个管理调用 [Amazon Web Services](https://aws.amazon.com/?utm_content=inline-mention) ECS 集群所需代码的例子。使用`make`，它可以从主 HCL 文件中移出，并保存在一个可以在运行时调用的模块中。在下面的例子中，200 个代码减少到 37 行:

![](img/58febc6ce5b7414b2f6d2e329a69de39.png)

## 连续验证

在 Terraform 上捕获系统的已知状态后，只需简单地检查一下，就能确保实际运行的系统与在 HCL 中捕获的所需状态一致。很多时候，当管理员甚至应用程序本身对系统进行更改时，会发生“漂移”。尤其是在受监管的环境中，例如医院，系统必须处于正确的状态。

今年早些时候，HashiCorp 在 Terraform Cloud 中添加了[漂移检测](https://www.hashicorp.com/campaign/drift-detection-for-terraform-cloud)，以持续检查基础设施状态，从而检测变化并提供警报，如果选择了该选项，还会提供补救措施。现在，另一个更新，[连续验证](https://www.terraform.io/cloud-docs/workspaces/health)扩展了这些检查，也包括用户断言或后置条件。

一个后置条件可能是确保证书没有过期。如果他们这样做，该软件可以向管理员发出警报，更新证书。另一个条件可能是检查新的容器图像，这些图像可能已经作为对安全补丁的响应而被更新。

该公司还在展会上公布了 Terraform Cloud 的许多其他新功能，包括支持[开放策略代理](https://www.openpolicyagent.org/)标准。Terraform Cloud 此前依赖内部的[哨兵](https://www.hashicorp.com/sentinel)来执行[政策作为代码](https://www.hashicorp.com/blog/why-policy-as-code)框架，但 OPA 正迅速成为政策编码的行业标准。它还引入了 Azure Provider Automation 工具、ServiceNow ServiceGraph 连接器和 Terraform 插件框架。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>