# 地形与云形成:哪个对你更好？

> 原文：<https://thenewstack.io/terraform-vs-cloudformation-which-is-better-for-you/>

肖恩·奥戴尔

肖恩是 Spacelift 的开发者关系主管。Sean 相信每个 IT 组织都能够并且应该发展和实践 DevOps 的生活方式。Sean 是一名改革后的基础架构管理员和架构师，他热衷于帮助开发人员和应用团队在多云世界中取得成功。Sean 拥有 20 年的经验，担任过从企业架构师到系统工程师和开发人员的各种角色。

IaC (Infrastructure-as-Code)顾名思义，就是使用代码创建和管理基础设施的过程。编码的基础设施易于扩展、维护、记录和复制。IaC 面临一些挑战，但自动化供应和配置比手动部署更快、更好。

云提供商通常会维护一个 IaC 工具，专门支持其云平台上的资源部署，例如，用于部署 AWS 资源的 AWS CloudFormation。然而，还有其他独立于任何云提供商的工具。一个这样的 IaC 工具是 Terraform。

在管理 AWS 资源时，您可能会发现很难在地形和云形成之间做出决定。希望这篇文章能让地形与云形成的讨论更加清晰。

## 什么是 AWS CloudFormation？

[AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) 是一项原生 AWS 服务，支持用户创建、供应和管理亚马逊资源，使管理、监控和测试基于 AWS 的基础设施变得更加容易。

## 什么是 Terraform？

Terraform 是一个流行的开源云无关 IaC 工具，由 HashiCorp 维护和开发。它允许通过连接多个云提供商来创建、更新和配置基础架构。

## 地形和云形成的区别

让我们根据以下标准比较地形和云的形成:

1.  模块性
2.  功能
3.  代码语法
4.  云兼容性
5.  状态管理
6.  卷回
7.  企业支持

### 第一:模块化

IaC 的一个用例是允许可重复性和快速供应的模块化。

Terraform 模块是分配用于执行一项任务的一组资源，可重复用于类似的基础设施组件。您可以创建自己的定制模块，并使用社区开发的模块。

CloudFormation 的堆栈类似于模块，但灵活性较差。您可以将 AWS 配置作为堆栈导入和导出，但是自动配置和嵌套堆栈会隐藏配置的详细信息。

### 第二:功能性

Terraform 为 IaC 带来了许多内置功能，可用于操纵数据，并提供对所提供的值进行组合、转换或操作的可能性。Terraform 的函数列表非常广泛，包括数字、字符串操作和文件系统。但是，您不能创建自定义函数。

CloudFormation 提供的功能不到 15 个，不足以管理大规模的基础设施。缺少内置函数导致了额外的工作——您必须在模板中创建自定义资源，并调用 lambda 函数来获取它们。

### 第三:代码语法

CloudFormation 使用了 JSON 和 YAML，这两个软件在开发者中很受欢迎。因此，没有(或很少)学习曲线。Terraform 的 [HashiCorp 配置语言(HCL)](https://www.terraform.io/docs/configuration/index.html) 语法可读性强，易于学习，但它仍然是一个“新事物”

### 第四:云兼容性

Terraform 和 CloudFormation 的一个显著区别是，Terraform 支持多种云和提供商，包括 Google、AWS 和 Azure，而 CloudFormation 仅限于 AWS 资源。

Terraform 支持所有的 AWS 资源，但我们不应该对 CloudFormation 首先支持新的 AWS 资源类型感到惊讶。

### 第五:国家管理

Terraform 有一个存储基础设施信息的状态文件，并作为所有 Terraform 资源的地图。默认情况下，状态存储在虚拟机或远程计算机上，因此协作几乎是不可能的。许多组织通过使用版本控制提供者、亚马逊 S3 桶或 Spacelift 的托管状态特性来采用 GitOps 方法。

有了 CloudFormation，你就不用担心了。AWS 始终控制着基础设施，如果状态有任何变化，它会显示一条详细的消息。

### 第六:回滚

Terraform 和 CloudFormation 都可以确保您不会意外删除其他应用程序中使用的资源。

CloudFormation 在删除基础设施状态之前会对其进行备份。如果更新或修改破坏了基础设施，它将自动回滚到上一个工作状态。

在 Terraform 中，您必须手动部署修复程序，并将其恢复到以前的配置。但是您可以在应用更新后运行测试来检查输出。一旦您发现输出令人满意，就可以提交更改。

### 第 7 名:企业支持

如果您是新手，并在整个基础架构中使用 AWS，知识库和 AWS 专家支持将填补您团队的技能缺口。您将安心入睡，因为您知道 AWS 团队可以帮助您解决任何问题。

Terraform 背后有一个庞大而活跃的社区，提供尽最大努力的支持，但它带来了许多错误信息和基于上下文的解决方案。Hashicorp 通过托管服务产品为 HCL 提供本地支持。

## 自动化基础设施即代码

AWS CloudFormation 和 Terraform 是最受欢迎的 IaC 工具，但不是市场上唯一的 IaC 工具。有来自微软的 Azure Resource Manager 和 Bicep，而 Google 为 Terraform 提供部署管理器和一流的支持。Pulumi 采用了一种独特的方法，通过支持各种编程语言来部署基础设施资源。Ansible、Chef 和 Puppet 等传统 IT 自动化解决方案也提供一些 IaC 功能。但是每种工具都有它自己的优点和复杂性。

许多组织构建了定制工具，后来发现这些定制 IaC 语言很难扩展，存在合规性问题，并且维护成本很高。

[Spacelift](https://spacelift.io/) 是一款用于基础设施即代码的复杂 CI/CD 工具，专为支持复杂的组织和基础设施需求而打造。Spacelift [支持多种 IaC 语言和框架，包括 CloudFormation 和 Terraform](https://spacelift.io/integrations) ，这允许您跨所有 IaC 语言标准化您的部署流程和合规性要求。

## 结论:地形与云的形成

如果您的整个基础设施都在 AWS 上，并且没有计划使用多云，那么 CloudFormation 是一个更好的选择。如果您是 AWS 服务的新手，本机支持将是有益的。它由 AWS 构建，具有更快的 AWS 相关更新。它还使用 JSON 和 YAML，因此与 HCL 不同，没有学习曲线。

如果您正在使用或计划使用多云资源，并且希望加快处理速度，Terraform 是最佳选择。模块化方法允许您创建可重用的模板，从而加快配置速度。此外，Terraform 提供了 CloudFormation 所缺乏的一系列功能，这有助于加快供应。

但是什么最适合你，要看你的要求。我建议在评估应用程序的基础结构策略之后选择 IaC 工具。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>